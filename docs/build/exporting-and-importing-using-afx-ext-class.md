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

[MFC uzantılı DL'ler](extension-dlls-overview.md) sınıfları dışa aktarmak için makro **AFX_EXT_CLASS** kullanır; MFC uzantısı DLL'ye bağlanan yürütülebilir uygulamalar, sınıfları almak için makroyu kullanır. Makro **AFX_EXT_CLASS** ile, MFC uzantısı DLL oluşturmak için kullanılan aynı üstbilgi dosyaları DLL bağlantı yürütülebilir ile kullanılabilir.

DLL'nizin üstbilgi dosyasına, AFX_EXT_CLASS **anahtar** sözcüğü sınıfınızın bildirimine aşağıdaki gibi ekleyin:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Bu makro, MFC `__declspec(dllexport)` tarafından önişlemci `_AFXDLL` sembolleri olarak tanımlanır ve `_AFXEXT` tanımlanır. Ancak makro ne `__declspec(dllimport)` zaman `_AFXDLL` tanımlanır `_AFXEXT` ve tanımlanmaz olarak tanımlanır. Önişlemci simgesi `_AFXDLL` tanımlandığında, MFC'nin paylaşılan sürümünün yürütülebilir hedef tarafından kullanıldığını gösterir (DLL veya uygulama). Her `_AFXDLL` ikisi `_AFXEXT` de ve tanımlandığında, bu hedef yürütülebilir bir MFC uzantısı DLL olduğunu gösterir.

MFC `AFX_EXT_CLASS` uzantısı `__declspec(dllexport)` DLL'den dışa aktarırken olarak tanımlandığınızda, bu sınıfın tüm simgelerinin dekore edilmiş adlarını .def dosyasına yerleştirmeden tüm sınıfları dışa aktarabilirsiniz.

Bu yöntemle bir .def dosyası ve sınıf için dekore edilmiş tüm adlar oluşturmaktan kaçınabilirsiniz, ancak adlar ordinal tarafından dışa aktarılabildiği için bir .def dosyası oluşturmak daha verimlidir. .def dosyası dışa aktarma yöntemini kullanmak için üstbilgi dosyanızın başına ve sonuna aşağıdaki kodu yerleştirin:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
> Satır oluşturma işlevlerini dışa aktarırken dikkatli olun, çünkü sürüm çakışmaları olasılığını oluşturabilirler. Satır dışı bir işlev uygulama koduna genişletilir; bu nedenle, daha sonra işlevi yeniden yazarsanız, uygulamanın kendisi yeniden derlenmedikçe güncelleştirilmez. Normalde, DLL işlevleri bunları kullanan uygulamaları yeniden oluşturmadan güncellenebilir.

## <a name="exporting-individual-members-in-a-class"></a>Bir Sınıfta Bireysel Üye İhraç Etme

Bazen sınıfınızın tek tek üyelerini dışa aktarmak isteyebilirsiniz. Örneğin, türetilmiş bir `CDialog`sınıf dışa aktarıyorsanız, yalnızca oluşturucuyu `DoModal` ve aramayı dışa aktarmanız gerekebilir. Dışa `AFX_EXT_CLASS` aktarmanız gereken tek tek üyeleri kullanabilirsiniz.

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

Artık sınıfın tüm üyelerini dışa aktarmamadığınız için, MFC makrolarının çalışma şekli nedeniyle ek bir sorunla karşılaşabilirsiniz. MFC'nin yardımcı makrolarından bazıları veri üyelerini gerçekten beyan eder veya tanımlar. Bu nedenle, bu veri üyeleri de DLL dışa aktarılmalıdır.

Örneğin, `DECLARE_DYNAMIC` bir MFC uzantısı DLL inşa ederken makro aşağıdaki gibi tanımlanır:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Statikle `AFX_DATA` başlayan satır, sınıfınızın içinde statik bir nesne beyan ediyor. Bu sınıfı doğru dışa aktarmak ve çalıştırılabilir bir istemciden çalışma zamanı bilgilerine erişmek için bu statik nesneyi dışa aktarmanız gerekir. Statik nesne `AFX_DATA`değiştirici ile bildirilir olduğundan, yalnızca DLL'nizi inşa `AFX_DATA` `__declspec(dllexport)` ederken olması ve `__declspec(dllimport)` istemcinizin çalıştırılabilir olarak tanımlanması gerekir. Zaten `AFX_EXT_CLASS` bu şekilde tanımlandığıniçin, sınıf tanımınızın etrafındakiyle `AFX_DATA` `AFX_EXT_CLASS` aynı olması için yeniden tanımlamanız gerekir.

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

MFC her zaman `AFX_DATA` makroları içinde tanımladığı veri öğeleri üzerinde simgeyi kullandığından, bu teknik tüm bu senaryolar için çalışır. Örneğin, için çalışır `DECLARE_MESSAGE_MAP`.

> [!NOTE]
> Sınıfın seçili üyeleri yerine sınıfın tamamını dışa aktarıyorsanız, statik veri üyeleri otomatik olarak dışa aktarılır.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.def dosyalarını kullanarak Bir DLL'den dışa aktarma](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) kullanarak bir DLL'den dışa aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [C dili çalıştırılabilir cihazlarda kullanılmak üzere C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++dil deki yürütülebilir cihazlarda kullanılmak üzere C işlevlerini dışa aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [Bir DLL'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla şey bilmek istiyorsun?

- [Dekore edilmiş isimler](reference/decorated-names.md)

- [Satır İçi işlevleri alma ve dışa aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı ithalat](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
