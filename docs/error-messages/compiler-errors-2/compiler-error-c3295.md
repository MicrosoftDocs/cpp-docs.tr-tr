---
title: Derleyici Hatası C3295 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3295
dev_langs:
- C++
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b8210aacf60c4c53faf50278e7494c90c58aa67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076430"
---
# <a name="compiler-error-c3295"></a>Derleyici Hatası C3295

'#pragma pragma' yalnızca kullanılabilir genel kapsamda veya ad alanı kapsamında

Bazı pragmalar bir işlevde kullanılamaz.  Bkz: [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3295 oluşturur.

```
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```