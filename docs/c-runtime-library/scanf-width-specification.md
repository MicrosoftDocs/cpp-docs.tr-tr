---
title: sacnf Genişlik Belirtimi
ms.date: 11/04/2016
api_location:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- scanf
helpviewer_keywords:
- scanf function, width specification
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
ms.openlocfilehash: 3b00996f3a17ab9298b1edba5a8e60826e19fdcc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957353"
---
# <a name="scanf-width-specification"></a>sacnf Genişlik Belirtimi

Bu bilgiler, gibi güvenli sürümler `scanf` `scanf_s`de dahil olmak üzere işlev ailesinde biçim dizelerinin yorumu için geçerlidir. Bu işlevler normalde giriş akışının bir belirteç dizisine bölündüğünü varsayar. Belirteçler boşluk (boşluk, sekme veya yeni satır) ile veya sayısal bir veri türünün, sayısal metne dönüştürülemeyen ilk karakter tarafından belirtildiği gibi doğal sonuna kadar ayrılmış olarak ayrılır. Ancak, bir belirtecin doğal sonundan önce girişin ayrıştırılmasını engellemek için genişlik belirtimi kullanılabilir.

*Genişlik* belirtimi ve tür alanı belirleyicisi arasındaki karakterlerden `%` oluşur. Bu, *Width* alanı adlı pozitif bir tamsayı ve alanın boyutunu belirten bir veya daha fazla karakter içerebilir ve bu da olabilir Tamsayı türünün **kısa** veya **uzun**olup olmadığına ilişkin bir gösterge gibi alanın türünün değiştirici olarak değerlendirilir. Bu tür karakterler boyut ön eki olarak adlandırılır.

## <a name="the-width-field"></a>Genişlik alanı

*Width* alanı, bu alan için okunacak en fazla karakter sayısını denetleyen pozitif bir ondalık tamsayıdır. En fazla *Genişlik* karakteri dönüştürülerek karşılık gelen `argument`bir şekilde depolanmaz. Boşluk karakteri (boşluk, sekme veya yeni satır) veya verilen biçime göre dönüştürülemeyen bir karakter, *genişliğe* ulaşılmadan önce gerçekleşmediğinde, *Width* 'ten az karakter okunabilir.

Genişlik belirtimi, bu işlevlerin güvenli sürümleri (ör. `scanf_s` `wscanf_s`,, vb.) için gerekli olan arabellek boyutu bağımsız değişkeninden ayrı ve birbirinden farklıdır. Aşağıdaki örnekte, Width belirtimi 20 ' dir ve giriş akışından 20 ' ye kadar karakter okunacağını gösterir. Arabellek uzunluğu 21 ' dir, bu da olası 20 karakter ve null Sonlandırıcı için yer işareti içerir:

```C
char str[21];
scanf_s("%20s", str, 21);
```

*Genişlik* alanı kullanılmıyorsa, `scanf_s` tüm belirteci dizeye okumayı dener. Belirtilen boyut, belirtecin tamamını tutabilecek kadar büyük değilse, hedef dizeye hiçbir şey yazılmaz. *Genişlik* alanı belirtilmişse, belirteçteki ilk *Genişlik* karakterleri, null Sonlandırıcı ile birlikte hedef dizeye yazılır.

## <a name="the-size-prefix"></a>Boyut ön eki

İsteğe bağlı **h**, **l**, **ll**, **I64** `argument` ve **l** önekleri, değiştirdikleri tür karakterine bağlı olarak, (uzun veya kısa, tek baytlı karakter veya geniş karakter) boyutunu belirtir. Bu biçim belirtimi karakterleri, aşağıdaki tabloda gösterildiği gibi bağımsız değişkenlerin `scanf` yorumunu `wscanf` belirtmek için veya işlevlerinde tür karakterleriyle birlikte kullanılır. Tür ön eki **I64** Microsoft UZANTıSıDıR ve ANSI uyumlu değildir. Tür karakterleri ve anlamları [scanf türü alan karakterleri](../c-runtime-library/scanf-type-field-characters.md)içindeki "scanf Işlevlerine yönelik karakter türleri" tablosunda açıklanmaktadır.

> [!NOTE]
> **H**, **l**ve **l** önekleri, türündeki `char`verilerle kullanıldığında Microsoft uzantılarıdır.

### <a name="size-prefixes-for-scanf-and-wscanf-format-type-specifiers"></a>Scanf ve wscanf Format-Type belirticileri için boyut önekleri

