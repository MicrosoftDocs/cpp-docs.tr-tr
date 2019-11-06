---
title: Derleyici Uyarısı (düzey 1) C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 97fd5703a744448db87634e313678cf4e824df7f
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626282"
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