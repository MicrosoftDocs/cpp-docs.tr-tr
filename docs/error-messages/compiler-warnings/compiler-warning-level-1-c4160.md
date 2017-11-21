---
title: "Derleyici Uyarısı (düzey 1) C4160 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4160
dev_langs: C++
helpviewer_keywords: C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 129dfabde1cba003ab31b763c0a94386318c38a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4160"></a>Derleyici Uyarısı (düzey 1) C4160
**#pragma**   
 ***pragma* (pop,...): daha önce basılmış tanımlayıcı bulamadı '**   
 ***tanımlayıcı* '**  
  
 Kaynak kodunuz pragma deyiminde değil gönderilen bir tanımlayıcı pop dener. Bu uyarıyı önlemek için Sil'i tanımlayıcı düzgün gönderilen olduğunu unutmayın.  
  
 Aşağıdaki örnek C4160 oluşturur:  
  
```  
// C4160.cpp  
// compile with: /W1  
#pragma pack(push)  
  
#pragma pack(pop, id)   // C4160  
// use identifier when pushing to resolve the warning  
// #pragma pack(push, id)  
  
int main() {  
}  
```