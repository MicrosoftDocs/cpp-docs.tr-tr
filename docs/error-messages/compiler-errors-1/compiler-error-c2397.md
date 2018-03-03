---
title: "Derleyici Hatası C2397 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2397
dev_langs:
- C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 315d375524884ec987fea747b1d3c20f2ad56173
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2397"></a>Derleyici Hatası C2397
daraltma dönüşümü 'type_2'-'type_1' dönüşümü gerektirir  
  
 Örtük bir daraltma dönüştürme tek düzen başlatma kullanırken bulundu.  
  
 C dili atamaları ve başlatma örtük daraltma dönüşümleri sağlar ve beklenmeyen daraltma birçok kod hataları nedenini olsa bile seri, C++ izler. Kod daha güvenli hale getirmek için bir başlatma listesinde daraltma dönüşümü meydana geldiğinde standart C++ bir tanılama iletisi gerektirir. Visual C++'da, tanılama derleyici hatası C2397 tek düzen başlatma desteklenen sözdizimi başına Visual Studio 2015'te kullanıldığında. Derleyici oluşturur [Derleyici Uyarısı (düzey 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) listesi veya Visual Studio 2013 tarafından desteklenen toplu başlatma sözdizimi kullanıldığında.  
  
 Dönüştürülen değerleri olası aralığı hedef sığabilecek bildiğinizde daraltma dönüşümü uygun olabilir. Bu durumda, derleyici mu birden fazla bilmeniz. Daraltma dönüşümü bilerek yaparsanız, amaçları açık bir statik atama kullanarak yapın. Aksi takdirde, bu hata iletisini neredeyse her zaman bir hata kodunuzda sahip gösterir. Başlatır nesneleri girişleri işleyebilecek büyüklükte türleri olmasını sağlayarak düzeltebilirsiniz.  
  
 Aşağıdaki örnek C2397 oluşturur ve bu düzeltmenin bir yolu gösterir:  
  
```  
// C2397.cpp -- C++ narrowing conversion diagnostics  
// Compile by using: cl /EHsc C2397.cpp  
#include <vector>   
  
struct S1 {  
    int m1;  
    double m2, m3;  
};  
  
void function_C2397(double d1) {  
    char c1 { 127 };          // OK  
    char c2 { 513 };          // error C2397  
  
    std::vector<S1> vS1;  
    vS1.push_back({ d1, 2, 3 }); // error C2397  
  
    // Possible fix if you know d1 always fits in an int  
    vS1.push_back({ static_cast<int>(d1), 2, 3 });   
}  
```