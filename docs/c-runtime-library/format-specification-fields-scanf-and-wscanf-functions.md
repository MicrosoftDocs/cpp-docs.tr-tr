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
ms.openlocfilehash: c99b951e0cbbb5d2a295eb336a856bdb6c4cc0e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391954"
---
# <a name="format-specification-fields-scanf-and-wscanf-functions"></a>Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri
Burada yer alan bilgiler tüm geçerli `scanf` güvenli sürümleri de dahil olmak üzere işlevlerin ailesi ve bildirmek için kullanılan simgeler açıklar `scanf` Giriş akışı gibi giriş akışı ayrıştırmayı işlevleri `stdin` için`scanf`, program değişkenleri eklenen değerlerinden.  
  
 Biçim belirtimi aşağıdaki biçime sahiptir:  
  
 `%`[`*`] [[genişliği](../c-runtime-library/scanf-width-specification.md)] [{[h &#124; l &#124; üm &#124; I64 &#124; L](../c-runtime-library/scanf-width-specification.md)}][türü](../c-runtime-library/scanf-type-field-characters.md)  
  
 `format` Bağımsız değişkeni giriş yorumu belirtir ve aşağıdakilerden birini veya birkaçını içerebilir:  
  
-   Boşluk karakterleri: boş (' '); sekme ('\t'); veya yeni satır ('\n'). Bir boşluk karakteri neden `scanf` okuyun, ancak depolama değil tüm ardışık boşluk karakterleri sonraki boşluk olmayan karakter kadar giriş. Herhangi bir sayı (0 dahil) ve boşluk karakterleri giriş birleşimi biçiminde bir boşluk karakterle eşleşir.  
  
-   Yüzde işaretini dışında boşluk olmayan karakterler (`%`). Bir boşluk olmayan karakter neden `scanf` okuyun, ancak değil depolamak, eşleşen bir boşluk olmayan karakter. Giriş akışı sonraki karakteri eşleşmiyorsa `scanf` sonlandırır.  
  
-   Biçim belirtimleri, yüzde işaretiyle sunulan (`%`). Biçim belirtimi neden `scanf` okuyup giriş karakter belirtilen bir türün değerlere Dönüştür. Değer bağımsız değişken bağımsız değişken listesinde atanır.  
  
 Biçim soldan sağa okunur. Giriş akışı karakter dizisi eşleşecek şekilde biçim belirtimleri dışında karakterler beklenen; Giriş akışı eşleşen karakterleri taranan ancak değil depolanır. Giriş akışı karakter biçimi belirtimiyle çakışırsa `scanf` sonlandırır, ve değil okuma değilse gibi karakter Giriş akışı bırakılır.  
  
 İlk biçim belirtimi karşılaşıldığında, ilk giriş alanının değeri bu belirtimine göre dönüştürülür ve ilk tarafından belirtilen konumda depolanan `argument`. İkinci biçim belirtimi dönüştürülür ve ikinci depolanan için ikinci giriş alanını neden `argument`, vb. sonuna kadar biçim dizesi.  
  
 Giriş alanını ilk boşluk karakteri (boşluk, sekme ya da yeni satır) kadar tüm karakterleri olarak tanımlı değil veya ilk kadar biçimi belirtimlerine göre ya da alan genişliği kadar (belirtilmişse) dönüştürülemez karakter ulaştı. Verilen özellikleriyle ilgili çok fazla bağımsız değişken varsa, ek bağımsız değişkenler hesaplanan ancak yoksayıldı. Sonuçları biçim belirtimi için yeterli bağımsız değişken varsa öngörülemeyen sonuçlara yol açabilir.  
  
 Her biçim belirtiminin tek bir karakter ya da belirli biçimlendirme seçeneğini gösterir sayı alanıdır. `type` Sonra son isteğe bağlı biçim alanı görüntülenir, karakteri belirler giriş alanını bir karakter, bir dize veya sayı yorumlanır.  
  
 En basit biçimi belirtimi yalnızca yüzde işareti içeriyor ve bir `type` karakter (örneğin, `%s`). Yüzde işareti (`%`) karakter ve şu karakterleri (kadar sonraki yüzde oturum) olan bir Denetim Biçimlendir karakter olarak hiçbir anlamı sıradan bir karakter dizisi olarak başka bir deyişle, bir dizi kabul sahip olduğunu sonrasında bir karakteri Giriş eşleşmelidir karakter. Örneğin, bir yüzde işareti karakteri giriş olduğunu belirtmek için kullanın `%%`.  
  
 Bir yıldız işareti (`*`) yüzde işaretinden belirtilen türde bir alan yorumlanır sonraki giriş alanını atamasının gizler. Alan taranan ancak değil depolanır.  
  
 Güvenli sürümleri (olanlar `_s` soneki), `scanf` ailesi işlevlerini gerektiren bir arabellek boyutu parametresi hemen her parametre türü geçirilmesi `c`, `C`, `s`, `S`veya `[`. Güvenli sürümleri hakkında daha fazla bilgi için `scanf` ailesi işlevlerini, bkz: [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [sacnf genişlik belirtimi](../c-runtime-library/scanf-width-specification.md)   
 [scanf türü alan karakterleri](../c-runtime-library/scanf-type-field-characters.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)