---
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 2cc5884a7473da9175a6b6af4b4251314deffeb4
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75313398"
---
# <a name="externdef"></a>EXTERNDEF

Türü *tür*olan bir veya daha fazla dış değişken, etiket veya *ad adı* adlandırılan sembolleri tanımlar.

## <a name="syntax"></a>Sözdizimi

> **Externdef** ⟦*dil türü*⟧ *adı* __:__ *tür* ⟦ __,__ ⟦*dil-tür*⟧ *adı* __:__ *tür* ... ⟧

## <a name="remarks"></a>Açıklamalar

*Dil türü* bağımsız değişkeni yalnızca 32-BIT Masd 'de geçerlidir.

Modül içinde *ad* tanımlıysa, [genel](public-masm.md)olarak kabul edilir. Modülde *ada* başvuruluyorsa, [extern](extern-masm.md)olarak kabul edilir. *Ada* başvurulmuyorsa, yok sayılır. *Tür* , *adı* bir sabit olarak içeri aktaran [ABS](operator-abs.md)olabilir. Genellikle içerme dosyalarında kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
