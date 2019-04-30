---
title: Derleyici Hatası C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: e684804ea31b16f31c82e244cb4f9a6aaf2d08c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386973"
---
# <a name="compiler-error-c2534"></a>Derleyici Hatası C2534

'identifier': Oluşturucu değer döndüremez

Oluşturucu bir değer döndürür veya bir dönüş türüne sahip (değil bile bir `void` dönüş türü).

Bu hata, kaldırarak düzeltilebilir `return` Oluşturucu tanımı from deyimi.

Aşağıdaki örnek, C2534 oluşturur:

```
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```