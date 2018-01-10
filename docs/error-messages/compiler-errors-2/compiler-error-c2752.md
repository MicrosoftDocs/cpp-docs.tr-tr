---
title: "Derleyici Hatası C2752 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2752
dev_langs: C++
helpviewer_keywords: C2752
ms.assetid: ae42b3ec-84a9-4e9d-8d59-3d208132d0b2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1372cac795bd6df83a92fe7c14980f618085176c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2752"></a>Derleyici Hatası C2752
'şablon': birden fazla kısmi uzmanlığı şablon bağımsız değişken listesiyle eşleşiyor  
  
 Bir örnekleme belirsiz.  
  
 Aşağıdaki örnek C2752 oluşturur:  
  
```  
// C2752.cpp  
template<class T, class U>   
struct A {};  
  
template<class T, class U>   
struct A<T*, U> {};  
  
template<class T, class U>   
struct A<T,U*> {};  
  
// try the following line instead  
// template<class T, class U> struct A<T*,U*> {};  
  
int main() {  
   A<char*,int*> a;   // C2752 an instantiation  
  
   // OK  
   A<char*,int> a1;  
   A<char,int*> a2;  
   A<char,int> a3;  
}  
```