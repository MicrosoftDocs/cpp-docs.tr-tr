---
title: "Derleyici Hatası C2120 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2120
dev_langs: C++
helpviewer_keywords: C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f04793ca0d1b216d9f75f253a198b928b1ea7d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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