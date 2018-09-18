---
title: Önemli hata C1002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f08255484b11f9f5d87fb67ac8ac7b401d4f6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044151"
---
# <a name="fatal-error-c1002"></a>Önemli hata C1002

2. geçiş yığın tükendi derleyicisidir

Derleyici, büyük olasılıkla çok fazla sembol veya karmaşık ifadeleri bir programla nedeniyle, ikinci geçişi sırasında dinamik bellek alanı yetersiz kaldı.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Kaynak dosyası birden çok daha küçük dosyalara bölün.

1. İfadeler, daha küçük alt ifadelere bölün.

1. Diğer programları veya bellek kullanan sürücüleri kaldırın.