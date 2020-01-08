---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: e27b0ae185542c11ee29119575d5c8225501f71e
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75313853"
---
# <a name="dosseg-32-bit-masm"></a>. DOSSEG (32-bit MASM)

Segmentleri MS-DOS segment kuralına göre sıralar: önce CODE, ardından DGROUP içinde değil segmentler ve sonra DGROUP içinde segmentler. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> **.DOSSEG**

## <a name="remarks"></a>Açıklamalar

DGROUP 'taki segmentler şu sırayı izler: BSS veya YıĞıNDA bulunmayan segmentler, sonra BSS kesimleri ve son olarak yığın kesimleri. Öncelikli olarak tek başına çalıştırılan programlarda CodeView desteğini sağlamak için kullanılır. [DOSSEG](dosseg.md)ile aynı.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
