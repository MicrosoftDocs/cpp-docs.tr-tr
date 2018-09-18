---
title: Derleyici Hatası C2375 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2375
dev_langs:
- C++
helpviewer_keywords:
- C2375
ms.assetid: 193c5e8b-1b20-4928-8a02-8c1cddaf2a26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ceb045c4001d6d2ab0cd5d1968abf453a85fab9d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047778"
---
# <a name="compiler-error-c2375"></a>Derleyici Hatası C2375

'function': yeniden tanımlama; bağlantı farklı

İşlev zaten farklı bir bağlantı tanımlayıcısı ile bildirilir.

Aşağıdaki örnek, C2375 oluşturur:

```
// C2375.cpp
// compile with: /Za /c
extern void func( void );
static void func( void );   // C2375
static void func2( void );   // OK
```