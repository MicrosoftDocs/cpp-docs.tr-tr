---
title: Önemli hata C1002
ms.date: 11/04/2016
f1_keywords:
- C1002
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
ms.openlocfilehash: 0588da99994be547742cc530ba435002a2d73359
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344829"
---
# <a name="fatal-error-c1002"></a>Önemli hata C1002

2. geçiş yığın tükendi derleyicisidir

Derleyici, büyük olasılıkla çok fazla sembol veya karmaşık ifadeleri bir programla nedeniyle, ikinci geçişi sırasında dinamik bellek alanı yetersiz kaldı.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Kaynak dosyası birden çok daha küçük dosyalara bölün.

1. İfadeler, daha küçük alt ifadelere bölün.

1. Diğer programları veya bellek kullanan sürücüleri kaldırın.