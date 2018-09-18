---
title: Derleyici Hatası C3199 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3199
dev_langs:
- C++
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed917b3711f7f757b0a4ad89f0e6594ea1642a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027290"
---
# <a name="compiler-error-c3199"></a>Derleyici Hatası C3199

kayan noktalı pragmaların geçersiz kullanımı: özel durumlar hassas olmayan modda desteklenmez

[Float_control](../../preprocessor/float-control.md) pragması, kayan nokta özel durum modeli altında belirtmek için kullanılan bir [/FP](../../build/reference/fp-specify-floating-point-behavior.md) dışında ayarlama **/FP: precise**.

Aşağıdaki örnek, C3199 oluşturur:

```
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```