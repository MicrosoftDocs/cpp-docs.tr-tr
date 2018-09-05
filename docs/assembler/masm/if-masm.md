---
title: IF (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca0cce834924f7fc147b1ef301d5bd345dfd2973
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685313"
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