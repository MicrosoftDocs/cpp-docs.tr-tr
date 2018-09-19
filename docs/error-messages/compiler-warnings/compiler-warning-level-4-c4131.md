---
title: Derleyici Uyarısı (düzey 4) C4131 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4131
dev_langs:
- C++
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43de917b2a6aff38602a6118e599c0d9df262a70
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033192"
---
# <a name="compiler-warning-level-4-c4131"></a>Derleyici Uyarısı (düzey 4) C4131

'function': eski stil bildirimci kullanıyor

Belirtilen işlev bildirimi prototip biçiminde değil.

Eski stil işlev bildirimleri prototip biçimine dönüştürülmelidir.

Aşağıdaki örnek, eski stil işlev bildirimi gösterilmektedir:

```
// C4131.c
// compile with: /W4 /c
void addrec( name, id ) // C4131 expected
char *name;
int id;
{ }
```

Aşağıdaki örnek, bir prototip form gösterir:

```
void addrec( char *name, int id )
{ }
```