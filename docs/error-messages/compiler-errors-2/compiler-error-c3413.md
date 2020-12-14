---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3413'
title: Derleyici hatası C3413
ms.date: 11/04/2016
f1_keywords:
- C3413
helpviewer_keywords:
- C3413
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
ms.openlocfilehash: 1b6f5ba895ce1db433fb8c8366e62ab3c0790f84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316251"
---
# <a name="compiler-error-c3413"></a>Derleyici hatası C3413

' name ': geçersiz açık örnek oluşturma

Derleyici hatalı oluşturulmuş bir açık örnek oluşturma algıladı.

Aşağıdaki örnek C3413 oluşturur:

```cpp
// C3413.cpp
template
class MyClass {};   // C3413
```

Olası çözüm:

```cpp
// C3413b.cpp
// compile with: /c
template <class T>
class MyClass {};

template <>
class MyClass<int> {};
```
