---
title: Derleyici Hatası C2688
ms.date: 11/04/2016
f1_keywords:
- C2688
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
ms.openlocfilehash: 5355abc603726eb1bacb7a22fa1095bf2d81c538
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266289"
---
# <a name="compiler-error-c2688"></a>Derleyici Hatası C2688

'C2::fgrv': birden çok içeren kovaryant dönüşler veya sanal devralma VARARG işlevleri için desteklenmiyor

Bir işlevin değişken bağımsız değişkenler içeriyorsa, birlikte değişken dönüş türleri Visual C++'da desteklenmez.

Bu hatayı gidermek için böylece bunlar görüntülenmez değişken bağımsız değişkenler kullanın veya dönüş değerlerini tüm sanal işlevler için aynı olun işlevlerinizi tanımlayın.

Aşağıdaki örnek, C2688 oluşturur:

```
// C2688.cpp
struct G1 {};
struct G2 {};
struct G3 : G1, G2 {};
struct G4 {};
struct G5 {};
struct G6 : G4, G5 {};
struct G7 : G3, G6 {};

struct C1 {
   virtual G4& fgrv(int,...);
};

struct C2 : C1 {
   virtual G7& fgrv(int,...);   // C2688, does not return G4&
};
```