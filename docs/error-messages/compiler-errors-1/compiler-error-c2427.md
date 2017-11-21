---
title: "Derleyici Hatası C2427 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2427
dev_langs: C++
helpviewer_keywords: C2427
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 416db305963b6357c6dce9c5b2d13f0a6ca186f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2427"></a>Derleyici Hatası C2427
'class': sınıf bu kapsamda tanımlanamıyor  
  
 İç içe geçmiş sınıf tanımlamak için bir girişimde bulunuldu, ancak iç içe geçmiş sınıf bir taban sınıfın en içeren sınıf bir üyesidir.  
  
 Aşağıdaki örnek C2427 oluşturur:  
  
```  
// C2427.cpp  
// compile with: /c  
template <class T>   
struct S {  
   struct Inner;   
};   
  
struct Y : S<int> {};   
  
struct Y::Inner {};   // C2427  
  
// OK  
template<typename T>  
struct S<T>::Inner {};  
```