---
title: Derleyici Hatası C2427
ms.date: 11/04/2016
f1_keywords:
- C2427
helpviewer_keywords:
- C2427
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
ms.openlocfilehash: b794b90a476f7712c80e7617ec3c0696afb290ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402833"
---
# <a name="compiler-error-c2427"></a>Derleyici Hatası C2427

'class': Bu kapsamda sınıf tanımlanamaz

İç içe geçmiş bir sınıf tanımlamak için bir girişimde bulunuldu, ancak iç içe geçmiş sınıf bir taban sınıfın en içeren sınıfın bir üyesidir.

Aşağıdaki örnek, C2427 oluşturur:

```
// C2427.cpp
// compile with: /c
template <class T>
struct S {
   struct Inner;
};

struct Y : S<int> {};

struct Y::Inner {};   // C2427

// OK
template<typename T>
struct S<T>::Inner {};
```