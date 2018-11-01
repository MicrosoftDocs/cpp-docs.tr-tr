---
title: .DOSSEG
ms.date: 08/30/2018
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 28b3e351030ee83693c0fec5568aacf9b4b77c27
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639445"
---
# <a name="dosseg"></a>.DOSSEG

MS-DOS segment kuralına göre segmentler sıralar: kod ilk olarak, ardından kesim DGROUP içinde değil ve ardından kesim içinde DGROUP.

## <a name="syntax"></a>Sözdizimi

> .DOSSEG

## <a name="remarks"></a>Açıklamalar

Bu sırada DGROUP segmentler izleyin: kesimleri BSS veya yığın, sonra BSS parçaları ve son olarak yığın kesimlerini. Tek başına programlarda MASM CodeView desteği sağlamak için kullanılır. Aynı [DOSSEG](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>