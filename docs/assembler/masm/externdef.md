---
description: 'Hakkında daha fazla bilgi edinin: EXTERNDEF'
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: b0ffc2154996fc7cea9f0b61917cadf7b776972f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130331"
---
# <a name="externdef"></a>EXTERNDEF

Türü *tür* olan bir veya daha fazla dış değişken, etiket veya *ad adı* adlandırılan sembolleri tanımlar.

## <a name="syntax"></a>Syntax

> **Externdef** ⟦*dil türü*⟧ *adı*__:__*tür* ⟦__,__ ⟦*dil-tür*⟧ *adı*__:__*tür* ... ⟧

## <a name="remarks"></a>Açıklamalar

*Dil türü* bağımsız değişkeni yalnızca 32-BIT Masd 'de geçerlidir.

Modül içinde *ad* tanımlıysa, [genel](public-masm.md)olarak kabul edilir. Modülde *ada* başvuruluyorsa, [extern](extern-masm.md)olarak kabul edilir. *Ada* başvurulmuyorsa, yok sayılır. *Tür* , *adı* bir sabit olarak içeri aktaran [ABS](operator-abs.md)olabilir. Genellikle içerme dosyalarında kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
