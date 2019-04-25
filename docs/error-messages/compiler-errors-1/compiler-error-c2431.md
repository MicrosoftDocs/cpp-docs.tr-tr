---
title: Derleyici Hatası C2431
ms.date: 11/04/2016
f1_keywords:
- C2431
helpviewer_keywords:
- C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
ms.openlocfilehash: 6298748b341d58c5d931566f714530a4858e46ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165885"
---
# <a name="compiler-error-c2431"></a>Derleyici Hatası C2431

'identifier' içinde geçersiz dizin yazmacı var

ESP kayıt ölçeği veya dizin ve temel kayıt kullanılır. İşlemci ya da izin vermiyor x86 için kodlama SIB.

Aşağıdaki örnek, C2431 oluşturur:

```
// C2431.cpp
// processor: x86
int main() {
   _asm mov ax, [ESI + 2*ESP]   // C2431
   _asm mov ax, [esp + esp]   // C2431
}
```