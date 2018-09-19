---
title: Derleyici Hatası C2397 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- C2397
dev_langs:
- C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3e76384ca2509663398fd7abd7badfd4057e8c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115105"
---
# <a name="compiler-error-c2397"></a>Derleyici Hatası C2397

'type_1' öğesinden 'type_2' öğesine dönüştürme bir daraltma dönüşümü gerektirir

Örtük bir daraltma dönüşümü Tekdüzen başlatma kullanırken bulunamadı.

C dili atama ve başlatma örtük daraltma dönüştürmelerini verir ve beklenmeyen daraltma bir birçok kod hatalarının nedenini olsa da C++ cins izler. Kodu daha güvenli hale getirmek için bir daraltma dönüşümü bir başlatma listesi oluştuğunda C++ standardı bir tanılama iletisi gerektirir. Visual C++'da tanılama derleyici hatası C2397 Tekdüzen başlatma desteklenen söz dizimleri başına Visual Studio 2015'te kullanıldığında. Derleyicinin oluşturduğu [Derleyici Uyarısı (düzey 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) kullanırken listesi veya Visual Studio 2013 tarafından desteklenen toplu başlatma söz dizimi.

Dönüştürülen değerler aralığı olası hedef sığabilen bildiğiniz bir daraltma dönüşümü uygun olabilir. Bu durumda, derleyici sağladığından daha fazla bilgi edinmek. Bir daraltma dönüşümü kasıtlı olarak yaparsanız, amacınızı açık bir statik dönüştürme kullanarak yapın. Aksi takdirde, bu hata iletisini neredeyse her zaman kodunuzda hata sahip gösterir. Bu nesneleri başlatır girişleri işleyebilecek büyüklükte türlere olmasını sağlayarak düzeltebilirsiniz.

Aşağıdaki örnek, C2397 oluşturur ve bunu çözmenin yollarından biri gösterilmektedir:

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