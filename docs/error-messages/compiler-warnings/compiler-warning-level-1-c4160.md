---
title: Derleyici Uyarısı (düzey 1) C4160 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4160
dev_langs:
- C++
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31c7c82ed4f79ce81abdfabb2b52968c2a481e97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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