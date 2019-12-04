---
title: Derleyici hatası C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: c1467a3c67cccf28cc6b9bd0f987fe77b8da8988
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757884"
---
# <a name="compiler-error-c2833"></a>Derleyici hatası C2833

' işleç işleci ' tanınan bir işleç veya tür değil

`operator` kelimesinin ardından, geçersiz kılmak istediğiniz bir operatör veya dönüştürmek istediğiniz bir tür gelmelidir.

Yönetilen bir türde tanımlayabileceğiniz işleçlerin bir listesi için, bkz. [Kullanıcı tanımlı işleçler](../../dotnet/user-defined-operators-cpp-cli.md).

Aşağıdaki örnek C2833 oluşturur:

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
