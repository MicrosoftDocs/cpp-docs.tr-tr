---
title: Derleyici Hatası C2337
ms.date: 11/04/2016
f1_keywords:
- C2337
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
ms.openlocfilehash: 63f18a12ccd1962dd221324f5557c29be89eb04c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188283"
---
# <a name="compiler-error-c2337"></a>Derleyici Hatası C2337

'öznitelik adı': öznitelik bulunamadı

Visual C++'ın bu sürümünde desteklenmeyen bir öznitelik kullandınız.

Aşağıdaki örnek, C2337 oluşturur:

```
// C2337.cpp
// compile with: /c
[emitidl];
[module(name="x")];
[grasshopper]   // C2337, not a supported attribute
class a{};
```