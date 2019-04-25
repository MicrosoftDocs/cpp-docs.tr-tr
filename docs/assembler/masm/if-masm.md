---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 2b91698640e028bf91d822c12b85ded651a04d8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203070"
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

Aşağıdaki yönergeleri için yerine kullanılabileceği [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI**, **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, ve **ELSEIFNDEF**. İsteğe bağlı olarak çeviren *elsestatements* önceki ifade false ise. İfadenin derleme zamanında değerlendirildiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>