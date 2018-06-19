---
title: __Declspec(dllimport) kullanarak bir uygulamaya aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82974ec688fbe688c98188c2e99a54462da81165
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368841"
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>__declspec(dllimport) Kullanarak Bir Uygulamaya Aktarma
DLL tarafından tanımlanan ortak sembolleri kullanan bir program içeri aktarılacak. Oluşturduğunuzda üstbilgi dosyaları, oluşturmak için DLL'leri kullanan uygulamaları kullanmak için **__declspec(dllimport)** genel semboller bildirimlerinde. Anahtar sözcüğü **__declspec(dllimport)** veya .def dosyaları ile dışarı aktarma olup olmadığını çalışır **__declspec(dllexport)** anahtar sözcüğü.  
  
 Kodunuzu daha okunabilir hale getirmek için makro tanımlamak **__declspec(dllimport)** ve içeri aktardığınız her simgeyi bildirmek için makrosu kullanın:  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 Kullanarak **__declspec(dllimport)** işlevi bildirimlerinde isteğe bağlıdır, ancak bu anahtar sözcük kullanırsanız derleyici daha verimli kod oluşturur. Ancak, kullanmalıdır **__declspec(dllimport)** DLL'in ortak veri sembolleri ve nesnelere erişmek içeri aktarma çalıştırılabilir. DLL kullanıcılarının hala bir içeri aktarma kitaplığı ile bağlantı gerektiğini unutmayın.  
  
 DLL hem istemci uygulaması için aynı üstbilgi dosyası kullanabilirsiniz. Bunu yapmak için DLL oluşturma veya istemci uygulaması oluşturma olup olmadığını belirten bir özel önişlemci sembolü kullanın. Örneğin:  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)  
  
-   [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir Uygulamaya Aktarma](../build/importing-into-an-application.md)