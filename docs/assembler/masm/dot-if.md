---
title: . EĞER | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .IF
dev_langs:
- C++
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7bd5ba5821b4dcfb2d088e31816f50540445018
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691550"
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