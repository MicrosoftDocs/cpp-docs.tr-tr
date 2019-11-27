---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 469b49832c171ee78336a0c457f0d269acd3b59d
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397535"
---
# <a name="externdef"></a>EXTERNDEF

Türü *tür*olan bir veya daha fazla dış değişken, etiket veya *ad adı* adlandırılan sembolleri tanımlar.

## <a name="syntax"></a>Sözdizimi

> **Externdef** ⟦*dil türü*⟧ *adı* __:__ *tür* ⟦ __,__ ⟦*dil-tür*⟧ *adı* __:__ *tür* ... ⟧

## <a name="remarks"></a>Açıklamalar

Modül içinde *ad* tanımlıysa, [genel](../../assembler/masm/public-masm.md)olarak kabul edilir. Modülde *ada* başvuruluyorsa, [extern](../../assembler/masm/extern-masm.md)olarak kabul edilir. *Ada* başvurulmuyorsa, yok sayılır. *Tür* , *adı* bir sabit olarak içeri aktaran [ABS](../../assembler/masm/operator-abs.md)olabilir. Genellikle içerme dosyalarında kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
