---
title: .IF
ms.date: 08/30/2018
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: cf9c594d843c937dd2191bee2a7cebadbc615c82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185273"
---
# <a name="if"></a>.IF

Testleri kod oluşturur `condition1` (örneğin, > 7 AX) ve yürüten *deyimleri* bu koşulun doğru olması durumunda.

## <a name="syntax"></a>Sözdizimi

> . Eğer condition1<br/>
> deyimler<br/>
> [[. ELSEIF condition2<br/>
> deyimleri]]<br/>
> [[. ELSE<br/>
> deyimleri]]<br/>
> .ENDIF

## <a name="remarks"></a>Açıklamalar

Varsa bir [. BAŞKA](../../assembler/masm/dot-else.md) orijinal koşul false ise aşağıdaki gibi kendi deyimler yürütülür. Çalışma zamanında koşulların değerlendirilmesi gerektiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>