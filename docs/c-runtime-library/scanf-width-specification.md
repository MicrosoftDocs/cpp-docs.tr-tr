---
title: sacnf Genişlik Belirtimi
ms.date: 11/04/2016
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- scanf
helpviewer_keywords:
- scanf function, width specification
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
ms.openlocfilehash: 1431002a7e7d0054ac20c05c76b05cabc96177c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390821"
---
# <a name="scanf-width-specification"></a>sacnf Genişlik Belirtimi

Bu bilgiler, Biçim dizesinde yorumunu geçerlidir `scanf` ailesindeki işlevlerin güvenli sürümleri gibi `scanf_s`. Bu işlevler, normalde giriş akışı, bir dizi belirteçleri ayrılmıştır varsayılır. Belirteçleri doğal sonuna kadar sayısal metne dönüştürülemedi ilk karakter tarafından belirtildiği gibi bir sayısal veri türü sayısal türleri söz konusu olduğunda veya boşluk (boşluk, sekme veya yeni satır) tarafından ayrılır. Ancak, bir belirteç doğal bitiminden önce durdurmak için giriş ayrıştırma neden genişlik belirtimi kullanılabilir.

*Genişliği* karakter arasında oluşur belirtimi `%` ve adlı bir pozitif tamsayı içerebilir tür alanı tanımlayıcısı *genişliği* alan ve bir veya daha fazla karakter tür bir tamsayı türü olup olmadığına dair bir gösterge gibi alan değiştiricileri olarak düşünülebilecek alanın boyutunu belirten **kısa** veya **uzun**. Bu tür karakterler boyut öneki adlandırılır.

## <a name="the-width-field"></a>Genişlik alanı

*Genişliği* Bu alan için okunacak maksimum karakter sayısını denetleme bir ondalık tamsayı alanıdır. En fazla *genişliği* karakter dönüştürülür ve karşılık gelen konumunda depolanan `argument`. Az *genişliği* karakterler olabilir (boşluk, sekme veya yeni satır) boşluk veya göre verilen biçime dönüştürülemez karakter önce oluşursa okuma *genişliği* ulaşıldığında.

Bu işlevlerin güvenli sürümleri tarafından gerekli arabellek boyutu bağımsız birbirinden ayrı ve genişlik belirtimi (yani, `scanf_s`, `wscanf_s`vb..). Aşağıdaki örnekte, genişlik belirtimi 20 olur olduğunu belirten en fazla 20 karakter giriş akışından okunacak olan. Arabellek uzunluğu yer olası 20 karakter artı null Sonlandırıcı içerir 21,'dir:

```C
char str[21];
scanf_s("%20s", str, 21);
```

Varsa *genişliği* alan kullanılmaz, `scanf_s` dizeye tüm belirteç okumaya çalışacaktır. Belirtilen boyut tüm belirteç tutmak için yeterince büyük değilse, hiçbir şey hedef dizeye yazılır. Varsa *genişliği* alanı belirtilirse, ardından ilk *genişliği* belirteci karakterleri hedef dize null Sonlandırıcı ile yazılır.

## <a name="the-size-prefix"></a>Boyut öneki

