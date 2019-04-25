---
title: Önemli hata C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: 8fe6b0f3bb1253f72c97f29070ba81cdbdf80508
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166665"
---
# <a name="fatal-error-c1071"></a>Önemli hata C1071

Beklenmeyen açıklamada dosya sonu bulundu

Derleyici, bir açıklama taranırken dosya sonuna ulaşıldı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Açıklama Sonlandırıcı eksik (* /).

1. Sonra bir kaynak dosyasının son satırda açıklama bulunan bir yeni satır karakteri eksik.

Aşağıdaki örnek, C1071 oluşturur:

```
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```