---
title: Derleyici Uyarısı (düzey 4) C4235 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4235
dev_langs:
- C++
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9e709017e51101efe53a8697bb145014f200871
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031827"
---
# <a name="compiler-warning-level-4-c4235"></a>Derleyici Uyarısı (düzey 4) C4235

Standart olmayan uzantı kullanıldı: 'anahtar sözcüğü' anahtar sözcüğü bu mimaride desteklenmiyor

Derleyici, kullanılan anahtar sözcüğü desteklemez.

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 2 uyarı C4235 yapmak için aşağıdaki kod satırını kullanın.

```
#pragma warning(2:4235)
```

Kaynak kodu dosyanızda.