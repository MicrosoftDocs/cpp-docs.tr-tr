---
title: sacnf genişlik belirtimi
ms.date: 10/22/2019
helpviewer_keywords:
- scanf function, width specification
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
ms.openlocfilehash: ea0b2728021e3093ab7818af17e60c598f73587f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444710"
---
# <a name="scanf-width-specification"></a>sacnf genişlik belirtimi

Bu bilgiler, `scanf_s`gibi güvenli sürümler dahil olmak üzere `scanf` işlev ailesinde biçim dizelerinin yorumu için geçerlidir. Bu işlevler normalde giriş akışının bir belirteç dizisine bölündüğünü varsayar. Belirteçler boşluk (boşluk, sekme veya yeni satır) ile veya sayısal türler için, sayısal metin olarak dönüştürülemeyen ilk karakter tarafından belirtildiği gibi sayısal bir veri türünün doğal sonuna kadar ayrılır. Ancak, bir belirtecin doğal sonundan önce girişin ayrıştırılmasını engellemek için genişlik belirtimi kullanılabilir.

*Genişlik* belirtimi, `%` ve tür alanı belirleyicisi arasındaki karakterlerden oluşur. Bu, *Width* alanı olarak adlandırılan pozitif bir tamsayı ve alanın boyutunu belirten bir veya daha fazla karakter içerebilir; bu da, tamsayı türünün **kısa** veya **uzun**olup olmadığına ilişkin bir gösterge gibi, alan türünün değiştiriciler olarak da düşünülebilir. Bu tür karakterler boyut ön eki olarak adlandırılır.

## <a name="the-width-field"></a>Genişlik alanı

*Width* alanı, bu alan için okunacak en fazla karakter sayısını denetleyen pozitif bir ondalık tamsayıdır. En fazla *Genişlik* karakteri dönüştürülmez ve karşılık gelen `argument`depolanmaz. Bir boşluk karakteri veya belirtilen biçime göre dönüştürülemediği bir karakter, *genişliğe* ulaşılmadan önce gerçekleşmediğinde, *Width* 'ten az karakter okunabilir.

Genişlik belirtimi, bu işlevlerin güvenli sürümleri (örneğin, `scanf_s`, `wscanf_s`vb.) için gerekli olan arabellek boyutu bağımsız değişkeninden ayrı ve birbirinden farklıdır. Aşağıdaki örnekte, Width belirtimi 20 ' dir ve giriş akışından 20 ' ye kadar karakter okunacağını gösterir. Arabellek uzunluğu 21 ' dir, bu da olası 20 karakter ve null Sonlandırıcı için yer işareti içerir:

```C
char str[21];
scanf_s("%20s", str, 21);
```

*Genişlik* alanı kullanılmıyorsa, `scanf_s` belirtecin tamamını dizeye okumayı dener. Belirtilen boyut, belirtecin tamamını tutabilecek kadar büyük değilse, hedef dizeye hiçbir şey yazılmaz. *Width* alanı belirtilmişse, belirteçteki ilk *Genişlik* karakterleri, null Sonlandırıcı ile birlikte hedef dizeye yazılır.

## <a name="the-size-prefix"></a>Boyut ön eki

İsteğe bağlı **h**, **HH**, **l**, **ll**, **I64**ve **l** önekleri, `argument` boyutunu (uzun veya kısa, tek baytlı karakter veya geniş karakter) belirtir ve bu da değiştirdikleri tür karakterine bağlıdır. Bu biçim belirtimi karakterleri, aşağıdaki tabloda gösterildiği gibi bağımsız değişkenlerin yorumlanmasını belirtmek için `scanf` veya `wscanf` işlevlerde tür karakterleriyle kullanılır. Tür ön eki **I64** Microsoft uzantısıdır ve standart C ile uyumlu değildir. Tür karakterleri ve anlamları [scanf türü alan karakterleri](../c-runtime-library/scanf-type-field-characters.md)içindeki "scanf Işlevlerine yönelik karakter türleri" tablosunda açıklanmaktadır.

> [!NOTE]
> **H**, **l**ve **l** önekleri, **char**türünde verilerle kullanıldığında Microsoft uzantılarıdır.

### <a name="size-prefixes-for-scanf-and-wscanf-format-type-specifiers"></a>Scanf ve wscanf Format-Type belirticileri için boyut önekleri

