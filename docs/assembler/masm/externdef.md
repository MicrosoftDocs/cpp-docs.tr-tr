---
title: EXTERNDEF | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- EXTERNDEF
dev_langs:
- C++
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5c3d42cabb88c38ce1d98da24cd2cb4ddec8d5b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683667"
---
# <a name="externdef"></a>EXTERNDEF

Bir veya daha fazla dış değişkenlerin, etiketler veya adlı sembolleri tanımlar *adı* türü olan `type`.

## <a name="syntax"></a>Sözdizimi

> [[Langtype]] EXTERNDEF adı: type [[, [[langtype]] ad: tür]]...

## <a name="remarks"></a>Açıklamalar

Varsa *adı* tanımlanan modülünde bunu kabul [genel](../../assembler/masm/public-masm.md). Varsa *adı* başvuruluyor modülünde bunu kabul [EXTERN](../../assembler/masm/extern-masm.md). Varsa *adı* olduğu başvurulmayan, göz ardı edilir. `type` Olabilir [ABS](../../assembler/masm/operator-abs.md), hangi içeri aktarmalar *adı* bir sabit olarak. Normalde kullanılan dosyaları ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>