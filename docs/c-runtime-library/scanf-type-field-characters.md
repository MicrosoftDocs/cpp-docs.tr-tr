---
title: scanf Türü Alan Karakterleri
ms.date: 11/04/2016
helpviewer_keywords:
- scanf function, type field characters
ms.assetid: 5d546a84-715b-44ca-b1c5-bbe997f9ff62
ms.openlocfilehash: 8ea5f53f5c6039cf15836ba995df0d63bd6fcb23
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233905"
---
# <a name="scanf-type-field-characters"></a>scanf Türü Alan Karakterleri

Aşağıdaki bilgiler, gibi `scanf` Güvenli sürümler dahil olmak üzere herhangi bir işlev ailesinden geçerlidir `scanf_s` .

`type`Karakter, gereken tek Biçim alanıdır; tüm isteğe bağlı biçim alanlarından sonra görüntülenir. `type`Karakter, ilişkili bağımsız değişkenin bir karakter, dize veya sayı olarak yorumlanıp yorumlanmadığını belirler.

### <a name="type-characters-for-scanf-functions"></a>Scanf işlevleri için tür karakterleri

|Karakter|Beklenen giriş türü|Bağımsız değişken türü|Güvenli sürümde boyut bağımsız değişkeni mi?|
|---------------|----------------------------|----------------------|--------------------------------------|
|`c`|İnde. `scanf`İşlevleriyle kullanıldığında, tek baytlık karakteri belirtir; `wscanf` işlevlerle kullanıldığında geniş bir karakter belirtir. Belirtildiğinde, normalde atlanan boşluk karakterleri okunacaktır `c` . Beyaz boşluk olmayan sonraki tek baytlı karakteri okumak için, kullanın `%1s` ; sonraki boşluk olmayan geniş karakteri okumak için kullanın `%1ws` .|İşlevleriyle kullanıldığında işaretçisi **`char`** `scanf` , **`wchar_t`** işlevlerle birlikte kullanıldığında işaretçisi `wscanf` .|Gereklidir. Boyut, null Sonlandırıcı için boşluk içermiyor.|
|`C`|Karşıt boyut karakteri. `scanf`İşlevleriyle kullanıldığında, geniş karakter belirtir; `wscanf` işlevlerle kullanıldığında, tek baytlık karakteri belirtir. Belirtildiğinde, normalde atlanan boşluk karakterleri okunacaktır `C` . Beyaz boşluk olmayan sonraki tek baytlı karakteri okumak için, kullanın `%1s` ; sonraki boşluk olmayan geniş karakteri okumak için kullanın `%1ws` .|İşlevleriyle kullanıldığında işaretçisi **`wchar_t`** `scanf` , **`char`** işlevlerle birlikte kullanıldığında işaretçisi `wscanf` .|Gereklidir. Boyut bağımsız değişkeni, null Sonlandırıcı için boşluk içermiyor.|
|`d`|Ondalık tam sayı.|İşaretçi **`int`** .|Hayır.|
|`i`|Bir tamsayı. Giriş dizesi "0x" veya "0X" ile başlıyorsa onaltılık, dize "0" ile başlıyorsa sekizlik, aksi durumda Decimal.|İşaretçi **`int`** .|Hayır.|
|`o`|Sekizlik tamsayı.|İşaretçi **`int`** .|Hayır.|
|`p`|Onaltılık rakamlarla bir işaretçi adresi. Okunan basamakların en fazla sayısı, makine mimarisine bağlı olarak bir işaretçinin boyutuna bağlıdır (32 veya 64 bit). "0x" veya "0X", ön ekler olarak kabul edilir.|İşaretçi **`void*`** .|Hayır.|
|`u`|İşaretsiz ondalık tamsayı.|İşaretçi **`unsigned int`** .|Hayır.|
|`x`|Onaltılık tamsayı.|İşaretçi **`int`** .|Hayır.|
|`e`, `E`, `f`, `F`, `g`, `G`|İsteğe bağlı işareti (+ veya-), ondalık noktası içeren bir veya daha fazla ondalık basamak serisini ve isteğe bağlı üs ("e" ya da "E") ve isteğe bağlı olarak işaretli bir tamsayı değeri içeren kayan nokta değeri.|İşaretçi **`float`** .|Hayır.|
|`a`, `A`|İsteğe bağlı bir ondalık noktası içeren bir veya daha fazla onaltılı basamaktan oluşan kayan nokta değeri ve ardından bir üs ("p" veya "P"), ardından ondalık bir değer.|İşaretçi **`float`** .|Hayır.|
|`n`|Akıştan veya arabellekten giriş okunamadı.|Olan işaretçisi **`int`** , ' ye kadar, geçerli işlev veya işlevlere yapılan geçerli çağrıda bulunan Stream veya buffer 'dan başarıyla okunan karakter sayısı `scanf` `wscanf` .|Hayır.|
|`s`|Dize, en fazla ilk boşluk karakteri (boşluk, sekme veya yeni satır). Boşluk karakterleriyle sınırlandırılmış dizeleri okumak için `[ ]` [scanf Width belirtiminde](../c-runtime-library/scanf-width-specification.md)anlatıldığı gibi köşeli ayraç () kümesini kullanın.|`scanf`İşlevlerle kullanıldığında, tek baytlık karakter dizisini belirtir; `wscanf` işlevlerle kullanıldığında, geniş karakterli diziyi belirtir. Her iki durumda da, karakter dizisi giriş alanı için yeterince büyük olmalı ve otomatik olarak eklenen null karakterini sonlandırıyor.|Gereklidir. Boyut, null Sonlandırıcı için boşluk içeriyor.|
|`S`|Ters boyut karakter dizesi, ilk beyaz boşluk karakteri (boşluk, sekme veya yeni satır). Boşluk karakterleriyle sınırlandırılmış dizeleri okumak için `[ ]` [scanf Width belirtiminde](../c-runtime-library/scanf-width-specification.md)anlatıldığı gibi köşeli ayraç () kümesini kullanın.|`scanf`İşlevlerle kullanıldığında, geniş karakterli diziyi belirtir; `wscanf` işlevlerle kullanıldığında, tek baytlık karakter dizisini belirtir. Her iki durumda da, karakter dizisi giriş alanı için yeterince büyük olmalı ve otomatik olarak eklenen null karakterini sonlandırıyor.|Gereklidir. Boyut, null Sonlandırıcı için boşluk içeriyor.|

