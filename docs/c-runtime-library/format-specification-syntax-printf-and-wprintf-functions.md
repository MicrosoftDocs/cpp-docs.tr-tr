---
title: 'Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri'
ms.date: 11/04/2016
helpviewer_keywords:
- format specification fields for printf function
- printf function format specification fields
- flag directives, printf function
- type fields, printf function
- width fields, printf function
- precision fields, printf function
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
ms.openlocfilehash: bccbe435d926a75990a4ca35b98c9b352dd40e8b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740309"
---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>Biçim belirtim Sözdizimi: printf ve wprintf işlevleri

Çeşitli `printf` ve `wprintf` işlevler bir biçim dizesi ve isteğe bağlı bağımsız değişkeni alır ve biçimlendirilmiş çıkış için bir karakter dizisi üretir. Sıfır veya daha fazla biçim dizesi içeren *yönergeleri*, çıkış veya kodlanmış ya da değişmez karakterler olan *dönüştürme belirtimleri* çıktıda bir bağımsız değişken biçimlendirme nasıl açıklanmaktadır. Bu konu, Biçim dizesinde dönüştürme belirtimleri kodlamak için kullanılan söz dizimini açıklar. Bu işlevlerin bir listesi için bkz. [Stream g/ç](../c-runtime-library/stream-i-o.md).

İsteğe bağlı ve gerekli alanlara bu formu dönüştürme belirtimi oluşur:

