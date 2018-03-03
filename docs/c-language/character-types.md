---
title: "Karakter türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a48382f5f7a3ab64518c44ec953005cd54a4fe03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="character-types"></a>Karakter Türleri
Harfinin öncesinde olmayan bir tamsayı karakter sabiti **L** türüne sahip `int`. Tek bir karakter içeren bir tamsayı karakter sabiti sayısal değer bir tamsayı olarak yorumlanan karakter değeridir. Örneğin, sayısal değer karakterinin `a` 97 ondalık ve onaltılık 61.  
  
 Sözdizimsel olarak, bir "joker karakter sabiti" harfinin önekli karakter sabiti olduğunda **L**. Joker karakter sabiti türünde `wchar_t`, STDDEF içinde tanımlanan bir tamsayı yazın. H üstbilgi dosyası. Örneğin:  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Joker karakter sabitleri 16 bit uzunluğunda ve genişletilmiş yürütme karakter kümesi üyeleri belirtin. Karakter türüne göre gösterilemeyecek kadar büyük harfler express izin `char`. Bkz: [çok baytlı ve geniş karakterler](../c-language/multibyte-and-wide-characters.md) geniş karakterler hakkında daha fazla bilgi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Karakter Sabitleri](../c-language/c-character-constants.md)