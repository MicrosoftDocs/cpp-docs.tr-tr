---
title: Derleyici Uyarısı (düzey 1) C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 657963dd0199c1474f0cef566e5a177a16247521
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299809"
---
# <a name="compiler-warning-level-1-c4117"></a>Derleyici Uyarısı (düzey 1) C4117

Makro adı 'name' ayrılmıştır; 'Command' yoksayıldı

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Tanımlayın veya önceden tanımlanmış bir makro tanımsız çalışılıyor.

1. Tanımlayın veya önişlemci işleci tanımsız **tanımlanan**.

Aşağıdaki örnek, C4117 oluşturur:

```
// C4117.cpp
// compile with: /W1
#define __FILE__ test         // C4117. __FILE__ is a predefined macro
#define ValidMacroName test   // ok

int main() {
}
```