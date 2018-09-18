---
title: Derleyici Hatası C2378 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2378
dev_langs:
- C++
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5aa4b8ecef6be2149132c9ccf533285cd0bb7f7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021830"
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