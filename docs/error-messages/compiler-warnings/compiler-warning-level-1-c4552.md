---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4552'
title: Derleyici Uyarısı (düzey 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 52cea1aac8b46fc5c1958bd917f6ab910ef326c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265928"
---
# <a name="compiler-warning-level-1-c4552"></a>Derleyici Uyarısı (düzey 1) C4552

' operator ': işlecin etkisi yok; yan etkisi olan işleç bekleniyordu

Bir ifade deyiminin ifadenin en üstünde yan etkisi olmayan bir işleci varsa, muhtemelen bir hata olabilir.

Bu uyarıyı geçersiz kılmak için, ifadeyi parantez içine alın.

Aşağıdaki örnek C4552 oluşturur:

```cpp
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```
