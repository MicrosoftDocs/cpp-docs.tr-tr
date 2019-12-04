---
title: Önemli hata C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: 2f39359d55b5564c6379c84f07e942cf3484e011
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747416"
---
# <a name="fatal-error-c1071"></a>Önemli hata C1071

açıklamada beklenmeyen dosya sonu bulundu

Derleyici, bir yorumu tararken dosyanın sonuna ulaştı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Eksik açıklama Sonlandırıcı (*/).

1. Kaynak dosyanın son satırındaki bir açıklamadan sonra yeni satır karakteri eksik.

Aşağıdaki örnek C1071 oluşturur:

```cpp
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```
