---
title: "Derleyici Hatası C2128 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: c2128
dev_langs: C++
helpviewer_keywords: C2128
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d0739af6c84b2dc1a7f86c5cb4843ce66e85bf85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2128"></a>Derleyici Hatası C2128
'function': alloc_text/same_seg yalnızca C bağlantı işlevleriyle uygulanabilir  
  
 `pragma``alloc_text` yalnızca C bağlantı sağlamak için bildirilen işlevler ile kullanılabilir.  
  
 Aşağıdaki örnek C2128 oluşturur:  
  
```  
// C2128.cpp  
// compile with: /c  
  
// Delete the following line to resolve.  
void func();  
// #pragma alloc_text("my segment", func)   // C2128  
  
extern "C" {  
void func();  
}  
  
#pragma alloc_text("my segment", func)  
void func() {}  
```