---
description: 'Daha fazla bilgi edinin: `scanf` genişlik belirtimi'
title: sacnf genişlik belirtimi
ms.date: 10/22/2019
helpviewer_keywords:
- scanf function, width specification
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
ms.openlocfilehash: f4b0e13ef87add74bc802ba11ea6b87d0dfc6b8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284440"
---
# <a name="scanf-width-specification"></a>`scanf` genişlik belirtimi

Bu bilgiler `scanf` , gibi güvenli sürümler de dahil olmak üzere işlev ailesinde biçim dizelerinin yorumu için geçerlidir `scanf_s` . Bu işlevler normalde giriş akışının bir belirteç dizisine bölündüğünü varsayar. Belirteçler boşluk (boşluk, sekme veya yeni satır) ile veya sayısal türler için, sayısal metin olarak dönüştürülemeyen ilk karakter tarafından belirtildiği gibi sayısal bir veri türünün doğal sonuna kadar ayrılır. Ancak, bir belirtecin doğal sonundan önce girişin ayrıştırılmasını engellemek için genişlik belirtimi kullanılabilir.

*Genişlik* belirtimi, `%` ve tür alanı belirleyicisi arasındaki karakterlerden oluşur. Bu, *Width* alanı olarak adlandırılan pozitif bir tamsayı ve alanın boyutunu belirten bir veya daha fazla karakter içerebilir; bu da, tamsayı türünün veya ' ın bir göstergesi gibi, alanın türünün değiştirici olarak kabul edilebilir **`short`** **`long`** . Bu tür karakterler boyut ön eki olarak adlandırılır.

## <a name="the-width-field"></a>Genişlik alanı

*Width* alanı, bu alan için okunacak en fazla karakter sayısını denetleyen pozitif bir ondalık tamsayıdır. En fazla *Genişlik* karakteri dönüştürülmez ve karşılık gelen `argument` . Bir boşluk karakteri veya belirtilen biçime göre dönüştürülemediği bir karakter, *genişliğe* ulaşılmadan önce gerçekleşmediğinde, *Width* 'ten az karakter okunabilir.

Genişlik belirtimi, bu işlevlerin güvenli sürümleri (örneğin,, vb.) için gerekli olan arabellek boyutu bağımsız değişkeninden ayrıdır ve ayrıdır `scanf_s` `wscanf_s` . Aşağıdaki örnekte, Width belirtimi 20 ' dir ve giriş akışından 20 ' ye kadar karakter okunacağını gösterir. Arabellek uzunluğu 21 ' dir, bu da olası 20 karakter ve null Sonlandırıcı için yer işareti içerir:

```C
char str[21];
scanf_s("%20s", str, 21);
```

*Genişlik* alanı kullanılmıyorsa, `scanf_s` Tüm belirteci dizeye okumayı dener. Belirtilen boyut, belirtecin tamamını tutabilecek kadar büyük değilse, hedef dizeye hiçbir şey yazılmaz. *Width* alanı belirtilmişse, belirteçteki ilk *Genişlik* karakterleri, null Sonlandırıcı ile birlikte hedef dizeye yazılır.

## <a name="the-size-prefix"></a>Boyut ön eki

İsteğe bağlı **h**, **HH**, **l**, **ll**, **I64** ve **l** önekleri, `argument` değiştirdikleri tür karakterine bağlı olarak, (uzun veya kısa, tek baytlı karakter veya geniş karakter) boyutunu belirtir. Bu biçim belirtimi karakterleri `scanf` `wscanf` , aşağıdaki tabloda gösterildiği gibi bağımsız değişkenlerin yorumunu belirtmek için veya işlevlerinde tür karakterleriyle birlikte kullanılır. Tür ön eki **I64** Microsoft uzantısıdır ve standart C ile uyumlu değildir. Tür karakterleri ve anlamları [ `scanf` tür alanı karakterleri](../c-runtime-library/scanf-type-field-characters.md)içindeki "scanf Işlevleri için tür karakterleri" tablosunda açıklanmaktadır.

> [!NOTE]
> **H**, **l** ve **l** önekleri, türündeki verilerle kullanıldığında Microsoft uzantılarıdır **`char`** .

### <a name="size-prefixes-for-scanf-and-wscanf-format-type-specifiers"></a>`scanf`Ve `wscanf` Biçim türü belirticileri için boyut önekleri

