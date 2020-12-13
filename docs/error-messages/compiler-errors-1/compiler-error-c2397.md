---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2397'
title: Derleyici hatası C2397
ms.date: 11/04/2016
f1_keywords:
- C2397
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
ms.openlocfilehash: 8e5f000b8d0881fd6a57bb4895afbdef0e7c598a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145385"
---
# <a name="compiler-error-c2397"></a>Derleyici hatası C2397

' type_1 ' değerinden ' type_2 ' öğesine dönüştürme bir daraltma dönüştürmesi gerektirir

Tekdüzen başlatma kullanılırken örtük bir daraltma dönüştürmesi bulundu.

C dili, atamalar ve başlatmada örtük daraltma dönüştürmelerine izin verir ve C++, beklenmeyen daraltma pek çok kod hatasının nedeni olmasına rağmen, C++ ' ı izler. Kodu daha güvenli hale getirmek için, bir başlatma listesinde daraltma dönüştürmesi gerçekleştiğinde C++ standardı bir tanılama iletisi gerektirir. Visual C++, tanılama, Visual Studio 2015 ' de başlayarak desteklenen Tekdüzen başlatma sözdizimi kullanılırken derleyici hatası C2397. Derleyici, Visual Studio 2013 tarafından desteklenen liste veya toplama başlatma sözdizimini kullanırken [Derleyici Uyarısı (düzey 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) oluşturur.

Bir daraltma dönüştürmesi, olası dönüştürülen değer aralığının hedefe uyabileceklerini bildiğiniz durumlarda uygulanabilir. Bu durumda, derleyicisinden daha fazlasını öğrenmiş olursunuz. Özellikle bir daraltma dönüştürmesi yaparsanız, bir statik atama kullanarak amaclarınızı açık hale getirin. Aksi takdirde, bu hata iletisi neredeyse her zaman kodunuzda bir hata olduğunu gösterir. Başlattığınız nesnelerin girdileri işlemek için yeterince büyük türlere sahip olduğundan emin olarak bu çözümü çözebilirsiniz.

Aşağıdaki örnek C2397 oluşturur ve bunu çözmek için bir yol gösterir:

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
