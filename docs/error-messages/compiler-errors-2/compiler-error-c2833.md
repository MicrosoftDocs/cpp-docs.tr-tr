---
title: Derleyici hatası C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: a6ffcb13d04f3c7c5ac62e147a2b6b2b305e11e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218175"
---
# <a name="compiler-error-c2833"></a>Derleyici hatası C2833

> ' işleç *işleci-adı*' tanınan bir işleç veya tür değil

Sözcüğe, **`operator`** geçersiz kılmak istediğiniz bir *operatör adı* veya dönüştürmek istediğiniz bir tür gelmelidir.

Yönetilen bir türde tanımlayabileceğiniz işleçlerin bir listesi için, bkz. [Kullanıcı tanımlı işleçler](../../dotnet/user-defined-operators-cpp-cli.md).

Aşağıdaki örnek C2833 oluşturur:

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
