---
title: .SAVEREG
ms.date: 12/16/2019
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 18cb6e563084e8c5357bec2a8052a2b38fcdffee
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317558"
---
# <a name="savereg"></a>.SAVEREG

Geçerli başlangıç sapmasını kullanarak belirtilen yazmaç (*reg*) ve konum (*konum*) için bir `UWOP_SAVE_NONVOL` ya da `UWOP_SAVE_NONVOL_FAR` bırakma kodu girişi oluşturur. MASı, en verimli kodlamayı seçer.

## <a name="syntax"></a>Sözdizimi

> **. Savereg** *reg* __,__ *konum*

## <a name="remarks"></a>Açıklamalar

**. SAVEREG** , ml64. exe kullanıcılarına, bir çerçeve işlevinin yük dışı bırakma ve [işlem çerçevesi bildiriminden](proc.md) öğesine genişleyen yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. SAVEREG** öncesinde eylemleri gerçekten uygulayan yönergelerden kaçınılmalıdır. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
