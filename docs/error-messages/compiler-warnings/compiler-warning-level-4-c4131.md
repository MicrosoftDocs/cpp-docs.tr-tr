---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4131'
title: Derleyici Uyarısı (düzey 4) C4131
ms.date: 11/04/2016
f1_keywords:
- C4131
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
ms.openlocfilehash: b4b54a38ad634b1cc0d444b0b6d5136b6a208626
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261794"
---
# <a name="compiler-warning-level-4-c4131"></a>Derleyici Uyarısı (düzey 4) C4131

' function ': eski stil bildirimci kullanıyor

Belirtilen işlev bildirimi, prototip biçiminde değil.

Eski stil işlev bildirimleri prototip biçimine dönüştürülmelidir.

Aşağıdaki örnek, bir eski stili işlev bildirimini gösterir:

```c
// C4131.c
// compile with: /W4 /c
void addrec( name, id ) // C4131 expected
char *name;
int id;
{ }
```

Aşağıdaki örnekte bir prototip formu gösterilmektedir:

```c
void addrec( char *name, int id )
{ }
```
