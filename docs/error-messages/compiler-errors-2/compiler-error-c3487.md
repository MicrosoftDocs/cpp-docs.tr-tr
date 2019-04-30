---
title: Derleyici Hatası C3487
ms.date: 11/04/2016
f1_keywords:
- C3487
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
ms.openlocfilehash: 01f8a1bd74ed2b7a3150afae5b46128c6f5b0ca2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381156"
---
# <a name="compiler-error-c3487"></a>Derleyici Hatası C3487

'dönüş türü': tüm dönüş ifadeleri aynı tür olarak çözümlenmelidir: daha önce 'dönüş türü' şeklindeydi

Tek bir dönüş deyimi içermiyorsa, bir lambda dönüş türü belirtmelisiniz. Bir lambda, birden fazla dönüş deyimleri içeriyorsa, tüm aynı türde olmalıdır.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Bir lambda sondaki dönüş türü belirtin. Lambda tüm döndürür aynı türü veya dönüş türüne örtük olarak dönüştürülebilir doğrulayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, lambda dönüş türleri eşleşmediğinden C3487 oluşturur:

```
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