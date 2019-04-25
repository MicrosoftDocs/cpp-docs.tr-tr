---
title: Derleyici Uyarısı (düzey 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: b374b67fa3319be35490358d7664bcb45bc640db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207036"
---
# <a name="compiler-warning-level-1-c4369"></a>Derleyici Uyarısı (düzey 1) C4369

'Numaralandırıcı': Numaralandırıcı değeri 'value', 'type' gösterilemez; değer 'yeni_değer'

Belirtilen temel alınan türü için en büyük değerden daha büyük olması için bir numaralandırıcı hesaplanır.  Bu taşmaya neden oldu ve derleyici Numaralandırıcı değer türü için olası en düşük değer olarak sarmalandı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4369 oluşturur.

```
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```