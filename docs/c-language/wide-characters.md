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
ms.openlocfilehash: bf20b58ad9343f1a90f07a7f4c07bccd397a5888
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="wide-characters"></a>Geniş Karakterler
**ANSI 3.1.3.4** birden fazla karakter içeren bir tamsayı karakter sabiti ya da birden çok baytlı karakter içeren bir geniş karakter sabit değeri  
  
 Normal karakter sabiti 'ab', (int)0x6162 tamsayı değerine sahiptir. Birden çok bayt olduğunda, daha önce bayt sol değeriyle gölgeye okuma **char_bıt** ve sonraki bayt ile düşük bit düzeyinde OR işleci kullanılarak karşılaştırılır **char_bıt** BITS. Çok baytlı karakter sabitindeki bayt sayısı, 32 bit hedef kodu için 4 olan sizeof(int) değerini aşamaz.  
  
 Çok baytlı karakter sabiti, yukarıdaki gibi okunur ve `mbtowc` çalışma zamanı işlevi kullanılarak geniş karakter sabitine dönüştürülür. Sonuç geçerli bir geniş karakter sabiti değilse, bir hata verilir. Herhangi bir durumda, `mbtowc` işlevi tarafından incelenen bayt sayısı `MB_CUR_MAX` değeriyle sınırlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakterler](../c-language/characters.md)