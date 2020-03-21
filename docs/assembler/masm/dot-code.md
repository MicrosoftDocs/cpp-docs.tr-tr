---
title: .CODE
ms.date: 12/17/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 7e53befcc46319d0ecf2287ab96a19a73a0b0b85
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076272"
---
# <a name="code"></a>.CODE

(yalnızca 32-bit masa.) İle kullanıldığında [. MODEL](dot-model.md), bir kod kesiminin başlangıcını gösterir.

## <a name="syntax"></a>Sözdizimi

> **. CODE** ⟦*Name*⟧ \
> ⟦ *segmentItem* ⟧... \
> ⟦ *codesegmentnameId* **bitiyor**;; ⟧\

### <a name="parameters"></a>Parametreler

*ad*\
Kod kesiminin adını belirten isteğe bağlı parametre. Küçük, küçük, kompakt ve düz [modeller](dot-model.md)için varsayılan ad **_TEXT** . Varsayılan ad, diğer modeller için *modulename*_TEXT.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[. VERI](dot-data.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
