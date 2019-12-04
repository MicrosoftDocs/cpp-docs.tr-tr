---
title: Derleyici hatası C2765
ms.date: 11/04/2016
f1_keywords:
- C2765
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
ms.openlocfilehash: 0c646d0ab28b97b546721180e46b0f22ea376f7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759834"
---
# <a name="compiler-error-c2765"></a>Derleyici hatası C2765

' function ': bir işlev şablonunun açık bir özelleştirmesi varsayılan bağımsız değişkenlere sahip olamaz

Bir işlev şablonunun açık bir özelleştirmesi üzerinde varsayılan bağımsız değişkenlere izin verilmez. Daha fazla bilgi için bkz. [Işlev şablonlarının açık özelleştirmesi](../../cpp/explicit-specialization-of-function-templates.md).

Aşağıdaki örnek C2765 oluşturur:

```cpp
// C2765.cpp
template<class T> void f(T t) {};

template<> void f<char>(char c = 'a') {}   // C2765
// try the following line instead
// template<> void f<char>(char c) {}
```
