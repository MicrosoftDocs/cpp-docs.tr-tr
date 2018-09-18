---
title: Derleyici Hatası C2490 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2490
dev_langs:
- C++
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36e4a44a6a2288ce712c77538edbd710f22f5315
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071815"
---
# <a name="compiler-error-c2490"></a>Derleyici Hatası C2490

'anahtar sözcüğü 'naked' özniteliği olan işlevde izin verilmez'

Olarak tanımlanan bir işlev [naked](../../cpp/naked-cpp.md) yapılandırılmış özel durum işleme kullanamazsınız.

Aşağıdaki örnek, C2490 oluşturur:

```
// C2490.cpp
// processor: x86
__declspec( naked ) int func() {
   __try{}   // C2490, structured exception handling
}
```