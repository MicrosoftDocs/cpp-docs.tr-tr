---
title: "Derleyici Hatası C3120 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3120
dev_langs: C++
helpviewer_keywords: C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6bdd5f5fe41fa794b536f71b3f88db01de99c646
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3120"></a>Derleyici Hatası C3120
'method_name': arabirim yöntemleri değişken bağımsız değişken listesi alamaz  
  
 Arabirim yöntemi bir değişken bağımsız değişken listesi alınamıyor. Örneğin, aşağıdaki arabirim tanımı C3120 oluşturur:  
  
```  
// C3120.cpp  
__interface A {  
int X(int i, ...);    // C3120  
};  
  
int main(void) { return(0); }  
```