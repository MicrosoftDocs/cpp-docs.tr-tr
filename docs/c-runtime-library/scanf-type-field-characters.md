---
title: scanf Türü Alan Karakterleri
ms.date: 11/04/2016
api_location:
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- scanf
helpviewer_keywords:
- scanf function, type field characters
ms.assetid: 5d546a84-715b-44ca-b1c5-bbe997f9ff62
ms.openlocfilehash: 86b57aff9cba5065c7c8053dc26e63e3c0cae169
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957827"
---
# <a name="scanf-type-field-characters"></a>scanf Türü Alan Karakterleri

Aşağıdaki bilgiler, gibi güvenli sürümler `scanf` `scanf_s`dahil olmak üzere herhangi bir işlev ailesinden geçerlidir.

`type` Karakter, gereken tek Biçim alanıdır; tüm isteğe bağlı biçim alanlarından sonra görüntülenir. `type` Karakter, ilişkili bağımsız değişkenin bir karakter, dize veya sayı olarak yorumlanıp yorumlanmadığını belirler.

### <a name="type-characters-for-scanf-functions"></a>Scanf işlevleri için tür karakterleri

|Karakter|Beklenen giriş türü|Bağımsız değişken türü|Güvenli sürümde boyut bağımsız değişkeni mi?|
|---------------|----------------------------|----------------------|--------------------------------------|
|`c`|İnde. `scanf` İşlevleriyle kullanıldığında, tek baytlık karakteri belirtir; `wscanf` işlevlerle kullanıldığında geniş bir karakter belirtir. Belirtildiğinde, normalde atlanan boşluk karakterleri okunacaktır `c` . Beyaz boşluk olmayan sonraki tek baytlı karakteri okumak için, kullanın `%1s`; sonraki boşluk olmayan geniş karakteri okumak için kullanın. `%1ws`|İşlevleriyle kullanıldığında işaretçisi `wchar_t` , işlevlerle birlikte `wscanf` kullanıldığında işaretçisi. `char` `scanf`|Gerekli. Boyut, null Sonlandırıcı için boşluk içermiyor.|
|`C`|Karşıt boyut karakteri. `scanf` İşlevleriyle kullanıldığında, geniş karakter belirtir; `wscanf` işlevlerle kullanıldığında, tek baytlık karakteri belirtir. Belirtildiğinde, normalde atlanan boşluk karakterleri okunacaktır `C` . Beyaz boşluk olmayan sonraki tek baytlı karakteri okumak için, kullanın `%1s`; sonraki boşluk olmayan geniş karakteri okumak için kullanın. `%1ws`|İşlevleriyle kullanıldığında işaretçisi `char` , işlevlerle birlikte `wscanf` kullanıldığında işaretçisi. `wchar_t` `scanf`|Gerekli. Boyut bağımsız değişkeni, null Sonlandırıcı için boşluk içermiyor.|
|`d`|Ondalık tam sayı.|`int`İşaretçi.|Hayır.|
|`i`|Bir tamsayı. Giriş dizesi "0x" veya "0X" ile başlıyorsa onaltılık, dize "0" ile başlıyorsa sekizlik, aksi durumda Decimal.|`int`İşaretçi.|Hayır.|
|`o`|Sekizlik tamsayı.|`int`İşaretçi.|Hayır.|
|`p`|Onaltılık rakamlarla bir işaretçi adresi. Okunan basamakların en fazla sayısı, makine mimarisine bağlı olarak bir işaretçinin boyutuna bağlıdır (32 veya 64 bit). "0x" veya "0X", ön ekler olarak kabul edilir.|`void*`İşaretçi.|Hayır.|
|`u`|İşaretsiz ondalık tamsayı.|`unsigned int`İşaretçi.|Hayır.|
|`x`|Onaltılık tamsayı.|`int`İşaretçi.|Hayır.|
|`e`, `E`, `f`, `F`, `g`, `G`|İsteğe bağlı işareti (+ veya-), ondalık noktası içeren bir veya daha fazla ondalık basamak serisini ve isteğe bağlı üs ("e" ya da "E") ve isteğe bağlı olarak işaretli bir tamsayı değeri içeren kayan nokta değeri.|`float`İşaretçi.|Hayır.|
|`a`, `A`|İsteğe bağlı bir ondalık noktası içeren bir veya daha fazla onaltılı basamaktan oluşan kayan nokta değeri ve ardından bir üs ("p" veya "P"), ardından ondalık bir değer.|`float`İşaretçi.|Hayır.|
|`n`|Akıştan veya arabellekten giriş okunamadı.|Olan işaretçisi `scanf` `wscanf` , ' ye kadar, geçerli işlev veya işlevlere yapılan geçerli çağrıda bulunan Stream veya buffer 'dan başarıyla okunan karakter sayısı. `int`|Hayır.|
|`s`|Dize, en fazla ilk boşluk karakteri (boşluk, sekme veya yeni satır). Boşluk karakterleriyle sınırlandırılmış dizeleri okumak için [scanf Width belirtiminde](../c-runtime-library/scanf-width-specification.md)anlatıldığı gibi köşeli ayraç (`[ ]`) kümesini kullanın.|`scanf` İşlevlerle kullanıldığında, tek baytlık karakter dizisini belirtir; `wscanf` işlevlerle kullanıldığında, geniş karakterli diziyi belirtir. Her iki durumda da, karakter dizisi giriş alanı için yeterince büyük olmalı ve otomatik olarak eklenen null karakterini sonlandırıyor.|Gerekli. Boyut, null Sonlandırıcı için boşluk içeriyor.|
|`S`|Ters boyut karakter dizesi, ilk beyaz boşluk karakteri (boşluk, sekme veya yeni satır). Boşluk karakterleriyle sınırlandırılmış dizeleri okumak için [scanf Width belirtiminde](../c-runtime-library/scanf-width-specification.md)anlatıldığı gibi köşeli ayraç (`[ ]`) kümesini kullanın.|`scanf` İşlevlerle kullanıldığında, geniş karakterli diziyi belirtir; `wscanf` işlevlerle kullanıldığında, tek baytlık karakter dizisini belirtir. Her iki durumda da, karakter dizisi giriş alanı için yeterince büyük olmalı ve otomatik olarak eklenen null karakterini sonlandırıyor.|Gerekli. Boyut, null Sonlandırıcı için boşluk içeriyor.|

