---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2279'
title: Derleyici hatası C2279
ms.date: 11/04/2016
f1_keywords:
- C2279
helpviewer_keywords:
- C2279
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
ms.openlocfilehash: e0f8822c77bd243bc2ec6002027d8eadb2aaf8a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228982"
---
# <a name="compiler-error-c2279"></a>Derleyici hatası C2279

özel durum belirtimi bir typedef bildiriminde yer alamaz

**/Za** kapsamında, bir typedef bildiriminde [özel durum belirtimlerine](../../cpp/exception-specifications-throw-cpp.md) izin verilmez.

Aşağıdaki örnek C2279 oluşturur:

```cpp
// C2279.cpp
// compile with: /Za /c
typedef int (*xy)() throw(...);   // C2279
typedef int (*xyz)();   // OK
```
