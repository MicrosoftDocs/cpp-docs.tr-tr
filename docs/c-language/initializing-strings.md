---
title: Başlatma dizeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- character arrays, initializing
- strings [C++], initializing
- initializing arrays, strings
ms.assetid: 0ab8079d-d0d3-48f9-afd1-36a7bb439b29
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c01dbea3cbcfaf89280f5fd61a31646b88ac491a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383985"
---
# <a name="initializing-strings"></a>Başlatma Dizeleri
Bir dize sabit değeri (veya geniş dize sabit değeri) ile bir karakterler (veya geniş karakterler) dizisi başlatabilirsiniz. Örneğin:  
  
```  
char code[ ] = "abc";  
```  
  
 dört öğeli karakter dizisi olarak `code` başlatır. Dördüncü öğe, tüm dize sabit değerlerini sonlandıran null karakterdir.  
  
 Tanımlayıcı listesi, yalnızca başlatılacak tanımlayıcıların sayısı kadar uzun olabilir. Dizede daha kısa bir dize boyutu belirtirseniz, ek karakterler yoksayılır. Örneğin, aşağıdaki bildirim üç öğeli karakter dizisi olarak `code` başlatır:  
  
```  
char code[3] = "abcd";  
```  
  
 Başlatıcının yalnızca ilk üç karakteri `code` öğesine atanır. `d` karakteri ve dizeyi sonlandıran null karakteri atılır. Bunun, sonlandırılmayan bir dize (yani sonunu gösteren bir 0 değeri olmayan bir dize) ve bu durumu gösteren bir tanılama iletisi oluşturduğunu unutmayın.  
  
 Bildirim  
  
```  
char s[] = "abc", t[3] = "abc";  
```  
  
 şununla aynıdır  
  
```  
char s[]  = {'a', 'b', 'c', '\0'},   
     t[3] = {'a', 'b', 'c' };  
```  
  
 Dizi belirtilen dizi boyutundan kısaysa, dizinin kalan öğeleri 0'a başlatılır.  
  
 **Microsoft özel**  
  
 Microsoft C'de, dize sabit değerlerinin uzunluğu en fazla 2048 bayt olabilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlatma](../c-language/initialization.md)