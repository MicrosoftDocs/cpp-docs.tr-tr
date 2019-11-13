---
title: Derleyici Uyarısı (düzey 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: 617cb2cc3774b288581a3868125ced19b28ba45a
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966506"
---
# <a name="compiler-warning-level-1-c4369"></a>Derleyici Uyarısı (düzey 1) C4369

' Numaralandırıcı ': ' Value ' Numaralandırıcı değeri ' Type ' olarak gösterilemez; değer ' new_value '

Numaralandırıcı, belirtilen temeldeki tür için en büyük değerden daha büyük olacak şekilde hesaplanmıştır.  Bu bir taşmaya neden oldu ve derleyicinin Numaralandırıcı değerini tür için olası en düşük değere sarmalanmış.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4369 oluşturur.

```cpp
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```