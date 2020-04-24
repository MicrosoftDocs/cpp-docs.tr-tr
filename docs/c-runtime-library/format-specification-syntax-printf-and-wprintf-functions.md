---
title: 'Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri'
ms.date: 10/21/2019
helpviewer_keywords:
- format specification fields for printf function
- printf function format specification fields
- flag directives, printf function
- type fields, printf function
- width fields, printf function
- precision fields, printf function
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
ms.openlocfilehash: 781c90414090ff8a21414c72f744ed275e315d56
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032167"
---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>Biçim belirtim sözdizimi: printf ve wprintf işlevleri

Çeşitli `printf` ve `wprintf` işlevler bir biçim dize ve isteğe bağlı bağımsız değişkenler almak ve çıktı için karakter biçimlendirilmiş bir dizi üretmek. Biçim dizesi, çıktı için gerçek karakterler veya çıktıda bir bağımsız değişkenin nasıl biçimlendirilir açıklayan kodlanmış *dönüşüm belirtimleri* olan sıfır veya daha fazla *yönerge*içerir. Bu makalede, biçim dizesinde dönüşüm belirtimlerini kodlamak için kullanılan sözdizimi açıklanmaktadır. Bu işlevlerin listesi için [Stream I/O](../c-runtime-library/stream-i-o.md)bölümüne bakın.

Dönüştürme belirtimi, bu formdaki isteğe bağlı ve gerekli alanlardan oluşur:

