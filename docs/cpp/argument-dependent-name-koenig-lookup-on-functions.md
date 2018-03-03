---
title: "İşlevlerde bağımsız değişkene bağlı ad (Koenig) arama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a468d5eef9a400bfa5e12c90ca62e05ea2f160d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="argument-dependent-name-koenig-lookup-on-functions"></a>İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama
Derleyici bağımsız değişkene bağlı ad araması bir nitelenmemiş işlev çağrısı tanımını bulmak için kullanabilirsiniz. Bağımsız değişkene bağlı ad arama Koenig araması olarak da adlandırılır. Her bağımsız değişkeni olarak bir işlev çağrısı türü, ad alanları, sınıflar, yapılar, birleşimler veya şablonları hiyerarşisi içinde tanımlanır. Bir nitelenmemiş belirttiğinizde [sonek](../cpp/postfix-expressions.md) işlev çağrısı derleyici her bağımsız değişken türü ile ilişkilendirilmiş hiyerarşi işlevi tanımında arar.  
  
## <a name="example"></a>Örnek  
 Örnekte, bu işlev derleyici Notlar `f()` bir bağımsız değişken `x`. Bağımsız değişken `x` türü `A::X`, ad alanında tanımlı `A`. Derleyici arama ad alanı `A` ve işlevi için bir tanım bulur `f()` türünde bir bağımsız değişken alan `A::X`.  
  
```  
// argument_dependent_name_koenig_lookup_on_functions.cpp  
namespace A  
{  
   struct X  
   {  
   };  
   void f(const X&)  
   {  
   }  
}  
int main()  
{  
// The compiler finds A::f() in namespace A, which is where   
// the type of argument x is defined. The type of x is A::X.  
   A::X x;  
   f(x);     
}  
```  
