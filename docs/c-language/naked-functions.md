---
title: "Naked işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- naked functions
- functions [C++], naked
- prolog code
- epilog code
ms.assetid: 2543c8af-00d4-4a2a-8a87-e746da1f9929
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7bafc912500c617db7d97d80665577ee9b74423d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="naked-functions"></a>Naked İşlevleri
**Microsoft özel**  
  
 `naked` depolama sınıfı özniteliği, C diline yönelik Microsoft'a özgü bir uzantıdır. `naked` depolama sınıfı özniteliğiyle bildirilen işlevler için derleyici giriş ve sonuç kodu olmadan kod oluşturur. Satır içi derleyici kodunu kullanarak kendi giriş/sonuç kodu dizilerinizi yazmak için bu özelliği kullanabilirsiniz. Çıplak işlevler, özellikle sanal cihaz sürücülerinin yazılmasında yararlıdır.  
  
 Çünkü `naked` özniteliği yalnızca bir işlev tanımı için geçerlidir ve bir tür değiştiricisi değil, naked işlevleri kullanma açıklanan genişletilmiş öznitelik sözdizimi [genişletilmiş depolama sınıfı öznitelikler](../c-language/c-extended-storage-class-attributes.md).  
  
 Aşağıdaki örnekte, `naked` özniteliğine sahip bir işlev tanımlanmaktadır:  
  
```  
__declspec( naked ) int func( formal_parameters )  
{  
   /* Function body */  
}  
```  
  
 Veya alternatif olarak:  
  
```  
#define Naked   __declspec( naked )  
  
Naked int func( formal_parameters )  
{  
   /* Function body */  
}  
```  
  
 `naked` özniteliği, yalnızca işlevin giriş ve sonuç dizileri için derleyicinin kod oluşturma yapısını etkiler. Bu tür işlevleri çağırmak için oluşturulan kodu etkilemez. Bu nedenle, `naked` özniteliği işlev türünün bir parçası olarak kabul edilmez ve işlev işaretçileri `naked` özniteliğine sahip olamaz. Ayrıca, `naked` özniteliği veri tanımına uygulanamaz. Örneğin, aşağıdaki kod hatalar oluşturur:  
  
```  
__declspec( naked ) int i;  /* Error--naked attribute not */  
                            /* permitted on data declarations. */  
```  
  
 `naked` özniteliği, yalnızca işlevin tanımıyla ilgilidir ve işlevin prototipinde belirtilemez. Aşağıdaki bildirim, bir derleyici hatası oluşturur:  
  
```  
__declspec( naked ) int func();   /* Error--naked attribute not */  
                     /* permitted on function declarations.    */   \  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C İşlev Tanımları](../c-language/c-function-definitions.md)