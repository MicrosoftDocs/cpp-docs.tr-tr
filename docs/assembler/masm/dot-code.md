---
title: .CODE
ms.date: 12/17/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 0975e96e670400b7fa221ae2d1b9982b5cee613b
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75314152"
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

