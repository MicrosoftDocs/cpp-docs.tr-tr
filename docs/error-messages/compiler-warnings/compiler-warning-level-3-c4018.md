---
title: Derleyici Uyarısı (düzey 3) C4018
description: Microsoft C/C++ derleyicisi uyarı C4018, nedenleri ve çözümlemesi.
ms.date: 10/16/2020
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.openlocfilehash: b9d01f6b733c2ca18880aa6f4b6fca9771f8123f
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176173"
---
# <a name="compiler-warning-level-3-c4018"></a>Derleyici Uyarısı (düzey 3) C4018

> '*belirteç*': imzalı/imzasız uyuşmazlığı

Karşılaştırma ve sayı için *belirteç* işleci **`signed`** kullanarak **`unsigned`** değeri dönüştürmek için derleyici gerekir **`signed`** **`unsigned`** .

## <a name="remarks"></a>Açıklamalar

Bu uyarıyı gidermenin bir yolu, ve türlerini karşılaştırdığınızda iki türden birini saçmanız durumunda olur **`signed`** **`unsigned`** .

## <a name="example"></a>Örnek

Bu örnek C4018 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4018.cpp
// compile with: cl /EHsc /W4 C4018.cpp
int main() {
    unsigned int uc = 0;
    int c = 0;
    unsigned int c2 = c; // implicit conversion

    if (uc < c)           // C4018
        uc = 0;

    if (uc < unsigned(c)) // OK
        uc = 0;

    if (uc < c2)          // Also OK
       uc = 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Uyarısı (düzey 4) C4388](c4388.md)\
[Derleyici Uyarısı (düzey 4) C4389](compiler-warning-level-4-c4389.md)
