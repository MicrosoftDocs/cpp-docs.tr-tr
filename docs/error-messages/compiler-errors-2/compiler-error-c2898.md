---
title: "Derleyici Hatası C2898 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2898
dev_langs: C++
helpviewer_keywords: C2898
ms.assetid: 68466e11-2541-4f6b-b772-13a642f30dfb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0833d3e4bab22673c6bca5aee64430134762e98f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2898"></a>Derleyici Hatası C2898
'bildirimi': üye işlev şablonları sanal olamaz  
  
 Aşağıdaki örnek C2898 oluşturur:  
  
```  
// C2898.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> virtual void f(T t) {}   // C2898  
};  
```