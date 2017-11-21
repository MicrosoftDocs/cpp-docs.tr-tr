---
title: "Dize değişmez değeri birleştirmesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- concatenating strings
- strings [C++], concatenating
ms.assetid: 51486b1f-4b1e-4061-9add-1aa38c6cdb3c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5974e192e32c612fe995cbc736e703f6168a3e8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="string-literal-concatenation"></a>Dize Değişmez Değeri Birleştirmesi
Bir satırdan fazla olan dize sabit değerleri oluşturmak için iki dizeyi bitiştirebilirsiniz. Bunu yapmak için ters eğik çizgi yazın, ardından RETURN tuşuna basın. Ters eğik çizgi, derleyicinin sonraki yeni satır karakterini yoksaymasına neden olur. Örneğin, dize sabit değeri  
  
```  
"Long strings can be bro\  
ken into two or more pieces."  
```  
  
 şu dizeyle aynıdır:  
  
```  
"Long strings can be broken into two or more pieces."  
```  
  
 Dize bitiştirme, bir satırdan daha uzun dizeler girmek için ters eğik çizginin ardından yeni satır karakteri kullandığınız her yerde kullanılabilir.  
  
 Değişmez değer dize içinde yeni bir satır zorlamak için satır başı karakteri kaçış sırası girin (**\n**) bozuk, aşağıdaki gibi satır istediğiniz dizesinde noktada:  
  
```  
"Enter a number between 1 and 100\nOr press Return"  
```  
  
 Dizeler kaynak kodunun herhangi bir sütununda başlayabileceği ve uzun dizeler sonraki satırın herhangi bir sütununda devam edebileceği için dizeleri kaynak kodunun okunabilirliğini artıracak şekilde konumlandırabilirsiniz. Her iki durumda da, çıktı sırasındaki ekran gösterimleri etkilenmez. Örneğin:  
  
```  
printf_s ( "This is the first half of the string, "  
           "this is the second half ") ;  
```  
  
 Dizenin her bölümü çift tırnak işareti içine alındığı sürece, bölümler bitiştirilir ve tek bir dize olarak çıkarılır. Bu birleştirme tarafından belirtilen derleme sırasında göre olaylar dizisi gerçekleşir [çeviri aşamaları](../preprocessor/phases-of-translation.md).  
  
```  
"This is the first half of the string, this is the second half"  
```  
  
 İki ayrı dize değişmez değerleri yalnızca beyaz boşlukla ayrılmış olarak başlatılan bir dize işaretçisi tek bir dize depolanır (işaretçileri içinde ele alınmıştır [işaretçi bildirimleri](../c-language/pointer-declarations.md)). Aşağıdaki örnekte olduğu gibi düzgün bir şekilde başvurulduğunda, sonuç önceki örnekle aynı olur:  
  
```  
char *string = "This is the first half of the string, "  
               "this is the second half";  
  
printf_s( "%s" , string ) ;  
```  
  
 6. çeviri aşamasında, bitişik dize sabit değerlerinin veya bitişik geniş dize sabit değerlerinin herhangi bir dizisi tarafından belirtilen çok baytlı karakter dizileri, tek çok baytlı karakter dizisi olarak bitiştirilir. Bu nedenle, programları yürütme sırasında dize sabit değerlerinin değiştirilmesine izin verilecek şekilde tasarlamayın. ANSI C standardı, bir dize değiştirme işleminin sonucunun tanımlanmamış olduğunu belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C dize değişmez değerleri](../c-language/c-string-literals.md)