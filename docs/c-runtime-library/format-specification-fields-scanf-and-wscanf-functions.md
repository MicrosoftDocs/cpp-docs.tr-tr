---
title: 'Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri'
ms.date: 11/04/2016
api_location:
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wscanf
- scanf
helpviewer_keywords:
- width, specifications in scanf function
- scanf format specifications
- scanf width specifications
- scanf type field characters
- type fields, scanf function
- format specification fields for scanf function
- type fields
ms.assetid: 7e95de1b-0b71-4de3-9f81-c9560c78e039
ms.openlocfilehash: 78b64ea29aebdfb355525be69dc7a9fdece55367
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944410"
---
# <a name="format-specification-fields-scanf-and-wscanf-functions"></a>Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri

Buradaki bilgiler, güvenli sürümler dahil olmak `scanf` üzere tüm işlev ailesine uygulanır ve `scanf` işlevlere giriş akışı gibi giriş akışını nasıl ayrıştırılacağını `stdin` `scanf`söylemekiçinkullanılansembolleriaçıklar., program değişkenlerine eklenen değerlere.

Biçim belirtimi aşağıdaki biçimdedir:

`%`[`*`] [[Width](../c-runtime-library/scanf-width-specification.md)] [{[h &#124; l &#124; ll &#124; I64 &#124; l](../c-runtime-library/scanf-width-specification.md)}][tür](../c-runtime-library/scanf-type-field-characters.md)

`format` Bağımsız değişkeni, girişin yorumunu belirtir ve aşağıdakilerden birini veya birkaçını içerebilir:

- Boşluk karakterleri: boş (' '); sekme (' \t '); veya yeni satır (' \n '). Boşluk karakteri, bir sonraki beyaz `scanf` boşluk olmayan karaktere kadar giriş içindeki tüm birbirini izleyen boşluk karakterlerini okumaya, ancak depolamamasına neden olur. Biçimdeki bir boşluk karakteri herhangi bir sayıyla (0 dahil) ve girişte boşluk karakterlerinin birleşiminden eşleşir.

- Yüzde işareti (`%`) dışında boşluk olmayan karakterler. Boşluk olmayan bir karakter, eşleşen boşluk olmayan `scanf` bir karakteri okumaya, ancak depolamamasına neden olur. Giriş akışındaki sonraki karakter eşleşmiyorsa, `scanf` sonlanır.

- Yüzde işaretiyle (`%`) tanıtılan biçim belirtimleri. Biçim belirtimi, girişte `scanf` belirtilen türdeki karakterleri okuyup dönüştürmeye neden olur. Değer, bağımsız değişken listesindeki bir bağımsız değişkene atanır.

Biçim soldan sağa okunurdur. Biçim belirtimlerinin dışındaki karakterlerin, giriş akışındaki karakterlerin dizisiyle eşleşmesi beklenir; Giriş akışındaki eşleşen karakterler tarandı ancak depolanmaz. Giriş akışındaki bir karakter biçim belirtimiyle çakışırsa, `scanf` sonlanır ve karakter giriş akışında okunmamışsınız gibi bırakılır.

İlk biçim belirtimine rastlandı, ilk giriş alanının değeri bu belirtime göre dönüştürülür ve ilki `argument`tarafından belirtilen konumda depolanır. İkinci biçim belirtimi ikinci giriş alanının ikinci `argument`olarak dönüştürülüp depolanmasına ve bu şekilde biçim dizesinin sonuna kadar devam etmesine neden olur.

Bir giriş alanı, ilk boşluk karakterine (boşluk, sekme veya yeni satır) kadar tüm karakterler veya biçim belirtimine göre dönüştürülemediği ilk karaktere kadar veya alan genişliğine (belirtilmişse) ulaşılana kadar tanımlanır. Verilen belirtimlerde çok fazla bağımsız değişken varsa, ek bağımsız değişkenler değerlendirilir ancak yok sayılır. Biçim belirtimi için yeterli bağımsız değişken yoksa sonuçlar öngörülemez.

Biçim belirtiminin her alanı tek bir karakter veya belirli bir biçim seçeneğini belirten bir sayıdır. Son isteğe bağlı biçim alanından sonra görünen karakter,girişalanınınbirkarakter,dizeveyasayıolarakyorumlanıpyorumlanmadığınıbelirler.`type`

En basit biçim belirtimi yalnızca yüzde işareti ve `type` karakteri içerir (örneğin, `%s`). Bir yüzde işareti (`%`), Biçim denetimi karakteri olarak anlamı olmayan bir karakter kullanıyorsa, o karakter ve aşağıdaki karakterler (bir sonraki yüzde işaretine kadar) normal bir karakter dizisi olarak değerlendirilir, yani bir dizisi girişle eşleşmesi gereken karakterler. Örneğin, bir yüzde işareti karakterinin giriş olarak kullanılacağını belirtmek için, kullanın `%%`.

Yüzde işaretini izleyen`*`bir yıldız işareti (), belirtilen türden bir alan olarak yorumlanan bir sonraki giriş alanının atanmasını bastırır. Alan taranır ancak depolanmaz.

İşlevlerin `_s` `scanf` ailesineait`C`güvenli sürümler (son ekine sahip olanlar),,,,,,,,, `c` `s` `S` veya`[`. İşlevlerin `scanf` ailesinin güvenli sürümleri hakkında daha fazla bilgi için bkz. [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md).

## <a name="see-also"></a>Ayrıca bkz.

[scanf Genişlik Belirtimi](../c-runtime-library/scanf-width-specification.md)<br/>
[scanf Türü Alan Karakterleri](../c-runtime-library/scanf-type-field-characters.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)
