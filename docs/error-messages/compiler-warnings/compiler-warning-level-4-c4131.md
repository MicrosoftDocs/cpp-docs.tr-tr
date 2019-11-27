---
title: Derleyici Uyarısı (düzey 4) C4131
ms.date: 11/04/2016
f1_keywords:
- C4131
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
ms.openlocfilehash: 266d62126d9154cd87706d3124e69e107bbdefde
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541574"
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