|Belirtmek için|Ön ek kullan|Tür belirticisiyle|
|----------------|----------------|-------------------------|
|**double**|**girişindeki**|**e**, **e**, **f**, **g**veya **g**|
|**uzun çift** (Double ile aynı)|**Girişindeki**|**e**, **e**, **f**, **g**veya **g**|
|**long int**|**girişindeki**|**d**, **i**, **o**, **x**veya **x**|
|**uzun işaretsiz int**|**girişindeki**|**larınız**|
|**uzun uzun**|**ceğiz**|**d**, **i**, **o**, **x**veya **x**|
|**kısa tamsayı**|**olsun**|**d**, **i**, **o**, **x**veya **x**|
|**kısa işaretsiz int**|**olsun**|**larınız**|
|**char**|**ss**|**d**, **i**, **o**, **x**veya **x**|
|**işaretsiz karakter**|**ss**|**larınız**|
|**tutulamaz**|**I64**|**d**, **i**, **o**, **u**, **x**veya **x**|
|`scanf` ile tek baytlık karakter|**olsun**|**c** veya **c**|
|`wscanf` ile tek baytlık karakter|**olsun**|**c** veya **c**|
|`scanf` geniş karakter|**girişindeki**|**c** veya **c**|
|`wscanf` geniş karakter|**girişindeki**|**c**veya **c**|
|`scanf` ile tek baytlık karakter dizesi|**olsun**|**s** veya **s**|
|`wscanf` ile tek baytlık karakter dizesi|**olsun**|**s** veya **s**|
|`scanf` olan geniş karakter dizesi|**girişindeki**|**s** veya **s**|
|`wscanf` olan geniş karakter dizesi|**girişindeki**|**s** veya **s**|

Aşağıdaki örnekler, `scanf_s` işlevleri ve `wscanf_s` işlevleri ile **h** ve **l** kullanır:

```C
scanf_s("%ls", &x, 2);     // Read a wide-character string
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character
```

`scanf` ailesinde güvenli olmayan bir işlev kullanıyorsanız, önceki bağımsız değişkenin arabellek uzunluğunu belirten boyut parametresini atlayın.

## <a name="reading-undelimited-strings"></a>Sınırsız dizeleri okuma

Boşluk karakterleriyle sınırlandırılmamış dizeleri okumak için, köşeli ayraçlar ( **[]** ) içindeki bir karakter kümesi, **s** (dize) türü karakteri için yerine kullanılabilir. Köşeli ayraçlar içindeki karakter kümesi, *Denetim dizesi*olarak adlandırılır. Karşılık gelen giriş alanı, denetim dizesinde görünmeyen ilk karaktere okunurdur. Küme içindeki ilk karakter bir şapka ( **^** ) ise, efekt tersine çevrilir: giriş alanı, karakter kümesinin geri kalanında görünen ilk karaktere kadar okunurdur.

% [ **A-z]** ve **% [z-a]** her ikisi de **% [abcde... ile eşdeğer olarak yorumlanır. z]** . Bu, yaygın bir `scanf` işlev uzantısıdır, ancak standart C tarafından gerekli değildir.

## <a name="reading-unterminated-strings"></a>Sonlandırılmamış dizeler okunuyor

Bir dizeyi Sonlandırıcı null karakteri (' \ 0 ') depolamadan depolamak için, N `%Nc`belirtimini kullanın, burada *N* , Decimal bir tamsayıdır. Bu durumda, **c** türü karakteri bağımsız değişkenin bir karakter dizisine bir işaretçi olduğunu gösterir. Sonraki *N* karakteri giriş akışından belirtilen konuma okundu ve hiçbir null karakter (' \ 0 ') eklenmez. *N* belirtilmemişse, varsayılan değeri 1 ' dir.

## <a name="when-scanf-stops-reading-a-field"></a>Scanf bir alanı okumayı durduruyor

`scanf` işlevi her giriş alanını ve karakteri karakteriyle tarar. Bazı nedenlerden biri için bir boşluk karakterine ulaşmadan önce belirli bir giriş alanını okumayı durdurabilir:

- Belirtilen genişliğe ulaşıldı.

- Sonraki karakter, belirtilen şekilde dönüştürülemez.

- Sonraki karakter, bir denetim dizesinde eşleşmesi beklenen bir karakterle çakışıyor.

- Bir sonraki karakter, belirli bir karakter kümesinde görünemez.

Her nedenden dolayı, `scanf` işlevi bir giriş alanını okumayı durdurduğu zaman, sonraki giriş alanı ilk okunmamış karakterden başlayarak kabul edilir. Çakışan karakter, varsa, okunmamış olarak değerlendirilir. Bu, sonraki giriş alanının ilk karakteri veya giriş akışındaki sonraki okuma işlemlerinde ilk karakterdir.

## <a name="see-also"></a>Ayrıca bkz.

[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)<br/>
[scanf Türü Alan Karakterleri](../c-runtime-library/scanf-type-field-characters.md)<br/>
