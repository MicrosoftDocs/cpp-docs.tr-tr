---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2765'
title: Derleyici hatası C2765
ms.date: 11/04/2016
f1_keywords:
- C2765
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
ms.openlocfilehash: 496f28645dddc0ac426716cc80ee0d6760042ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239551"
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
