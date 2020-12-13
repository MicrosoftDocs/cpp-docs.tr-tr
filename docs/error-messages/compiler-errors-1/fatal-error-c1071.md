---
description: 'Daha fazla bilgi edinin: önemli hata C1071'
title: Önemli hata C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: c4a6734dcb515b6d495eac720f83ba39be3c3677
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344386"
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
