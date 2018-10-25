---
title: scanf türü alan karakterleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04a4c2005dc0a7e0e052002198bebb7c78267843
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059965"
---
# <a name="scanf-type-field-characters"></a>scanf Türü Alan Karakterleri

Aşağıdaki bilgiler herhangi biri geçerlidir `scanf` işlevlerin güvenli sürümleri, gibi ailesi `scanf_s`.

`type` Karakter yalnızca gerekli biçimi alanı; sonra herhangi bir isteğe bağlı bir biçim alan görünür. `type` Karakteri belirler ilişkili bağımsız değişken karakter, dize veya sayı yorumlanır.

### <a name="type-characters-for-scanf-functions"></a>Scanf işlevleri için tür karakterleri

|Karakter|Beklenen Giriş türü|Bağımsız değişken türü|Boyut bağımsız değişkeni güvenli sürümünde?|
|---------------|----------------------------|----------------------|--------------------------------------|
|`c`|karakter. İle kullanıldığında `scanf` İşlevler, tek baytlı karakter; ile kullanıldığında belirtir `wscanf` İşlevler, geniş karakter belirtir. Normalde atlanır beyaz boşluk karakterleri okuma `c` belirtilir. Sonraki-boşluk-olmayan tek baytlı karakter okumak için kullandığınız `%1s`; sonraki olmayan boşluk geniş karakteri okuyun, kullanın `%1ws`.|İşaretçi `char` ile kullanıldığında `scanf` İşlevler, işaretçi `wchar_t` ile kullanıldığında `wscanf` işlevleri.|Gerekli. Boyut, null sonlandırıcıyı ortasının içermez.|
|`C`|Ters boyutu karakter. İle kullanıldığında `scanf` İşlevler, geniş karakter; ile kullanıldığında belirtir `wscanf` İşlevler, tek baytlı karakter belirtir. Normalde atlanır beyaz boşluk karakterleri okuma `C` belirtilir. Sonraki-boşluk-olmayan tek baytlı karakter okumak için kullandığınız `%1s`; sonraki olmayan boşluk geniş karakteri okuyun, kullanın `%1ws`.|İşaretçi `wchar_t` ile kullanıldığında `scanf` İşlevler, işaretçi `char` ile kullanıldığında `wscanf` işlevleri.|Gerekli. Boyut bağımsız değişkeni, null sonlandırıcıyı ortasının içermez.|
|`d`|Ondalık tamsayı.|İşaretçi `int`.|Hayır.|
|`i`|Bir tamsayı. Giriş dizesinin "0 x" veya "0 X" ile başlıyorsa onaltılık dize "0" ile aksi takdirde ondalık başlıyorsa sekizlik.|İşaretçi `int`.|Hayır.|
|`o`|Sekizlik bir tamsayı.|İşaretçi `int`.|Hayır.|
|`p`|İşaretçi adresi onaltılık basamak olarak. Okuma basamak sayısı makine mimarisine bağımlı bir işaretçi (BITS), 32 veya 64 boyutuna bağlıdır. "0 x" veya "0 X" ön ekleri kabul edilir.|İşaretçi `void*`.|Hayır.|
|`u`|İmzalanmamış ondalık tamsayı.|İşaretçi `unsigned int`.|Hayır.|
|`x`|Onaltılık tamsayı.|İşaretçi `int`.|Hayır.|
|`e`, `E`, `f`, `F`, `g`, `G`|Kayan nokta değeri oluşan isteğe bağlı işareti (+ veya -), bir isteğe bağlı olarak imzalı bir tamsayı değeri tarafından izlenen isteğe bağlı üs ("e" veya "E") ve ondalık nokta içeren bir veya daha fazla ondalık basamak dizisi.|İşaretçi `float`.|Hayır.|
|`a`, `A`|Bir veya daha fazla onaltılık basamak isteğe bağlı bir ondalık ve ondalık bir değer tarafından izlenen bir üstel ("p" veya "P") içeren bir dizi oluşan kayan nokta değeri.|İşaretçi `float`.|Hayır.|
|`n`|Herhangi bir giriş akışı veya arabellek okuyun.|İşaretçi `int`, depolanan rakam veya karakter sayısını başarıyla olduğu içine akıştan okunan veya arabellek geçerli çağrıda o noktaya kadar `scanf` işlevleri veya `wscanf` işlevleri.|Hayır.|
|`s`|Dize, ilk boşluk karakteri (boşluk, sekme veya yeni satır) kadar. Boşluk karakterleri tarafından ayrılmış olmayan dizeler okumak için köşeli ayraçların kullanın (`[ ]`) bölümünde açıklandığı gibi [scanf genişlik belirtimi](../c-runtime-library/scanf-width-specification.md).|İle kullanıldığında `scanf` İşlevler, tek baytlı karakter dizisi; ile kullanıldığında gösterir `wscanf` İşlevler, geniş karakter dizisi olduğunu belirtir. Her iki durumda da, karakter dizisinin giriş alanı yanı sıra otomatik olarak eklenir sondaki boş karakter için yeterince büyük olması gerekir.|Gerekli. Boyut, null sonlandırıcıyı ortasının içerir.|
|`S`|Bunun tersi boyutu ilk boşluk karakteri (boşluk, sekme veya yeni satır) en fazla karakter dizesi. Boşluk karakterleri tarafından ayrılmış olmayan dizeler okumak için köşeli ayraçların kullanın (`[ ]`) bölümünde açıklandığı gibi [scanf genişlik belirtimi](../c-runtime-library/scanf-width-specification.md).|İle kullanıldığında `scanf` İşlevler, geniş karakter dizisi; ile kullanıldığında gösterir `wscanf` İşlevler, tek baytlı karakter dizisi olduğunu belirtir. Her iki durumda da, karakter dizisinin giriş alanı yanı sıra otomatik olarak eklenir sondaki boş karakter için yeterince büyük olması gerekir.|Gerekli. Boyut, null sonlandırıcıyı ortasının içerir.|

