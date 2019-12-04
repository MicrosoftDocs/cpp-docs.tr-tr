---
title: Derleyici hatası C2688
ms.date: 11/04/2016
f1_keywords:
- C2688
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
ms.openlocfilehash: cc871467e1e3fb23edc6231c3adb182f5e26c0d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760250"
---
# <a name="compiler-error-c2688"></a>Derleyici hatası C2688

' C2:: fgrv ': birden fazla veya sanal devralmayla birlikte değişken dönüşler vararg işlevleri için desteklenmez

Bir işlev değişken bağımsız değişkenler içerdiğinde, birlikte değişken C++ dönüş türleri görselde desteklenmez.

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
