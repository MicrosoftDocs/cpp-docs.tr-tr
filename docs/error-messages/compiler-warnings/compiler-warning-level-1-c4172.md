---
title: Derleyici Uyarısı (düzey 1) C4172 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4172
dev_langs:
- C++
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 746442638820d0c81144611a678996dc4c8483b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276665"
---
# <a name="compiler-warning-level-1-c4172"></a>Derleyici Uyarısı (düzey 1) C4172
yerel değişken ya da geçici adresini döndürüyor  
  
 Bir işlev adresi yerel değişken ya da geçici nesne döndürür. İşlevi döndüğünde, döndürülen adresi geçerli değil şekilde yerel değişkenleri ve geçici nesneler yok olur.  
  
 Böylece yerel nesne adresi döndürmüyor işlevi yeniden tasarlamanız.  
  
 Aşağıdaki örnek C4172 oluşturur:  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```