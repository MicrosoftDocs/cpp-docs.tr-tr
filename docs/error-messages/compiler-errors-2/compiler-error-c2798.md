---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2798'
title: Derleyici hatası C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: d3a78eaf09797d658c64b5659dcd0e05191fab1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297596"
---
# <a name="compiler-error-c2798"></a>Derleyici hatası C2798

' Super:: Member ' belirsiz

Birden çok devralınmış yapı, [süper](../../cpp/super.md)ile başvurduğunuz üyeyi içerir. Hatayı aşağıdakilerden birini yaparak giderebilirsiniz:

- D devralma listesinden B1 veya B2 kaldırılıyor.

- B1 veya B2 içindeki veri üyesinin adını değiştirme.

Aşağıdaki örnek C2798 oluşturur:

```cpp
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```
