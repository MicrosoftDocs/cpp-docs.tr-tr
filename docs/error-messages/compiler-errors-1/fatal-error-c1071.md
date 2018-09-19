---
title: Önemli hata C1071 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1071
dev_langs:
- C++
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b4487de60148e1da7668bc44c996c5dfb955a9d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033010"
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