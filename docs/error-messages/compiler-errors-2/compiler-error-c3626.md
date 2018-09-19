---
title: Derleyici Hatası C3626 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3626
dev_langs:
- C++
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba6fb7c03c7c957999ca75e3946e4f78d290b78a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094708"
---
# <a name="compiler-error-c3626"></a>Derleyici Hatası C3626

'anahtar sözcüğü': '__event' anahtar sözcüğü yalnızca kullanılabilir COM arabirimleri, üye işlevleri ve temsilci işaretçileri olan veri üyeleri

Bir anahtar sözcük yanlış kullanıldı.

Aşağıdaki örnek, C3626 oluşturur:

```
// C3626.cpp
// compile with: /c
struct A {
   __event int i;   // C3626
// try the following line instead
// __event int i();
};
```