İsteğe bağlı önekleri **h**, **l**, **ll**, **I64**, ve **L** boyutunubelirtmek`argument`(uzun veya kısa, tek baytlı karakter veya geniş karakter, değiştirilen türü karakter bağlı olarak). Bu biçim belirtimi karakter türü karakter ile kullanılan `scanf` veya `wscanf` işlevleri aşağıdaki tabloda gösterildiği gibi değişkenleri yorumu belirtin. Tür önek **I64** bir Microsoft uzantısıdır ve ANSI uyumlu değil. Tür karakterleri ve bunların anlamlarını açıklayan "Karakter scanf işlevleri için tür" tablosunda açıklanan [scanf türü alan karakterleri](../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> **h**, **l**, ve **L** ön ekleri veri türü ile kullanıldığında Microsoft genişletmeleridir `char`.

### <a name="size-prefixes-for-scanf-and-wscanf-format-type-specifiers"></a>Scanf ve wscanf biçim türü belirteçleri için boyut önekleri

|Belirtmek için|Önek kullanın|Tür belirticisiyle|
|----------------|----------------|-------------------------|
|**double**|**m**|**e**, **E**, **f**, **g**, veya **G**|
|**uzun çift** (aynı çift)|**L**|**e**, **E**, **f**, **g**, veya **G**|
|**Long int**|**m**|**d**, **miyim**, **o**, **x**, veya **X**|
|**İmzasız Long int**|**m**|**u**|
|**Long long**|**Tümünü**|**d**, **miyim**, **o**, **x**, veya **X**|
|`short int`|**h**|**d**, **miyim**, **o**, **x**, veya **X**|
|**işaretsiz kısa tamsayı**|**h**|**u**|
|__**int64**|**I64**|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|Tek baytlı karakter ile `scanf`|**h**|**c** veya **C**|
|Tek baytlı karakter ile `wscanf`|**h**|**c** veya **C**|
|Geniş karakter ile `scanf`|**m**|**c** veya **C**|
|Geniş karakter ile `wscanf`|**m**|**c**, veya **C**|
|Tek baytlı - karakter dizesi ile `scanf`|**h**|**s** veya **S**|
|Tek baytlı - karakter dizesi ile `wscanf`|**h**|**s** veya **S**|
|Geniş karakter dizesi ile `scanf`|**m**|**s** veya **S**|
|Geniş karakter dizesi ile `wscanf`|**m**|**s** veya **S**|

Aşağıdaki örneklerde **h** ve **l** ile `scanf_s` işlevleri ve `wscanf_s` İşlevler:

```C
scanf_s("%ls", &x, 2);     // Read a wide-character string
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character
```

Güvenli olmayan bir işlevde kullanıyorsanız `scanf` ailesi, önceki bağımsız değişken arabellek uzunluğunu gösteren boyut parametreyi atlayın.

## <a name="reading-undelimited-strings"></a>Okuma sınırlandırılmamış dizeler

Boşluk tarafından ayrılmış olmayan dizeler okumak için karakter, köşeli ayraçlar içindeki karakter kümesi (**[]**) için yerine **s** tür karakteri (dize). Köşeli ayraçlar içindeki karakter kümesini denetim dize olarak adlandırılır. Karşılık gelen giriş alanını denetim dizesinde görünmez ilk karaktere okuyun. Kümedeki ilk karakteri bir şapka olup olmadığını (**^**), ters bir etkisi: Giriş alanı karakter kümesini geri kalanında görünen ilk karaktere okuyun.

Unutmayın **% [a-z]** ve **[z-a] %** eşdeğer olarak yorumlanır **% [abcde... z]**. Bu, bir ortak `scanf` işlevi uzantısı, ancak ANSI standardı, gerekmediğini unutmayın.

## <a name="reading-unterminated-strings"></a>Okuma Sonlandırılmamış dizeleri

Bir sonlandırıcı null karakteri ('\0') depolamadan bir dize depolamak için belirtimi kullanın **%** <em>n</em>**c** burada *n* ondalık bir tamsayıdır. Bu durumda, **c** türü karakter bağımsız değişkeni bir karakter dizisine bir işaretçi olduğunu gösterir. Sonraki *n* karakterleri belirtilen konuma giriş akışından okuma ve hiçbir null karakteri ('\0') eklenir. Varsa *n* belirtilmezse, varsayılan değer 1'dir.

## <a name="when-scanf-stops-reading-a-field"></a>Scanf bir alanının okunmasını durduğunda

`scanf` İşlevi, her bir giriş alanı, karakter tarar. Bir boşluk karakteri için çeşitli nedenlerle ulaşmadan önce belirli bir giriş alanını okuma durdurabilir:

- Belirtilen genişlik ulaşıldı.

- Sonraki karakteri dönüştürülemez belirtildiği gibi.

- Eşleştirilecek beklenen denetim dizesindeki bir karakter ile sonraki karakter çakışıyor.

- Belirtilen karakter kümesinde görünmesini sonraki karakteri başarısız olur.

Herhangi bir nedenle zaman `scanf` işlevi, giriş alanını okuma durdurur, sonraki giriş alanı okunmamış ilk karakterde başlamak için değerlendirilir. Çakışan bir karakter varsa, kabul okunmamış ve sonraki giriş alanı ilk karakteri veya giriş akışında sonraki okuma işlemleri ilk karakteri.

## <a name="see-also"></a>Ayrıca bkz.

[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)<br/>
[scanf Türü Alan Karakterleri](../c-runtime-library/scanf-type-field-characters.md)<br/>
