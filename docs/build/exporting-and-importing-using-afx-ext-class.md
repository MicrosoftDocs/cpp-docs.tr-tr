---
title: "AFX_EXT_CLASS kullanarak içeri aktarma ve dışarı aktarma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: afx_ext_class
dev_langs: C++
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 753395713bd4831f1dbc55403134898ae68ca182
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exporting-and-importing-using-afxextclass"></a>AFX_EXT_CLASS Kullanarak İçeri ve Dışarı Aktarma  
  
[MFC uzantı DLL'leri](../build/extension-dlls-overview.md) makrosu kullanma **AFX_EXT_CLASS** dışarı aktarmak için sınıfları; sınıflarını içeri aktarmak için makro MFC uzantı DLL'si bağlantı yürütülebilir dosyaları kullanın. İle **AFX_EXT_CLASS** makrosu, DLL, DLL'e yürütülebilir dosyaları ile kullanılabilir MFC uzantı oluşturmak için kullanılan aynı başlık dosyaları.  
  
 DLL üstbilgi dosyasına ekleyin **AFX_EXT_CLASS** sınıfınız bildirimi aşağıdaki gibi anahtar:  
  
```cpp  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
Bu makrosu MFC tarafından tanımlanan `__declspec(dllexport)` zaman önişlemci sembolleri `_AFXDLL` ve `_AFXEXT` tanımlanır. Ancak makrosu olarak tanımlanan `__declspec(dllimport)` zaman `_AFXDLL` tanımlanır ve `_AFXEXT` tanımlı değil. Tanımlandığında, önişlemci sembolü `_AFXDLL` MFC'nin paylaşılan sürümünün hedef çalıştırılabilir (DLL ya da bir uygulama) tarafından kullanılmakta olduğunu gösterir. Her ikisi de `_AFXDLL` ve `_AFXEXT` olan tanımlı, bu hedef çalıştırılabilir MFC uzantı DLL'si olduğunu gösterir.  
  
Çünkü `AFX_EXT_CLASS` olarak tanımlanan `__declspec(dllexport)` bir MFC uzantı DLL dışarı aktarılırken o sınıfın simgeleri düzenlenmiş adları .def dosyasına koymadan tüm sınıflar dışarı aktarabilirsiniz.  
  
Bu yöntemle .def dosyası ve tüm sınıfı için düzenlenmiş adları oluşturmaktan önleyebilirsiniz rağmen adlarını sıralı olarak alınabileceğinden .def dosyası oluşturmak daha verimlidir. Verme .def dosyası yöntemi kullanmak için aşağıdaki kod, üstbilgi dosyası başında ve sonunda yerleştir:  
  
```cpp  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  Sürüm çakışması olasılığı oluşturduğundan satır içi işlevler verirken dikkatli olun. Satır içi işlev uygulama koda genişletilmiş; işlevi yeniden yazma, uygulamanın kendisinin derlenmiştir sürece bu nedenle, onu güncelleştirilmez. Normalde, DLL işlevleri, bunları kullanan uygulamaları derlenmeden güncelleştirilebilir.  
  
## <a name="exporting-individual-members-in-a-class"></a>Bir sınıftaki tek tek üyeleri dışarı aktarma  
  
Bazen, sınıfı tek tek üyeleri vermek isteyebilirsiniz. Dışa aktarıyorsanız, örneğin, bir `CDialog`-türetilmiş sınıf, yalnızca Oluşturucusu vermeniz gerekebilir ve `DoModal` çağırın. Kullanabileceğiniz `AFX_EXT_CLASS` dışarı aktarmak için gereken tek tek üyeleri üzerinde.  
  
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
  
Sınıfın tüm üyeleri artık verdiğiniz olduğundan, MFC makroları çalışma biçimini nedeniyle ek sorunlarla çalıştırabilirsiniz. MFC'nin yardımcı makroları çeşitli gerçekte bildirme veya veri üyeleri tanımlayın. Bu nedenle, bu veri üyeleri de, DLL'den dışarı aktarılmalıdır.  
  
Örneğin, `DECLARE_DYNAMIC` makrosu MFC uzantı DLL'si oluştururken aşağıdaki gibi tanımlanır:  
  
```cpp  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
Statik ile başlayan satır `AFX_DATA` sınıfınızın içinde statik bir nesne bildirme. Bu sınıf doğru şekilde dışa aktarmak ve çalışma zamanı bilgileri yürütülebilir bir istemciden erişmek için bu statik nesneyi dışarı aktarmanız gerekir. Statik nesne değiştiricisi ile bildirildiğinden `AFX_DATA`, yalnızca tanımlamanız gerekecek `AFX_DATA` olmasını `__declspec(dllexport)` DLL dosyanızı oluştururken ve olarak tanımlamak `__declspec(dllimport)` istemciniz yürütülebilir oluştururken. Çünkü `AFX_EXT_CLASS` zaten tanımlı bu yolla yeniden tanımlamanız yeterlidir `AFX_DATA` aynı olacak şekilde `AFX_EXT_CLASS` Sınıf tanımınız geçici.  
  
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
  
MFC her zaman kullandığından `AFX_DATA` içinde makroları, tanımladığı veri öğeleri takımından gibi senaryolar için bu tekniği çalışır. Örneğin, için çalışır `DECLARE_MESSAGE_MAP`.  
  
> [!NOTE]
>  Seçilen sınıf üyeleri yerine bütün sınıfı dışa aktarıyorsanız, statik veri üyeleri otomatik olarak dışarı aktarılır.  
  
### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [.Def dosyaları kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C veya C++ dili yürütülebilir öğelerinde kullanmak için C işlevlerini dışarı aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec(dllimport) kullanarak bir uygulama içeri aktarmak için](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Düzenlenmiş adlar](../build/reference/decorated-names.md)  
  
-   [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)  
  
-   [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL'den dışarı aktarma](../build/exporting-from-a-dll.md)