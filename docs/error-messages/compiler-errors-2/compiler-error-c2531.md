---
title: Derleyici Hatası C2531 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2531
dev_langs:
- C++
helpviewer_keywords:
- C2531
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05af2bd4f1dc3403f5ecbb3254564292698624aa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045100"
---
# <a name="compiler-error-c2531"></a>Derleyici Hatası C2531

'identifier': bir bit alanı geçersiz başvuru

Bit alanları başvuruları izin verilmez.

Aşağıdaki örnek, C2531 oluşturur:

```
// C2531.cpp
// compile with: /c
class P {
   int &b1 : 10;   // C2531
   int b2 : 10;   // OK
};
```