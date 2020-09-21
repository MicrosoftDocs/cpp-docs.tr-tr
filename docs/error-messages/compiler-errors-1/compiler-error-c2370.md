---
title: Derleyici hatası C2370
ms.date: 11/04/2016
f1_keywords:
- C2370
helpviewer_keywords:
- C2370
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
ms.openlocfilehash: fe48dff881bb478a6d00fa3fe6f9446a68cbd787
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743483"
---
# <a name="compiler-error-c2370"></a>Derleyici hatası C2370

' tanımlayıcı ': yeniden tanımlama; farklı depolama sınıfı

Tanımlayıcı, farklı bir depolama sınıfıyla zaten tanımlanmış.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2370 oluşturur:

```cpp
// C2370.cpp
// compile with: /Za /c
extern int i;
static int i;   // C2370
int i;   // OK
```

Aşağıdaki örnek C2370 oluşturur:

```cpp
// C2370b.cpp
#define Thread __declspec( thread )
extern int tls_i;
int Thread tls_i;   // C2370 declaration and the definition differ
int tls_i;   // OK
```
