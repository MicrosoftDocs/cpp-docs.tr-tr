---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2835'
title: Derleyici hatası C2835
ms.date: 11/04/2016
f1_keywords:
- C2835
helpviewer_keywords:
- C2835
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
ms.openlocfilehash: f5fa04e6c34ce4bcad99022bd1a5e0f20bba41be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194429"
---
# <a name="compiler-error-c2835"></a>Derleyici hatası C2835

Kullanıcı tanımlı ' Type ' dönüştürmesi hiçbir biçimsel parametre alır

Kullanıcı tanımlı tür dönüştürmeleri resmi parametre alamaz.

Aşağıdaki örnek C2835 oluşturur:

```cpp
// C2835.cpp
class A {
public:
   char v_char;

   A() {
      v_char = 'A';
   };
   operator char(char a) {   // C2835
   // try the following line instead
   // operator char() {
      return v_char + 1;
   };
};

int main() {
   A a;
}
```
