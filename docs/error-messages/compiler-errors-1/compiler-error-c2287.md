---
title: Derleyici hatası C2287
ms.date: 11/04/2016
f1_keywords:
- C2287
helpviewer_keywords:
- C2287
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
ms.openlocfilehash: 234d0e85d0d6772340797fb6880e0ef79d4191ef
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759145"
---
# <a name="compiler-error-c2287"></a>Derleyici hatası C2287

' class ': devralma temsili: ' representation1 ', gerekli olan ' representation2 ' öğesinden daha az genel

Bir sınıf gerekenden daha basit bir gösterimle bildirilmiştir.

Aşağıdaki örnek C2287 oluşturur:

```cpp
// C2287.cpp
// compile with: /vmg /c
class __single_inheritance X;
class __single_inheritance Y;

struct A { };
struct B { };
struct X : A, B { };  // C2287  X uses multiple inheritance
struct Y : A { };  // OK
```
