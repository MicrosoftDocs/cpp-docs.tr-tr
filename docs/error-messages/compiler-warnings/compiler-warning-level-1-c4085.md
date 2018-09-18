---
title: Derleyici Uyarısı (düzey 1) C4085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4085
dev_langs:
- C++
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff99599ad2c5d43fa8539a6525ba2fb4b4cdfa31
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046777"
---
# <a name="compiler-warning-level-1-c4085"></a>Derleyici Uyarısı (düzey 1) C4085

Beklenen pragma parametresinin 'on' veya 'off' olması

Pragma gerektiren bir **üzerinde** veya **kapalı** parametresi. Pragma yoksayıldı.

Aşağıdaki örnek, C4085 oluşturur:

```
// C4085.cpp
// compile with: /W1 /LD
#pragma optimize( "t", maybe )  // C4085
```