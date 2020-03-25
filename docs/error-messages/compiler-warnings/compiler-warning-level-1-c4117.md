---
title: Derleyici Uyarısı (düzey 1) C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 2474645a555748b559b1661a2b5327ca1b83e534
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176384"
---
# <a name="compiler-warning-level-1-c4117"></a>Derleyici Uyarısı (düzey 1) C4117

' name ' makro adı ayrılmıştır; ' Komut ' yoksayıldı

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Önceden tanımlanmış bir makronun tanımlanması veya tanımlanması kaldırılmaya çalışılıyor.

1. **Tanımlanan**Önişlemci işlecinin tanımlanması veya tanımlanması kaldırılmaya çalışılıyor.

Aşağıdaki örnek C4117 oluşturur:

```cpp
// C4117.cpp
// compile with: /W1
#define __FILE__ test         // C4117. __FILE__ is a predefined macro
#define ValidMacroName test   // ok

int main() {
}
```