Gerekirse, boyut bağımsız değişkenleri, uygulanan bağımsız değişkenin hemen ardından parametre listesinde geçirilmelidir. Örneğin, aşağıdaki kod:

```
char string1[11], string2[9];
scanf_s("%10s %8s", string1, 11, string2, 9);
```

en fazla 10 uzunluğuna sahip bir dize `string1` ve en fazla 8 uzunluğunda bir dize okur `string2` . Boşluk, null Sonlandırıcı için ayrılmış olması gerektiğinden, arabellek boyutları en az bir genişlik belirtimden daha büyük olmalıdır.

Biçim dizesi, tek baytlı karakter veya işlevin geniş karakterli sürümünün kullanılıp kullanılmadığına bakılmaksızın tek baytlık veya geniş karakter girişini işleyebilir. Bu nedenle, işlevler ve işlevlerle tek baytlık veya geniş karakterleri okumak için `scanf` `wscanf` aşağıdaki gibi biçim belirticilerini kullanın.

|Karakteri şöyle okumak için|Bu işlevi kullanın|Bu biçim belirticileriyle|
|--------------------------|-----------------------|----------------------------------|
|tek bayt|`scanf` işlevleri|`c`, `hc` , veya`hC`|
|tek bayt|`wscanf` işlevleri|`C`, `hc` , veya`hC`|
|geniş|`wscanf` işlevleri|`c`, `lc` , veya`lC`|
|geniş|`scanf` işlevleri|`C`, `lc` , veya`lC`|

`scanf`İşlevleri işlevlerle ve işlevlerle taramak için `wscanf` Yukarıdaki tabloyu biçim türü tanımlayıcılarla, `s` `S` ve yerine kullanın `c` `C` .

## <a name="see-also"></a>Ayrıca bkz.

[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)