**%**[[*bayraklar*](#flags)] [[*genişlik*](#width)] [. [*hassas*](#precision)] [[*boyut*](#size)] [*türü*](#type)

Dönüştürme belirtiminin her alanı, belirli bir biçim seçeneğini veya dönüştürme belirtimini belirten bir karakter veya sayıdır. Gerekli *tür* alanı, bir bağımsız değişkene uygulanacak dönüşüm türünü belirtir. İsteğe bağlı *bayraklar,* *genişlik*ve *kesinlik* alanları, öncü alanlar veya sıfırlar, yaslama ve görüntühassasiyet gibi ek biçim yönlerini denetler. *Boyut* alanı, tüketilen ve dönüştürülen bağımsız değişkenin boyutunu belirtir.

Temel dönüşüm belirtimi yalnızca yüzde işaretini ve *bir tür* karakterini içerir. Örneğin, `%s` bir dize dönüştürme belirtir. Yüzde işareti karakterini yazdırmak `%%`için . Yüzde işaretini biçim alanı olarak anlamı olmayan bir karakter takip ederse, geçersiz parametre işleyicisi çağrılır. Daha fazla bilgi için [Parametre Doğrulama'ya](../c-runtime-library/parameter-validation.md)bakın.

> [!IMPORTANT]
> Güvenlik ve kararlılık için, dönüşüm belirtimi dizelerinin kullanıcı tanımlı olmadığından emin olun. Örneğin, kullanıcıdan bir ad girmesini ve girdiyi adlandırılmış `user_name`bir dize değişkeninde depolayan bir program düşünün. Yazdırmak `user_name`için bunu yapmayın:
>
> `printf( user_name ); /* Danger!  If user_name contains "%s", program will crash */`
>
> Bunun yerine, bunu yapın:
>
> `printf( "%s", user_name );`

<a name="type"></a>

> [!NOTE]
> Visual `printf` Studio 2015'te işlevailesi ve `scanf` işlevi **sıralı** `<stdio.h>` olarak `<conio.h>` ilan edildi ve üstbilgi ve üstbilgiye taşındı. Eski kodu geçirtiyorsanız, bu işlevlerle bağlantılı olarak *LNK2019'u* görebilirsiniz. Daha fazla bilgi için Visual [C++ değişiklik geçmişi 2003 - 2015'e](../porting/visual-cpp-change-history-2003-2015.md#stdio_and_conio)bakın.

## <a name="type-conversion-specifier"></a>Tür dönüştürme belirtimi

*Tür* dönüştürme belirtimi karakteri, ilgili bağımsız değişkenin bir karakter, bir dize, işaretçi, bir tamsayı veya kayan nokta sayısı olarak yorumlanıp yorumlanacağıbelirtilir. *Tür* karakteri yalnızca gerekli dönüşüm belirtimi alanıdır ve isteğe bağlı alanlardan sonra görüntülenir.

Biçim dizesini izleyen bağımsız değişkenler, ilgili *tür* karakterine ve isteğe bağlı [boyut](#size) önekine göre yorumlanır. Karakter `char` türleri için `wchar_t` dönüşümler ve **c** veya **C**kullanılarak belirtilir ve tek bayt ve çok bayt veya geniş karakter dizeleri kullanılarak belirtilir **s** veya **S**kullanılarak , hangi biçimlendirme işlevinin kullanıldığına bağlı olarak. **c** ve **s** kullanılarak belirtilen karakter ve dize `char` `char*` bağımsız `printf` değişkenleri, `wchar_t` aile `wchar_t*` `wprintf` işlevleri veya aile işlevleri olarak ve bunlar tarafından yorumlanır. **C** ve **S** kullanılarak belirtilen karakter ve dize `wchar_t` `wchar_t*` bağımsız `printf` değişkenleri, `char` aile `char*` `wprintf` işlevleri veya aile işlevleri olarak ve bunlar tarafından yorumlanır. Bu davranış Microsoft'a özgüdür.

`short`D , **i**, `int` `long` **o** **,** **u**, **x**, ve **X**kullanılarak belirlenen tamsayı türleri , , , `long long`, ve bunların `unsigned` varyantları. Kayan nokta türleri `float`, `double`, `long double`ve , **a**, **A**, **e**, **E**, **f**, **F**, **g**, ve **G**kullanılarak belirtilir . Varsayılan olarak, bir *boyut* öneki tarafından değiştirilmedikçe, tamsayı bağımsız `int` değişkenleri türüne zorlanır ve kayan `double`nokta bağımsız değişkenleri . 64 bit sistemlerde, `int` bir 32 bit lik bir değerdir; bu nedenle, **ll** veya **I64** *boyutu* öneki kullanılmadığı sürece çıkış için biçimlendirildiğinde 64 bit tamsayılar kesilir. **p** ile belirtilen işaretçi türleri platform için varsayılan işaretçi boyutunu kullanır.

> [!NOTE]
> **Microsoft'a özel:** **Z** tipi karakter ve **c**, **C**, **s**ve **S** tipi karakterlerin davranışı `printf` `wprintf` ve işlevleri ile kullanıldığında, Microsoft uzantıları vardır. ISO C standardı dar karakterler ve dizeler için **sürekli c** ve **s** kullanır ve **c** ve **s** geniş karakterler ve dizeleri için, tüm biçimlendirme işlevleri.

### <a name="type-field-characters"></a>Alan karakterlerini yazın

|Türü karakter|Bağımsız Değişken|Çıktı biçimi|
|--------------------|--------------|-------------------|
|**C**|Karakter|Fonksiyonlarla `printf` kullanıldığında, tek baytlık bir karakter belirtir; işlevleri ile `wprintf` kullanıldığında, geniş bir karakter belirtir.|
|**C**|Karakter|Fonksiyonlar `printf` ile kullanıldığında, geniş bir karakter belirtir; işlevlerle `wprintf` kullanıldığında, tek baytlık bir karakter belirtir.|
|**D**|Tamsayı|İmzalı ondalık sayı.|
|**Ⅰ**|Tamsayı|İmzalı ondalık sayı.|
|**o**|Tamsayı|İmzasız sekizli tümseci.|
|**U**|Tamsayı|İmzasız ondalık sayı.|
|**X**|Tamsayı|İmzasız hexadecimal tamsayı; "abcdef" kullanır.|
|**X**|Tamsayı|İmzasız hexadecimal tamsayı; "ABCDEF" kullanır.|
|**E**|Kayan nokta|[-]*d.dddd*__e±__*dd*\[*d*], *d* ondalık basamak olduğu biçime sahip imzalı değer, *dddd* belirtilen duyarlık bağlı olarak bir veya daha fazla ondalık basamak veya varsayılan olarak altı ve *dd*\[*d*] çıktı [biçimine](../c-runtime-library/set-output-format.md) ve büyüklüğüne bağlı olarak iki veya üç ondalık basamaktır.|
|**E**|Kayan nokta|**E** formatı ile aynı olan **e** yerine **e** üs tanıttı.|
|**F**|Kayan nokta|[-]*dddd*formuna sahip imzalı değer __.__ *dddd*, *dddd* bir veya daha fazla ondalık basamak tır. Ondalık noktadan önceki basamak sayısı sayının büyüklüğüne, ondalık noktadan sonraki basamak sayısı ise istenen duyarlığa veya varsayılan olarak altı basamaksayısına bağlıdır.|
|**F**|Kayan nokta|Sonsuzluk ve nan çıktısı dışında **f** biçimiyle aynıdır.|
|**G**|Kayan nokta|İmzalanan **değerler,** verilen değer ve kesinlik için hangisi daha kompaktsa f veya **e** biçiminde görüntülenir. **E** biçimi yalnızca değerin üst bölümü -4'ten küçük veya daha büyük veya *hassas* bağımsız değişkene eşit olduğunda kullanılır. Sondaki sıfırlar kesilir ve ondalık nokta yalnızca bir veya daha fazla basamak onu takip ederse görüntülenir.|
|**G**|Kayan nokta|**G** biçimiile özdeş, e dışında **,** **yerine e**, üs tanıttı (uygun olduğunda).|
|**A**|Kayan nokta|[-]0x*h.hhhh*__p±__*dd*formuna sahip imzalı hexadecimal çift duyarlıklı kayan nokta değeri , *h.hhhh* mantissanın hex basamakları (küçük harf kullanarak) ve *dd* üs için bir veya daha fazla basamakvardır. Kesinlik, noktadan sonraki basamak sayısını belirtir.|
|**A**|Kayan nokta|[-]0X*h.hhhh*__P±__*dd*formuna sahip imzalı hexadecimal çift duyarlıklı kayan nokta değeri , *h.hhhh* mantissanın hex basamakları (büyük harflerkullanılarak) ve *dd* üs için bir veya daha fazla basamaktır. Kesinlik, noktadan sonraki basamak sayısını belirtir.|
|**n**|Sonda için işaretçi|Akışa veya arabelleğe şimdiye kadar başarıyla yazılmış karakter sayısı. Bu değer, adresi bağımsız değişken olarak verilen tamsayıda depolanır. Işaret eden bir integer boyutu bir bağımsız değişken boyutu belirtimi öneki tarafından denetlenebilir. **n** belirtici varsayılan olarak devre dışı bırakılır; bilgi için önemli güvenlik notuna bakın.|
|**P**|İşaretçi türü|Bağımsız değişkeni hexadecimal basamaklarda bir adres olarak görüntüler.|
|**S**|Dize|İşlevlerle `printf` kullanıldığında, tek bayt veya çok bayt karakter dizesi belirtir; işlevlerle `wprintf` kullanıldığında, geniş karakterli bir dize belirtir. Karakterler ilk null karaktere kadar veya *kesinlik* değerine ulaşılına kadar görüntülenir.|
|**S**|Dize|Işlevlerle `printf` kullanıldığında, geniş karakterli bir dize belirtir; işlevlerle `wprintf` kullanıldığında, tek bayt veya çok bayt karakter dizesi belirtir. Karakterler ilk null karaktere kadar veya *kesinlik* değerine ulaşılına kadar görüntülenir.|
|**Z**|`ANSI_STRING`veya `UNICODE_STRING` yapı|Bir [ANSI_STRING](/windows/win32/api/ntdef/ns-ntdef-string) veya [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) yapının adresi bağımsız değişken olarak geçirildiğinde, `Buffer` yapının alanı tarafından işaret edilen arabellekte bulunan dize görüntülenir. Bir `UNICODE_STRING` bağımsız değişken belirtmek için **w** *boyut* değiştirici öneki kullanın—örneğin, `%wZ`. Yapının `Length` alanı dize uzunluğuna, baytlara ayarlanmalıdır. Yapının `MaximumLength` alanı arabelleğe bayt olarak uzunluğa ayarlanmalıdır.<br /><br /> Tipik olarak, **Z** türü karakter gibi bir dönüşüm belirtimi kullanan sürücü hata `dbgPrint` `kdPrint`ayıklama işlevleri yalnızca kullanılır.|

Visual Studio 2015'ten başlayarak, kayan nokta dönüştürme belirticisine karşılık gelen bağımsız değişken (**a**, **A**, **e**, **E**, **f**, **F**, **g**, **G**) sonsuz, belirsiz veya NaN ise, biçimlendirilmiş çıktı C99 standardına uygundur. Bu tablo biçimlendirilmiş çıktıyı listeler:

|Değer|Çıktı|
|-----------|------------|
|Sonsuz -luk|`inf`|
|Sessiz Nan|`nan`|
|Sinyal NaN|`nan(snan)`|
|Belirsiz NaN|`nan(ind)`|

Bu değerlerden herhangi biri bir işaret tarafından önceden belirlenmiş olabilir. Kayan nokta *türü* dönüştürme belirtimi karakteri büyük harf ise, çıktı da büyük harflerle biçimlendirilir. Örneğin, `%F` biçim belirtici yerine `%f`ise, sonsuzluk `INF` yerine `inf`biçimlendirilir. Bu `scanf` değerler bu dizeleri ayrıştırabilir, böylece bu değerler `printf` `scanf` bir gidiş-dönüş ve işlevler yapabilir.

Visual Studio 2015'ten önce CRT, sonsuz, belirsiz ve NaN değerlerinin çıktısı için farklı, standart dışı bir biçim kullanmıştı:

|Değer|Çıktı|
|-----------|------------|
|+ sonsuzluk|`1.#INF`*rasgele basamaklar*|
|- sonsuzluk|`-1.#INF`*rasgele basamaklar*|
|Belirsiz (sessiz NaN ile aynı)|*basamaklı* `.#IND` *rasgele basamaklar*|
|NaN|*basamaklı* `.#NAN` *rasgele basamaklar*|

Bunlardan herhangi biri bir işaret tarafından önceden belirlenmiş olabilir ve alan genişliğine ve hassasiyetine bağlı olarak, bazen alışılmadık efektlerle biraz farklı biçimlendirilmiş olabilir. Örneğin, `printf("%.2f\n", INFINITY)` #INF `1.#J` 2 basamaklı kesinlik "yuvarlanır" çünkü yazdırılır.

> [!NOTE]
> Karşılık gelen bağımsız değişken `%s` `%S`veya , `Buffer` ya da karşılık gelen `%Z`bağımsız değişkenin alanı, bir null işaretçi ise, "(null)" görüntülenir.

> [!NOTE]
> Tüm üstel biçimlerde, görüntülenecek üs sayısının en az sayısı ikidir ve yalnızca gerektiğinde üç tane kullanır. [_set_output_format](../c-runtime-library/set-output-format.md) işlevini kullanarak, Visual Studio 2013 ve öncesi için yazılmış kodla geriye doğru uyumluluk için görüntülenen basamak sayısını üçe ayarlayabilirsiniz.

> [!IMPORTANT]
> `%n` Biçim doğal olarak güvenli olmadığından, varsayılan olarak devre dışı bırakılır. Bir `%n` biçim dizesi ile karşılaşılırsa, [Parametre Doğrulama'da](../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Desteği `%n` etkinleştirmek için [_set_printf_count_output](../c-runtime-library/reference/set-printf-count-output.md)bakın.

<a name="flags"></a>

## <a name="flag-directives"></a>Bayrak yönergeleri

Dönüşüm belirtiminde ilk isteğe bağlı alan, işaretlerin, boşlukların, satır aralığının, ondalık noktaların ve sekizli ve heksadecimal öneklerin çıktısını ve çıktısını belirten bayrak *yönergeleri,* sıfır veya daha fazla bayrak karakteri içerir. Dönüşüm belirtiminde birden fazla bayrak yönergesi görünebilir ve bayrak karakterleri herhangi bir sırada görünebilir.

### <a name="flag-characters"></a>Karakterleri işaretleme

|Bayrak|Anlamı|Varsayılan|
|----------|-------------|-------------|
|**-**|Sol, sonucu verilen alan genişliği içinde hizalar.|Sağa hizala.|
|**+**|İmzalı bir türdeyse çıktı değerini önek için bir işaret (+ veya -) kullanın.|İşaret yalnızca negatif imzalı değerler (-) için görünür.|
|**0**|*Genişlik* **0**ile önceden belirlenmişse, en küçük genişliğe ulaşılına kadar satır aralığı sıfırlar eklenir. Hem **0** **-** hem de görünürse, **0** yoksayılır. Bir tamsayı biçimi için **0** belirtilmişse **(i**, **u**, **x**, **X**, **o**, **d**) ve bir kesinlik belirtimi de mevcutsa—örneğin, `%04.d` **-0** yoksayılır. **A** veya **A** kayan nokta biçimi için **0** belirtilirse, önde gelen sıfırlar veya `0x` `0X` önek sonra, mantissa hazırlanır.|Dolgu yok.|
|**boş** (' ')|İmzalanmış ve pozitifse çıktı değerini önek için boş bir boşluk kullanın. Boş ve + bayrakları her ikisi de görünürse boş yoksayılır.|Boş görünmez.|
|**#**|**o**, **x**veya **X** biçimiyle kullanıldığında, **#** bayrak sıfır olmayan çıkış değerini önek için sırasıyla 0, 0x veya 0X kullanır.|Boş görünmez.|
||**E**, **E**, **f**, **F**, **a**veya **A** **#** biçimi yle kullanıldığında, bayrak çıkış değerini ondalık bir nokta içerecek şekilde zorlar.|Ondalık nokta yalnızca basamaklar onu takip ederse görünür.|
||**G** veya **G** biçimiyle kullanıldığında, **#** bayrak çıkış değerini ondalık bir nokta içerecek şekilde zorlar ve sondaki sıfırların kesilmesini önler.<br /><br /> **C**, **d**, **i**, **u**, veya **s**ile kullanıldığında göz ardı edilir.|Ondalık nokta yalnızca basamaklar onu takip ederse görünür. Sondaki sıfırlar kesilir.|

<a name="width"></a>

## <a name="width-specification"></a>Genişlik belirtimi

Dönüşüm belirtiminde, isteğe bağlı genişlik belirtimi alanı herhangi bir *bayrak* karaktersonra görünür. *Genişlik* bağımsız değişkeni, çıktı olan en az karakter sayısını kontrol eden negatif olmayan ondalık bir tamsayıdır. Çıktı değerindeki karakter sayısı belirtilen genişlikten azsa, en az genişliğe ulaşılıncaya kadar sol hizalama bayrağının**-**( ) belirtilip belirtilmedik lerine bağlı olarak, değerlerin soluna veya sağına boşluklar eklenir. *Genişlik* 0 ile önceden belirlenmişse, dönüştürme sonsuzluğa veya NaN'a olduğu durumlar dışında, en küçük genişliğe ulaşılıncaya kadar, satır uçlarına veya kayan nokta dönüşümlerine satır aralığı sıfırlar eklenir.

Genişlik belirtimi hiçbir zaman bir değerin kesildirilmesine neden olmaz. Çıktı değerindeki karakter sayısı belirtilen genişlikten büyükse veya *genişlik* verilmiyorsa, değerin tüm karakterleri *kesinlik* belirtimine tabi olarak çıktıdır.

Genişlik belirtimi bir yıldız`*`işaretiise `int` , bağımsız değişken listesinden bir bağımsız değişken değeri sağlar. *Genişlik* bağımsız değişkeni, bu örnekte gösterildiği gibi, bağımsız değişken listesinde biçimlendirilmekte olan değerden önce olmalıdır:

`printf("%0*d", 5, 3);  /* 00003 is output */`

Dönüşüm belirtiminde eksik veya küçük *bir genişlik* değeri çıktı değerinin kesilmeye neden olmaz. Dönüştürme nin sonucu *genişlik* değerinden daha genişse, alan dönüşüm sonucunu içerecek şekilde genişletilir.

<a name="precision"></a>

## <a name="precision-specification"></a>Hassas belirtim

Dönüştürme belirtiminde, üçüncü isteğe bağlı alan hassas belirtimdir. Bir dönem (.) ve ardından, dönüşüm türüne bağlı olarak, dize karakter sayısını, ondalık basamak sayısını veya çıktı edilecek önemli basamak sayısını belirten negatif olmayan ondalık tamsayıdan oluşur.

Genişlik belirtiminin aksine, kesinlik belirtimi çıktı değerinin kesilmeye veya kayan nokta değerinin yuvarlamasına neden olabilir. *Kesinlik* 0 olarak belirtilirse ve dönüştürülecek değer 0 ise, sonuç, bu örnekte gösterildiği gibi karakter çıkışı değildir:

`printf( "%.0d", 0 );      /* No characters output */`

Kesinlik belirtimi bir yıldız\*işaretiise `int` , bağımsız değişken listesinden bir bağımsız değişken değeri sağlar. Bağımsız değişken listesinde, *kesinleştirilmiş* bağımsız değişken, bu örnekte gösterildiği gibi biçimlendirilmekte olan değerden önce olmalıdır:

`printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`

*Tür* karakteri, aşağıdaki tabloda gösterildiği *gibi, kesinlik* atlandığında *ya kesinliğin* yorumlanmasını ya da varsayılan kesinliği belirler.

### <a name="how-precision-values-affect-type"></a>Hassas Değerler Türü Nasıl Etkiler?

|Tür|Anlamı|Varsayılan|
|----------|-------------|-------------|
|**a**, **A**|Kesinlik, noktadan sonraki basamak sayısını belirtir.|Varsayılan kesinlik 13'dür. Kesinlik 0 ise, **#** bayrak kullanılmadığı sürece ondalık nokta yazdırılmaz.|
|**c**, **C**|Hassasiyetin bir etkisi yok.|Karakter yazdırılır.|
|**d**, **i**, **o**, **u**, **x**, **X**|Kesinlik, yazdırılacak en az basamak sayısını belirtir. Bağımsız değişkendeki basamak sayısı *kesinlikten*azsa, çıkış değeri solda sıfırlarla birlikte eklenir. Basamak sayısı *kesinliği*aştığında değer kesilir.|Varsayılan kesinlik 1'dir.|
|**e**, **E**|Kesinlik, ondalık noktadan sonra yazdırılacak basamak sayısını belirtir. Son yazdırılan basamak yuvarlanır.|Varsayılan kesinlik 6'dır. *Kesinlik* 0 ise veya dönem (.) onu izleyen bir sayı olmadan görünürse, ondalık nokta yazdırılmaz.|
|**f**, **F**|Kesin değer ondalık noktadan sonra basamak sayısını belirtir. Ondalık bir nokta görünürse, önünde en az bir basamak görünür. Değer uygun basamak sayısına yuvarlanır.|Varsayılan kesinlik 6'dır. *Kesinlik* 0 ise veya dönem (.) onu izleyen bir sayı olmadan görünüyorsa, ondalık nokta yazdırılmaz.|
|**g**, **G**|Kesinlik, yazdırılan en yüksek önemli basamak sayısını belirtir.|Altı önemli basamak yazdırılır ve sondaki sıfırlar kesilir.|
|**s**, **S**|Kesinlik, yazdırılacak maksimum karakter sayısını belirtir. *Hassasiyeti* aşan karakterler yazdırılmaz.|Karakterler null bir karakterle karşılaşına kadar yazdırılır.|

<a name="size"></a>

## <a name="argument-size-specification"></a>Bağımsız değişken boyutu belirtimi

Dönüştürme belirtiminde, *boyut* alanı *tür* dönüştürme belirtileyicisi için bir bağımsız değişken uzunluğu değiştiricidir. *Tür* alanına *boyut* alanı önekleri-**hh,** **h**, **j,** **l** (küçük L), **L**, **ll**, **t**, **w**, **z**, **I** (büyük harf i), **I32**, ve **I64**—ilgili bağımsız değişkenin "boyutunu" belirt-uzun veya kısa, 32-bit veya 64-bit, tek bayt karakter veya geniş karakter—değiştirdikleri dönüşüm belirteçlerine bağlı olarak. Bu boyut önekleri, aşağıdaki tabloda `printf` gösterildiği `wprintf` gibi bağımsız değişken boyutlarının yorumlanmasını belirtmek için işlevlerin ve işlevlerin ailelerindeki *tür* karakterleri ile birlikte kullanılır. *Boyut* alanı bazı bağımsız değişken türleri için isteğe bağlıdır. Boyut öneki belirtilmediğinde, formatter, 32 bit türleri `char`ve `short` `int` `long` `int` `float` `double` `long double` kayan nokta bağımsız değişkenleri olarak 32 bit türleri olarak imzalanmış veya imzalanmamış, imzalanmış veya `double` imzalanmamış, büyük hata bağımsız değişkenleri ve kayan nokta bağımsız değişkenleri 64 bit türleri olarak tüketir. Bu davranış, değişken bağımsız değişken listeleri için varsayılan bağımsız değişken promosyon kurallarıyla eşleşir. Bağımsız değişken tanıtımı hakkında daha fazla bilgi için, [Postfix ifadelerinde](../cpp/postfix-expressions.md)Elips ve Varsayılan Bağımsız Değişkenler'e bakın. Hem 32 bit hem de 64 bit sistemlerde, 64 bit tamsayı bağımsız değişkeninin dönüşüm belirtimi **ll** veya **I64**boyutu önekini içermelidir. Aksi takdirde, maddenin davranışı tanımsızdır.

Bazı türler 32 bit ve 64 bit kodfarklı boyutlardadır. Örneğin, `size_t` x86 için derlenen kodda 32 bit, x64 için derlenen kodda 64 bit vardır. Değişken genişlik türleri için platform-agnostik biçimlendirme kodu oluşturmak için değişken genişlikli bağımsız değişken boyutu değiştirici kullanabilirsiniz. Alternatif olarak, 64 bit bağımsız değişken boyutu değiştirici kullanın ve değişken genişlikteki bağımsız değişken türünü açıkça 64 bitle tanıtın. Microsoft'a özgü **I** (büyük harf i) bağımsız değişken boyutu değiştirici değişken genişlikteki tümsedo bağımsız değişkenlerini işler, ancak taşınabilirlik için türüne özgü **j**, **t**ve **z** değiştiriciler öneririz.

### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>printf ve wprintf Format-Type Specifiers için Boyut Önekleri

|Belirtmek için|Önek kullanma|Tür belirtici ile|
|----------------|----------------|-------------------------|
|`char`<br />`unsigned char`|**Hh**|**d**, **i**, **o**, **u**, **x**, veya **X**|
|`short int`<br />`short unsigned int`|**H**|**d**, **i**, **o**, **u**, **x**, veya **X**|
|`__int32`<br />`unsigned __int32`|**I32**|**d**, **i**, **o**, **u**, **x**, veya **X**|
|`__int64`<br />`unsigned __int64`|**I64**|**d**, **i**, **o**, **u**, **x**, veya **X**|
|`intmax_t`<br />`uintmax_t`|**j** veya **I64**|**d**, **i**, **o**, **u**, **x**, veya **X**|
|`long double`|**l** (küçük L) veya **L**|**a**, **A**, **e**, **E**, **f**, **F**, **g**, veya **G**|
|`long int`<br />`long unsigned int`|**l** (küçük L)|**d**, **i**, **o**, **u**, **x**, veya **X**|
|`long long int`<br />`unsigned long long int`|**ll** (küçük LL)|**d**, **i**, **o**, **u**, **x**, veya **X**|
|`ptrdiff_t`|**t** veya **I** (büyük harf i)|**d**, **i**, **o**, **u**, **x**, veya **X**|
|`size_t`|**z** veya **I** (büyük harf i)|**d**, **i**, **o**, **u**, **x**, veya **X**|
|Tek bayt karakter|**H**|**c** veya **C**|
|Geniş karakter|**l** (küçük L) veya **w**|**c** veya **C**|
|Tek bayt karakter dizesi|**H**|**s**, **S**, veya **Z**|
|Geniş karakterli dize|**l** (küçük L) veya **w**|**s**, **S**, veya **Z**|

`ptrdiff_t` Ve `size_t` türleri `__int32` veya `unsigned __int32` 32-bit platformlarda `__int64` `unsigned __int64` ve 64-bit platformlarda. **I** (büyük harf i), **j**, **t**ve **z** boyutu önekleri platform için doğru bağımsız değişken genişliğini alır.

Visual C++'da, farklı bir tür olmasına `long double` rağmen, `double`.

**HC** veya **hC** tipi belirtileyici işlevlerde **c** `printf` ve fonksiyonlarda `wprintf` **C** ile eş anlamlıdır. Bir **lc**, **lC**, **wc**, veya **wC** tipi belirteç `printf` fonksiyonları `wprintf` **C** ile eşanlamlı ve işlevleri **c** ile eşanlamlıdır. **HS** veya **hS** tipi belirtileyici, işlevlerde **s** `printf` s ve işlevlerde `wprintf` **S** ile eş anlamlıdır. LS , **lS**, **ws** veya **wS** tipi belirtileyici, `printf` işlevlerde S ve **ls** **işlevlerde** `wprintf` **s** ile eş anlamlıdır.

> [!NOTE]
> **Microsoft'a özel:** **I** (büyük harf i), **I32**, **I64**ve **w** bağımsız değişken boyutu değiştirici önekleri Microsoft uzantılarıdır ve ISO C uyumlu değildir. Tip verileriyle kullanıldığında **h** önek `char` ve tür verileriyle kullanıldığında **l** (küçük Harf L) önek Microsoft `double` uzantılarıdır.

## <a name="see-also"></a>Ayrıca bkz.

[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[printf_p Konumsal Parametreler](../c-runtime-library/printf-p-positional-parameters.md)