|Belirtmek için|Ön ek kullan|Tür belirticisiyle|
|----------------|----------------|-------------------------|
|**double**|**girişindeki**|**e**, **e**, **f**, **g**veya **g**|
|**uzun çift** (Double ile aynı)|**L**|**e**, **e**, **f**, **g**veya **g**|
|**long int**|**girişindeki**|**d**, **i**, **o**, **x**veya **x**|
|**uzun işaretsiz int**|**girişindeki**|**u**|
|**uzun uzun**|**ceğiz**|**d**, **i**, **o**, **x**veya **x**|
|`short int`|**h**|**d**, **i**, **o**, **x**veya **x**|
|**kısa işaretsiz int**|**h**|**u**|
|__**Int64**|**I64**|**d**, **i**, **o**, **u**, **x**veya **x**|
|İle tek baytlık karakter`scanf`|**h**|**c** veya **c**|
|İle tek baytlık karakter`wscanf`|**h**|**c** veya **c**|
|İle geniş karakter`scanf`|**girişindeki**|**c** veya **c**|
|İle geniş karakter`wscanf`|**girişindeki**|**c**veya **c**|
|İle tek baytlık karakter dizesi`scanf`|**h**|**s** veya **s**|
|İle tek baytlık karakter dizesi`wscanf`|**h**|**s** veya **s**|
|İle geniş karakterli dize`scanf`|**girişindeki**|**s** veya **s**|
|İle geniş karakterli dize`wscanf`|**girişindeki**|**s** veya **s**|

Aşağıdaki örnekler, işlevleri ve `wscanf_s` işlevleri ile `scanf_s` **h** ve l kullanır:

```C
scanf_s("%ls", &x, 2);     // Read a wide-character string
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character
```

`scanf` Ailesinden güvenli olmayan bir işlev kullanıyorsanız, önceki bağımsız değişkenin arabellek uzunluğunu belirten boyut parametresini atlayın.

## <a name="reading-undelimited-strings"></a>Sınırsız dizeleri okuma

Boşluk karakterleriyle sınırlandırılmamış dizeleri okumak için, köşeli ayraçlar ( **[]** ) içindeki bir karakter kümesi, **s** (dize) türü karakteri için yerine kullanılabilir. Köşeli ayraçlar içindeki karakter kümesi, denetim dizesi olarak adlandırılır. Karşılık gelen giriş alanı, denetim dizesinde görünmeyen ilk karaktere okunurdur. Küme içindeki ilk karakter bir şapka ( **^** ) ise, efekt tersine çevrilir: Giriş alanı, karakter kümesinin geri kalanında görüntülenen ilk karaktere kadar okunurdur.

% [ **A-z]** ve **% [z-a]** değerinin **% [abcde... ile eşdeğer olarak yorumlandığını unutmayın. z]** . Bu, yaygın `scanf` bir işlev uzantısıdır, ancak ANSI standardının bunu gerektirmediğini unutmayın.

## <a name="reading-unterminated-strings"></a>Sonlandırılmamış dizeler okunuyor

Bir dizeyi, Sonlandırıcı null karakterini (' \ 0 ') depolamadan depolamak <em>için n</em>**c** belirtimini **%** kullanın; burada *n* , Decimal bir tamsayıdır. Bu durumda, **c** türü karakteri bağımsız değişkenin bir karakter dizisine bir işaretçi olduğunu gösterir. Sonraki *n* karakteri giriş akışından belirtilen konuma okundu ve hiçbir null karakter (' \ 0 ') eklenmez. *N* belirtilmemişse, varsayılan değeri 1 ' dir.

## <a name="when-scanf-stops-reading-a-field"></a>Scanf bir alanı okumayı durduruyor

`scanf` İşlevi her giriş alanını ve karakteri karakteriyle tarar. Çeşitli nedenlerle bir boşluk karakterine ulaşmadan önce belirli bir giriş alanını okumayı durdurabilir:

- Belirtilen genişliğe ulaşıldı.

- Sonraki karakter, belirtilen şekilde dönüştürülemez.

- Sonraki karakter, bir denetim dizesinde eşleşmesi beklenen bir karakterle çakışıyor.

- Bir sonraki karakter, belirli bir karakter kümesinde görünemez.

Her nedenden dolayı, `scanf` işlev bir giriş alanını okumayı durdurulduğunda, sonraki giriş alanı ilk okunmamış karakterden başlayarak kabul edilir. Çakışan karakter, varsa, okunmamış olarak değerlendirilir ve sonraki giriş alanının ilk karakteri veya giriş akışındaki sonraki okuma işlemlerinde ilk karakter kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[Biçim Belirtimi Alanları: scanf ve wscanf İşlevleri](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)<br/>
[scanf Türü Alan Karakterleri](../c-runtime-library/scanf-type-field-characters.md)<br/>
