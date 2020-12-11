---
description: 'Hakkında daha fazla bilgi edinin: AFX_EXT_CLASS kullanarak dışarı aktarma ve Içeri aktarma'
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
ms.openlocfilehash: 9c82874b1e5e8791f2825cf6874399fab0e10eaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156690"
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

Bu makro `__declspec(dllexport)` , önişlemci sembolleri `_AFXDLL` ve TANıMLANDıĞı gibi MFC tarafından tanımlanır `_AFXEXT` . Ancak makro tanımlandığı gibi tanımlanır `__declspec(dllimport)` `_AFXDLL` ve `_AFXEXT` tanımlı değildir. Tanımlandığında, Önişlemci sembolü, `_AFXDLL` MFC 'nin paylaşılan sürümünün hedef yürütülebilir (BIR DLL veya bir uygulama) tarafından kullanıldığını gösterir. Hem hem `_AFXDLL` de `_AFXEXT` tanımlandığında bu, hedef YÜRÜTÜLEBILIRIN bir MFC uzantı dll olduğunu gösterir.

, `AFX_EXT_CLASS` `__declspec(dllexport)` Bir MFC uzantı dll 'sinden dışarı aktarılırken olduğu gibi tanımlandığından, tüm sınıfları, bu sınıfın tüm sembolleri için düzenlenmiş adları. def dosyasına yerleştirmeksizin dışarı aktarabilirsiniz.

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

Bazen sınıfınızın tek tek üyelerini dışarı aktarmak isteyebilirsiniz. Örneğin, bir `CDialog` türetilmiş sınıfı dışarı aktarıyorsanız, yalnızca oluşturucuyu ve çağrısını dışarı aktarmanız gerekebilir `DoModal` . `AFX_EXT_CLASS`' İ dışa aktarmanız gereken ayrı Üyeler üzerinde kullanabilirsiniz.

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

Örneğin, `DECLARE_DYNAMIC` makro MFC uzantı DLL 'si oluştururken aşağıdaki gibi tanımlanır:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Static ile başlayan çizgi, `AFX_DATA` sınıfınızın içinde statik bir nesne bildiriyor. Bu sınıfı doğru dışarı aktarmak ve bir istemci yürütülebilirinin çalışma zamanı bilgilerine erişmek için bu statik nesneyi dışarı aktarmanız gerekir. Statik nesne değiştiriciyle bildirildiği `AFX_DATA` için, yalnızca `AFX_DATA` `__declspec(dllexport)` DLL 'nizi oluştururken ve bunu `__declspec(dllimport)` istemci yürütülebilir dosyanızı oluştururken olduğu gibi tanımlayarak tanımlamanız gerekir. `AFX_EXT_CLASS`Bu şekilde zaten tanımlandığından, `AFX_DATA` sınıf tanımınızın etrafında aynı olması için yalnızca yeniden tanımlamanız gerekir `AFX_EXT_CLASS` .

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

MFC her zaman `AFX_DATA` kendi makroları içinde tanımladığı veri öğelerinde sembol kullandığından, bu teknik tüm senaryolar için de kullanılır. Örneğin, için geçerlidir `DECLARE_MESSAGE_MAP` .

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
