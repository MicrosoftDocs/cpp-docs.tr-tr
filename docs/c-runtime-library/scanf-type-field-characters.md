---
title: scanf Türü Alan Karakterleri
ms.date: 11/04/2016
helpviewer_keywords:
- scanf function, type field characters
ms.assetid: 5d546a84-715b-44ca-b1c5-bbe997f9ff62
ms.openlocfilehash: dbc6142a87bee00b130589fef5ab92a44f189864
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444743"
---
# <a name="scanf-type-field-characters"></a>scanf Türü Alan Karakterleri

Aşağıdaki bilgiler, `scanf_s`gibi güvenli sürümler dahil olmak üzere `scanf` işlevleri için geçerlidir.

`type` karakter, gereken tek Biçim alanıdır; tüm isteğe bağlı biçim alanlarından sonra görüntülenir. `type` karakter, ilişkili bağımsız değişkenin bir karakter, dize veya sayı olarak yorumlanıp yorumlanmadığını belirler.

### <a name="type-characters-for-scanf-functions"></a>Scanf işlevleri için tür karakterleri

|Karakter|Beklenen giriş türü|Bağımsız değişken türü|Güvenli sürümde boyut bağımsız değişkeni mi?|
|---------------|----------------------------|----------------------|--------------------------------------|
|`c`|İnde. `scanf` işlevleriyle kullanıldığında, tek baytlık karakteri belirtir; `wscanf` işlevleriyle kullanıldığında, geniş karakter belirtir. `c` belirtildiğinde normalde atlanan boşluk karakterleri okunacaktır. Beyaz boşluk olmayan tek baytlı karakteri okumak için `%1s`kullanın; boşluk olmayan sonraki geniş karakteri okumak için `%1ws`kullanın.|`scanf` işlevleriyle kullanıldığında `char` işaretçisi, `wscanf` işlevleriyle kullanıldığında `wchar_t` işaretçisi.|Gereklidir. Boyut, null Sonlandırıcı için boşluk içermiyor.|
|`C`|Karşıt boyut karakteri. `scanf` işlevleriyle kullanıldığında, geniş karakter belirtir; `wscanf` işlevleriyle kullanıldığında, tek baytlık karakteri belirtir. `C` belirtildiğinde normalde atlanan boşluk karakterleri okunacaktır. Beyaz boşluk olmayan tek baytlı karakteri okumak için `%1s`kullanın; boşluk olmayan sonraki geniş karakteri okumak için `%1ws`kullanın.|`scanf` işlevleriyle kullanıldığında `wchar_t` işaretçisi, `wscanf` işlevleriyle kullanıldığında `char` işaretçisi.|Gereklidir. Boyut bağımsız değişkeni, null Sonlandırıcı için boşluk içermiyor.|
|`d`|Ondalık tam sayı.|`int`işaretçisi.|Hayır.|
|`i`|Bir tamsayı. Giriş dizesi "0x" veya "0X" ile başlıyorsa onaltılık, dize "0" ile başlıyorsa sekizlik, aksi durumda Decimal.|`int`işaretçisi.|Hayır.|
|`o`|Sekizlik tamsayı.|`int`işaretçisi.|Hayır.|
|`p`|Onaltılık rakamlarla bir işaretçi adresi. Okunan basamakların en fazla sayısı, makine mimarisine bağlı olarak bir işaretçinin boyutuna bağlıdır (32 veya 64 bit). "0x" veya "0X", ön ekler olarak kabul edilir.|`void*`işaretçisi.|Hayır.|
|`u`|İşaretsiz ondalık tamsayı.|`unsigned int`işaretçisi.|Hayır.|
|`x`|Onaltılık tamsayı.|`int`işaretçisi.|Hayır.|
|`e`, `E`, `f`, `F`, `g`, `G`|İsteğe bağlı işareti (+ veya-), ondalık noktası içeren bir veya daha fazla ondalık basamak serisini ve isteğe bağlı üs ("e" ya da "E") ve isteğe bağlı olarak işaretli bir tamsayı değeri içeren kayan nokta değeri.|`float`işaretçisi.|Hayır.|
|`a`, `A`|İsteğe bağlı bir ondalık noktası içeren bir veya daha fazla onaltılı basamaktan oluşan kayan nokta değeri ve ardından bir üs ("p" veya "P"), ardından ondalık bir değer.|`float`işaretçisi.|Hayır.|
|`n`|Akıştan veya arabellekten giriş okunamadı.|`int`işaretçisi, içinde, geçerli `scanf` işlevlere veya `wscanf` işlevlere kadar olan akıştan veya arabelleğinden bu noktaya kadar başarıyla okunan karakter sayısı.|Hayır.|
|`s`|Dize, en fazla ilk boşluk karakteri (boşluk, sekme veya yeni satır). Boşluk karakterleriyle sınırlandırılmış dizeleri okumak için, [scanf Width belirtiminde](../c-runtime-library/scanf-width-specification.md)anlatıldığı gibi köşeli ayraç (`[ ]`) kümesini kullanın.|`scanf` işlevleriyle kullanıldığında, tek baytlık karakter dizisini belirtir; `wscanf` işlevleriyle kullanıldığında, geniş karakter dizisini belirtir. Her iki durumda da, karakter dizisi giriş alanı için yeterince büyük olmalı ve otomatik olarak eklenen null karakterini sonlandırıyor.|Gereklidir. Boyut, null Sonlandırıcı için boşluk içeriyor.|
|`S`|Ters boyut karakter dizesi, ilk beyaz boşluk karakteri (boşluk, sekme veya yeni satır). Boşluk karakterleriyle sınırlandırılmış dizeleri okumak için, [scanf Width belirtiminde](../c-runtime-library/scanf-width-specification.md)anlatıldığı gibi köşeli ayraç (`[ ]`) kümesini kullanın.|`scanf` işlevleriyle kullanıldığında, geniş karakterli diziyi belirtir; `wscanf` işlevleriyle kullanıldığında, tek baytlık karakter dizisini belirtir. Her iki durumda da, karakter dizisi giriş alanı için yeterince büyük olmalı ve otomatik olarak eklenen null karakterini sonlandırıyor.|Gereklidir. Boyut, null Sonlandırıcı için boşluk içeriyor.|

