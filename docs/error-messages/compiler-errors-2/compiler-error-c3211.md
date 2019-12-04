---
title: Derleyici hatası C3211
ms.date: 11/04/2016
f1_keywords:
- C3211
helpviewer_keywords:
- C3211
ms.assetid: 85e33fed-3b59-4315-97e6-20d31c6a985a
ms.openlocfilehash: 7eaad3088eafb55a310a1c95306d6c265c777021
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740513"
---
# <a name="compiler-error-c3211"></a>Derleyici hatası C3211

' Explicit özelleşme ': açık özelleştirme kısmı özelleştirme sözdizimi kullanıyor; bunun yerine şablon < > kullanın

Açık bir özelleştirme hatalı biçimlendirilmiş.

Aşağıdaki örnek C3211 oluşturur:

```cpp
// C3211.cpp
// compile with: /LD
template<class T>
struct s;

template<class T>
// use the following line instead
// template<>
struct s<int>{};   // C3211
```
