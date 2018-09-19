---
title: Önemli hata C1021 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1021
dev_langs:
- C++
helpviewer_keywords:
- C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcb464a676b47baa4589c17269819d3a84d058fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029918"
---
# <a name="fatal-error-c1021"></a>Önemli hata C1021

Geçersiz önişlemci komutu 'string'

`string` geçerli değil [önişlemci yönergesi](../../preprocessor/preprocessor-directives.md). Hatayı gidermek için geçerli bir önişlemci adı kullanın. `string`.

Aşağıdaki örnek, C1021 oluşturur:

```
// C1021.cpp
#BadPreProcName    // C1021 delete line
```