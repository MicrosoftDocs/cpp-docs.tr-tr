---
title: Geniş Karakterler
ms.date: 11/04/2016
helpviewer_keywords:
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
ms.openlocfilehash: 619adfd398f3955708df3267613de40e71e15fa6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452071"
---
# <a name="wide-characters"></a>Geniş Karakterler

**ANSI 3.1.3.4** birden fazla karakter içeren tamsayı karakter sabitinin ya da birden çok baytlı karakter içeren bir geniş karakter sabiti değeri

Normal karakter sabiti 'ab', (int)0x6162 tamsayı değerine sahiptir. Birden fazla bayt olduğunda, daha önce bayt sol değeriyle kaydırılacak okuma **char_bıt** ve sonraki bayt bit düzeyinde OR işleci kullanılarak düşük ile karşılaştırılır **char_bıt** bitleri. Çok baytlı karakter sabitindeki bayt sayısı, 32 bit hedef kodu için 4 olan sizeof(int) değerini aşamaz.

Çok baytlı karakter sabiti, yukarıdaki gibi okunur ve `mbtowc` çalışma zamanı işlevi kullanılarak geniş karakter sabitine dönüştürülür. Sonuç geçerli bir geniş karakter sabiti değilse, bir hata verilir. Herhangi bir durumda, `mbtowc` işlevi tarafından incelenen bayt sayısı `MB_CUR_MAX` değeriyle sınırlıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Karakterler](../c-language/characters.md)