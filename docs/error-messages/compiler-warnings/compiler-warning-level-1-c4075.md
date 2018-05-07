---
title: Derleyici Uyarısı (düzey 1) C4075 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4075
dev_langs:
- C++
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9a0d9fb3808af9ed05454b5b07d471303abc654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4075"></a>Derleyici Uyarısı (düzey 1) C4075
Tanınmayan başlatma alanına yerleştirir başlatıcıları  
  
 A [#pragma init_seg](../../preprocessor/init-seg.md) bilinmeyen bölüm adı kullanır. Derleyici yoksayar **pragma** komutu.  
  
 Aşağıdaki örnek C4075 oluşturur:  
  
```  
// C4075.cpp  
// compile with: /W1  
#pragma init_seg("mysegg")   // C4075  
  
// try..  
// #pragma init_seg(user)  
  
int main() {  
}  
```