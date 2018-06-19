---
title: Derleyici Hatası C2120 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2120
dev_langs:
- C++
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f977f3a0ffda275a0819f01f8c99f12236babd5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165724"
---
# <a name="compiler-error-c2120"></a>Derleyici Hatası C2120
Tüm türleriyle 'void' geçersiz  
  
 `void` Türü, başka bir türüne sahip bir bildirimde kullanılır.  
  
 Aşağıdaki örnek C2120 oluşturur:  
  
```  
// C2120.cpp  
int main() {  
   void int i;   // C2120  
   int j;   // OK  
}  
```