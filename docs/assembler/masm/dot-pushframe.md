---
title: .PUSHFRAME
description: Açıklanır. Bir çerçeve işlevinin nasıl geriye doğru yapılacağını belirtmek için kullanılan PUSHFRAME MASı yönergesi.
ms.date: 12/06/2019
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: 0aaec119d26d87fddb1eba505458da1250a5926e
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317584"
---
# <a name="pushframe"></a>.PUSHFRAME

Bir `UWOP_PUSH_MACHFRAME` bırakma kodu girişi oluşturur. İsteğe bağlı **kod** anahtar sözcüğü belirtilirse, geriye doğru izleme kod girişine 1 değiştiricisi verilir. Aksi takdirde değiştirici 0 ' dır.

## <a name="syntax"></a>Sözdizimi

> **. PUSHFRAME** ⟦**kodu**⟧;;

## <a name="remarks"></a>Açıklamalar

. PUSHFRAME, ml64. exe kullanıcılarına bir çerçevenin nasıl yük erileyelini belirlemesine izin verir. Yalnızca [işlem çerçevesi bildiriminden](proc.md) öğesine genişleyen prolog 'da izin verilir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. PUSHFRAME** , önünde olmayan eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
