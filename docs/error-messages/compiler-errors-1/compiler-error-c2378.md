---
title: Derleyici Hatası C2378
ms.date: 11/04/2016
f1_keywords:
- C2378
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
ms.openlocfilehash: fb6d228826cf1b21904863505c0963069e89d32d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436588"
---
# <a name="compiler-error-c2378"></a>Derleyici Hatası C2378

'identifier': yeniden tanımlama; simge bir typedef ile aşırı yüklenemez

Tanımlayıcı olarak tanımlandığından bir `typedef`.

Aşağıdaki örnek, C2378 oluşturur:

```
// C2378.cpp
// compile with: /c
int i;
typedef int i;   // C2378
typedef int b;   // OK
```