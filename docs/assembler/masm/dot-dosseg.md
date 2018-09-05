---
title: . DOSSEG | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33ee0b0b049ece65786c4d4857c2e082a067fee4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693238"
---
# <a name="dosseg"></a>.DOSSEG

MS-DOS segment kuralına göre segmentler sıralar: kod ilk olarak, ardından kesim DGROUP içinde değil ve ardından kesim içinde DGROUP.

## <a name="syntax"></a>Sözdizimi

> .DOSSEG

## <a name="remarks"></a>Açıklamalar

Bu sırada DGROUP segmentler izleyin: kesimleri BSS veya yığın, sonra BSS parçaları ve son olarak yığın kesimlerini. Tek başına programlarda MASM CodeView desteği sağlamak için kullanılır. Aynı [DOSSEG](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>