---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2370'
title: Derleyici hatası C2370
ms.date: 11/04/2016
f1_keywords:
- C2370
helpviewer_keywords:
- C2370
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
ms.openlocfilehash: 75fcb952dadcb14d0edeb3e18b9cad1c6af535f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326077"
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
