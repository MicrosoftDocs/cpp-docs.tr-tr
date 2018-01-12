---
title: "Derleyici Hatası C2745 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2745
dev_langs: C++
helpviewer_keywords: C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 08574b9af70dbeb198fc0abc0eb03e14f5dd58cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2745"></a>Derleyici Hatası C2745
'belirteci': Bu belirteç tanımlayıcıya dönüştürülemez  
  
 Tanımlayıcıları yasal karakterlerden oluşmasına gerekir.  
  
 Aşağıdaki örnek C2745 oluşturur:  
  
```  
// C2745.cpp  
// compile with: /clr  
int main() {  
   int __identifier([));   // C2745  
}  
```