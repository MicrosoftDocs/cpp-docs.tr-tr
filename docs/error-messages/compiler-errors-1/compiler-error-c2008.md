---
title: Derleyici hatası C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 292f5c6ab9a4e14077f848ff57ff08adefeb09a1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757338"
---
# <a name="compiler-error-c2008"></a>Derleyici hatası C2008

' karakter ': makro tanımında beklenmiyor

Karakter, makro adının hemen sonrasında görünür. Hatayı gidermek için makro adından sonra bir boşluk olması gerekir.

Aşağıdaki örnek C2008 oluşturur:

```cpp
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

Olası çözüm:

```cpp
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```
