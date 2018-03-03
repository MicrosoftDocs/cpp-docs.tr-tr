---
title: "scanf türü alan karakterleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- scanf
dev_langs:
- C++
helpviewer_keywords:
- scanf function, type field characters
ms.assetid: 5d546a84-715b-44ca-b1c5-bbe997f9ff62
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ebc971ea109a0e83288f5bb000e09461f4fbefec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="scanf-type-field-characters"></a>scanf Türü Alan Karakterleri
Aşağıdaki bilgiler herhangi biri geçerlidir `scanf` gibi güvenli sürümleri dahil olmak üzere işlevlerin ailesi `scanf_s`.  
  
 `type` Karakter yalnızca gerekli biçim alanı; isteğe bağlı biçim alanları sonra görünür. `type` Karakter belirler ilişkili bağımsız değişken karakter, dize veya sayı yorumlanır.  
  
### <a name="type-characters-for-scanf-functions"></a>Scanf işlevler için türü karakterleri  
  
|Karakter|Beklenen Giriş türü|Bağımsız değişken türü|Güvenli sürümünde boyutu bağımsız değişkeniyle?|  
|---------------|----------------------------|----------------------|--------------------------------------|  
|`c`|Karakter. İle kullanıldığında `scanf` İşlevler, tek baytlı karakter; kullanıldığında belirtir `wscanf` İşlevler, geniş karakter belirtir. Normalde atlanır boşluk karakterleri okuma `c` belirtilir. Sonraki boşluk olmayan tek baytlı karakter okumak için kullandığınız `%1s`; sonraki olmayan-boşluk geniş karakter okuma, kullanmak için `%1ws`.|İşaretçi `char` ile kullanıldığında `scanf` İşlevler, işaretçi `wchar_t` ile kullanıldığında `wscanf` işlevleri.|Gerekli. Boyutu null Sonlandırıcı alanı içermez.|  
|`C`|Ters boyutu karakter. İle kullanıldığında `scanf` İşlevler, geniş karakter; kullanıldığında belirtir `wscanf` İşlevler, tek baytlı karakter belirtir. Normalde atlanır boşluk karakterleri okuma `C` belirtilir. Sonraki boşluk olmayan tek baytlı karakter okumak için kullandığınız `%1s`; sonraki olmayan-boşluk geniş karakter okuma, kullanmak için `%1ws`.|İşaretçi `wchar_t` ile kullanıldığında `scanf` İşlevler, işaretçi `char` ile kullanıldığında `wscanf` işlevleri.|Gerekli. Boyut bağımsız değişkeni null Sonlandırıcı alanı içermez.|  
|`d`|Ondalık tamsayı.|İşaretçi `int`.|Hayır.|  
|`i`|Bir tam sayı. Giriş dizesi "0 x" veya "0 X" ile başlıyorsa onaltılık dize "0", aksi takdirde ondalık başlıyorsa sekizli.|İşaretçi `int`.|Hayır.|  
|`o`|Sekizlik tamsayı.|İşaretçi `int`.|Hayır.|  
|`p`|Onaltılık basamak bir işaretçi adresi. Okuma basamak sayısı üst sınırı, makine mimarisine bağlı bir işaretçi (32 veya 64 bit) boyutuna bağlıdır. "0 x" veya "0 X" önekleri kabul edilir.|İşaretçi `void*`.|Hayır.|  
|`u`|İmzasız ondalık tamsayı.|İşaretçi `unsigned int`.|Hayır.|  
|`x`|Onaltılık tamsayı.|İşaretçi `int`.|Hayır.|  
|`e`, `E`, `f`, `F`, `g`, `G`|Kayan nokta değeri isteğe bağlı oturum oluşan (+ veya -), ondalık ayırıcıdan ve isteğe bağlı olarak imzalanmış bir tamsayı ve ardından isteğe bağlı üs ("e" veya "E") içeren bir veya daha fazla ondalık basamak dizisi.|İşaretçi `float`.|Hayır.|  
|`a`, `A`|Bir veya daha fazla onaltılık basamak isteğe bağlı bir ondalık ayırıcısı ve ondalık bir değer tarafından izlenen bir üs ("p" veya "P") içeren bir dizi oluşan kayan nokta değeri.|İşaretçi `float`.|Hayır.|  
|`n`|Herhangi bir giriş akışı veya arabellek okuyun.|İşaretçi `int`, hangi saklı karakter sayısını başarıyla içine akışından okuma veya arabellek geçerli çağrıda bu noktaya kadar `scanf` işlevleri veya `wscanf` işlevleri.|Hayır.|  
|`s`|İlk boşluk karakteri (boşluk, sekme ya da yeni satır) kadar dizesi. Boşluk karakterleri tarafından ayrılmış değil dizeleri okumak için köşeli ayraç kümesi kullanın (`[ ]`) makalesinde ele alındığı gibi [sacnf genişlik belirtimi](../c-runtime-library/scanf-width-specification.md).|İle kullanıldığında `scanf` İşlevler, tek baytlı karakter dizisi; kullanıldığında güveninin `wscanf` İşlevler, joker karakter dizisi belirtir. Her iki durumda da karakter dizisi giriş alanını artı otomatik olarak eklenir sonlandırma null karakteri için yeterince büyük olması gerekir.|Gerekli. Boyut için null Sonlandırıcı alanı içerir.|  
|`S`|İlk boşluk karakteri (boşluk, sekme ya da yeni satır) en fazla karakter dizesi karşıtı boyutu. Boşluk karakterleri tarafından ayrılmış değil dizeleri okumak için köşeli ayraç kümesi kullanın (`[ ]`) makalesinde ele alındığı gibi [sacnf genişlik belirtimi](../c-runtime-library/scanf-width-specification.md).|İle kullanıldığında `scanf` İşlevler, birlikte kullanıldığında joker karakter dizisi; güveninin `wscanf` İşlevler, tek bayt karakter dizisi belirtir. Her iki durumda da karakter dizisi giriş alanını artı otomatik olarak eklenir sonlandırma null karakteri için yeterince büyük olması gerekir.|Gerekli. Boyut için null Sonlandırıcı alanı içerir.|  
  
  
 Boyut bağımsız değişkenleri gerektiriyorsa, hemen uygulandıkları bağımsız değişkeni aşağıdaki parametre listesinde geçirilmesi gerekir. Örneğin, aşağıdaki kod:  
  
