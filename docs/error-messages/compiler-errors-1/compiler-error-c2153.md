---
title: Derleyici hatası C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: 1f03b196b7ddaae80dac1941cdde5be16acace5f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748690"
---
# <a name="compiler-error-c2153"></a>Derleyici hatası C2153

onaltılık sabitlerin en az bir onaltılı basamak olmalıdır

0x, 0X ve \x on altılı sabitleri geçerli değil. En az bir onaltılık basamak x veya X izlemelidir.

Aşağıdaki örnek C2153 oluşturur:

```cpp
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```
