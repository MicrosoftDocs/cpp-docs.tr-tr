---
title: "Derleyici Hatası C2754 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2754
dev_langs: C++
helpviewer_keywords: C2754
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 924867394629c4c8227c8f50f76a9d32cbb750e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2754"></a>Derleyici Hatası C2754
'uzmanlık': Kısmi uzmanlığı bağımlı tür olmayan şablon parametresi olamaz  
  
 Kısmen bağımlı tür olmayan şablon parametresine sahip bir şablon sınıfı özelleştirmek için girişimde bulunuldu. Bu duruma izin verilmez.  
  
 Aşağıdaki örnek C2754 oluşturur:  
  
```  
// C2754.cpp  
// compile with: /c  
  
template<class T, T t>  
struct A {};  
  
template<class T, int N>  
struct B {};  
  
template<class T> struct A<T,5> {};   // C2754  
template<> struct A<int,5> {};   // OK  
template<class T> struct B<T,5> {};   // OK  
```