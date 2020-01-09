---
title: EXTERN (MASM)
ms.date: 12/06/2019
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 681c4091a3c54a781bed4b01b235dfeb04f552c6
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318104"
---
# <a name="extern"></a>EXTERN

Türü *tür*olan bir veya daha fazla dış değişken, etiket veya *ad adı* adlandırılan sembolleri tanımlar.

## <a name="syntax"></a>Sözdizimi

> **Extern** ⟦*Language-Type*⟧ *Name* ⟦ __(__ *Altıd* __)__ ⟧ __:__ *tür* ⟦ __,__ ⟦*dil türü*⟧ *adı* ⟦ __(__ *Altıd* __)__ ⟧ __:__ *tür* ... ⟧

## <a name="remarks"></a>Açıklamalar

*Dil türü* bağımsız değişkeni yalnızca 32-BIT Masd 'de geçerlidir.

*Tür* , *adı* bir sabit olarak içeri aktaran [ABS](operator-abs.md)olabilir. [EXTRN](extrn.md)ile aynı.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
