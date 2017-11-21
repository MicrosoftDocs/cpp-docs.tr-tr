---
title: "Derleyici Hatası C2892 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2892
dev_langs: C++
helpviewer_keywords: C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 821069a21b6cf935590e0c999c5dbda1c69801f2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2892"></a>Derleyici Hatası C2892
Yerel sınıf üye şablonları olmaması  
  
 Şablonlu üye işlevleri bir işlevde tanımlı bir sınıf geçerli değil.  
  
 Aşağıdaki örnek C2892 oluşturur:  
  
```  
// C2892.cpp  
int main() {  
   struct local {  
      template<class T>   // C2892  
      void f() {}  
   };  
}  
```