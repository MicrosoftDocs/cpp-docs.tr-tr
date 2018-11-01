---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 23d34af470e825a8535de8cb28645a7bfb4c4d1b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619771"
---
# <a name="externdef"></a>EXTERNDEF

Bir veya daha fazla dış değişkenlerin, etiketler veya adlı sembolleri tanımlar *adı* türü olan `type`.

## <a name="syntax"></a>Sözdizimi

> [[Langtype]] EXTERNDEF adı: type [[, [[langtype]] ad: tür]]...

## <a name="remarks"></a>Açıklamalar

Varsa *adı* tanımlanan modülünde bunu kabul [genel](../../assembler/masm/public-masm.md). Varsa *adı* başvuruluyor modülünde bunu kabul [EXTERN](../../assembler/masm/extern-masm.md). Varsa *adı* olduğu başvurulmayan, göz ardı edilir. `type` Olabilir [ABS](../../assembler/masm/operator-abs.md), hangi içeri aktarmalar *adı* bir sabit olarak. Normalde kullanılan dosyaları ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>