Gerekirse, boyut bağımsız değişkenleri, uygulanan bağımsız değişkenin hemen ardından parametre listesinde geçirilmelidir. Örneğin, aşağıdaki kod:

```
char string1[11], string2[9];
scanf_s("%10s %8s", string1, 11, string2, 9);
```

`string1`en fazla 10 uzunluğuna sahip bir dize ve `string2`en fazla 8 uzunluğunda bir dize okur. Boşluk, null Sonlandırıcı için ayrılmış olması gerektiğinden, arabellek boyutları en az bir genişlik belirtimden daha büyük olmalıdır.

Biçim dizesi, tek baytlı karakter veya işlevin geniş karakterli sürümünün kullanılıp kullanılmadığına bakılmaksızın tek baytlık veya geniş karakter girişini işleyebilir. Bu nedenle, `scanf` işlevleri ve `wscanf` işlevleriyle tek baytlık veya geniş karakterleri okumak için, biçim belirticilerini aşağıdaki gibi kullanın.

|Karakteri şöyle okumak için|Bu işlevi kullanın|Bu biçim belirticileriyle|
|--------------------------|-----------------------|----------------------------------|
|tek bayt|`scanf` işlevleri|`c`, `hc`veya `hC`|
|tek bayt|`wscanf` işlevleri|`C`, `hc`veya `hC`|
|geniş|`wscanf` işlevleri|`c`, `lc`veya `lC`|
|geniş|`scanf` işlevleri|`C`, `lc`veya `lC`|

`scanf` işlevlerle ve `wscanf` işlevlerle dizeleri taramak için yukarıdaki tabloyu, `c` ve `C`yerine biçim tür belirticileri `s` ve `S` kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)
