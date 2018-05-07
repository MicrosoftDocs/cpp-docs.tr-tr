---
title: Derleyici Hatası C2767 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2767
dev_langs:
- C++
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5ac628d1e02c53b0ed0872873ef23ef708df982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2767"></a>Derleyici Hatası C2767
yönetilen veya WinRTarray boyut uyuşmazlığı: N bağımsız değişkenli - M sağlanan bekleniyor  
  
 Bir yönetilen veya WinRT dizi bildirimi ill biçimlendirilmiş. Daha fazla bilgi için bkz: [dizi](../../windows/arrays-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C2767 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2767.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>(2,3); // C2767  
   array<int> ^p2 = new array<int>(2);   // OK  
}  
```