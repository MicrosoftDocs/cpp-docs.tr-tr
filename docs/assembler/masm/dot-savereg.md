---
description: Hakkında daha fazla bilgi edinin:. SAVEREG
title: .SAVEREG
ms.date: 12/16/2019
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 8b946c9b25c3f4dc6a4696b418e85487e20014eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131189"
---
# <a name="savereg"></a>.SAVEREG

Geçerli başlangıç sapmasını `UWOP_SAVE_NONVOL` `UWOP_SAVE_NONVOL_FAR` kullanarak belirtilen yazmaç (*reg*) ve konum (*konum*) için bir veya aşağı doğru bırakma kodu girişi oluşturur. MASı, en verimli kodlamayı seçer.

## <a name="syntax"></a>Syntax

> **. Savereg** *reg*__,__ *konum*

## <a name="remarks"></a>Açıklamalar

**. SAVEREG** , ml64.exe kullanıcıların bir çerçeve işlevinin yük dışı bırakma ve [işlem çerçevesi bildiriminden](proc.md) öğesine genişleyen yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca ve oluşturur `.xdata` `.pdata` . **. SAVEREG** öncesinde eylemleri gerçekten uygulayan yönergelerden kaçınılmalıdır. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [x64 Için ması (ml64.exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
