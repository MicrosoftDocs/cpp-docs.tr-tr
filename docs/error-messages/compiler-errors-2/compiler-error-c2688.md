---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2688'
title: Derleyici hatası C2688
ms.date: 11/04/2016
f1_keywords:
- C2688
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
ms.openlocfilehash: 17219fe6f4358b73ace0435e60d8fc2b7a9b6df8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330682"
---
# <a name="compiler-error-c2688"></a>Derleyici hatası C2688

' C2:: fgrv ': birden fazla veya sanal devralmayla birlikte değişken dönüşler vararg işlevleri için desteklenmez

Bir işlev değişken bağımsız değişkenler içerdiğinde Visual C++ birlikte değişken dönüş türleri desteklenmez.

Bu hatayı çözmek için işlevlerinizi, değişken bağımsız değişkenleri kullanmadan veya dönüş değerlerini tüm sanal işlevler için aynı olacak şekilde tanımlayın.

Aşağıdaki örnek C2688 oluşturur:

```cpp
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