```  
char string1[11], string2[9];  
scanf_s("%10s %8s", string1, 11, string2, 9);  
```  
  
 10 en büyük uzunluğa sahip bir dize okur `string1`ve 8 en büyük uzunluğa sahip bir dize `string2`. Arabellek boyutu en az bir alan itibaren genişlik belirtimleri fazla null Sonlandırıcı için ayrılmış olması gerekir.  
  
 Biçim dizesi tek baytlı karakter veya işlevi bir joker karakter sürümü kullanılıp kullanılmamasına bakılmaksızın tek baytlı ve geniş karakter giriş işleyebilir. Bu nedenle, tek baytlı veya uluslararası karakter ile okumak için `scanf` işlevleri ve `wscanf` İşlevler, biçim belirticileri şu şekilde kullanın.  
  
|Karakter olarak okumak için|Bu işlevi kullanın|İle bu biçim belirticileri|  
|--------------------------|-----------------------|----------------------------------|  
|tek bayt|`scanf`İşlevler|`c`, `hc`, veya`hC`|  
|tek bayt|`wscanf`İşlevler|`C`, `hc`, veya`hC`|  
|geniş|`wscanf`İşlevler|`c`, `lc`, veya`lC`|  
|geniş|`scanf`İşlevler|`C`, `lc`, veya`lC`|  
  
 Dizelerle taranacak `scanf` işlevleri ve `wscanf` işlevlerini kullanmak yukarıdaki tabloda biçim türü-tanımlayıcıları ile `s` ve `S` yerine `c` ve `C`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)