Gerekirse, boyut bağımsız değişkenleri, uygulanan bağımsız değişkenin hemen ardından parametre listesinde geçirilmelidir. Örneğin, aşağıdaki kod:

```
char string1[11], string2[9];
scanf_s("%10s %8s", string1, 11, string2, 9);
```

en fazla 10 `string1`uzunluğuna sahip bir dize ve en fazla `string2`8 uzunluğunda bir dize okur. Boşluk, null Sonlandırıcı için ayrılmış olması gerektiğinden, arabellek boyutları en az bir genişlik belirtimden daha büyük olmalıdır.

Biçim dizesi, tek baytlı karakter veya işlevin geniş karakterli sürümünün kullanılıp kullanılmadığına bakılmaksızın tek baytlık veya geniş karakter girişini işleyebilir. Bu nedenle, `scanf` işlevler ve `wscanf` işlevlerle tek baytlık veya geniş karakterleri okumak için aşağıdaki gibi biçim belirticilerini kullanın.

|Karakteri şöyle okumak için|Bu işlevi kullanın|Bu biçim belirticileriyle|
|--------------------------|-----------------------|----------------------------------|
|tek bayt|`scanf` işlevleri|`c`, `hc`, veya`hC`|
|tek bayt|`wscanf` işlevleri|`C`, `hc`, veya`hC`|
|geniş|`wscanf` işlevleri|`c`, `lc`, veya`lC`|
|geniş|`scanf` işlevleri|`C`, `lc`, veya`lC`|

`scanf` İşlevleri işlevlerle ve `wscanf` işlevlerle taramak için yukarıdaki tabloyu `S` biçim türü tanımlayıcılarla `s` , `c` ve `C`yerine kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)
