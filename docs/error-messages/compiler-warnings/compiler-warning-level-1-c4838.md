---
title: Derleyici Uyarısı (düzey 1) C4838
ms.date: 11/04/2016
f1_keywords:
- C4838
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
ms.openlocfilehash: dcb7062c751320a9f9c612b42caf6d018047d8d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532970"
---
# <a name="compiler-warning-level-1-c4838"></a>Derleyici Uyarısı (düzey 1) C4838

'type_1' öğesinden 'type_2' öğesine dönüştürme bir daraltma dönüşümü gerektirir

Örtük bir daraltma dönüşümü, toplama veya liste başlatma kullanırken bulunamadı.

C dili atama ve başlatma örtük daraltma dönüştürmelerini verir ve beklenmeyen daraltma bir birçok kod hatalarının nedenini olsa da C++ cins izler. Kodu daha güvenli hale getirmek için bir daraltma dönüşümü bir başlatma listesi oluştuğunda C++ standardı bir tanılama iletisi gerektirir. Visual C++'da tanılama olan [derleyici hatası C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) itibaren Visual Studio 2015'te desteklenen tek düzen başlatma sözdizimi kullanılırken. Derleyici, liste veya Visual Studio 2013 tarafından desteklenen toplu başlatma söz dizimi kullanırken C4838 uyarı oluşturur.

Dönüştürülen değerler aralığı olası hedef sığabilen bildiğiniz bir daraltma dönüşümü uygun olabilir. Bu durumda, derleyici sağladığından daha fazla bilgi edinmek. Bir daraltma dönüşümü kasıtlı olarak yaparsanız, amacınızı açık bir statik dönüştürme kullanarak yapın. Aksi takdirde, bu uyarı iletisi neredeyse her zaman kodunuza, bir hata olduğunu gösterir. Bu nesneleri başlatır girişleri işleyebilecek büyüklükte türlere olmasını sağlayarak düzeltebilirsiniz.

Aşağıdaki örnek, C4838 oluşturur ve bunu çözmenin yollarından biri gösterilmektedir:

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