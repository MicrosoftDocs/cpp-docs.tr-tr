---
title: Derleyici Hatası C3487
ms.date: 11/04/2016
f1_keywords:
- C3487
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
ms.openlocfilehash: 7b38755470e3746066711382b2ed471badc8e197
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738446"
---
# <a name="compiler-error-c3487"></a>Derleyici Hatası C3487

' Return Type ': tüm dönüş ifadeleri aynı tür olarak çözümlenmelidir: daha önce ' Return Type ' idi

Bir lambda, tek bir dönüş ekstresi içermiyorsa, dönüş türünü belirtmelidir. Lambda birden çok return deyimi içeriyorsa, bunların hepsi aynı türde olmalıdır.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Lambda için bir bitiş dönüş türü belirtin. Lambdanın tüm dönüşlerden aynı türde olduğunu veya dönüş türüne örtük olarak dönüştürülebilir olduğunu doğrulayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, lambda dönüş türleri eşleşmediğinden C3487 oluşturur:

```cpp
// C3487.cpp
// Compile by using: cl /c /W4 C3487.cpp

int* test(int* pi) {
   // To fix the error, uncomment the trailing return type below
   auto odd_pointer = [=]() /* -> int* */ {
      if (*pi % 2)
         return pi;
      return nullptr; // C3487 - nullptr is not an int* type
   };
   return odd_pointer();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
