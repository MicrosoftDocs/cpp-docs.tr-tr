---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 2b91698640e028bf91d822c12b85ded651a04d8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555811"
---
# <a name="if-masm"></a>IF (MASM)

Derlemenin verir *if* varsa *İfade1* true (sıfırdan farklı) veya *elseifstatements* varsa *İfade1* yanlış (0) ve *expression2* geçerlidir.

## <a name="syntax"></a>Sözdizimi

> Eğer *İfade1*<br/>
> *if*<br/>
> [[ELSEIF *expression2*<br/>
> *elseifstatements*]]<br/>
> [[ELSE<br/>
> *elsestatements*]]<br/>
> ENDIF

## <a name="remarks"></a>Açıklamalar

Aşağıdaki yönergeleri için yerine kullanılabileceği [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI** , **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, ve **ELSEIFNDEF** . İsteğe bağlı olarak çeviren *elsestatements* önceki ifade false ise. İfadenin derleme zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>