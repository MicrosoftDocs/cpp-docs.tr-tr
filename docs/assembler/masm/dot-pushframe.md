---
title: .PUSHFRAME
description: Açıklanır. Bir çerçeve işlevinin nasıl geriye doğru yapılacağını belirtmek için kullanılan PUSHFRAME MASı yönergesi.
ms.date: 12/06/2019
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: 5f951396291ecb12dab500a364f176106c5daa8b
ms.sourcegitcommit: 2cac0150ab3bc8260f866451019b8e22c7e1ac11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2019
ms.locfileid: "74945858"
---
# <a name="pushframe"></a>.PUSHFRAME

Bir `UWOP_PUSH_MACHFRAME` bırakma kodu girişi oluşturur. İsteğe bağlı **kod** anahtar sözcüğü belirtilirse, geriye doğru izleme kod girişine 1 değiştiricisi verilir. Aksi takdirde değiştirici 0 ' dır.

## <a name="syntax"></a>Sözdizimi

> **. PUSHFRAME** ⟦**kodu**⟧;;

## <a name="remarks"></a>Açıklamalar

. PUSHFRAME, ml64. exe kullanıcılarına bir çerçevenin nasıl yük erileyelini belirlemesine izin verir. Yalnızca [işlem çerçevesi bildiriminden](../../assembler/masm/proc.md) öğesine genişleyen prolog 'da izin verilir [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. PUSHFRAME** , önünde olmayan eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
