---
title: Derleyici Uyarısı (düzey 1) C4052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4052
dev_langs:
- C++
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5c937e602f14789419f6b124034503c127f6dc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4052"></a>Derleyici Uyarısı (düzey 1) C4052
işlev bildirimleri farklı; değişken bağımsız değişken içeriyor  
  
 Bir işlevin bildirimi değişken bağımsız değişken içermiyor. Yoksayılır.  
  
 Aşağıdaki örnek C4052 oluşturur:  
  
```  
// C4052.c  
// compile with: /W4 /c  
int f();  
int f(int i, ...);   // C4052  
```