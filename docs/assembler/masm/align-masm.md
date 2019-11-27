---
title: ALIGN (MASM)
ms.date: 01/02/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: 22b18f2e238c780377b84fc2be3eb6678686bb73
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399282"
---
# <a name="align-masm"></a>ALIGN (MASM)

**ALIGN** yönergesi, bir sonraki veri öğesini veya yönergesini, parametresinin birden çok katı olan bir adrese göre hizalar. Parametre, kesim hizalamasına eşit veya daha küçük bir 2 (örneğin, 1, 2, 4, vb.) bir üssü olmalıdır.

## <a name="syntax"></a>Sözdizimi

> ⟦*Numarasını* **Hizala** ⟧

## <a name="remarks"></a>Açıklamalar

**ALIGN** yönergesi, bir veri öğesinin veya yönergesinin başlangıç sapmasını belirtmenize olanak tanır. Hizalanmış veriler, veri öğeleri arasındaki harcanan alan masrafına göre performansı iyileştirebilir. Veri erişimleri, önbellek satırlarına sığan sınırlarda olduğunda büyük performans geliştirmeleri görülebilir. Yerel türler için doğal sınırlardaki erişimler, iç donanım yeniden hizalaması mikro kodunda daha az zaman harcamasıdır.

Hizalı yönergelerin ihtiyacı, düz bir adresleme modeli kullanan Modern işlemcilerde nadir olmakla birlikte, diğer adresleme modelleriyle ilgili eski koddaki sıçrama hedefleri için de gerekli olabilir.

Veriler hizalandığında atlanan alan sıfırlardan doldurulur. Yönergeler hizalandığında, atlanan alan uygun boyutlardaki NOP yönergeleriyle doldurulur.

## <a name="see-also"></a>Ayrıca bkz.

[Bile](even.md)\
[Yönergeler başvurusu](directives-reference.md)
