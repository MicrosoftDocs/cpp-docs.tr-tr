---
title: "Derleyici Hatası C3510 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3510
dev_langs: C++
helpviewer_keywords: C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dddfa1ed7c21f36bebdbefb0049e356bba9cdc8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3510"></a>Derleyici Hatası C3510
bağımlı türü Kitaplığı 'type_lib' bulamıyor  
  
 [no_registry](../../preprocessor/no-registry.md) ve [auto_search](../../preprocessor/auto-search.md) için geçirilmiş `#import` ancak derleyici başvurulan tür kitaplığını bulamıyor değildi.  
  
 Bu hatayı gidermek için tüm tür kitaplıklarını ve başvurulan tür kitaplıklarının derleyiciye kullanılabilir olduğundan emin olun.  
  
 Aşağıdaki örnek C3510 oluşturur:  
  
 Aşağıdaki iki tür kitaplıklarına oluşturulan ve o C3510a.tlb silindi veya yolunda değil.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 Ve ardından ikinci tür kitaplığı için kaynak kodu:  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 Ve ardından istemci kodu:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```