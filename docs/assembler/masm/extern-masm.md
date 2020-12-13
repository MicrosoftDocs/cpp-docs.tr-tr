---
description: 'Daha fazla bilgi edinin: EXTERN'
title: EXTERN (MASM)
ms.date: 12/06/2019
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 354a390a16fb663dc6e907e37022a362c3ab5648
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130357"
---
# <a name="extern"></a>EXTERN

Türü *tür* olan bir veya daha fazla dış değişken, etiket veya *ad adı* adlandırılan sembolleri tanımlar.

## <a name="syntax"></a>Syntax

> **Extern** ⟦*Language-Type*⟧ *Name* ⟦ __(__*Altıd*__)__ ⟧ __:__ *tür* ⟦__,__ ⟦*dil türü*⟧ *adı* ⟦ __(__*Altıd*__)__ ⟧ __:__ *tür* ... ⟧

## <a name="remarks"></a>Açıklamalar

*Dil türü* bağımsız değişkeni yalnızca 32-BIT Masd 'de geçerlidir.

*Tür* , *adı* bir sabit olarak içeri aktaran [ABS](operator-abs.md)olabilir. [EXTRN](extrn.md)ile aynı.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
