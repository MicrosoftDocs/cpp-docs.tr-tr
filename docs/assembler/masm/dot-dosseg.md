---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 17edea122afc03a8c3a2fdc86ee6c06c2ccf3c85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398483"
---
# <a name="dosseg-32-bit-masm"></a>. DOSSEG (32-bit MASM)

Segmentleri MS-DOS segment kuralına göre sıralar: önce CODE, ardından DGROUP içinde değil segmentler ve sonra DGROUP içinde segmentler. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> **.DOSSEG**

## <a name="remarks"></a>Açıklamalar

DGROUP 'taki segmentler şu sırayı izler: BSS veya YıĞıNDA bulunmayan segmentler, sonra BSS kesimleri ve son olarak yığın kesimleri. Öncelikli olarak tek başına çalıştırılan programlarda CodeView desteğini sağlamak için kullanılır. [DOSSEG](../../assembler/masm/dosseg.md)ile aynı.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
