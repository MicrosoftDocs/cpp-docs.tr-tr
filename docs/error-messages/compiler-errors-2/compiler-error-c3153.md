---
title: Derleyici Hatası C3153 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3153
dev_langs:
- C++
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c9829313947c7d3e954ddfd309f47d571ae2639
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3153"></a>Derleyici Hatası C3153
'arabirimi': arabiriminin bir örneği oluşturulamıyor  
  
 Bir arabirim başlatılamaz. Arabirim üyeleri kullanmak için arabirimi öğesinden bir sınıf türetin, arabirim üyeleri uygulayan ve üyeleri kullanır.  
  
 Aşağıdaki örnek C3153 oluşturur:  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  
