---
title: Derleyici Hatası C3487 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3487
dev_langs:
- C++
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acd0dad31a565b9e75741e3a66a5d48dfedec69f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087116"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)