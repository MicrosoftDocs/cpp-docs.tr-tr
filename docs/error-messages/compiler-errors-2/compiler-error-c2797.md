---
title: "Derleyici Hatası C2797 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2797
dev_langs:
- C++
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c8fd31905eb92db8ad2e3af941772584f6f64ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2797"></a>Derleyici Hatası C2797
(Obsolete) Üye başlatıcı listesi veya statik olmayan veri üye başlatıcıdan içinde listesi başlatma uygulanmadı.  
  
 Bu uyarı, Visual Studio 2015'te kullanımdan kalkmıştır. Visual Studio 2013 ve önceki sürümleri, Visual C++ derleyicisi listesi başlatma üye başlatıcı listesi veya bir statik olmayan veri üye başlatıcıdan içinde uygulamıyor. Visual Studio 2013 güncelleştirme 3 önce bu sessiz hatalı kod oluşturma için yol açabilecek bir işlev çağrısı için dönüştürüldü. Visual Studio 2013 güncelleştirme 3'ü bu hata olarak bildirir.  
  
 Bu örnek C2797 oluşturur:  
  
```  
#include <vector>  
struct S {  
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'  
  
    std::vector<int> v1;  
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'  
};  
  
```  
  
 Bu örnek ayrıca C2797 oluşturur:  
  
```  
struct S1 {  
    int i;  
};  
  
struct S2 {  
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664  
    S1 s1;  
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664  
};  
  
```  
  
 Bu sorunu gidermek için açık yapımı iç listeleri kullanabilirsiniz. Örneğin:  
  
```  
#include <vector>  
typedef std::vector<int> Vector;  
struct S {  
    S() : v1(Vector{1}) {}  
  
    Vector v1;  
    Vector v2 = Vector{1, 2};  
};  
  
```  
  
 Liste başlatma gerektirmiyorsa:  
  
```  
struct S {  
    S() : s1("") {}  
  
    std::string s1;  
    std::string s2 = std::string("");  
};  
  
```  
  
 (Visual Studio 2013'te derleyici bu örtülü olarak önce Visual Studio 2013 güncelleştirme 3 desteklemez.)