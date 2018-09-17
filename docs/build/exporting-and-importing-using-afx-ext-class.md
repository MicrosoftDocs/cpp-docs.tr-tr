---
title: AFX_EXT_CLASS kullanarak içeri aktarma ve dışarı aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- afx_ext_class
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46964b4babc7d7afd4b523ee37981296e9f7dc57
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711954"
---
# <a name="exporting-and-importing-using-afxextclass"></a>AFX_EXT_CLASS Kullanarak İçeri ve Dışarı Aktarma

[MFC uzantı DLL'leri](../build/extension-dlls-overview.md) makroyu kullanın **AFX_EXT_CLASS** sınıfları dışarı aktarmak için; sınıflarını içeri aktarmak için makro MFC uzantısı DLL için bağlama yürütülebilir dosyaları kullanın. İle **AFX_EXT_CLASS** makrosu, MFC uzantısı DLL için DLL'e yürütülebilir dosyaları ile kullanılabilir oluşturmak için kullanılan aynı üst bilgi dosyaları.

DLL'niz üstbilgi dosyasına ekleyin **AFX_EXT_CLASS** sınıfının bildirimi aşağıdaki gibi anahtar:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Bu makro MFC tarafından tanımlanan `__declspec(dllexport)` , önişlemci sembolleri `_AFXDLL` ve `_AFXEXT` tanımlanır. Ancak bir makro olarak tanımlı `__declspec(dllimport)` olduğunda `_AFXDLL` tanımlanır ve `_AFXEXT` tanımlı değil. Tanımlandığında, önişlemci sembolü `_AFXDLL` MFC'nin paylaşılan sürümünden hedef yürütülebilir (DLL ya da uygulama) tarafından kullanılmakta olduğunu gösterir. Her ikisi de `_AFXDLL` ve `_AFXEXT` olan tanımlanan, bu hedef çalıştırılabilir bir MFC uzantılı DLL olduğunu gösterir.

Çünkü `AFX_EXT_CLASS` olarak tanımlanan `__declspec(dllexport)` bir MFC uzantılı DLL dışa aktarırken o sınıfın sembolleri düzenlenmiş adları .def dosyasına koymadan tüm sınıflar dışarı aktarabilirsiniz.

.Def dosyası ve tüm düzenlenmiş adları sınıfı için bu yöntemle oluşturmaktan kaçının olsa da, sıralı olarak adlarını alınabileceğinden .def dosyası oluşturmak daha etkilidir. Verme .def dosyası yöntemi kullanmak için aşağıdaki kodu, üst bilgi dosyası başında ve sonunda yerleştirin:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
>  Sürüm çakışması olasılığı oluşturduğundan satır içi işlevleri dışa aktarırken dikkatli olun. Satır içi işlev, uygulama kodunda genişletilmiş; Daha sonra işlevi yeniden yazma, uygulamanın kendisi yeniden derlenen sürece bu nedenle, bu güncelleştirilmiyor. Normalde, DLL işlevleri, bunları kullanan uygulamalar yeniden derlenmeden güncelleştirilebilir.

## <a name="exporting-individual-members-in-a-class"></a>Bir sınıf içinde tek tek üyeleri dışa aktarma

Bazen tek tek üyeleri sınıfınızın vermek isteyebilirsiniz. Dışa aktarıyorsanız, örneğin, bir `CDialog`-türetilmiş sınıf, yalnızca Oluşturucu dışarı aktarmak gerekebilir ve `DoModal` çağırın. Kullanabileceğiniz `AFX_EXT_CLASS` dışarı aktarmak için gereken tek tek üyeleri üzerinde.

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

Sınıfın tüm üyeleri artık dışarı aktardığınız olduğundan, ek bir sorunla karşılaşırsanız, MFC makroları çalışma şekli nedeniyle çalıştırabilirsiniz. Birkaç MFC'nin yardımcı makroları gerçekten bildirmek veya veri üyeleri tanımlar. Bu nedenle, bu veri üyeleri Ayrıca, DLL'den dışarı aktarılmalıdır.

Örneğin, `DECLARE_DYNAMIC` makro bir MFC uzantılı DLL oluşturma sırasında şu şekilde tanımlanır:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Statik ile başlayan satırı `AFX_DATA` Sınıfınız içinde statik nesne bildirme. Bu sınıfı doğru olarak dışarı aktarın ve çalışma zamanı bilgileri yürütülebilir bir istemciden erişmek için bu statik nesne dışarı aktarmanız gerekir. Statik nesne değiştiriciyle bildirildiğinden `AFX_DATA`, tanımlamak yeterlidir `AFX_DATA` olmasını `__declspec(dllexport)` DLL dosyanızı oluştururken ve olarak tanımlayın `__declspec(dllimport)` istemcinizi yürütülebilir oluştururken. Çünkü `AFX_EXT_CLASS` zaten tanımlanmış bu şekilde, yeniden tanımlanacak yeterlidir `AFX_DATA` aynı olacak şekilde `AFX_EXT_CLASS` sınıf tanımına geçici bir çözüm.

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

MFC her zaman kullandığından `AFX_DATA` sembol tüm senaryolar için bu tekniği works veri öğelerinde kendi makrosunda tanımlar. Örneğin, için çalıştığını `DECLARE_MESSAGE_MAP`.

> [!NOTE]
>  Seçilen üyeleri sınıf yerine sınıfın tamamı dışa aktarıyorsanız, otomatik olarak statik veri üyeleri dışa aktarılır.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.Def dosyalarını kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ dili çalıştırılabilirlerinde kullanmak için C işlevlerini dışa aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](../build/determining-which-exporting-method-to-use.md)

- [__Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın](../build/importing-into-an-application-using-declspec-dllimport.md)

- [DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Düzenlenmiş adlar](../build/reference/decorated-names.md)

- [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)

## <a name="see-also"></a>Ayrıca Bkz.

[DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)