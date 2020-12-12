---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2892'
title: Derleyici hatası C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: bcc1a43298973e270c39656b965b76cd75f3472e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278356"
---
# <a name="compiler-error-c2892"></a>Derleyici hatası C2892

Yerel sınıfın üye şablonları olamaz

Şablonlu üye işlevleri, bir işlevde tanımlı bir sınıfta geçerli değildir.

Aşağıdaki örnek C2892 oluşturur:

```cpp
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```
