---
description: Hakkında daha fazla bilgi edinin:. DOSSEG (32-bit MASM)
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 636f3f811b20e7cf9955648c71025cfb1766fb47
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132112"
---
# <a name="dosseg-32-bit-masm"></a>. DOSSEG (32-bit MASM)

Segmentleri MS-DOS segment kuralına göre sıralar: önce CODE, ardından DGROUP içinde değil segmentler ve sonra DGROUP içinde segmentler. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Syntax

> **. DOSSEG**

## <a name="remarks"></a>Açıklamalar

DGROUP 'taki segmentler şu sırayı izler: BSS veya YıĞıNDA bulunmayan segmentler, sonra BSS kesimleri ve son olarak yığın kesimleri. Öncelikli olarak tek başına çalıştırılan programlarda CodeView desteğini sağlamak için kullanılır. [DOSSEG](dosseg.md)ile aynı.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
