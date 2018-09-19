---
title: Geniş karakterler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cf748aac5bc05dcc5bbb05b75ae34563398cad2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087506"
---
# <a name="wide-characters"></a>Geniş Karakterler

**ANSI 3.1.3.4** birden fazla karakter içeren tamsayı karakter sabitinin ya da birden çok baytlı karakter içeren bir geniş karakter sabiti değeri

Normal karakter sabiti 'ab', (int)0x6162 tamsayı değerine sahiptir. Birden fazla bayt olduğunda, daha önce bayt sol değeriyle kaydırılacak okuma **char_bıt** ve sonraki bayt bit düzeyinde OR işleci kullanılarak düşük ile karşılaştırılır **char_bıt** bitleri. Çok baytlı karakter sabitindeki bayt sayısı, 32 bit hedef kodu için 4 olan sizeof(int) değerini aşamaz.

Çok baytlı karakter sabiti, yukarıdaki gibi okunur ve `mbtowc` çalışma zamanı işlevi kullanılarak geniş karakter sabitine dönüştürülür. Sonuç geçerli bir geniş karakter sabiti değilse, bir hata verilir. Herhangi bir durumda, `mbtowc` işlevi tarafından incelenen bayt sayısı `MB_CUR_MAX` değeriyle sınırlıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Karakterler](../c-language/characters.md)