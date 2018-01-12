---
title: "Derleyici Uyarısı (düzey 4) C4336 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4336
dev_langs: C++
helpviewer_keywords: C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 524d5d1aab2b63854ec334f6eb94a62e9fb127c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4336"></a>Derleyici Uyarısı (düzey 4) C4336
Çapraz referanslı Kitaplığı 'type_lib1' 'type_lib2' almadan önce içeri aktarma türü  
  
 Tür kitaplığı ile başvuruldu [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi. Ancak, tür kitaplığı ile başvurulmadı başka bir tür kitaplığı başvuru bulunan `#import`. Bu bir .tlb dosyası derleyici tarafından bulunamadı.  
  
 Verilen iki tür kitaplıkları (midl.exe ile derlenmiş) aşağıdaki iki dosyalarından oluşturulan diskteki:  
  
```  
// c4336a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library c4336aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C4336  
   {  
      one, two, three  
   };  
};  
```  
  
 İkinci tür kitaplığı:  
  
```  
// c4336b.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4336bLib  
{  
   importlib ("c4336a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4336  
   {  
      enum E_C4336 e;  
   };  
};  
```  
  
 Aşağıdaki örnek C4336 oluşturur:  
  
```  
// C4336.cpp  
// compile with: /W4 /LD  
// #import "C4336a.tlb"  
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve  
```