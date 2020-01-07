---
title: IF1 ve IF2
ms.date: 11/21/2019
f1_keywords:
- IF2
- IF1
helpviewer_keywords:
- IF2 directive
- IF2 directive
ms.assetid: a0f75564-b51b-4e39-ad3b-f7421e7ecad6
ms.openlocfilehash: 60f8b0dcedb61ac06de929aff300845e342d7cfc
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317324"
---
# <a name="if1-and-if2"></a>IF1 ve IF2

**IF1** bloğu ilk derleme geçişinde değerlendirilir.

**IF2** bloğu her derleme geçişi üzerinde DEĞERLENDIRILIR **: SETIF2** **true**ise.

## <a name="syntax"></a>Sözdizimi

> **IF1;;**

> **IF2;;**

## <a name="remarks"></a>Açıklamalar

Sözdiziminin [tamamı için bkz](if-masm.md) .

Sürüm 5,1 ' den farklı olarak, MASU 6,1 ve üzeri, onun ilk geçişinde işini en iyi şekilde gerçekleştirir, daha sonra gerektiğinde daha fazla geçiş yapar. Buna karşılık, MASı 5,1 her zaman iki kaynak geçişte her zaman ayrıştırır. Sonuç olarak, Masd 6,1 ve üzeri sürümlerde bazı geçiş bağımlı yapıları düzeltmeniz veya silmeniz gerekebilir.

### <a name="two-pass-directives"></a>İki taramalı yönergeler

Uyumluluk sağlamak için Masa 6,1 ve üzeri, iki geçişe başvuran 5,1 yönergelerini destekler. Bunlar dahildir **. ERR1**, **. ERR2**, **IF1**, **IF2**, **ELSEIF1**ve **ELSEIF2**. İkinci geçiş yapıları için, [SETIF2 seçeneğini](option-masm.md)belirtmeniz gerekir. **Seçenek SETIF2**olmadan, **IF2** ve **. ERR2** yönergeleri hataya neden olur:

```output
.ERR2 not allowed : single-pass assembler
```

MASM6,1 ve üzeri, ilk geçiş yapılarını farklı şekilde işler. Öğesine davranır **. As ERR1** yönergesi **. HATA**ve **IF1** yönergesi **gibi.**

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