Boyut bağımsız değişkenleri gerektiriyorsa, uygulandıkları bağımsız değişkeni takip parametre listesinde geçirilmelidir. Örneğin, aşağıdaki kodu:

```
char string1[11], string2[9];
scanf_s("%10s %8s", string1, 11, string2, 9);
```

dize uzunluğu en fazla 10 ile okur `string1`ve bir dize uzunluğu en fazla 8 `string2`. Arabellek boyutlarını genişlik belirtimleri alanı itibaren en az bir fazla null Sonlandırıcı için ayrılmış olması gerekir.

Biçim dizesi tek baytlı karakter veya geniş karakter sürümünü işlevi kullanılıp kullanılmamasına bakılmaksızın tek baytlı veya geniş karakter giriş başa çıkabilir. Bu nedenle, tek baytlı veya geniş karakterleri okumak için `scanf` işlevleri ve `wscanf` İşlevler, biçim belirticileri şu şekilde kullanın.

|Karakter olarak okumak için|Bu işlevi kullanın|Bu biçim tanımlayıcıları ile|
|--------------------------|-----------------------|----------------------------------|
|tek bayt|`scanf` İşlevleri|`c`, `hc`, veya `hC`|
|tek bayt|`wscanf` İşlevleri|`C`, `hc`, veya `hC`|
|geniş|`wscanf` İşlevleri|`c`, `lc`, veya `lC`|
|geniş|`scanf` İşlevleri|`C`, `lc`, veya `lC`|

Dizeleri tarama `scanf` işlevler ve `wscanf` işlevlerini kullanan yukarıdaki tabloda biçim türü-belirteçleriyle `s` ve `S` yerine `c` ve `C`.

## <a name="see-also"></a>Ayrıca Bkz.

[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)