---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4369'
title: Derleyici Uyarısı (düzey 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: 97f7882438124e8788559ec1453bd84d3ec371d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339975"
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
