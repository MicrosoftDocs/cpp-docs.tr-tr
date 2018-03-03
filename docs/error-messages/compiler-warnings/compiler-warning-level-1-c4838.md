---
title: "Derleyici Uyarısı (düzey 1) C4838 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4838
dev_langs:
- C++
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76002ebf0a6ac6e610b1fcd10d02fab49287495b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4838"></a>Derleyici Uyarısı (düzey 1) C4838
daraltma dönüşümü 'type_2'-'type_1' dönüşümü gerektirir  
  
 Örtük bir daraltma dönüştürme toplama veya liste başlatma kullanırken bulundu.  
  
 C dili atamaları ve başlatma örtük daraltma dönüşümleri sağlar ve beklenmeyen daraltma birçok kod hataları nedenini olsa bile seri, C++ izler. Kod daha güvenli hale getirmek için bir başlatma listesinde daraltma dönüşümü meydana geldiğinde standart C++ bir tanılama iletisi gerektirir. Visual C++'da, tanılama olan [derleyici hatası C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) Visual Studio 2015'te başlayan desteklenen tek düzen başlatma sözdizimi kullanılırken. Derleyici, liste veya Visual Studio 2013 tarafından desteklenen toplu başlatma sözdizimi kullanılırken C4838 uyarı oluşturur.  
  
 Dönüştürülen değerleri olası aralığı hedef sığabilecek bildiğinizde daraltma dönüşümü uygun olabilir. Bu durumda, derleyici mu birden fazla bilmeniz. Daraltma dönüşümü bilerek yaparsanız, amaçları açık bir statik atama kullanarak yapın. Aksi takdirde, bu uyarı iletisi neredeyse her zaman kodunuzda bir hata olduğunu gösterir. Başlatır nesneleri girişleri işleyebilecek büyüklükte türleri olmasını sağlayarak düzeltebilirsiniz.  
  
 Aşağıdaki örnek C4838 oluşturur ve bu düzeltmenin bir yolu gösterir:  
  
```  
// C4838.cpp -- C++ narrowing conversion diagnostics  
// Compile by using: cl /EHsc C4838.cpp  
  
struct S1 {  
    int m1;  
    double m2, m3;  
};  
  
void function_C4838(double d1) {  
    double ad[] = { 1, d1 }; // OK  
    int ai[] = { 1, d1 };    // warning C4838  
    S1 s11 = { 1, 2, d1 };   // OK  
    S1 s12 { d1, 2, 3 };     // warning C4838  
    S1 s13 { static_cast<int>(d1), 2, 3 }; // possible fix for C4838  
}  
```