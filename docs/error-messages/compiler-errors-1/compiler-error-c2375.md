---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2375'
title: Derleyici hatası C2375
ms.date: 11/04/2016
f1_keywords:
- C2375
helpviewer_keywords:
- C2375
ms.assetid: 193c5e8b-1b20-4928-8a02-8c1cddaf2a26
ms.openlocfilehash: 187188caa851191c44280e24d9321ea3cb24f9f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174773"
---
# <a name="compiler-error-c2375"></a>Derleyici hatası C2375

' function ': yeniden tanımlama; farklı bağlantı

İşlev, farklı bir bağlantı belirticisiyle zaten tanımlanmış.

Aşağıdaki örnek C2375 oluşturur:

```cpp
// C2375.cpp
// compile with: /Za /c
extern void func( void );
static void func( void );   // C2375
static void func2( void );   // OK
```
