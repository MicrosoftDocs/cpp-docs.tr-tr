---
title: 'Biçim belirtim Sözdizimi: printf ve wprintf işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- format specification fields for printf function
- printf function format specification fields
- flag directives, printf function
- type fields, printf function
- width fields, printf function
- precision fields, printf function
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c15ba418657dde291c6833caafae071ca0260a65
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>Biçim belirtim Sözdizimi: printf ve wprintf işlevleri

Çeşitli `printf` ve `wprintf` işlevleri bir biçim dizesi ve isteğe bağlı bağımsız değişkenler ve biçimlendirilmiş çıktısı için bir karakter dizisi üretir. Sıfır veya daha fazla biçim dizesi içeren *yönergeleri*, çıktı veya kodlanmış için değişmez değer her iki karakter olan *dönüştürme belirtimleri* çıktıda bir bağımsız değişken biçimlendirme açıklanmaktadır. Bu konuda dönüştürme belirtimleri dize biçiminde kodlamak için kullanılan söz dizimi açıklanmıştır. Bu işlevlerin listesi için bkz: [akış g/ç](../c-runtime-library/stream-i-o.md).

Bu formdaki isteğe bağlıdır ve gerekli alanlara dönüştürme belirtimi oluşur:

**%**[[*bayrakları*](#flags)] [[*genişliği*](#width)] [.[ *duyarlık*](#precision)] [[*boyutu*](#size)][*türü*](#type)

Her alanı dönüştürme belirtimi, bir karakter ya da belirli biçim seçeneği veya dönüştürme belirticisi belirten bir sayı alır. Gerekli *türü* alan bir bağımsız değişken uygulanacak dönüştürme türünü belirtir. İsteğe bağlı *bayrakları*, *genişliği*, ve *duyarlık* alanları denetim öndeki boşlukları veya sıfır, düzeltme ve görüntülenen duyarlık gibi ek biçim Konular. *Boyutu* alan bağımsız değişkeni kullanılan ve dönüştürülen boyutunu belirler.

Bir temel dönüştürme belirtimi yalnızca yüzde işareti içeriyor ve bir *türü* karakter. Örneğin, `%s` dize dönüştürme belirtir. Bir yüzde işareti karakteri yazdırmak için kullanın `%%`. Bir biçim alanı olarak bir anlamı yoktur bir karakterle yüzde işareti izlediyseniz, geçersiz parametre işleyicisi çağrılır. Daha fazla bilgi için bkz: [parametre doğrulaması](../c-runtime-library/parameter-validation.md).

> [!IMPORTANT]
> Güvenlik ve kararlılık için dizeleri değil kullanıcı tanımlı bu dönüştürme belirtimi emin olun. Örneğin, kullanıcıdan bir ad girin ve giriş adlı bir dize değişkeni depolayan bir program dikkate `user_name`. Yazdırmak için `user_name`, bunu yapmayın:
>
> `printf( user_name ); /* Danger!  If user_name contains "%s", program will crash */`
>
> Bunun yerine, bunu yapın:
>
> `printf( "%s", user_name );`

<a name="type"></a>

## <a name="type-conversion-specifier"></a>Tür dönüştürme belirteci

*Türü* dönüştürme belirleyici karakter karşılık gelen bağımsız değişkeni bir karakter, bir dize, bir işaretçi, tamsayı veya kayan noktalı sayı yorumlamak belirtir. *Türü* karakter yalnızca gerekli dönüştürme belirtimi alan ve sonra isteğe bağlı alanları görüntülenir.

Biçim dizesi izleyin bağımsız değişkenleri karşılık gelen göre yorumlanır *türü* karakter ve isteğe bağlı [boyutu](#size) öneki. Karakter türleri için dönüşümleri `char` ve `wchar_t` kullanılarak belirtilen **c** veya **C**, ve tek baytlı ve çok baytlı veya geniş karakter dizeleri belirtilen kullanarak**s** veya **S**hangi biçimlendirme işlevi kullanılan bağlı olarak. Kullanılarak belirtilen karakter ve dize bağımsız değişkenleri **c** ve **s** olarak yorumlanır `char` ve `char*` tarafından `printf` ailesi işlevleri veya as `wchar_t` ve `wchar_t*` tarafından `wprintf` ailesi işlevleri. Kullanılarak belirtilen karakter ve dize bağımsız değişkenleri **C** ve **S** olarak yorumlanır `wchar_t` ve `wchar_t*` tarafından `printf` ailesi işlevleri veya as `char` ve `char*` tarafından `wprintf` ailesi işlevleri. Bu, belirli Microsoft davranıştır.

Tamsayı türleri gibi `short`, `int`, `long`, `long long`ve bunların `unsigned` çeşitleri, belirtilen kullanarak **d**, **ı**, **o**, **u**, **x**, ve **X**. Kayan nokta türleri gibi `float`, `double`, ve `long double`, kullanılarak belirtilen **bir**, **A**, **e**, **E**, **f**, **F**, **g**, ve **G**. Varsayılan olarak, tarafından değiştirilmiş sürece bir *boyutu* tamsayı bağımsız değişkenlerini önek, yüklenen için `int` türü ve kayan nokta değişkenleri için yüklenen `double`. 64 bitlik sistemlerde bir `int` 32-bit değeri; sürece için çıktı biçimlendirildiğinden, bu nedenle, 64-bit tamsayı kesilecek bir *boyutu* öneki **üm** veya **I64**kullanılır. Tarafından belirtilen işaretçi türleri **p** platform için varsayılan işaretçi boyutu kullanabilirsiniz.

> [!NOTE]
> **Microsoft özel**  
> **Z** karakter ve davranışını yazın **c**, **C**, **s**, ve **S** türü karakter bunlar ile kullanılan `printf` ve `wprintf` işlevlerdir, Microsoft uzantıları. ISO C standardı kullanır **c** ve **s** dar karakterler ve dizeler için tutarlı bir şekilde ve **C** ve **S** geniş karakterler ve dizeler için tüm biçimlendirme işlevleri.

### <a name="type-field-characters"></a>Tür alanı karakterleri

|Türü karakteri|Bağımsız Değişken|Çıktı biçimi|
|--------------------|--------------|-------------------|
|**c**|Karakter|İle kullanıldığında `printf` İşlevler, tek baytlı karakter; kullanıldığında belirtir `wprintf` İşlevler, geniş karakter belirtir.|
|**C**|Karakter|İle kullanıldığında `printf` İşlevler, geniş karakter; kullanıldığında belirtir `wprintf` İşlevler, tek baytlı karakter belirtir.|
|**d**|Tamsayı|İmzalanmış ondalık tamsayı.|
|**i**|Tamsayı|İmzalanmış ondalık tamsayı.|
|**o**|Tamsayı|İmzasız sekizlik tamsayı.|
|**u**|Tamsayı|İmzasız ondalık tamsayı.|
|**x**|Tamsayı|İşaretsiz onaltılık tamsayı; "abcdef" kullanır|
|**X**|Tamsayı|İşaretsiz onaltılık tamsayı; "ABCDEF" kullanır|
|**e**|Kayan nokta|Formun [-] sahip değeri işaretli*d.dddd*__e±__*GG*[*d*] burada *d* bir ondalık basamak, *dddd* belirtilen duyarlık bağlı olarak bir veya daha fazla ondalık basamak ya da varsayılan olarak, altı ve *GG*[*d*] bağlıolarakikiveyaüçondalıkbasamak[çıktı biçimi](../c-runtime-library/set-output-format.md) ve üs boyutu.|
|**E**|Kayan nokta|Aynı **e** dışında biçimi **E** yerine **e** üs tanıtır.|
|**f**|Kayan nokta|Formun [-] sahip değeri işaretli*dddd*__.__ *dddd*, burada *dddd* bir veya daha fazla ondalık basamak. Ondalık sayı büyüklüğünü bağlıdır önce basamak sayısı ve istenen duyarlılık veya altı varsayılan Ondalık ayırıcının bağlıdır sonra basamak sayısı.|
|**F**|Kayan nokta|Aynı **f** sonsuzluk ve nan çıkış büyük harfli dışında biçimlendirin.|
|**g**|Kayan nokta|İmzalı değerler görüntülenir **f** veya **e** biçimi, hangisi verilen değer ve duyarlık için daha kısadır. **e** biçimi değeri üs değerinden -4 olduğunda yalnızca ya da sıfırdan büyük veya eşit kullanılır *duyarlık* bağımsız değişkeni. Sondaki sıfırlar kesilir ve yalnızca bir ondalık ayırıcısı görüntülenir veya daha fazla basamak izleyerek.|
|**G**|Kayan nokta|Aynı **g** , dışında biçiminde **E**, yerine **e**, üs (uygun olan yerlerde) sunar.|
|**a**|Kayan nokta|Formun [-] sahip onaltılık çift duyarlıklı kayan noktalı değeri imzalı 0 x*h.hhhh*__p±__*GG*, burada *h.hhhh* onaltılık olan Mantis rakamı (büyük küçük harf kullanarak) ve *GG* üs için bir veya daha fazla basamak şunlardır. Duyarlık noktadan sonra basamak sayısını belirtir.|
|**A**|Kayan nokta|Formun [-] 0 X onaltılık çift duyarlıklı kayan noktalı değeri işaretli*h.hhhh*__P±__*GG*, burada *h.hhhh* onaltılık olan Mantis rakamı (büyük harf kullanarak) ve *GG* üs için bir veya daha fazla basamak şunlardır. Duyarlık noktadan sonra basamak sayısını belirtir.|
|**n**|Tamsayı işaretçi|Başarıyla kadarki akış veya arabelleğe yazılan karakterlerin sayısı. Bu değer, adresi bağımsız değişken olarak verilen tamsayı depolanır. Bir bağımsız değişkeni boyut belirtimi önekiyle işaret tamsayı boyutunu denetlenebilir. **n** belirticisi varsayılan olarak devre dışı; önemli güvenlik notu bilgi için bkz.|
|**p**|İşaretçi türü|Bağımsız değişkeni bir adresi onaltılık basamak olarak görüntüler.|
|**s**|Dize|İle kullanıldığında `printf` İşlevler, bir tek baytlı ve çok baytlı karakter dizesi; kullanıldığında belirtir `wprintf` İşlevler, bir joker karakter dizesini belirtir. Karakter ilk null karakter kadar veya kadar görüntülenir *duyarlık* değerine ulaşılmadan.|
|**S**|Dize|İle kullanıldığında `printf` İşlevler, birlikte kullanıldığında bir joker karakter dizesi; belirtir `wprintf` İşlevler, bir tek baytlı ve çok baytlı karakter dizesi belirtir. Karakter ilk null karakter kadar veya kadar görüntülenir *duyarlık* değerine ulaşılmadan.|
|**Z**|`ANSI_STRING` veya `UNICODE_STRING` yapısı|Zaman adresini bir [ANSI_STRING](http://msdn.microsoft.com/library/windows/hardware/ff540605.aspx) veya [UNICODE_STRING](http://msdn.microsoft.com/library/windows/hardware/ff564879.aspx) yapısı bağımsız değişken olarak geçirilen, gösterdiği arabellek bulunan dizesini görüntüler `Buffer` yapısı alan. Kullanım bir *boyutu* değiştiricisi öneki **w** belirtmek için bir `UNICODE_STRING` bağımsız değişkeni — Örneğin, `%wZ`. `Length` Yapısı alan uzunluğu dizesi için bayt cinsinden ayarlanması gerekir. `MaximumLength` Yapısının alanını uzunluğa arabellek, bayt cinsinden ayarlanması gerekir.<br /><br /> Genellikle, **Z** türü karakteri yalnızca hata ayıklama dönüştürme belirtimi gibi kullandığınız işlevleri sürücüde kullanılan `dbgPrint` ve `kdPrint`.|

Visual Studio 2015'te ise başlangıç bir kayan nokta dönüşümü belirticisi karşılık gelen bağımsız değişkeni (**bir**, **A**, **e**, **E**, **f**, **F**, **g**, **G**) belirsiz, sonsuz veya NaN, biçimlendirilmiş çıkışı C99 standardına uygun. Bu tabloda biçimlendirilmiş çıkışı listelenmektedir:

|Değer|Çıkış|
|-----------|------------|
|sonsuz|`inf`|
|Sessiz NaN|`nan`|
|NaN sinyali gönderiliyor|`nan(snan)`|
|Belirsiz NaN|`nan(ind)`|

Bu değerleri, bir oturum tarafından önek. Bir kayan nokta ise *türü* dönüştürme belirleyici karakterdir bir büyük harf, ardından çıktı ayrıca büyük harflerle biçimlendirilir. Örneğin, biçim belirteci ise `%F` yerine `%f`, bir sonsuz olarak biçimlendirilmiş `INF` yerine `inf`. `scanf` İşlevleri de bu dizeleri ayrıştırma, bu değerleri gidiş aracılığıyla olabilmeniz `printf` ve `scanf` işlevleri.

Visual Studio 2015 önce CRT farklı, standart olmayan bir biçimde sonsuz belirsiz çıktısını ve NaN değerler için kullanılır:

|Değer|Çıkış|
|-----------|------------|
|+ sonsuz|`1.#INF` *rasgele basamak*|
|-sonsuz|`-1.#INF` *rasgele basamak*|
|Sonsuz (sessiz NaN ile aynı)|*basamak* `.#IND` *rasgele basamak*|
|NaN|*basamak* `.#NAN` *rasgele basamak*|

Bunları herhangi biri bir oturum tarafından öneki ve biraz daha farklı alan genişliği ve olağan dışı efektleri ile bazen duyarlık bağlı olarak biçimlendirilmiş olabilir. Örneğin, `printf("%.2f\n", INFINITY)` yazdıracak `1.#J` #INF "kesinliğini 2 basamak için yuvarlanmasını çünkü".

> [!NOTE]
> Bağımsız değişken için karşılık gelen varsa `%s` veya `%S`, veya `Buffer` karşılık gelen bağımsız değişken alan `%Z`, null işaretçi "(boş)" görüntülenir.

> [!NOTE]
> Tüm üstel biçimlerde görüntülemek için üs, basamak sayısı alt sınırını iki, üç yalnızca gerekirse kullanmaktır. Kullanarak [_set_output_format](../c-runtime-library/set-output-format.md) işlevi, üç önce ve Visual Studio 2013 için yazılan kod ile geriye dönük uyumluluk için görüntülenen basamak sayısını ayarlayabilirsiniz.

> [!IMPORTANT]
> Çünkü `%n` biçimidir doğası gereği güvenli, varsayılan olarak devre dışıdır. Varsa `%n` karşılaşılması durumunda bir biçim dizesi geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../c-runtime-library/parameter-validation.md). Etkinleştirmek için `%n` destek, bkz: [_set_printf_count_output](../c-runtime-library/reference/set-printf-count-output.md).

<a name="flags"></a>

## <a name="flag-directives"></a>Bayrak yönergeleri

Bir dönüştürme belirtimi ilk isteğe bağlı alanı içeren *bayrak yönergeleri*, sıfır veya daha fazla bayrak çıkış gerekçe belirtin ve işaretleri, boşluklar, baştaki sıfırlar, ondalık ayırıcıların çıkış ve sekizli denetleyen karakter ve onaltılık önekleri. Birden çok bayrak yönergesi dönüştürme belirtiminde görünebilir ve bayrağı karakterleri herhangi bir sırada yer alabilir.

### <a name="flag-characters"></a>Bayrak karakterleri

|Bayrağı|Açıklama|Varsayılan|
|----------|-------------|-------------|
|**-**|Verilen alan genişliği içinde sonuç Sola Hizala.|Sağa Hizala.|
|**+**|Bir oturum kullanın (+ veya -) imzalı bir tür ise çıkış değerini ön eki.|Oturum, yalnızca imzalı için negatif değerler (-) görünür.|
|**0**|Varsa *genişliği* tarafından önekli **0**başında en küçük genişliği ulaşılana kadar sıfır eklenir. Her iki **0** ve **-** görünen **0** göz ardı edilir. Varsa **0** bir tamsayı biçimi için belirtilen (**ı**, **u**, **x**, **X**, **o**, **d**) ve duyarlık belirtimi de varsa — örneğin, `%04.d`— **0** göz ardı edilir. Varsa **0** için belirtilen **bir** veya **A** kayan nokta biçimi, baştaki sıfırlar $a Mantis için sonra `0x` veya `0X` öneki.|Dolgu.|
|**blank** (' ')|İmzalı ve pozitif ise önek çıktı değeri için boş bir kullanın. Boş, her iki göz ardı edilir boş ve + bayrakları görünür.|Hiçbir boş görünür.|
|**#**|İle kullanıldığında **o**, **x**, veya **X** biçimi **#** bayrak kullandığı 0, 0 x, ya da 0 sırasıyla ön eki her sıfır olmayan X Çıkış değeri.|Hiçbir boş görünür.|
||İle kullanıldığında **e**, **E**, **f**, **F**, **bir** veya **A** Biçim, **#** bayrak, ondalık ayırıcıdan içerecek şekilde çıkış değerini zorlar.|Yalnızca rakam izlerseniz, ondalık ayırıcıdan görüntülenir.|
||İle kullanıldığında **g** veya **G** biçimi **#** bayrağı ondalık içerecek şekilde çıkış değerini zorlar ve sondaki sıfırlar kesme engeller.<br /><br /> İle kullanıldığında göz ardı **c**, **d**, **ı**, **u**, veya **s**.|Yalnızca rakam izlerseniz, ondalık ayırıcıdan görüntülenir. Sondaki sıfırlar kesilir.|

<a name="width"></a>

## <a name="width-specification"></a>Genişlik belirtimi

İsteğe bağlı genişlik belirtimi alanında sonra herhangi bir dönüştürme belirtimi görünür *bayrakları* karakter. *Genişliği* bağımsız değişkeni olan en az sayıda çıkış karakteri denetleyen negatif olmayan bir ondalık tamsayı. Çıkış değerini karakter sayısı belirtilen genişlik azsa boşlukları sola veya sağa değerlerin eklenir — olup sol hizalama bayrak bağlı olarak (**-**) belirtilen — en düşük kadar Genişlik ulaşıldı. Varsa *genişliği* konduğundan dönüştürme bir sonsuz veya NaN olduğunda dışında en küçük genişliği ulaşılana kadar 0 ile öndeki sıfırların tamsayı veya kayan nokta dönüşümleri eklenir.

Genişlik belirtimi hiçbir zaman kesilecek değeri neden olur. Çıkış değerini karakter sayısı belirtilen genişliğinden büyükse veya *genişliği* olan verilen değil, tüm karakterleri değerinin çıktı tabi olan *duyarlık* belirtimi.

Genişlik belirtimi yıldız ise (`*`), bir `int` bağımsız değişken listesi değişkenden değer sağlar. *Genişliği* Bu örnekte gösterildiği gibi bağımsız değişken bağımsız değişken listesinde biçimlendirilmiş değer gelmelidir:

`printf("%0*f", 5, 3);  /* 00003 is output */`

Eksik veya küçük *genişliği* dönüştürme belirtimi değerinde bir çıkış değeri kesilmesi neden olmaz. Bir dönüştürme sonucu daha geniş ise *genişliği* alanın değeri genişletir dönüştürme sonucu içerecek şekilde.

<a name="precision"></a>

## <a name="precision-specification"></a>Duyarlık belirtimleri

Bir dönüştürme belirtimi üçüncü isteğe bağlı duyarlık belirtimi bir alandır. Dönüştürme türüne bağlı olarak, dize karakter sayısını, ondalık basamak sayısını veya önemli çıkış olmasını basamak sayısını belirten bir negatif olmayan ondalık tamsayı tarafından izlenen bir nokta (.) oluşur.

Genişlik belirtimi, çıkış değerini kesilmesi ya da bir kayan nokta değeri yuvarlama duyarlık belirtimi neden olabilir. Varsa *duyarlık* dönüştürülecek 0 ve değeri 0'dır, sonuç hiçbir karakter çıktı Bu örnekte gösterildiği gibi belirtilir:

`printf( "%.0d", 0 );      /* No characters output */`

Duyarlık belirtimi yıldız ise (\*), bir `int` bağımsız değişken listesi değişkenden değer sağlar. Bağımsız değişken listesinde *duyarlık* bağımsız değişkeni, bu örnekte gösterildiği gibi biçimlendirilen, değer gelmelidir:

`printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`

*Türü* karakter ya da yorumu belirler *duyarlık* veya varsayılan duyarlık zaman *duyarlık* aşağıdaki tabloda gösterildiği gibi atlanır.

### <a name="how-precision-values-affect-type"></a>Nasıl Precision değerleri türü etkiler

|Tür|Açıklama|Varsayılan|
|----------|-------------|-------------|
|**a**, **A**|Duyarlık noktadan sonra basamak sayısını belirtir.|Varsayılan duyarlık 13'tür. Duyarlık 0 ise, ondalık ayırıcıdan sürece yazdırılır **#** bayrağı kullanılır.|
|**c**, **C**|Duyarlık hiçbir etkisi olmaz.|Karakter yazdırılır.|
|**d**, **i**, **o**, **u**, **x**, **X**|Duyarlık yazdırılması basamak sayısı alt sınırını belirtir. Bağımsız değişken basamak sayısı ise değerinden *duyarlık*, çıkış değerini sıfırlarla soldaki doldurulan. Basamak sayısını aştığında değeri kesilmiş değil *duyarlık*.|Varsayılan duyarlık 1'dir.|
|**e**, **E**|Duyarlılık ondalık ayırıcıdan sonra yazdırılması basamak sayısını belirtir. Son yazdırılan basamaklı yuvarlanır.|Varsayılan duyarlık 6'dır. Varsa *duyarlık* 0 veya aşağıdaki içermeyen bir sayı nokta (.) görüntülenir, ondalık ayırıcıdan yazdırılır.|
|**f**, **F**|Duyarlılık değeri ondalık ayırıcıdan sonra basamak sayısını belirtir. Ondalık görünürse, en az bir rakam önce görünür. Değer basamak uygun sayıya yuvarlanır.|Varsayılan duyarlık 6'dır. Varsa *duyarlık* 0 ise veya nokta (.) onu izleyen koymadan görünürse, ondalık ayırıcıdan yazdırılır.|
|**g**, **G**|Duyarlık yazdırılan basamak sayısını belirtir.|Altı basamaktan yazdırılabilir ve sondaki sıfırları kesilir.|
|**s**, **S**|Duyarlık yazdırılması için karakter üst sınırını belirtir. Excess, karakterleri *duyarlık* değil yazdırılır.|Bir null karakter karşılaşılana kadar karakter yazdırılır.|

<a name="size"></a>

## <a name="argument-size-specification"></a>Bağımsız değişkeni boyut belirtimi

Bir dönüştürme belirtiminde *boyutu* alandır için bir bağımsız değişken uzunluğu değiştiricisi *türü* dönüştürme tanımlayıcısı. *Boyutu* alan ön eklerin *türü* alan —**hh**, **h**, **j**, **l** (Küçük Harf L), **L**, **üm**, **t**, **w**, **z**, **ı**(büyük harf i), **I32**, ve **I64**— karşılık gelen bağımsız değişkeni "boyutu" belirtin — uzun veya kısa bir 32 bit veya 64-bit, tek baytlı karakter veya geniş karakter — bağlı olarak Bunlar değiştirme dönüştürme tanımlayıcısı. Bu boyut önekleri ile kullanılan *türü* içinde karakterleri `printf` ve `wprintf` aileleri aşağıdaki tabloda gösterildiği gibi bağımsız değişken boyutları yorumu belirtin işlevlerin. *Boyutu* alandır bazı bağımsız değişken türleri için isteğe bağlı. Boyutu önek belirtildiğinde, biçimlendirici tamsayı bağımsız değişkeni tüketir — Örneğin, imzalı veya imzasız `char`, `short`, `int`, `long`ve sıralama türlerinde — olarak 32-bit `int` türleri ve `float`, `double`, ve `long double` kayan nokta değişkenleri olarak 64-bit tüketilen `double` türleri. Değişken bağımsız değişken listeleri için varsayılan bağımsız değişkeni yükseltme kurallar eşleşir. Üç noktalar ve varsayılan bağımsız değişkenler bağımsız değişkeni yükseltme hakkında daha fazla bilgi için bkz: [sonek ifadeleri](../cpp/postfix-expressions.md). 32 bit ve 64 bitlik sistemlerde bir 64-bit tamsayı bağımsız değişkeni dönüştürme belirtimi boyutu öneki içermelidir **üm** veya **I64**. Aksi takdirde, biçimlendirici davranışını tanımlanmamıştır.

Bazı türleri 32-bit ve 64 bit kodu farklı boyutlarda olabilir. Örneğin, `size_t` 32 bit uzun x86 ve 64 bit cinsinden x64 için derlenmiş kod derlenmiş kod. Platform bağımsız değişken genişlikli türleri için biçimlendirme kodu oluşturmak için bir değişken genişlikli bağımsız değişkeni boyut değiştirici kullanabilirsiniz. Alternatif olarak, 64-bit bağımsız değişkeni boyut değiştiricisini kullanın ve 64 bit değişken genişlikli bağımsız değişken türü açıkça yükseltin. Microsoft'a özgü **ı** (büyük harf i) bağımsız değişkeni Boyutu değiştiricisi işleme değişken genişlikli tamsayı bağımsız değişkeni, ancak türüne özgü öneririz **j**, **t**ve **z** değiştiricileri taşınabilirlik için.

### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>Printf ve wprintf biçim türü tanımlayıcıları için boyutu önekleri

|Belirtmek için|Ön ekini kullanın|Tür belirteci ile|
|----------------|----------------|-------------------------|
|`char`<br />`unsigned char`|**hh**|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|`short int`<br />`short unsigned int`|**h**|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|`__int32`<br />`unsigned __int32`|**I32**|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|`__int64`<br />`unsigned __int64`|**I64**|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|`intmax_t`<br />`uintmax_t`|**j** veya **I64**|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|`long double`|**l** (M küçük harf) veya **m**|**bir**, **A**, **e**, **E**, **f**, **F**, **g**, veya **G**|
|`long int`<br />`long unsigned int`|**m** (küçük harf M)|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|`long long int`<br />`unsigned long long int`|**üm** (tümü küçük harf)|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|`ptrdiff_t`|**t** veya **ı** (büyük harf i)|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|`size_t`|**z** veya **ı** (büyük harf i)|**d**, **ı**, **o**, **u**, **x**, veya **X**|
|Tek baytlı karakter|**h**|**c** veya **C**|
|Geniş karakter|**l** (M küçük harf) veya **w**|**c** veya **C**|
|Tek baytlı karakter dizesi|**h**|**s**, **S**, veya **Z**|
|Joker karakter dizesi|**l** (M küçük harf) veya **w**|**s**, **S**, veya **Z**|

`ptrdiff_t` Ve `size_t` türleri `__int32` veya `unsigned __int32` 32-bit platformlarda ve `__int64` veya `unsigned __int64` 64 bit platformlarda. **I** (büyük harf i), **j**, **t**, ve **z** boyutu önekleri platform için doğru bağımsız değişken genişlik alın.

Visual C++ ' ta rağmen `long double` farklı bir tür aynı iç gösterimi olarak sahip `double`.

Bir **hc** veya **hC** tür belirteci ile eşanlamlı **c** içinde `printf` işlevleri ile **C** içinde `wprintf` işlevleri. Bir **lc**, **lC**, **wc** veya **wC** tür belirteci ile eşanlamlı **C** içinde `printf` İşlevler ile **c** içinde `wprintf` işlevleri. Bir **hs** veya **hS** tür belirteci ile eşanlamlı **s** içinde `printf` işlevleri ile **S** içinde `wprintf` işlevleri. Bir **ls**, **lS**, **ws** veya **wS** tür belirteci ile eşanlamlı **S** içinde `printf` İşlevler ile **s** içinde `wprintf` işlevleri.

> [!NOTE]
> **Microsoft özel**  
> **I** (büyük harf i), **I32**, **I64**, ve **w** bağımsız değişkeni boyut değiştiricisi önekleri Microsoft uzantıları ve ISO C ile uyumlu değildir. **h** önek veri türü ile kullanıldığında `char` ve **l** (M küçük harf) veri türü ile kullanıldığında önek `double` Microsoft uzantıları.

## <a name="see-also"></a>Ayrıca Bkz.

[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)  
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)  
[printf_p Konumsal Parametreler](../c-runtime-library/printf-p-positional-parameters.md)  