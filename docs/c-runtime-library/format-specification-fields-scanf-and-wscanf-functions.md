---
title: 'Biçim belirtimi alanları: scanf ve wscanf işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apilocation:
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- wscanf
- scanf
dev_langs:
- C++
helpviewer_keywords:
- width, specifications in scanf function
- scanf format specifications
- scanf width specifications
- scanf type field characters
- type fields, scanf function
- format specification fields for scanf function
- type fields
ms.assetid: 7e95de1b-0b71-4de3-9f81-c9560c78e039
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f99d7dac7878f46fceea4435703a55f2199f374
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094513"
---
# <a name="format-specification-fields-scanf-and-wscanf-functions"></a>Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri

Tüm bilgileri burada geçerli `scanf` işlevlerin güvenli sürümleri dahil olmak üzere, Aile ve bildirmek için kullanılan simgeler açıklar `scanf` nasıl ayrıştıracağını Giriş akışı gibi bir giriş akışı işlevleri `stdin` için`scanf`, program değişkenlere eklenen değerlerine.

Biçim belirtimi aşağıdaki biçime sahiptir:

`%`[`*`] [[genişliği](../c-runtime-library/scanf-width-specification.md)] [{[h &#124; l &#124; ll &#124; I64 &#124; L](../c-runtime-library/scanf-width-specification.md)}][türü](../c-runtime-library/scanf-type-field-characters.md)

`format` Bağımsız değişkeni giriş yorumu belirtir ve bir veya birkaçını içerebilir:

- Beyaz boşluk karakterleri: boş (' '); sekme ('\t'); veya satır başı karakteri ('\n'). Bir boşluk karakteri neden `scanf` okuyun, ancak saklamadığı, giriş sonraki-boşluk-olmayan karaktere kadar tüm ardışık boşluk karakterleri. Herhangi bir sayı (0 dahil) ve beyaz boşluk karakterleri girişteki bir bileşimini biçimde bir boşluk karakteri eşleşir.

- Yüzde işareti dışında boşluk olmayan karakterler (`%`). Bir boşluk olmayan karakter neden `scanf` okuyun, ancak saklamadığı, eşleşen bir boşluk olmayan karakter. Giriş akışındaki sonraki karakteri ile eşleşmiyorsa `scanf` sonlandırır.

- Biçim belirtimleri, yüzde işareti tarafından sunulan (`%`). Biçim belirtimi neden `scanf` okuyup karakterler belirtilen bir türün değerlerine dönüştüren. Bağımsız değişken listesindeki bağımsız değişken değeri atanır.

Biçim, soldan sağa doğru okunur. Giriş akışındaki karakterlerin dizisiyle eşleşecek şekilde biçim belirtimleri dışındaki karakterleri beklenen; Giriş akışı eşleşen karakterleri taranan ancak depolanmadı. Giriş akışı bir karakterin biçim belirtimi ile çakışırsa `scanf` sonlandırır, ve değil okuma gibi giriş akışında karakter kaldı.

İlk biçim belirtimiyle karşılaştığında ilk giriş alanının değeri bu belirtimine göre dönüştürülür ve ilk tarafından belirtilen konumda depolanan `argument`. İkinci biçim belirtimi ikinci giriş alanı dönüştürülür ve ikinci depolanan neden `argument`, biçim dizesinin sonuna aracılığıyla ve benzeri.

Giriş alanını ilk boşluk karakteri (boşluk, sekme veya yeni satır) kadar tüm karakterleri olarak tanımlı değil veya biçim belirtimine göre veya alan genişliği kadar (belirtilmişse) dönüştürülemez karakter kadar ilk ulaşıldığında. Belirli özellikleri için çok fazla bağımsız değişken varsa, ek bağımsız değişkenler değerlendirilir ancak yoksayıldı. Biçim belirtimi için yeterli bağımsız değişken yoksa sonuçlar tahmin edilemez.

Tek bir karakter veya bir özel biçim seçeneği gösteren bir sayı biçim belirtiminin her bir alan eder. `type` Sonra son isteğe bağlı bir biçim alanın görünen karakteri belirler giriş alan bir karakter, bir dize veya sayı yorumlanır.

En basit biçim belirtimi yalnızca yüzde işareti içeriyor ve `type` karakter (örneğin, `%s`). Yüzde işareti (`%`) karakteri ve şu karakterleri (kadar sonraki yüzde işareti) olan bir biçim denetimi karakter olarak anlamı normal bir karakter dizisi olarak diğer bir deyişle, bir dizi işlem sahip bir karakterin ardından karakter giriş eşleşmelidir. Örneğin, bir yüzde işareti karakteri girdi olmaya uygun olduğunu belirtmek için kullanın `%%`.

Bir yıldız işareti (`*`) yüzde işareti aşağıdaki belirtilen türde bir alan olarak yorumlanır sonraki giriş alanı atamasını engeller. Alan taranan ancak depolanmadı.

Güvenli sürümler (olanlar `_s` soneki), `scanf` işlevler ailesini gerektiren bir arabellek büyüklüğü parametresi hemen her parametre türü geçirilmesi `c`, `C`, `s`, `S`veya `[`. Güvenli sürümleri hakkında daha fazla bilgi için `scanf` işlevler ailesini görmek [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md).

## <a name="see-also"></a>Ayrıca Bkz.

[scanf Genişlik Belirtimi](../c-runtime-library/scanf-width-specification.md)<br/>
[scanf Türü Alan Karakterleri](../c-runtime-library/scanf-type-field-characters.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)