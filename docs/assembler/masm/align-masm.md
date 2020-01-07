---
title: ALIGN (MASM)
ms.date: 12/17/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: 700721768deaf92e88b32a97e68c6e017219d19d
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316596"
---
# <a name="align"></a>ALIGN

**ALIGN** yönergesi, bir sonraki veri öğesini veya yönergesini, parametresinin birden çok katı olan bir adrese göre hizalar. Parametre, kesim hizalamasına eşit veya daha küçük bir 2 (örneğin, 1, 2, 4, vb.) bir üssü olmalıdır.

## <a name="syntax"></a>Sözdizimi

> ⟦*ConstantExpression*⟧ **Hizala**

## <a name="remarks"></a>Açıklamalar

**ALIGN** yönergesi, bir veri öğesinin veya yönergesinin başlangıç sapmasını belirtmenize olanak tanır. Hizalanmış veriler, veri öğeleri arasındaki harcanan alan masrafına göre performansı iyileştirebilir. Veri erişimleri, önbellek satırlarına sığan sınırlarda olduğunda büyük performans geliştirmeleri görülebilir. Yerel türler için doğal sınırlardaki erişimler, iç donanım yeniden hizalaması mikro kodunda daha az zaman harcamasıdır.

Hizalı yönergelerin ihtiyacı, düz bir adresleme modeli kullanan Modern işlemcilerde nadir olmakla birlikte, diğer adresleme modelleriyle ilgili eski koddaki sıçrama hedefleri için de gerekli olabilir.

Veriler hizalandığında atlanan alan sıfırlardan doldurulur. Yönergeler hizalandığında, atlanan alan uygun boyutlardaki NOP yönergeleriyle doldurulur.

## <a name="see-also"></a>Ayrıca bkz.

[Bile](even.md)\
[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
