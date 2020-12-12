---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2833'
title: Derleyici hatası C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: 3c1bd2cc60478dc5868c74d4bfeac1d7d3a4d9a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194494"
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
