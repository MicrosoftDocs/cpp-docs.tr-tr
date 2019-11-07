---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: 83c9ff588e2fe273e24e1d0b1c16517c5eee3365
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703787"
---
# <a name="if-32-bit-masm"></a>. IF (32-bit masa)

`condition1` test eden (örneğin, AX > 7) kodu üretir ve bu koşulun doğru olması durumunda *deyimleri* yürütür. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> . Condition1 Ise<br/>
> deyimler<br/>
> [[. Condition2 Ise ELSEıF<br/>
> deyimler]]<br/>
> [[. DEĞILSE<br/>
> deyimler]]<br/>
> .ENDIF

## <a name="remarks"></a>Açıklamalar

Bir [. ](../../assembler/masm/dot-else.md)Bundan sonra, özgün koşul yanlış ise deyimleri yürütülür. Koşulların çalışma zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>