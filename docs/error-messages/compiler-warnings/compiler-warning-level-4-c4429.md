---
title: Derleyici Uyarısı (düzey 4) C4429 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4429
dev_langs:
- C++
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00d4812fb1eefdd4364376288f063a6bf8b5dddf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4429"></a>Derleyici Uyarısı (düzey 4) C4429
Olası eksik veya hatalı oluşturulmuş evrensel karakter-adı  
  
 Derleyici hatalı biçimlendirilmiş evrensel karakter adları olabilir bir karakter dizisi algıladı. Evrensel karakter adları olan `\u` dört onaltılık basamak tarafından izlenen veya `\U` sekiz onaltılık basamak ile izlenen.  
  
 Aşağıdaki örnek C4429 oluşturur:  
  
```  
// C4429.cpp  
// compile with: /W4 /WX  
int \ug0e4 = 0;   // C4429  
// Try the following line instead:  
// int \u00e4 = 0;   // OK, a well-formed universal character name.  
```