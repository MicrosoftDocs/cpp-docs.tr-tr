---
title: ALIGN (MASM)
ms.date: 01/02/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: eb42b1952b3fd59438f0dd4c29d48c91c4d8864d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166483"
---
# <a name="align-masm"></a>ALIGN (MASM)

**HİZALA** yönergesi, sonraki veri öğesi veya katlarından biri, parametresinin bir adresi yönerge hizalar. Parametre 2'in üssü olmalıdır (örneğin, 1, 2, 4 ve benzeri) küçük veya eşit segment hizalama için.

## <a name="syntax"></a>Sözdizimi

> Hizalama [[*numarası*]]

## <a name="remarks"></a>Açıklamalar

**HİZALA** yönergesi, bir veri öğesi veya bir yönerge başlangıç uzaklığı belirtmenize olanak sağlar. Hizalanmış veri performansı, veri öğeleri arasındaki harcanmış çoğaltamaz artırabilir. Büyük performans geliştirmeleri, veri erişimleri sınırlarındaki önbellek satırları içinde uygun olduğunda görülebilir. Yerel türler için doğal sınırlara erişimlerde daha az zaman içinde iç donanım yeniden hizalama mikro kod için harcanan anlamına gelir.

Hizalanmış yönergeleri gereksinimini düz bir adresleme modeli kullanan, ancak diğer adresleme modelleri için eski kod atlama hedefleri için gerekli olabilecek modern işlemcilerde nadir olarak rastlanıyor.

Veri hizalandığında Atlanan alanı sıfırlarla doldurulur. Yönergeler hizalandığında, atlanan alanı uygun şekilde boyutlandırıldığından NOP yönergeleri ile doldurulur.

## <a name="see-also"></a>Ayrıca bkz.

[EVEN](even.md)<br/>
[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>