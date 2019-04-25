---
title: Derleyici Hatası C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: 296224532b19d9ff85c8644aa653b6d842205213
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265886"
---
# <a name="compiler-error-c2892"></a>Derleyici Hatası C2892

Yerel sınıfın üye şablonları olamaz

Şablonlu üye işlevleri, bir işlev içinde tanımlanmış bir sınıf içinde geçerli değildir.

Aşağıdaki örnek, C2892 oluşturur:

```
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```