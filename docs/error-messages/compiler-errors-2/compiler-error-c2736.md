---
title: Derleyici hatası C2736
ms.date: 11/04/2016
f1_keywords:
- C2736
helpviewer_keywords:
- C2736
ms.assetid: 95a6bc28-c0cb-49dc-87e6-e993dbbba881
ms.openlocfilehash: 6a7781ebcd7cefdbcff13599912c06062f20501e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759691"
---
# <a name="compiler-error-c2736"></a>Derleyici hatası C2736

cast 'da ' anahtar sözcük ' anahtar sözcüğüne izin verilmez

Anahtar sözcüğü bir dönüştürmede geçersizdir.

Aşağıdaki örnek C2736 oluşturur:

```cpp
// C2736.cpp
int main() {
   return (virtual) 0;   // C2736
   // try the following line instead
   // return 0;
}
```
