---
title: Derleyici Uyarısı (düzey 1) C4838
ms.date: 11/04/2016
f1_keywords:
- C4838
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
ms.openlocfilehash: c3ddc861e5da271903372eac1ef1e8f6916e06df
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199374"
---
# <a name="compiler-warning-level-1-c4838"></a>Derleyici Uyarısı (düzey 1) C4838

' type_1 ' değerinden ' type_2 ' öğesine dönüştürme bir daraltma dönüştürmesi gerektirir

Toplama veya liste başlatma kullanılırken örtük bir daraltma dönüştürmesi bulundu.

C dili, atamalar ve başlatma içindeki örtük daraltma dönüştürmelerine izin verir C++ ve beklenmeyen daraltma birçok kod hatasının nedeni olsa da bu şekilde ayarlanır. Kodu daha güvenli hale getirmek için C++ , bir başlatma listesinde daraltma dönüştürmesi gerçekleştiğinde standart bir tanılama iletisi gerektirir. Visual Studio C++2015 ' de başlangıçta desteklenen Tekdüzen başlatma sözdizimi kullanılırken, Visual Studio 'Da tanılama [derleyici hatası C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) . Derleyici, Visual Studio 2013 tarafından desteklenen liste veya toplama başlatma sözdizimini kullanırken uyarı C4838 oluşturur.

Bir daraltma dönüştürmesi, olası dönüştürülen değer aralığının hedefe uyabileceklerini bildiğiniz durumlarda uygulanabilir. Bu durumda, derleyicisinden daha fazlasını öğrenmiş olursunuz. Özellikle bir daraltma dönüştürmesi yaparsanız, bir statik atama kullanarak amaclarınızı açık hale getirin. Aksi takdirde, bu uyarı iletisi neredeyse her zaman kodunuzda bir hata olduğunu gösterir. Başlattığınız nesnelerin girdileri işlemek için yeterince büyük türlere sahip olduğundan emin olarak bu çözümü çözebilirsiniz.

Aşağıdaki örnek C4838 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
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
