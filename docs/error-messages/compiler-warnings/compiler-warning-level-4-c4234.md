---
title: Derleyici Uyarısı (düzey 4) C4234 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4234
dev_langs:
- C++
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6ce6ba622cb480096144706589a01dee7326f38
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118238"
---
# <a name="compiler-warning-level-4-c4234"></a>Derleyici Uyarısı (düzey 4) C4234

Standart olmayan uzantı kullanıldı: 'anahtar sözcüğü' anahtar sözcüğü gelecekte kullanılmak üzere ayrılmış

Derleyici, kullanılan anahtar sözcüğü henüz uygulamıyor.

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 4 uyarısı sorunu C4234 yapmak için

```
#pragma warning(2:4234)
```

Kaynak kodu dosyanızda.