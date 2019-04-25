---
title: Derleyici Hatası C2874
ms.date: 11/04/2016
f1_keywords:
- C2874
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
ms.openlocfilehash: 04cbce14fc1fcb1d5bbb07c7f847c479988224a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165106"
---
# <a name="compiler-error-c2874"></a>Derleyici Hatası C2874

'symbol' birden çok bildirimi bildirim kullanımı neden olur

Bildirimi, aynı öğesini iki kez tanımlanmış olması neden olur.

Aşağıdaki örnek, C2874 oluşturur:

```
// C2874.cpp
namespace Z {
   int i;
}

int main() {
   int i;
   using Z::i;   // C2874, i already declared
}
```