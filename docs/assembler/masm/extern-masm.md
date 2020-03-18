---
title: EXTERN (MASM)
ms.date: 12/06/2019
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 2674f358fe22f74c5272d90a0d8cbff234ddcd11
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440877"
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
