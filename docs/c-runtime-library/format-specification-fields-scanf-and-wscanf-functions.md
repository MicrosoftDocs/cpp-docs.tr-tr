---
title: 'Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri'
ms.date: 11/04/2016
helpviewer_keywords:
- width, specifications in scanf function
- scanf format specifications
- scanf width specifications
- scanf type field characters
- type fields, scanf function
- format specification fields for scanf function
- type fields
ms.assetid: 7e95de1b-0b71-4de3-9f81-c9560c78e039
ms.openlocfilehash: 025d4c164d3afe1ca6b05c1c8e76441109cbc4ae
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438369"
---
# <a name="format-specification-fields-scanf-and-wscanf-functions"></a>Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri

Buradaki bilgiler, güvenli sürümler dahil olmak üzere tüm `scanf` işlevleri için geçerlidir ve `scanf` işlevleri, `scanf`için giriş akışı `stdin`, program değişkenlerine eklenen değerlere nasıl ayrıştırılacağını söylemek için kullanılan sembolleri açıklar.

Biçim belirtimi aşağıdaki biçimdedir:

`%`[`*`] [[Width](../c-runtime-library/scanf-width-specification.md)] [{[h &#124; l &#124; ll &#124; I64 &#124; l](../c-runtime-library/scanf-width-specification.md)}][tür](../c-runtime-library/scanf-type-field-characters.md)

`format` bağımsız değişkeni, girişin yorumunu belirtir ve aşağıdakilerden birini veya daha fazlasını içerebilir:

- Boşluk karakterleri: boş (' '); sekme (' \t '); veya yeni satır (' \n '). Boşluk karakteri, bir sonraki boşluk olmayan karaktere kadar giriş içindeki tüm birbirini izleyen boşluk karakterlerini okumasına, ancak depolamamasına `scanf` neden olur. Biçimdeki bir boşluk karakteri herhangi bir sayıyla (0 dahil) ve girişte boşluk karakterlerinin birleşiminden eşleşir.

- Yüzde işareti (`%`) dışında boşluk olmayan karakterler. Boşluk olmayan bir karakter, eşleşen bir boşluk olmayan karakter `scanf` okumasına, ancak depolamamasına neden olur. Giriş akışındaki bir sonraki karakter eşleşmezse `scanf` sonlanır.

- Yüzde işaretiyle (`%`) tanıtılan biçim belirtimleri. Biçim belirtimi `scanf` girişte bulunan karakterleri belirtilen bir türün değerlerine okumasına ve dönüştürmesine neden olur. Değer, bağımsız değişken listesindeki bir bağımsız değişkene atanır.

Biçim soldan sağa okunurdur. Biçim belirtimlerinin dışındaki karakterlerin, giriş akışındaki karakterlerin dizisiyle eşleşmesi beklenir; Giriş akışındaki eşleşen karakterler tarandı ancak depolanmaz. Giriş akışındaki bir karakter biçim belirtimiyle çakışıyorsa, `scanf` sonlanır ve karakter giriş akışında okunmamışsınız gibi bırakılır.

İlk biçim belirtimine rastlandı, ilk giriş alanının değeri bu belirtime göre dönüştürülür ve ilk `argument`tarafından belirtilen konumda depolanır. İkinci biçim belirtimi ikinci giriş alanının ikinci `argument`dönüştürülmesine ve depolanmasına, yani biçim dizesinin sonuna kadar devam etmesine neden olur.

Bir giriş alanı, ilk boşluk karakterine (boşluk, sekme veya yeni satır) kadar tüm karakterler veya biçim belirtimine göre dönüştürülemediği ilk karaktere kadar veya alan genişliğine (belirtilmişse) ulaşılana kadar tanımlanır. Verilen belirtimlerde çok fazla bağımsız değişken varsa, ek bağımsız değişkenler değerlendirilir ancak yok sayılır. Biçim belirtimi için yeterli bağımsız değişken yoksa sonuçlar öngörülemez.

Biçim belirtiminin her alanı tek bir karakter veya belirli bir biçim seçeneğini belirten bir sayıdır. Son isteğe bağlı biçim alanından sonra görünen `type` karakteri, giriş alanının bir karakter, dize veya sayı olarak yorumlanıp yorumlanmadığını belirler.

En basit biçim belirtimi yalnızca yüzde işareti ve bir `type` karakteri içerir (örneğin, `%s`). Bir yüzde işareti (`%`), Biçim denetimi karakteri olarak anlamı olmayan bir karakter tarafından izleniyorsa, o karakter ve aşağıdaki karakterler (bir sonraki yüzde işaretine kadar) normal bir karakter dizisi, diğer bir deyişle, girişle eşleşmesi gereken bir karakter dizisi olarak değerlendirilir. Örneğin, bir yüzde işareti karakterinin giriş olarak kullanılacağını belirtmek için `%%`kullanın.

Yüzde işaretini izleyen bir yıldız işareti (`*`), belirtilen türden bir alan olarak yorumlanan bir sonraki giriş alanının atanmasını bastırır. Alan taranır ancak depolanmaz.

`scanf` işlevlerinin güvenlik ailesine ait güvenli sürümler (`_s` sonekine sahip olanlar), `c`, `C`, `s`, `S` veya `[`türündeki her parametrenin hemen ardından bir arabellek boyutu parametresinin geçirilmesini gerektirir. `scanf` işlevlerinin güvenli sürümleri hakkında daha fazla bilgi için bkz. [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md).

## <a name="see-also"></a>Ayrıca bkz.

[scanf Genişlik Belirtimi](../c-runtime-library/scanf-width-specification.md)<br/>
[scanf Türü Alan Karakterleri](../c-runtime-library/scanf-type-field-characters.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)
