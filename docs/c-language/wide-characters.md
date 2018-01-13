---
title: "Geniş karakterler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab885d5d807fe81b3058d533a70cdbaa9e3e523a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wide-characters"></a>Geniş Karakterler
**ANSI 3.1.3.4** birden fazla karakter içeren bir tamsayı karakter sabiti ya da birden çok baytlı karakter içeren bir geniş karakter sabit değeri  
  
 Normal karakter sabiti 'ab', (int)0x6162 tamsayı değerine sahiptir. Birden çok bayt olduğunda, daha önce bayt sol değeriyle gölgeye okuma **char_bıt** ve sonraki bayt ile düşük bit düzeyinde OR işleci kullanılarak karşılaştırılır **char_bıt** BITS. Çok baytlı karakter sabitindeki bayt sayısı, 32 bit hedef kodu için 4 olan sizeof(int) değerini aşamaz.  
  
 Çok baytlı karakter sabiti, yukarıdaki gibi okunur ve `mbtowc` çalışma zamanı işlevi kullanılarak geniş karakter sabitine dönüştürülür. Sonuç geçerli bir geniş karakter sabiti değilse, bir hata verilir. Herhangi bir durumda, `mbtowc` işlevi tarafından incelenen bayt sayısı `MB_CUR_MAX` değeriyle sınırlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakterler](../c-language/characters.md)