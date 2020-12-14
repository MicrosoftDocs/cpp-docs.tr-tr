---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2766'
title: Derleyici hatası C2766
ms.date: 11/04/2016
f1_keywords:
- C2766
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
ms.openlocfilehash: bace06c6dc4392fa023317d9711005837d156aa2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239499"
---
# <a name="compiler-error-c2766"></a>Derleyici hatası C2766

Açık özelleştirme; ' özelleşme ' zaten tanımlandı

Yinelenen açık uzmanlık işlemlerine izin verilmez. Daha fazla bilgi için bkz. [Işlev şablonlarının açık özelleştirmesi](../../cpp/explicit-specialization-of-function-templates.md).

Aşağıdaki örnek C2766 oluşturur:

```cpp
// C2766.cpp
// compile with: /c
template<class T>
struct A {};

template<>
struct A<int> {};

template<>
struct A<int> {};   // C2766
// try the following line instead
// struct A<char> {};
```
