---
title: "Derleyici Hatası C3205 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3205
dev_langs: C++
helpviewer_keywords: C3205
ms.assetid: 802d306e-5ff3-4491-8a22-c5f1c072d005
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 46b42d19bd42bafbb6baf6b8af368bd10c9dd1ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3205"></a>Derleyici Hatası C3205
'parametresi' şablon parametresi için bağımsız değişken listesi eksik  
  
A [şablonu](../../cpp/templates-cpp.md) parametresi eksik.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3205 oluşturur:  
  
```cpp  
// C3205.cpp  
template<template<class> class T> struct A {  
   typedef T unparameterized_type;   // C3205  
   // try the following line instead  
   // typedef T<int> unparameterized_type;  
};  
  
template <class T>  
struct B {  
   typedef int value_type;  
};  
  
int main() {  
   A<B> x;  
}  
```