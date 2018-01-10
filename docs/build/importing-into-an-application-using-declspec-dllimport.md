---
title: __Declspec(dllimport) kullanarak bir uygulamaya aktarma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __declspec
- dllimport
dev_langs: C++
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9766c6088e3f99711b936b10db0443da49b52c6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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