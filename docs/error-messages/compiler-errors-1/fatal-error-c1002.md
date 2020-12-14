---
description: 'Daha fazla bilgi edinin: önemli hata C1002'
title: Önemli hata C1002
ms.date: 11/04/2016
f1_keywords:
- C1002
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
ms.openlocfilehash: edd4ffbd6ce4c8a7f70640619d8dc52775dd0195
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262717"
---
# <a name="fatal-error-c1002"></a>Önemli hata C1002

2. geçişte derleyicinin yığın alanı kalmadı

Büyük olasılıkla çok fazla sembol veya karmaşık ifade içeren bir program nedeniyle derleyicinin ikinci geçişi sırasında dinamik bellek alanı kalmadı.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Kaynak dosyayı birkaç küçük dosyaya bölün.

1. İfadeleri daha küçük bir alt ifadeye bölün.

1. Belleği kullanan diğer programları veya sürücüleri kaldırın.
