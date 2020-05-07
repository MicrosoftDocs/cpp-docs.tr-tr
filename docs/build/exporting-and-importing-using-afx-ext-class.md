---
title: AFX_EXT_CLASS Kullanarak İçeri ve Dışarı Aktarma
ms.date: 11/04/2016
f1_keywords:
- afx_ext_class
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
ms.openlocfilehash: 95c72f8251a8a59833483eb948709c80a69d03d7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328606"
---
# <a name="exporting-and-importing-using-afx_ext_class"></a>AFX_EXT_CLASS Kullanarak İçeri ve Dışarı Aktarma

[MFC uzantı dll 'leri](extension-dlls-overview.md) , sınıfları dışarı aktarmak için **AFX_EXT_CLASS** makroları kullanır; MFC uzantısı DLL 'sine bağlanan yürütülebilir dosyalar, sınıfları içeri aktarmak için makrosunu kullanır. **AFX_EXT_CLASS** MAKROYLA, MFC uzantı dll 'sini oluşturmak için kullanılan üst bilgi dosyaları, dll 'ye bağlanan yürütülebilir dosyalarla birlikte kullanılabilir.

DLL 'nizin başlık dosyasında, sınıfınızın bildirimine aşağıdaki şekilde **AFX_EXT_CLASS** anahtar sözcüğünü ekleyin:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Bu makro, önişlemci sembolleri `__declspec(dllexport)` `_AFXDLL` ve `_AFXEXT` tanımlandığı gibi MFC tarafından tanımlanır. Ancak makro tanımlandığı gibi `__declspec(dllimport)` `_AFXDLL` tanımlanır ve `_AFXEXT` tanımlı değildir. Tanımlandığında, Önişlemci sembolü `_AFXDLL` , MFC 'nin paylaşılan sürümünün hedef yürütülebilir (bir dll veya bir uygulama) tarafından kullanıldığını gösterir. Hem hem `_AFXDLL` de `_AFXEXT` tanımlandığında bu, hedef yürütülebilirin bir MFC uzantı dll olduğunu gösterir.

`AFX_EXT_CLASS` , Bir MFC uzantı `__declspec(dllexport)` dll 'sinden dışarı aktarılırken olduğu gibi tanımlandığından, tüm sınıfları, bu sınıfın tüm sembolleri için düzenlenmiş adları. def dosyasına yerleştirmeksizin dışarı aktarabilirsiniz.

Bu yöntemle bir. def dosyası ve sınıfın tüm düzenlenmiş adlarını oluşturmaktan kaçınabilseniz de, adlar sıralı olarak verilebildiğinden. def dosyası oluşturulması daha etkilidir. Dışarı aktarma işlemi için. def dosya yöntemini kullanmak için, üst bilgi dosyanızın başına ve sonuna aşağıdaki kodu yerleştirin:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
> Sürüm çakışmaları olasılığını oluşturabileceğinden, satır içi işlevleri dışarı aktarırken dikkatli olun. Satır içi işlev uygulama koduna genişletilir; Bu nedenle, daha sonra işlevi yeniden verirseniz, uygulamanın kendisi yeniden derlenmediği takdirde bu, güncellenmez. Normalde, DLL işlevleri onları kullanan uygulamaları yeniden oluşturmadan güncellenebilir.

## <a name="exporting-individual-members-in-a-class"></a>Bir sınıftaki tek tek üyeleri dışarı aktarma

Bazen sınıfınızın tek tek üyelerini dışarı aktarmak isteyebilirsiniz. Örneğin, bir `CDialog`türetilmiş sınıfı dışarı aktarıyorsanız, yalnızca oluşturucuyu ve `DoModal` çağrısını dışarı aktarmanız gerekebilir. ' İ dışa `AFX_EXT_CLASS` aktarmanız gereken ayrı Üyeler üzerinde kullanabilirsiniz.

Örneğin:

```cpp
class CExampleDialog : public CDialog
{
public:
   AFX_EXT_CLASS CExampleDialog();
   AFX_EXT_CLASS int DoModal();
   ...
   // rest of class definition
   ...
};
```

Artık sınıfın tüm üyelerini dışarı aktaramadığından, MFC makrolarının çalışma biçimi nedeniyle ek bir sorunla karşılaşabilirsiniz. MFC 'nin yardımcı makrolarının bazıları aslında veri üyelerini bildirir veya tanımlar. Bu nedenle, bu veri üyeleri DLL 'nizden de verilmelidir.

Örneğin, `DECLARE_DYNAMIC` makro MFC uzantı dll 'si oluştururken aşağıdaki gibi tanımlanır:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Static `AFX_DATA` ile başlayan çizgi, sınıfınızın içinde statik bir nesne bildiriyor. Bu sınıfı doğru dışarı aktarmak ve bir istemci yürütülebilirinin çalışma zamanı bilgilerine erişmek için bu statik nesneyi dışarı aktarmanız gerekir. Statik `AFX_DATA`nesne değiştiriciyle `AFX_DATA` BILDIRILDIĞI için `__declspec(dllexport)` , yalnızca dll 'nizi oluştururken ve bunu istemci yürütülebilir dosyanızı oluştururken olduğu gibi `__declspec(dllimport)` tanımlayarak tanımlamanız gerekir. `AFX_EXT_CLASS` Bu şekilde zaten tanımlandığından, sınıf tanımınızın `AFX_EXT_CLASS` etrafında aynı olması için yalnızca yeniden tanımlamanız `AFX_DATA` gerekir.

Örneğin:

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS

class CExampleView : public CView
{
   DECLARE_DYNAMIC()
   // ... class definition ...
};

#undef  AFX_DATA
#define AFX_DATA
```

MFC her zaman kendi makroları `AFX_DATA` içinde tanımladığı veri öğelerinde sembol kullandığından, bu teknik tüm senaryolar için de kullanılır. Örneğin, için `DECLARE_MESSAGE_MAP`geçerlidir.

> [!NOTE]
> Sınıfın seçili üyeleri yerine sınıfının tamamını dışarı aktarıyorsanız statik veri üyeleri otomatik olarak dışarı aktarılabilir.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [. Def dosyalarını kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport) kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [C Dili Çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ Dili Çalıştırılabilirlerinde kullanmak için C işlevlerini dışarı aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Düzenlenmiş adlar](reference/decorated-names.md)

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
