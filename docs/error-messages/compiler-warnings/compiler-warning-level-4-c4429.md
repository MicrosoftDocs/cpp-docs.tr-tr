---
title: "Derleyici Uyarısı (düzey 4) C4429 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4429
dev_langs: C++
helpviewer_keywords: C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58b2a23b8abb3ab385f8c8a285ad1178299fa52d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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