---
description: 'Daha fazla bilgi edinin: geniş karakterler'
title: Geniş Karakterler
ms.date: 11/04/2016
helpviewer_keywords:
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
ms.openlocfilehash: 64b175402f98c1e687f453a897c8e240fd176e0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260832"
---
# <a name="wide-characters"></a>Geniş Karakterler

**ANSI 3.1.3.4 &** Birden fazla karakter içeren bir tamsayı karakter sabiti veya birden fazla çok baytlı karakter içeren geniş bir karakter sabiti değeri

Normal karakter sabiti 'ab', (int)0x6162 tamsayı değerine sahiptir. Birden fazla bayt olduğunda, daha önce okunan baytlar **CHAR_BIT** değeri ile sola kaydırılmıştır ve sonraki bayt, düşük **CHAR_BIT** bitleriyle bit düzeyinde OR işleci kullanılarak karşılaştırılır. Çok baytlı karakter sabitindeki bayt sayısı, 32 bit hedef kodu için 4 olan sizeof(int) değerini aşamaz.

Çok baytlı karakter sabiti, yukarıdaki gibi okunur ve `mbtowc` çalışma zamanı işlevi kullanılarak geniş karakter sabitine dönüştürülür. Sonuç geçerli bir geniş karakter sabiti değilse, bir hata verilir. Herhangi bir durumda, `mbtowc` işlevi tarafından incelenen bayt sayısı `MB_CUR_MAX` değeriyle sınırlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Karakterler](../c-language/characters.md)
