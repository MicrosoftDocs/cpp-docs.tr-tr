---
title: 'Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri'
ms.date: 11/04/2016
ms.topic: reference
ms.custom: contperfq1
helpviewer_keywords:
- width, specifications in scanf function
- scanf format specifications
- scanf width specifications
- scanf type field characters
- type fields, scanf function
- format specification fields for scanf function
- type fields
ms.assetid: 7e95de1b-0b71-4de3-9f81-c9560c78e039
ms.openlocfilehash: 4be7aa5e0790f0124890ee981ffd58e3027ea59b
ms.sourcegitcommit: 111ee74772d7f308d3414b5d42cbc1e90287f081
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88659337"
---
# <a name="format-specification-fields-scanf-and-wscanf-functions"></a>Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri

Buradaki bilgiler `scanf` , güvenli sürümler dahil olmak üzere tüm işlev ailesine uygulanır ve işlevleri, giriş `scanf` akışı gibi giriş akışını `stdin` `scanf` Program değişkenlerine eklenen değerlere nasıl ayrıştıracağını söylemek için kullanılan sembolleri açıklar.

Biçim belirtimi aşağıdaki biçimdedir:

`%`[ `*` ] [[Width](../c-runtime-library/scanf-width-specification.md)] [{[h &#124; l &#124; ll &#124; I64 &#124; l](../c-runtime-library/scanf-width-specification.md)}][tür](../c-runtime-library/scanf-type-field-characters.md)

`format`Bağımsız değişkeni, girişin yorumunu belirtir ve aşağıdakilerden birini veya birkaçını içerebilir:

- Boşluk karakterleri: boş (' '); sekme (' \t '); veya yeni satır (' \n '). Boşluk karakteri `scanf` , bir sonraki beyaz boşluk olmayan karaktere kadar giriş içindeki tüm birbirini izleyen boşluk karakterlerini okumaya, ancak depolamamasına neden olur. Biçimdeki bir boşluk karakteri herhangi bir sayıyla (0 dahil) ve girişte boşluk karakterlerinin birleşiminden eşleşir.

- Yüzde işareti () dışında boşluk olmayan karakterler `%` . Boşluk olmayan bir karakter `scanf` , eşleşen boşluk olmayan bir karakteri okumaya, ancak depolamamasına neden olur. Giriş akışındaki sonraki karakter eşleşmiyorsa, `scanf` sonlanır.

- Yüzde işaretiyle () tanıtılan biçim belirtimleri `%` . Biçim belirtimi `scanf` , girişte belirtilen türdeki karakterleri okuyup dönüştürmeye neden olur. Değer, bağımsız değişken listesindeki bir bağımsız değişkene atanır.

Biçim soldan sağa okunurdur. Biçim belirtimlerinin dışındaki karakterlerin, giriş akışındaki karakterlerin dizisiyle eşleşmesi beklenir; Giriş akışındaki eşleşen karakterler tarandı ancak depolanmaz. Giriş akışındaki bir karakter biçim belirtimiyle çakışırsa, `scanf` sonlanır ve karakter giriş akışında okunmamışsınız gibi bırakılır.

İlk biçim belirtimine rastlandı, ilk giriş alanının değeri bu belirtime göre dönüştürülür ve ilki tarafından belirtilen konumda depolanır `argument` . İkinci biçim belirtimi ikinci giriş alanının ikinci olarak dönüştürülüp depolanmasına ve bu `argument` şekilde biçim dizesinin sonuna kadar devam etmesine neden olur.

Bir giriş alanı, ilk boşluk karakterine (boşluk, sekme veya yeni satır) kadar tüm karakterler veya biçim belirtimine göre dönüştürülemediği ilk karaktere kadar veya alan genişliğine (belirtilmişse) ulaşılana kadar tanımlanır. Verilen belirtimlerde çok fazla bağımsız değişken varsa, ek bağımsız değişkenler değerlendirilir ancak yok sayılır. Biçim belirtimi için yeterli bağımsız değişken yoksa sonuçlar öngörülemez.

Biçim belirtiminin her alanı tek bir karakter veya belirli bir biçim seçeneğini belirten bir sayıdır. `type`Son isteğe bağlı biçim alanından sonra görünen karakter, giriş alanının bir karakter, dize veya sayı olarak yorumlanıp yorumlanmadığını belirler.

En basit biçim belirtimi yalnızca yüzde işareti ve `type` karakteri içerir (örneğin, `%s` ). Bir yüzde işareti ( `%` ), bir biçim denetimi karakteri olarak anlamı olmayan bir karakter kullanıyorsa, o karakter ve aşağıdaki karakterler (bir sonraki yüzde işaretine kadar) normal bir karakter dizisi, diğer bir deyişle, girişle eşleşmesi gereken bir karakter dizisi olarak değerlendirilir. Örneğin, bir yüzde işareti karakterinin giriş olarak kullanılacağını belirtmek için, kullanın `%%` .

Yüzde işaretini izleyen bir yıldız işareti ( `*` ), belirtilen türden bir alan olarak yorumlanan bir sonraki giriş alanının atanmasını bastırır. Alan taranır ancak depolanmaz.

`_s`İşlevlerin ailesine ait güvenli sürümler (son ekine sahip olanlar) `scanf` ,, veya türündeki her parametrenin hemen ardından bir arabellek boyutu parametresinin geçirilmesini gerektirir `c` `C` `s` `S` `[` . İşlevlerin ailesinin güvenli sürümleri hakkında daha fazla bilgi için `scanf` bkz. [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md).

## <a name="see-also"></a>Ayrıca bkz.

[scanf genişlik belirtimi](../c-runtime-library/scanf-width-specification.md)<br/>
[scanf türü alan karakterleri](../c-runtime-library/scanf-type-field-characters.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)
