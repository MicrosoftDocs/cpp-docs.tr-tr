---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 8f0388c3df9804c0cdb105162a962a44fe207345
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703317"
---
# <a name="dosseg-32-bit-masm"></a>. DOSSEG (32-bit MASM)

Segmentleri MS-DOS segment kuralına göre sıralar: önce CODE, ardından DGROUP içinde değil segmentler ve sonra DGROUP içinde segmentler. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> .DOSSEG

## <a name="remarks"></a>Açıklamalar

DGROUP 'taki segmentler şu sırayı izler: BSS veya YıĞıNDA bulunmayan segmentler, sonra BSS kesimleri ve son olarak yığın kesimleri. Öncelikli olarak tek başına çalıştırılan programlarda CodeView desteğini sağlamak için kullanılır. [DOSSEG](../../assembler/masm/dosseg.md)ile aynı.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>