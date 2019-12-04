---
title: Derleyici hatası C2010
ms.date: 11/04/2016
f1_keywords:
- C2010
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
ms.openlocfilehash: 7341c77ecf2863431fa3e5c0a454077c89601b6b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752437"
---
# <a name="compiler-error-c2010"></a>Derleyici hatası C2010

' character ': makro biçimsel parametre listesinde beklenmiyor

Bir makro tanımının biçimsel parametre listesinde karakter yanlış kullanılıyor. Hatayı çözmek için karakteri kaldırın.

Aşağıdaki örnek C2010 oluşturur:

```cpp
// C2010.cpp
// compile with: /c
#define mymacro(a|) (2*a)   // C2010
#define mymacro(a) (2*a)   // OK
```
