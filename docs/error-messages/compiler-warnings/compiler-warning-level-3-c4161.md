---
title: "Derleyici Uyarısı (Düzey 3) C4161 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4161
dev_langs:
- C++
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d61de9a9a02f55114319af677db29630038966a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4161"></a>Derleyici Uyarısı (Düzey 3) C4161
\#pragma pragma(pop...): iter'den daha fazla POP  
  
 Kaynak kodunuz bir gönderim pragma için daha fazla pop içerdiğinden ***pragma***, yığın beklendiği gibi çalışmayabilir. Uyarı önlemek için POP sayısı gönderim sayısını aşmadığından emin olun.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4161 oluşturur:  
  
```  
// C4161.cpp  
// compile with: /W3 /LD  
#pragma pack(push, id)  
#pragma pack(pop, id)  
#pragma pack(pop, id)   // C4161, an extra pop  
  
#pragma bss_seg(".my_data1")  
int j;  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;  
  
#pragma bss_seg(pop, stack1)  
int m;  
  
#pragma bss_seg(pop, stack1)   // C4161  
```