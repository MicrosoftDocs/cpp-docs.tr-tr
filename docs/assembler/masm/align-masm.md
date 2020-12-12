---
description: 'Daha fazla bilgi edinin: HIZALA'
title: ALIGN (MASM)
ms.date: 12/17/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: d13fce5d70d96e4e88a3f1044f633be0145a3fc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121777"
---
# <a name="align"></a>ALIGN

**ALIGN** yönergesi, bir sonraki veri öğesini veya yönergesini, parametresinin birden çok katı olan bir adrese göre hizalar. Parametre, kesim hizalamasına eşit veya daha küçük bir 2 (örneğin, 1, 2, 4, vb.) bir üssü olmalıdır.

## <a name="syntax"></a>Syntax

> ⟦*ConstantExpression*⟧ **Hizala**

## <a name="remarks"></a>Açıklamalar

**ALIGN** yönergesi, bir veri öğesinin veya yönergesinin başlangıç sapmasını belirtmenize olanak tanır. Hizalanmış veriler, veri öğeleri arasındaki harcanan alan masrafına göre performansı iyileştirebilir. Veri erişimleri, önbellek satırlarına sığan sınırlarda olduğunda büyük performans geliştirmeleri görülebilir. Yerel türler için doğal sınırlardaki erişimler, iç donanım yeniden hizalaması mikro kodunda daha az zaman harcamasıdır.

Hizalı yönergelerin ihtiyacı, düz bir adresleme modeli kullanan Modern işlemcilerde nadir olmakla birlikte, diğer adresleme modelleriyle ilgili eski koddaki sıçrama hedefleri için de gerekli olabilir.

Veriler hizalandığında atlanan alan sıfırlardan doldurulur. Yönergeler hizalandığında, atlanan alan uygun boyutlardaki NOP yönergeleriyle doldurulur.

## <a name="see-also"></a>Ayrıca bkz.

[ÇALıŞSA](even.md)\
[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
