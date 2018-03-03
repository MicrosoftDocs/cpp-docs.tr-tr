---
title: "Derleyici Hatası C3028 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3028
dev_langs:
- C++
helpviewer_keywords:
- C3028
ms.assetid: 175e697f-8e8f-492a-8456-6240ffbbb900
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec61ff0b01a2f934102f0899ebfca41697f7c5d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3028"></a>Derleyici Hatası C3028
'member': bir veri paylaşımı yan tümcesinde yalnızca bir değişken ya da statik veri üyesi kullanılabilir  
  
 Bir değişken ya da statik veri üyesi dışında bir simge azaltma yan tümcesine geçirildi.  
  
 Aşağıdaki örnek C3028 oluşturur:  
  
```  
// C3028.cpp  
// compile with: /openmp /link vcomps.lib  
int g_i;  
  
class MyClass {  
public:  
   MyClass();  
   MyClass(int x);  
   static int x_public;  
   int mbr;  
private:  
   static int x_private;  
};  
  
int MyClass::x_public;  
int MyClass::x_private;  
  
namespace XyzNS {  
   struct xyz { int x; };  
   xyz xyz;  
}  
  
namespace NS {  
   int a1;  
   struct Bar {  
      static MyClass MyClass;  
   };  
   struct Baz : public Bar {  
      using NS::Bar::MyClass;  
   };  
}  
  
MyClass NS::Bar::MyClass;  
  
typedef int MyInt;  
  
template <class T, size_t n> class CTempl {  
public:  
   static T public_array[n];  
private:  
   static T private_array[n];  
};  
  
template<class T,size_t n> T CTempl<T,n>::public_array[n];  
template<class T,size_t n> T CTempl<T,n>::private_array[n];  
  
CTempl<int,5> tx;  
  
struct Incomplete;  
extern Incomplete inc;  
  
MyClass::MyClass(int x) {  
  
   #pragma omp parallel reduction(+: x, g_i, x_public, x_private)     
   // OK  
      ;  
  
   #pragma omp parallel reduction(+: x, g_i, MyClass::x_public,   
   MyClass::x_private)     
   // OK  
      ;  
  
   #pragma omp parallel reduction(+: mbr)     
   // C3028, member of a class.  
      ;  
}  
  
int main() {  
  
   #pragma omp parallel reduction(+:main)     
   // C3028, main is a function.  
      ;  
  
   #pragma omp parallel reduction(+: XyzNS)     
   // C3028, XyzNS is a namespace.  
      ;  
}  
```