|Belirtmek için|Ön ek kullan|Tür belirticisiyle|
|----------------|----------------|-------------------------|
|**`double`**|**girişindeki**|**e**, **e**, **f**, **g** veya **g**|
|**`long double`** (aynı **`double`** )|**L**|**e**, **e**, **f**, **g** veya **g**|
|**`long int`**|**girişindeki**|**d**, **i**, **o**, **x** veya **x**|
|**`long unsigned int`**|**girişindeki**|**larınız**|
|**`long long`**|**ceğiz**|**d**, **i**, **o**, **x** veya **x**|
|**`short int`**|**h**|**d**, **i**, **o**, **x** veya **x**|
|**`short unsigned int`**|**h**|**larınız**|
|**`char`**|**hh**|**d**, **i**, **o**, **x** veya **x**|
|**`unsigned char`**|**hh**|**larınız**|
|**`int64`**|**I64**|**d**, **i**, **o**, **u**, **x** veya **x**|
|İle tek baytlık karakter `scanf`|**h**|**c** veya **c**|
|İle tek baytlık karakter `wscanf`|**h**|**c** veya **c**|
|İle geniş karakter `scanf`|**girişindeki**|**c** veya **c**|
|İle geniş karakter `wscanf`|**girişindeki**|**c** veya **c**|
|İle tek baytlık karakter dizesi `scanf`|**h**|**s** veya **s**|
|İle tek baytlık karakter dizesi `wscanf`|**h**|**s** veya **s**|
|İle geniş karakter dizesi `scanf`|**girişindeki**|**s** veya **s**|
|İle geniş karakter dizesi `wscanf`|**girişindeki**|**s** veya **s**|

Aşağıdaki örnekler, işlevleri ve işlevleri ile **h** ve **l** kullanır `scanf_s` `wscanf_s` :

```C
scanf_s("%ls", &x, 2);     // Read a wide-character string
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character
```

Ailesinden güvenli olmayan bir işlev kullanıyorsanız `scanf` , önceki bağımsız değişkenin arabellek uzunluğunu belirten boyut parametresini atlayın.

## <a name="reading-undelimited-strings"></a>Sınırsız dizeleri okuma

Boşluk karakterleriyle sınırlı olmayan dizeleri okumak için köşeli ayraç () içindeki bir karakter kümesi, **`[ ]`** **s** (dize) türü karakteri için değiştirilebilir. Köşeli ayraçlar içindeki karakter kümesi, *Denetim dizesi* olarak adlandırılır. Karşılık gelen giriş alanı, denetim dizesinde görünmeyen ilk karaktere okunurdur. Küme içindeki ilk karakter bir şapka ( **`^`** ) ise, efekt tersine çevrilir: giriş alanı, karakter kümesinin geri kalanında görüntülenen ilk karaktere okunurdur.

% [ **A-z]** ve **% [z-a]** her ikisi de **% [abcde... ile eşdeğer olarak yorumlanır. z]**. Bu, ortak bir `scanf` işlev uzantısıdır, ancak standart C için gerekli değildir.

## <a name="reading-unterminated-strings"></a>Sonlandırılmamış dizeler okunuyor

Bir dizeyi Sonlandırıcı null karakteri (' \ 0 ') depolamadan depolamak için, N değerini kullanın; `%Nc` burada *N* , Decimal bir tamsayıdır. Bu durumda, **c** türü karakteri bağımsız değişkenin bir karakter dizisine bir işaretçi olduğunu gösterir. Sonraki *N* karakteri giriş akışından belirtilen konuma okundu ve hiçbir null karakter (' \ 0 ') eklenmez. *N* belirtilmemişse, varsayılan değeri 1 ' dir.

## <a name="when-scanf-stops-reading-a-field"></a>`scanf`Bir alanı okumayı kestiğinde

`scanf`İşlevi her giriş alanını ve karakteri karakteriyle tarar. Bazı nedenlerden biri için bir boşluk karakterine ulaşmadan önce belirli bir giriş alanını okumayı durdurabilir:

- Belirtilen genişliğe ulaşıldı.

- Sonraki karakter, belirtilen şekilde dönüştürülemez.

- Sonraki karakter, bir denetim dizesinde eşleşmesi beklenen bir karakterle çakışıyor.

- Bir sonraki karakter, belirli bir karakter kümesinde görünemez.

Her nedenden dolayı, `scanf` işlev bir giriş alanını okumayı durdurulduğunda, sonraki giriş alanı ilk okunmamış karakterden başlayarak kabul edilir. Çakışan karakter, varsa, okunmamış olarak değerlendirilir. Bu, sonraki giriş alanının ilk karakteri veya giriş akışındaki sonraki okuma işlemlerinde ilk karakterdir.

## <a name="see-also"></a>Ayrıca bkz.

[`scanf`, `_scanf_l`, `wscanf`, `_wscanf_l`](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[`scanf_s`, `_scanf_s_l`, `wscanf_s`, `_wscanf_s_l`](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[Biçim belirtimi alanları: `scanf` ve `wscanf` işlevleri](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)<br/>
[`scanf` Tür alanı karakterleri](../c-runtime-library/scanf-type-field-characters.md)<br/>
