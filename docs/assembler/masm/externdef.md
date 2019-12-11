---
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: e757781151bd1bb57940e5c54f7333a5daa93c74
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987889"
---
# <a name="externdef"></a>EXTERNDEF

Türü *tür*olan bir veya daha fazla dış değişken, etiket veya *ad adı* adlandırılan sembolleri tanımlar.

## <a name="syntax"></a>Sözdizimi

> **Externdef** ⟦*dil türü*⟧ *adı* __:__ *tür* ⟦ __,__ ⟦*dil-tür*⟧ *adı* __:__ *tür* ... ⟧

## <a name="remarks"></a>Açıklamalar

*Dil türü* bağımsız değişkeni yalnızca 32-BIT Masd 'de geçerlidir.

Modül içinde *ad* tanımlıysa, [genel](../../assembler/masm/public-masm.md)olarak kabul edilir. Modülde *ada* başvuruluyorsa, [extern](../../assembler/masm/extern-masm.md)olarak kabul edilir. *Ada* başvurulmuyorsa, yok sayılır. *Tür* , *adı* bir sabit olarak içeri aktaran [ABS](../../assembler/masm/operator-abs.md)olabilir. Genellikle içerme dosyalarında kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