**%**[[*flags*](#flags)][[*width*](#width)][.[*precision*](#precision)][[*size*](#size)][*type*](#type)

Her alanı dönüştürme belirtimi, bir karakter veya seçeneği veya dönüştürme bir özel biçim belirticisi belirten bir sayı alır. Gerekli *türü* alanı bağımsız değişkeni uygulanacak dönüştürme türünü belirtir. İsteğe bağlı *bayrakları*, *genişliği*, ve *duyarlık* alanlarını başında boşluk veya sıfır ve gerekçe görüntülenen duyarlık gibi ek biçimi özelliklerini denetleyin. *Boyutu* alanı bağımsız değişkeni kullanılan ve dönüştürülen boyutunu belirtir.

Bir temel dönüştürme belirtimi yalnızca yüzde işareti içeriyor ve *türü* karakter. Örneğin, `%s` dize dönüştürme belirtir. Yüzde işareti karakteri yazdırmak için kullanın `%%`. Biçimi alanı olarak hiçbir anlamı bir karakter olarak yüzde işareti izlediyseniz, geçersiz parametre işleyicisi çağrılır. Daha fazla bilgi için [Parameter Validation](../c-runtime-library/parameter-validation.md).

> [!IMPORTANT]
> Güvenlik ve tutarlılık için dizeleri değil kullanıcı tanımlı bu dönüştürme belirtimi emin olun. Örneğin, kullanıcıdan bir ad girin ve giriş adlı bir dize değişkeni içinde depolayan bir program düşünün `user_name`. Yazdırılacak `user_name`, bunu yapmayın:
>
> `printf( user_name ); /* Danger!  If user_name contains "%s", program will crash */`
>
> Bunun yerine, bunu yapabilirsiniz:
>
> `printf( "%s", user_name );`

<a name="type"></a>

## <a name="type-conversion-specifier"></a>Tür dönüştürme tanımlayıcısı

*Türü* dönüştürme tanımlayıcı karakteri karşılık gelen bağımsız değişken karakter, bir dize, bir işaretçi, bir tamsayı veya kayan noktalı bir sayı yorumlamak belirtir. *Türü* karakter yalnızca gerekli dönüştürme belirtimi alan ve sonra isteğe bağlı alanları görüntülenir.

Biçim dizesi izleyen bağımsız değişkenleri karşılık gelen göre yorumlanır *türü* karakter ve isteğe bağlı [boyutu](#size) önek. Karakter türleri için dönüştürme `char` ve `wchar_t` kullanılarak belirtilen **c** veya **C**, ve tek baytlı ve çok baytlı veya geniş karakter dizeleri belirtilen kullanarak**s** veya **S**bağlı olarak hangi biçimlendirme işlevi kullanılır. Kullanılarak belirtilen karakter ve dize bağımsız değişkenleri **c** ve **s** olarak yorumlanır `char` ve `char*` tarafından `printf` ailesi işlevleri veya as `wchar_t` ve `wchar_t*` tarafından `wprintf` ailesi işlevleri. Kullanılarak belirtilen karakter ve dize bağımsız değişkenleri **C** ve **S** olarak yorumlanır `wchar_t` ve `wchar_t*` tarafından `printf` ailesi işlevleri veya as `char` ve `char*` tarafından `wprintf` ailesi işlevleri. Microsoft'a özgü davranıştır.

Tamsayı türleri gibi `short`, `int`, `long`, `long long`ve bunların `unsigned` çeşitleri kullanılarak belirtilir **d**, **miyim**, **o**, **u**, **x**, ve **X**. Kayan nokta türleri gibi `float`, `double`, ve `long double`, kullanılarak belirtilen **bir**, **A**, **e**, **E**, **f**, **F**, **g**, ve **G**. Varsayılan olarak, tarafından değiştirilmediği sürece bir *boyutu* önek, tamsayı bağımsız değişkenleri için zorlanır `int` türü ve kayan nokta bağımsız değişkenleri zorlanır `double`. 64 bitlik sistemlerde bir `int` 32-bit bir değerdir; sürece çıkış için biçimlendirilir, bu nedenle, 64-bit tamsayıya kesilecek bir *boyutu* öneki **ll** veya **I64**kullanılır. Tarafından belirtilen işaretçi türleri **p** varsayılan işaretçi boyutu platformu kullanın.

> [!NOTE]
> **Microsoft Specific** **Z** karakter ve davranışını yazın **c**, **C**, **s**, ve **S** ile kullanıldığında karakter yazın `printf` ve `wprintf` işlevleri, Microsoft genişletmeleridir. ISO C standardı kullanan **c** ve **s** dar karakterler ve dizeler için tutarlı bir şekilde ve **C** ve **S** geniş karakterler ve dizeler için tüm biçimlendirme işlevleri.

### <a name="type-field-characters"></a>Türü alan karakterleri

|Türü karakteri|Bağımsız Değişken|Çıkış biçimi|
|--------------------|--------------|-------------------|
|**c**|Karakter|İle kullanıldığında `printf` İşlevler, bir tek baytlı karakter; ile kullanıldığında belirtir `wprintf` İşlevler, bir geniş karakter belirtir.|
|**C**|Karakter|İle kullanıldığında `printf` İşlevler, bir geniş karakter; ile kullanıldığında belirtir `wprintf` İşlevler, bir tek baytlı karakter belirtir.|
|**d**|Tamsayı|İmzalanmış ondalık tamsayı.|
|**i**|Tamsayı|İmzalanmış ondalık tamsayı.|
|**o**|Tamsayı|İmzalanmamış sekizlik tamsayı.|
|**u**|Tamsayı|İmzalanmamış ondalık tamsayı.|
|**x**|Tamsayı|İmzasız onaltılık tamsayı; "abcdef" kullanır.|
|**X**|Tamsayı|İmzasız onaltılık tamsayı; "ABCDEF" kullanır.|
|**e**|Kayan nokta|[-] Biçiminde olan değeri işaretli*d.dddd*__e±__*GG*[*d*] burada *d* bir adet ondalık rakam olduğunu *dddd* belirtilen duyarlık bağlı olarak bir veya daha fazla ondalık basamak veya varsayılan olarak altı ve *GG*[*d*] bağlıolarakikiveyaüçondalıkbasamak[çıkış biçimi](../c-runtime-library/set-output-format.md) ve üs boyutu.|
|**E**|Kayan nokta|Aynı **e** dışında biçimi **E** yerine **e** üs tanıtır.|
|**f**|Kayan nokta|[-] Biçiminde olan değeri işaretli*dddd*__.__ *dddd*burada *dddd* bir veya daha fazla ondalık basamak. Ondalık sayı büyüklüğünü üzerinde bağlıdır önce basamak sayısı ve istenen duyarlık veya altı varsayılan ondalık ayırıcıdan sonraki basamak sayısı.|
|**F**|Kayan nokta|Aynı **f** sonsuzluk ve nan çıkış büyük harfle dışında biçimlendirin.|
|**g**|Kayan nokta|İşaretli değerleri görüntülenir **f** veya **e** biçimi, hangisi için belirtilen değer ve duyarlık daha kısadır. **e** değerinin üs -4'den az olduğunda yalnızca veya büyüktür veya eşittir biçimi kullanılır *duyarlık* bağımsız değişken. Sıfırları kesilir ve yalnızca bir ondalık görünür veya daha fazla basamak takip edin.|
|**G**|Kayan nokta|Aynı **g** , hariç biçimde **E**, yerine **e**, üs (uygun olduğunda) sunar.|
|**a**|Kayan nokta|[-] Biçiminde olan onaltılık çift duyarlıklı kayan nokta değeri işaretli 0 x*h.hhhh*__p±__*GG*burada *h.hhhh* onaltılık olan Mantis basamak (küçük harf kullanarak) ve *GG* bir veya daha fazla rakamdır, üs için. Duyarlık noktadan sonra basamak sayısını belirtir.|
|**A**|Kayan nokta|[-] 0 X biçiminde olan onaltılık çift duyarlıklı kayan nokta değeri işaretli*h.hhhh*__P±__*GG*burada *h.hhhh* onaltılık olan Mantis basamak (büyük harf kullanarak) ve *GG* bir veya daha fazla rakamdır, üs için. Duyarlık noktadan sonra basamak sayısını belirtir.|
|**n**|Tamsayı işaretçisi|Başarıyla şu ana kadar akış veya arabelleğe yazılan karakter sayısı. Bu değer, adresi bağımsız değişken olarak verilen tamsayı depolanır. Tamsayı işaret boyutunu bir bağımsız değişkeni boyut belirtimi ön eke göre denetlenebilir. **n** Belirleyicisi, varsayılan olarak devre dışıdır; önemli güvenlik notu bilgi için bkz.|
|**p**|İşaretçi türü|Bağımsız değişkenin adresi onaltılık basamak olarak görüntüler.|
|**s**|Dize|İle kullanıldığında `printf` İşlevler, bir tek baytlı veya çok baytlı karakter dizesi; ile kullanıldığında belirtir `wprintf` İşlevler, bir geniş karakter dizesini belirtir. İlk boş karaktere kadar veya kadar karakter görüntülenmezse *duyarlık* değerine ulaşılmadan.|
|**S**|Dize|İle kullanıldığında `printf` İşlevler, geniş karakterli bir dizedir; ile kullanıldığında belirtir `wprintf` İşlevler, bir tek baytlı veya çok baytlı karakter dizesi belirtir. İlk boş karaktere kadar veya kadar karakter görüntülenmezse *duyarlık* değerine ulaşılmadan.|
|**Z**|`ANSI_STRING` veya `UNICODE_STRING` yapısı|Zaman adresini bir [ANSI_STRING](/windows/desktop/api/ntdef/ns-ntdef-_string) veya [UNICODE_STRING](/windows-hardware/drivers/ddi/content/wudfwdm/ns-wudfwdm-_unicode_string) yapısı bağımsız değişkeni geçirilir, işaret ettiği arabellek içindeki dize görüntüler `Buffer` yapısı alan. Kullanım bir *boyutu* değiştiricisi öneki **w** belirtmek için bir `UNICODE_STRING` bağımsız değişken — Örneğin, `%wZ`. `Length` Yapısının alanı dize uzunluğu için bayt cinsinden ayarlanması gerekir. `MaximumLength` Yapısının alanı uzunluğu arabellek, bayt cinsinden ayarlanması gerekir.<br /><br /> Genellikle, **Z** türü karakter yalnızca bir dönüştürme belirtimi gibi kullandığınız işlevlerinde hata ayıklama sürücüde kullanılan `dbgPrint` ve `kdPrint`.|

Visual Studio 2015'te başlatılmasının bir kayan nokta dönüştürme belirleyicisine karşılık gelen bağımsız değişken (**bir**, **A**, **e**, **E**, **f**, **F**, **g**, **G**) belirsiz sonsuz veya NaN, biçimlendirilmiş çıktı C99 standartlarına uyar. Bu tabloda biçimlendirilmiş çıktı:

|Değer|Çıkış|
|-----------|------------|
|sonsuz|`inf`|
|Sessiz bir NaN|`nan`|
|NaN sinyali gönderiliyor|`nan(snan)`|
|Belirsiz NaN|`nan(ind)`|

Bu değerlerden herhangi birini bir işaretiyle önekli. Bir kayan nokta varsa *türü* dönüştürme belirleyici karakterin büyük harf olup, ardından çıktı ayrıca büyük harflerle biçimlendirilir. Örneğin, biçim belirticisi ise `%F` yerine `%f`, sonsuzluk olarak biçimlendirilmiş `INF` yerine `inf`. `scanf` İşlevleri de bu dizeleri ayrıştırma, bu değerleri bir gidiş dönüş aracılığıyla anlamanızı sağlayacak `printf` ve `scanf` işlevleri.

Visual Studio 2015 öncesinde CRT çıktısı belirsiz sonsuz ve NaN değerleri için farklı, standart bir biçim kullanılır:

|Değer|Çıkış|
|-----------|------------|
|+ Infinity|`1.#INF` *rasgele rakamlar*|
|-Infinity|`-1.#INF` *rasgele rakamlar*|
|Belirsiz (sessiz bir NaN ile aynı)|*basamak* `.#IND` *rasgele rakamlar*|
|NaN|*basamak* `.#NAN` *rasgele rakamlar*|

Bunlardan birine bir işaretiyle önekli ve biraz daha farklı alan genişliğini ve duyarlığı, bazen beklenmedik etkileri olan bağlı olarak biçimlendirilmiş olabilir. Örneğin, `printf("%.2f\n", INFINITY)` yazdırır `1.#J` #INF "2 basamaklı kesinliği için yuvarlanmasını çünkü".

> [!NOTE]
> Bağımsız değişken için karşılık gelen, `%s` veya `%S`, veya `Buffer` karşılık gelen bağımsız değişken alan `%Z`, bir null işaretçiyse, "(null)" görüntülenir.

> [!NOTE]
> Tüm üstel biçimlerde, üs görüntülenecek basamak sayısı alt sınırını iki, üç yalnızca gerekirse kullanmaktır. Kullanarak [_set_output_format](../c-runtime-library/set-output-format.md) işlevi üç Visual Studio 2013 için ve önce yazılmış kod ile geriye dönük uyumluluk için görüntülenecek basamak sayısını ayarlayabilirsiniz.

> [!IMPORTANT]
> Çünkü `%n` biçimi doğası gereği güvenli, varsayılan olarak devre dışıdır. Varsa `%n` karşılaşılanaa bir biçim dizesinde geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../c-runtime-library/parameter-validation.md). Etkinleştirmek için `%n` desteklemek için bkz: [_set_printf_count_output](../c-runtime-library/reference/set-printf-count-output.md).

<a name="flags"></a>

## <a name="flag-directives"></a>Bayrak yönergeleri

İlk isteğe bağlı bir dönüştürme belirtimi alanını içeren *bayrak yönergeleri*, sıfır veya daha fazla bayrak çıkış gerekçe belirtin ve işareti, boşluk, baştaki sıfırlar, ondalık basamak çıkış ve sekizlik denetim karakterleri ve onaltılık ön ekler. Bir dönüştürme belirtimi birden fazla bayrağı yönergesi görünebilir ve bayrağı karakter herhangi bir sırada görünebilir.

### <a name="flag-characters"></a>Bayrağı karakter

|Bayrağı|Açıklama|Varsayılan|
|----------|-------------|-------------|
|**-**|Sola Hizala: Belirtilen alan genişliği içinde sonucu.|Sağa Hizala.|
|**+**|Bir oturum kullanın (+ veya -) işaretli bir türe ise çıkış değeri ön eki.|Oturum, yalnızca imzalı için negatif değerler (-) görünür.|
|**0**|Varsa *genişliği* tarafından öneki **0**, önde gelen minimum genişliğini ulaşılana kadar sıfır eklenir. Her iki **0** ve **-** görünen **0** göz ardı edilir. Varsa **0** bir tamsayı biçimi için belirtilen (**miyim**, **u**, **x**, **X**, **o**, **d**) ve duyarlık belirtimi de vardır; örneğin, `%04.d`— **0** göz ardı edilir. Varsa **0** için belirtilen **bir** veya **A** kayan nokta biçimi, önünde sıfır $a Mantis için sonra `0x` veya `0X` önek.|Doldurma olmaması.|
|**blank** (' ')|Boş bir çıkış değeri önek olarak işaretli ve pozitif ise eklemek için kullanın. Her iki boşluk yoksayılır boş ve + bayrakları görünür.|Hiçbir boş görünür.|
|**#**|İle kullanıldığında **o**, **x**, veya **X** biçimi **#** bayrak kullandığı 0, 0 x ' veya 0 sırasıyla ön eki her sıfır olmayan X Çıkış değeri.|Hiçbir boş görünür.|
||İle kullanıldığında **e**, **E**, **f**, **F**, **bir** veya **A** Biçim, **#** bayrak, ondalık nokta içeren çıkış değeri zorlar.|Ondalık basamak onu izleyen görüntülenir.|
||İle kullanıldığında **g** veya **G** biçimi **#** bayrağı ondalık nokta içeren çıkış değeri zorlar ve sondaki sıfırlar atacağı engeller.<br /><br /> İle kullanıldığında göz ardı **c**, **d**, **miyim**, **u**, veya **s**.|Ondalık basamak onu izleyen görüntülenir. Sondaki sıfırlar kesilir.|

<a name="width"></a>

## <a name="width-specification"></a>Genişlik belirtimi

İsteğe bağlı bir genişlik belirtimi alanı sonra herhangi bir dönüştürme belirtiminde görünür *bayrakları* karakter. *Genişliği* olmayan en az sayıda çıkış karakteri denetleyen negatif olmayan bir ondalık tamsayı bağımsız değişken. Çıkış değeri karakter sayısı belirtilen genişlik küçükse sola veya sağa değerlerin boşluklar eklenir — olup sola hizalama bayrak bağlı olarak (**-**) belirtilen — en düşük kadar Genişlik ulaşıldı. Varsa *genişliği* öneki dönüştürme bir sonsuz veya NaN olduğunda dışında minimum genişliğini ulaşılana kadar 0 tarafından baştaki sıfırlar tamsayı veya kayan nokta dönüştürme eklenir.

Genişlik belirtimi hiçbir zaman kesilecek değeri neden olur. Çıkış değeri karakter sayısı belirtilen genişlik büyükse veya *genişliği* olduğundan verilen değil, tüm karakter değerinin çıktı tabi olan *duyarlık* belirtimi.

Genişlik belirtimi bir yıldız işareti ise (`*`), bir `int` bağımsız değişken bağımsız değişken listesinden değeri sağlar. *Genişliği* Bu örnekte gösterildiği gibi bağımsız değişken bağımsız değişken listesinde biçimlendirilen değer gelmelidir:

`printf("%0*f", 5, 3);  /* 00003 is output */`

Eksik veya küçük *genişliği* dönüştürme belirtimi değerinde bir çıkış değeri atacağı neden olmaz. Daha geniş bir dönüştürmenin sonucu ise *genişliği* değeri, alan dönüştürme sonucu içerecek şekilde genişletir.

<a name="precision"></a>

## <a name="precision-specification"></a>Duyarlık belirtimleri

Bir dönüştürme belirtiminde üçüncü isteğe bağlı alan duyarlık belirtimi olur. Dönüştürme türüne bağlı olarak, dize karakter sayısı, ondalık basamak sayısını veya çıkış olarak anlamlı basamak sayısını belirten bir negatif olmayan ondalık tamsayı tarafından izlenen bir nokta (.) oluşur.

Genişlik belirtimi farklı olarak, çıkış değeri kesilmesi veya kayan nokta değerini yuvarlama duyarlık belirtimi neden olabilir. Varsa *duyarlık* dönüştürülecek 0 ve değeri 0 ise, sonuç hiçbir karakter çıktı Bu örnekte gösterildiği gibi belirtilir:

`printf( "%.0d", 0 );      /* No characters output */`

Duyarlık belirtimi bir yıldız işareti ise (\*), bir `int` bağımsız değişken bağımsız değişken listesinden değeri sağlar. Bağımsız değişken listesindeki *duyarlık* bağımsız değişkeni, bu örnekte gösterildiği gibi Biçimlendirilmekte olan, değerin gelmelidir:

`printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`

*Türü* karakter ya da yorumunu belirler *duyarlık* veya varsayılan duyarlık olduğunda *duyarlık* aşağıdaki tabloda gösterildiği gibi atlanır.

### <a name="how-precision-values-affect-type"></a>Nasıl duyarlık değerleri türü

|Tür|Açıklama|Varsayılan|
|----------|-------------|-------------|
|**a**, **A**|Duyarlık noktadan sonra basamak sayısını belirtir.|Varsayılan duyarlık 13'tür. Duyarlık 0 ise, hiçbir ondalık sürece yazdırılır **#** bayrağı kullanılır.|
|**c**, **C**|Duyarlık etkisi yoktur.|Karakter yazdırılır.|
|**d**, **i**, **o**, **u**, **x**, **X**|Duyarlık yazdırılması basamak sayısı alt sınırını belirtir. Bağımsız değişken basamak sayısını ise kısa *duyarlık*, çıkış değeri soldaki sıfırlarla doldurulur. Değerin basamak sayısını aştığında kesilmiş değil *duyarlık*.|Varsayılan duyarlık 1'dir.|
|**e**, **E**|Kesinlik ondalık ayırıcıdan sonra yazdırılması basamak sayısını belirtir. Son yazdırılan basamak yuvarlanır.|Varsayılan duyarlık 6'dır. Varsa *duyarlık* 0 veya aşağıdaki olmadan bir sayı nokta (.) görüntülenir, ondalık noktası yok yazdırılır.|
|**f**, **F**|Duyarlık değeri ondalık ayırıcıdan sonra basamak sayısını belirtir. Ondalık noktası varsa, en az bir rakam önce görünür. Değerin basamak uygun sayıya yuvarlanır.|Varsayılan duyarlık 6'dır. Varsa *duyarlık* 0 ya da aşağıdaki olmadan bir sayı nokta (.) görünürse, ondalık noktası yok yazdırılır.|
|**g**, **G**|Duyarlık yazdırılan basamak sayısını belirtir.|Altı basamaktan yazdırılır ve sondaki sıfırları kesilir.|
|**s**, **S**|Duyarlık maksimum yazdırılan karakter sayısını belirtir. Etkilenmesinin karakterleri *duyarlık* yazdırılmaz.|Bir null karakteri karşılaşılanaa kadar karakterleri yazdırılır.|

<a name="size"></a>

## <a name="argument-size-specification"></a>Bağımsız değişkeni boyut belirtimi

Bir dönüştürme belirtimi *boyutu* alandır için bir bağımsız değişken uzunluk değiştiricisidir *türü* dönüştürme belirleyicisine. *Boyutu* alanı önekleri *türü* alan —**hh**, **h**, **j**, **m** (Küçük Harf L), **L**, **ll**, **t**, **w**, **z**, **miyim**(büyük harf i), **I32**, ve **I64**— ilgili bağımsız değişkenin "boyutunu" belirtin — uzun veya kısa bir 32 bit veya 64-bit, tek baytlı karakter veya geniş karakter — bağlı olarak Değiştirilen dönüştürme belirleyicisine. Bu boyut önekleri ile kullanılan *türü* öğesindeki karakterler `printf` ve `wprintf` aileleri aşağıdaki tabloda gösterildiği gibi bağımsız değişken boyutları yorumunu belirtmek için işlev. *Boyutu* alanı bazı bağımsız değişken türleri için isteğe bağlıdır. Boyut öneki belirtilmediğinde, tamsayı bağımsız değişkenleri biçimlendirici kullanır; Örneğin, imzalı veya imzasız `char`, `short`, `int`, `long`ve Numaralandırma türleri — olarak 32-bit `int` türleri ve `float`, `double`, ve `long double` kayan nokta bağımsız değişkenleri olarak 64-bit tüketilen `double` türleri. Bu değişken bağımsız değişken listeleri için varsayılan bağımsız değişken promosyon kurallarını eşleşir. Üç noktalar ve varsayılan bağımsız değişken bağımsız değişken yükseltme hakkında daha fazla bilgi için bkz [sonek ifadeleri](../cpp/postfix-expressions.md). Hem 32-bit hem de 64-bit sistemlerde, 64-bit tamsayı bağımsız değişkeninin dönüştürme belirtimi boyut öneki içermelidir **ll** veya **I64**. Aksi takdirde, biçimlendirici davranışı tanımsızdır.

Bazı türleri farklı boyut 32-bit ve 64-bit kodu verilmiştir. Örneğin, `size_t` 32 bit uzun x86 ve 64 bit x64 için derlenmiş kod içine derlenmiş kod. Platformdan bağımsız değişken genişlikli türleri için biçimlendirme kod oluşturmak için bir bağımsız değişken genişlikli Boyutu değiştiricisi kullanabilirsiniz. Alternatif olarak, 64-bit bağımsız değişkeni boyut değiştiricisini kullanın ve açıkça değişken genişlikli bağımsız değişken türü 64 bit yükseltin. Microsoft'a özgü **miyim** (büyük harf i) bağımsız değişkeni boyut değiştiricisi değişken genişlikli tamsayı bağımsız değişkenleri işleme, ancak türe özgü öneririz **j**, **t**ve **z** taşınabilirlik için değiştiriciler.

### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>Printf ve wprintf biçim türü belirteçleri için boyut önekleri

|Belirtmek için|Önek kullanın|Tür belirticisiyle|
|----------------|----------------|-------------------------|
|`char`<br />`unsigned char`|**hh**|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|`short int`<br />`short unsigned int`|**h**|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|`__int32`<br />`unsigned __int32`|**I32**|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|`__int64`<br />`unsigned __int64`|**I64**|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|`intmax_t`<br />`uintmax_t`|**j** veya **I64**|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|`long double`|**m** (Küçük Harf L) veya **m**|**bir**, **A**, **e**, **E**, **f**, **F**, **g**, veya **G**|
|`long int`<br />`long unsigned int`|**m** (Küçük Harf L)|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|`long long int`<br />`unsigned long long int`|**tümünü** (tümünü küçük harf)|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|`ptrdiff_t`|**t** veya **miyim** (büyük harf i)|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|`size_t`|**z** veya **miyim** (büyük harf i)|**d**, **miyim**, **o**, **u**, **x**, veya **X**|
|Tek baytlı karakter|**h**|**c** veya **C**|
|geniş karakter|**m** (Küçük Harf L) veya **w**|**c** veya **C**|
|Tek baytlı karakter dizesi|**h**|**s**, **S**, veya **Z**|
|Geniş karakter dizesi|**m** (Küçük Harf L) veya **w**|**s**, **S**, veya **Z**|

`ptrdiff_t` Ve `size_t` türleridir `__int32` veya `unsigned __int32` 32-bit platformlarda ve `__int64` veya `unsigned __int64` 64-bit platformlarda. **miyim** (büyük harf i), **j**, **t**, ve **z** boyut önekleri platformuna yönelik doğru bağımsız değişken genişliğini yararlanın.

Visual C++ ' ta rağmen `long double` farklı bir tür aynı iç gösterime sahip `double`.

Bir **hc** veya **hC** tür tanımlayıcısı ile eşanlamlıdır **c** içinde `printf` işlevleri ile **C** içinde `wprintf` işlevleri. Bir **lc**, **lC**, **wc** veya **wC** tür tanımlayıcısı ile eşanlamlıdır **C** içinde `printf` İşlevler ile **c** içinde `wprintf` işlevleri. Bir **hs** veya **hS** tür tanımlayıcısı ile eşanlamlıdır **s** içinde `printf` işlevleri ile **S** içinde `wprintf` işlevleri. Bir **ls**, **lS**, **ws** veya **wS** tür tanımlayıcısı ile eşanlamlıdır **S** içinde `printf` İşlevler ile **s** içinde `wprintf` işlevleri.

> [!NOTE]
> **Microsoft Specific** **miyim** (büyük harf i), **I32**, **I64**, ve **w** bağımsız değişkeni boyut değiştirici önekleri Microsoft olan Uzantılar ve olan ISO C uyumlu değil. **h** önek veri türü ile kullanıldığında `char` ve **l** (Küçük Harf L) veri türü ile kullanıldığında önek `double` Microsoft uzantılarıdır.

## <a name="see-also"></a>Ayrıca bkz.

[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[printf_p Konumsal Parametreler](../c-runtime-library/printf-p-positional-parameters.md)
