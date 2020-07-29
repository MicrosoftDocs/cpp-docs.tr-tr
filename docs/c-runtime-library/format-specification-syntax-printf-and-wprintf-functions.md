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
ms.openlocfilehash: 122536ae79c9b7d634677c6b7ec7fc4974f52b4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218760"
---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>Biçim belirtim sözdizimi: printf ve wprintf işlevleri

Çeşitli `printf` ve `wprintf` işlevleri bir biçim dizesi ve isteğe bağlı bağımsız değişkenler alır ve çıktı için biçimlendirilen bir karakter dizisi üretir. Biçim dizesi, çıkışta bir bağımsız değişkeni biçimlendirmeyi açıklayan, çıkış veya kodlanmış *dönüştürme belirtimleri* için sabit karakter olan sıfır veya daha fazla *yönergeler*içerir. Bu makalede, dönüştürme belirtimlerini biçim dizesinde kodlamak için kullanılan söz dizimi açıklanmaktadır. Bu işlevlerin listesi için bkz. [akış g/ç](../c-runtime-library/stream-i-o.md).

Bir dönüştürme belirtimi, bu formdaki isteğe bağlı ve gerekli alanlardan oluşur:

**%**[[*bayraklar*](#flags)] [[*Genişlik*](#width)] [. [*duyarlık*](#precision)] [[*Boyut*](#size)] [*tür*](#type)

Dönüştürme belirtiminin her alanı, belirli bir biçim seçeneğini veya dönüştürme belirticisini belirten bir karakterdir veya bir sayıdır. Gerekli *tür* alanı bir bağımsız değişkene uygulanacak dönüştürme türünü belirtir. İsteğe bağlı *bayraklar*, *Genişlik*ve *duyarlık* alanları, baştaki boşluklar, sıfır, bloklama ve görünen duyarlık gibi ek biçim yönlerini denetler. *Boyut* alanı tüketilen ve dönüştürülen bağımsız değişkenin boyutunu belirtir.

Temel bir dönüştürme belirtimi yalnızca yüzde işaretini ve bir *tür* karakterini içerir. Örneğin, `%s` bir dize dönüştürmesi belirtir. Bir yüzde işareti karakteri yazdırmak için kullanın `%%` . Bir yüzde işaretinin, biçim alanı olarak anlamı olmayan bir karakter gelmesi durumunda, geçersiz parametre işleyicisi çağrılır. Daha fazla bilgi için bkz. [parametre doğrulama](../c-runtime-library/parameter-validation.md).

> [!IMPORTANT]
> Güvenlik ve kararlılık için, dönüştürme belirtimi dizelerinin Kullanıcı tanımlı olmadığından emin olun. Örneğin, kullanıcıdan bir ad girmesini isteyen ve girdiyi adlı bir dize değişkenine depolayan bir programı düşünün `user_name` . Yazdırmak için bunu `user_name` yapın:
>
> `printf( user_name ); /* Danger!  If user_name contains "%s", program will crash */`
>
> Bunun yerine şunu yapın:
>
> `printf( "%s", user_name );`

<a name="type"></a>

> [!NOTE]
> Visual Studio 2015 ' de `printf` ve içindeki `scanf` İşlevler, **`inline`** `<stdio.h>` ve üst bilgileri ile olarak bildirilmiştir ve taşınır `<conio.h>` . Eski kodu geçiriyorsanız, Bu işlevlerle bağlantılı *LNK2019* görebilirsiniz. Daha fazla bilgi için bkz. [Visual C++ değişiklik geçmişi 2003-2015](../porting/visual-cpp-change-history-2003-2015.md#stdio_and_conio).

## <a name="type-conversion-specifier"></a>Tür dönüştürme Belirleyicisi

*Tür* dönüştürme belirleyicisi karakteri, ilgili bağımsız değişkenin bir karakter, dize, bir işaretçi, bir tamsayı veya kayan noktalı sayı olarak yorumlanıp yorumlanmayacağını belirtir. *Tür* karakteri, tek gerekli dönüştürme belirtimi alanıdır ve herhangi bir isteğe bağlı alandan sonra görüntülenir.

Biçim dizesini izleyen bağımsız değişkenler, karşılık gelen *tür* karakterine ve isteğe bağlı [Boyut](#size) önekine göre yorumlanır. Karakter türleri için dönüştürmeler **`char`** ve **`wchar_t`** **c** veya **c**kullanılarak belirtilir ve kullanılan biçimlendirme işlevine bağlı olarak, tek baytlı ve çok baytlı veya geniş karakter dizeleri **s** veya **s**kullanılarak belirtilir. **C** ve **s** kullanılarak belirtilen karakter ve dize bağımsız değişkenleri **`char`** **`char*`** `printf` , Aile işlevleri veya as **`wchar_t`** `wchar_t*` `wprintf` ailesi işlevleri olarak yorumlanır. **C** ve **S** kullanılarak belirtilen karakter ve dize bağımsız değişkenleri **`wchar_t`** `wchar_t*` `printf` , Aile işlevleri veya as **`char`** **`char*`** `wprintf` ailesi işlevleri olarak yorumlanır. Bu davranış, Microsoft 'a özgüdür.

,,, Ve türevleri gibi tamsayı türleri **`short`** **`int`** **`long`** **`long long`** **`unsigned`** **d**, **i**, **o**, **u**, **x**ve **x**kullanılarak belirtilir. , Ve gibi kayan nokta türleri **`float`** **`double`** **`long double`** **bir**, **a**, **e**, **e**, **f**, **f**, **g**ve **g**kullanılarak belirtilir. Varsayılan olarak, bir *Boyut* öneki tarafından değiştirilmedikleri takdirde, tamsayı bağımsız değişkenleri **`int`** türüne zorlanır ve kayan nokta bağımsız değişkenleri öğesine zorlanır **`double`** . 64 bitlik sistemlerde, bir **`int`** 32 bit değeridir; bu nedenle, **ll** veya **I64** *Boyut* öneki kullanılmadığı takdirde, 64 bit tamsayılar çıkış için biçimlendirildiklerinde kesilir. **P** tarafından belirtilen işaretçi türleri, platform için varsayılan işaretçi boyutunu kullanır.

> [!NOTE]
> **Microsoft 'a özgü:**\
> Ve işlevleri ile birlikte kullanıldıkları sırada **Z** türü karakteri ve **c**, **c**, **s**ve **s** türü karakterlerinin davranışı, `printf` `wprintf` Microsoft uzantılarıdır. ISO C standardı, her biçimlendirme işlevlerinde geniş karakter ve dizeler için **c ve s** **'yi sürekli olarak ve** **c** ve **s** kullanır.

### <a name="type-field-characters"></a>Tür alanı karakterleri

|Tür karakteri|Bağımsız Değişken|Çıkış biçimi|
|--------------------|--------------|-------------------|
|**,**|Karakter|`printf`İşlevleriyle kullanıldığında, tek baytlık bir karakter belirtir; `wprintf` işlevlerle kullanıldığında, geniş bir karakter belirtir.|
|**,**|Karakter|`printf`İşlevleriyle kullanıldığında, geniş bir karakter belirtir; `wprintf` işlevlerle kullanıldığında, tek baytlık bir karakter belirtir.|
|**TID**|Tamsayı|İşaretli ondalık tam sayı.|
|**i**|Tamsayı|İşaretli ondalık tam sayı.|
|**gelirken**|Tamsayı|İşaretsiz sekizlik tamsayı.|
|**larınız**|Tamsayı|İşaretsiz ondalık tamsayı.|
|**x**|Tamsayı|İşaretsiz onaltılık tamsayı; "abcdef" kullanır.|
|**Sayı**|Tamsayı|İşaretsiz onaltılık tamsayı; "ABCDEF" kullanır.|
|**a**|Kayan nokta|[-]*D. gggg*__e ±__*dd* \[ *d*] biçimindeki işaretli değer; burada *d* , belirtilen duyarlığa göre bir veya daha *dddd* fazla ondalık basamak, ya da varsayılan olarak altı veya *dd* \[ *d*üç ondalık basamak, üs 'un [Çıkış biçimine](../c-runtime-library/set-output-format.md) ve boyutuna bağlıdır.|
|**A**|Kayan nokta|**E** 'nin üs 'i **sağlaması yerine** **e biçimi dışında, e biçimiyle** aynıdır.|
|**vadeli**|Kayan nokta|[-]*Gggg*biçimindeki işaretli değer __.__ *gggg,* *gggg* bir veya daha fazla ondalık basamak. Ondalık ayırıcıdan önceki basamakların sayısı, sayının büyüklüğüne ve ondalık ayırıcıdan sonraki basamak sayısı, istenen duyarlığa veya altıya göre varsayılan olarak değişir.|
|**Vadeli**|Kayan nokta|Sonsuzluk ve Nan çıkışının büyük harfli olduğu durumlar dışında **f** biçimiyle aynıdır.|
|**Acil**|Kayan nokta|İşaretli değerler, verilen değer ve duyarlık için daha küçük olduğu için **f** veya **e** biçiminde görüntülenir. **E** biçimi, yalnızca değerin üs değeri-4 ' ten küçük veya *duyarlık* bağımsız değişkeninden büyük veya ona eşit olduğunda kullanılır. Sondaki sıfırlar kesilir ve ondalık nokta yalnızca bir veya daha fazla basamak bunu izlemişse görünür.|
|**Acil**|Kayan nokta|**G** biçimiyle aynı, **e** **yerine e 'nin**değil üs (uygun yerlerde) tanıtılmıştır.|
|**a**|Kayan nokta|[-] 0x*h. sshh*__p ±__*dd*biçimindeki işaretli onaltılık çift duyarlıklı kayan nokta değeri; burada *h. hhhh* , Mantis 'in onaltılık basamaklardır (küçük harfli harfler kullanılarak) ve *gg* üs için bir veya daha fazla sayı. Duyarlık, noktadan sonraki basamak sayısını belirtir.|
|**A**|Kayan nokta|[-] 0X*h. sshh*__P ±__*dd*biçimindeki işaretli onaltılık çift duyarlıklı kayan nokta değeri; burada *h. hhhh* , Mantis 'in onaltılık basamaklardır (büyük harfler kullanılarak) ve *gg* ise üs için bir veya daha fazla rakamdır. Duyarlık, noktadan sonraki basamak sayısını belirtir.|
|**No**|Tamsayı işaretçisi|Akışın veya arabelleğin şimdiye kadar başarıyla yazıldığı karakter sayısı. Bu değer, adresi bağımsız değişken olarak verilen tamsayı olarak depolanır. Gösterilen tamsayının boyutu bir bağımsız değişken boyut belirtimi öneki tarafından denetlenebilir. **N** belirticisi varsayılan olarak devre dışıdır; bilgi için önemli güvenlik notuna bakın.|
|**Lama**|İşaretçi türü|Bağımsız değişkenini onaltılık rakamlarla bir adres olarak görüntüler.|
|**malar**|Dize|`printf`İşlevleriyle kullanıldığında, tek baytlık veya çok baytlı bir karakter dizesi belirtir; `wprintf` işlevlerle kullanıldığında, geniş karakterli bir dize belirtir. Karakterler ilk null karaktere kadar veya *duyarlık* değerine ulaşılana kadar görüntülenir.|
|**S**|Dize|`printf`İşlevleriyle kullanıldığında, geniş karakterli bir dize belirtir; `wprintf` işlevlerle kullanıldığında, tek baytlık veya çok baytlı bir karakter dizesi belirtir. Karakterler ilk null karaktere kadar veya *duyarlık* değerine ulaşılana kadar görüntülenir.|
|**Z**|`ANSI_STRING`veya `UNICODE_STRING` Yapı|Bağımsız değişken olarak bir [ANSI_STRING](/windows/win32/api/ntdef/ns-ntdef-string) veya [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) yapısının adresi geçirildiğinde, yapının alanı tarafından işaret edilen arabellekte bulunan dizeyi görüntüler `Buffer` . Bir bağımsız değişken belirtmek için **w** için bir *Boyut* değiştirici öneki kullanın `UNICODE_STRING` — Örneğin, `%wZ` . `Length`Yapının alanı, dizenin bayt cinsinden uzunluğa ayarlanmalıdır. `MaximumLength`Yapının alanı, arabelleğin bayt cinsinden uzunluğa ayarlanmalıdır.<br /><br /> Genellikle, **Z** türü karakteri yalnızca, ve gibi bir dönüştürme belirtimi kullanan sürücü hata ayıklama işlevlerinde kullanılır `dbgPrint` `kdPrint` .|

Visual Studio 2015 ' den başlayarak, bir kayan nokta dönüştürme tanımlayıcısına (**a**, **a**, **e**, **e**, **f**, **f**, **g**, **g**) karşılık gelen bağımsız değişken sonsuz, sonsuz veya NaN ise, biçimlendirilen çıktı C99 standardına uygundur. Bu tablo, biçimlendirilen çıktıyı listeler:

|Değer|Çıktı|
|-----------|------------|
|sonsuz|`inf`|
|Sessiz NaN|`nan`|
|Sinyal NaN|`nan(snan)`|
|Belirsiz NaN|`nan(ind)`|

Bu değerlerden herhangi birine bir işaret ön eki uygulanabilir. Bir kayan nokta *türü* dönüştürme tanımlayıcı karakteri büyük harfle ayarlanırsa, çıktı büyük harflerle de biçimlendirilir. Örneğin, Biçim belirleyicisi `%F` yerine ise `%f` , bir sonsuzluk yerine olarak biçimlendirilir `INF` `inf` . `scanf`İşlevler ayrıca bu dizeleri ayrıştırarak, bu değerler ve işlevleri arasında gidiş dönüş yapabilir `printf` `scanf` .

Visual Studio 2015 ' den önce, CRT sonsuz, sonsuz ve NaN değerlerinin çıkışı için farklı, standart olmayan bir biçim kullandı:

|Değer|Çıktı|
|-----------|------------|
|+ sonsuzluk|`1.#INF`*rastgele rakamlar*|
|-sonsuzluk|`-1.#INF`*rastgele rakamlar*|
|Sonsuz (sessiz NaN ile aynı)|*basamak* `.#IND` *rastgele rakamlar*|
|NaN|*basamak* `.#NAN` *rastgele rakamlar*|

Bunlardan herhangi biri bir işaret tarafından ön eki alınmış olabilir ve bazı durumlarda bazen olağandışı etkilerle, alan genişliğine ve duyarlığına bağlı olarak biraz farklı şekilde biçimlendirilmiştir. Örneğin, `printf("%.2f\n", INFINITY)` `1.#J` #INF, "yuvarlanmış" olarak 2 basamaklı olacak şekilde yazdırılır.

> [!NOTE]
> Ya da öğesine karşılık gelen bağımsız `%s` değişken `%S` ya da `Buffer` karşılık gelen bağımsız değişken alanı `%Z` bir null işaretçiyse, "(null)" görüntülenir.

> [!NOTE]
> Tüm üstel formatlarda, görüntülenecek üs en az basamak sayısı iki, yalnızca gerekliyse üç değer kullanılır. [_Set_output_format](../c-runtime-library/set-output-format.md) işlevini kullanarak, geriye doğru uyumluluk için Visual Studio 2013 ve daha önce yazılan kodla birlikte görüntülenecek basamak sayısını ayarlayabilirsiniz.

> [!IMPORTANT]
> `%n`Biçim doğal olarak güvenli olmadığı için varsayılan olarak devre dışıdır. `%n`Bir biçim dizesinde karşılaşılırsa, [parametre doğrulama](../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Desteğini etkinleştirmek için `%n` bkz. [_set_printf_count_output](../c-runtime-library/reference/set-printf-count-output.md).

<a name="flags"></a>

## <a name="flag-directives"></a>Bayrak yönergeleri

Bir dönüştürme belirtiminde ilk isteğe bağlı alan *bayrak yönergeleri*, sıfır veya daha fazla bayrak karakteri ve işaret, boşluk, öndeki sıfırlar, ondalık noktaları ve sekizli ve onaltılık ön ekleri denetim çıktısını belirtir. Bir dönüştürme belirtiminde birden fazla bayrak yönergesi görünebilir ve bayrak karakterleri herhangi bir sırada görünebilir.

### <a name="flag-characters"></a>Bayrak karakterleri

|Bayrak|Anlamı|Varsayılan|
|----------|-------------|-------------|
|**-**|Sonucu verilen alan genişliği içinde sola hizalayın.|Sağa Hizala.|
|**+**|İmzalı bir tür ise çıkış değeri öneki için bir işaret (+ veya-) kullanın.|İmza yalnızca negatif işaretli değerler için görünür (-).|
|**0**|*Width* 'in ön eki **0**ise, en düşük genişliğe ulaşılana kadar baştaki sıfır eklenir. Her ikisi de **0** ve **-** görünürse **0** yok sayılır. Bir tamsayı biçimi (**i**, **u**, **x**, **x**, **o**, **d**) için **0** belirtilmişse ve duyarlık belirtimi de varsa — Örneğin, `%04.d` **0** yok sayılır. **Bir** **veya kayan nokta** biçimi için **0** belirtilmişse, `0x` veya ön ekiyle sonra öndeki sıfırlar Mantis 'e eklenir `0X` .|Doldurma yok.|
|**boş** (' ')|İmzalanmışsa ve pozitifse çıkış değerini önek olarak almak için boş kullanın. Blank ve + bayraklarının her ikisi de görünürse boş değer yok sayılır.|Boş görünür.|
|**#**|**O**, **x**veya **x** biçimiyle kullanıldığında, **#** bayrak sıfır dışında bir çıkış değerine önek olarak, sırasıyla 0, 0x veya 0x kullanır.|Boş görünür.|
||**E**, **e**, **f**, **f**, **a** **veya biçim ile** kullanıldığında, **#** bayrak çıkış değerini ondalık bir nokta içerecek şekilde zorlar.|Ondalık noktası yalnızca basamak varsa görünür.|
||**G** veya **g** biçimiyle kullanıldığında, **#** bayrak çıkış değerini ondalık bir nokta içerecek şekilde zorlar ve sondaki sıfırların kesilmesini önler.<br /><br /> **C**, **d**, **i**, **u**veya **s**ile kullanıldığında yoksayılır.|Ondalık noktası yalnızca basamak varsa görünür. Sondaki sıfırlar kesilir.|

<a name="width"></a>

## <a name="width-specification"></a>Genişlik belirtimi

Bir dönüştürme belirtiminde, isteğe bağlı genişlik belirtim alanı herhangi bir *bayrak* karakterinden sonra görüntülenir. *Width* bağımsız değişkeni, çıktı olan minimum karakter sayısını denetleyen negatif olmayan bir ondalık tamsayıdır. Çıkış değerindeki karakter sayısı belirtilen genişlikle azsa, **-** En düşük genişliğe ulaşılana kadar sol hizalama bayrağının () belirtildiğine bağlı olarak, değerlerin soluna veya sağına eklenir. *Width* 'in öneki 0 ise, en düşük genişliğe ulaşılana kadar, baştaki sıfırlar tamsayı veya kayan nokta dönüştürmelerine eklenir, ancak dönüştürme sonsuz veya NaN olur.

Genişlik belirtimi hiçbir koşulda değerin kesilmesine neden olmaz. Çıkış değerindeki karakter sayısı belirtilen genişlikden daha büyükse veya *Genişlik* verilmezse, değerin tüm karakterleri çıkış olur ve *duyarlık* belirtimine tabidir.

Genişlik belirtimi bir yıldız işareti () ise `*` , **`int`** bağımsız değişken listesindeki bir bağımsız değişken değeri sağlar. *Width* bağımsız değişkeni, bu örnekte gösterildiği gibi bağımsız değişken listesinde biçimlendirilmekte olan değerden önce gelmelidir:

`printf("%0*d", 5, 3);  /* 00003 is output */`

Dönüştürme belirtiminde eksik veya küçük bir *Genişlik* değeri, çıkış değerinin kesilmesine neden olmaz. Dönüştürmenin sonucu *Width* değerinden daha genişse, alan dönüştürme sonucunu içerecek şekilde genişler.

<a name="precision"></a>

## <a name="precision-specification"></a>Duyarlık belirtimi

Bir dönüştürme belirtiminde, üçüncü isteğe bağlı alan duyarlık belirtimidir. Bir nokta (.) ve ardından dönüştürme türüne bağlı olarak negatif olmayan bir ondalık tamsayı gelir, dize karakterlerinin sayısını, ondalık basamak sayısını veya çıkış yapılacak anlamlı basamak sayısını belirtir.

Genişlik belirtiminin aksine duyarlık belirtimi, çıkış değerinin kesilmesine veya kayan noktalı bir değerin yuvarlamasına neden olabilir. *Duyarlık* 0 olarak belirtilmişse ve dönüştürülecek değer 0 ise, bu örnekte gösterildiği gibi, sonuç hiçbir karakter çıktısı değildir:

`printf( "%.0d", 0 );      /* No characters output */`

Duyarlık belirtimi bir yıldız işareti () ise \* , **`int`** bağımsız değişken listesindeki bir bağımsız değişken değeri sağlar. Bağımsız değişken listesinde *duyarlık* bağımsız değişkeni, bu örnekte gösterildiği gibi, biçimlendirilen değerden önce gelmelidir:

`printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`

Aşağıdaki tabloda gösterildiği gibi, *tür* karakteri duyarlık *ya da varsayılan duyarlık yorumunu* belirler *precision* .

### <a name="how-precision-values-affect-type"></a>Duyarlık değerlerinin türü nasıl etkiler

|Tür|Anlamı|Varsayılan|
|----------|-------------|-------------|
|**a**, **a**|Duyarlık, noktadan sonraki basamak sayısını belirtir.|Varsayılan duyarlık 13 ' dir. Duyarlık 0 ise, bayrak kullanılmadığı takdirde hiçbir ondalık noktası yazdırılmaz **#** .|
|**c**, **c**|Duyarlık hiçbir etkiye sahip değildir.|Karakter yazdırılır.|
|**d**, **i**, **o**, **u**, **x**, **x**|Duyarlık, yazdırılacak en az basamak sayısını belirtir. Bağımsız değişkendeki basamak sayısı *duyarlıktan*küçükse, çıkış değeri sıfırlı sola doldurulur. Basamak sayısı *duyarlık*değerini aştığında değer kesilmez.|Varsayılan duyarlık 1 ' dir.|
|**e**, **e**|Duyarlık, ondalık ayırıcıdan sonra yazdırılacak basamakların sayısını belirtir. Son basılan basamak yuvarlanır.|Varsayılan duyarlık 6 ' dır. *Duyarlık* 0 ise veya nokta (.) bundan sonra bir sayı olmadan görünürse, hiçbir ondalık noktası yazdırılmaz.|
|**f**, **f**|Duyarlık değeri, ondalık ayırıcıdan sonraki basamak sayısını belirtir. Ondalık bir nokta görünürse, önce en az bir basamak görüntülenir. Değer, uygun basamak sayısına yuvarlanır.|Varsayılan duyarlık 6 ' dır. *Duyarlık* 0 ise veya nokta (.) onu takip eden bir sayı olmadan görünürse, hiçbir ondalık noktası yazdırılmaz.|
|**g**, **g**|Duyarlık, yazdırılan en fazla önemli basamak sayısını belirtir.|Altı önemli basamak yazdırılır ve sondaki sıfırlar kesilir.|
|**s**, **s**|Duyarlık, yazdırılacak en fazla karakter sayısını belirtir. *Duyarlık* fazla olan karakterler yazdırılmıyor.|Null karakter bulunana kadar karakterler yazdırılır.|

<a name="size"></a>

## <a name="argument-size-specification"></a>Bağımsız değişken boyutu belirtimi

Bir dönüştürme belirtiminde, *Boyut* alanı *tür* dönüştürme belirticisi için bir bağımsız değişken uzunluğu değiştiricisidir. *Boyut* alanı, *tür* alanına ön ekler (**HH**, **h**, **j**, **l** (küçük l), **l**, **ll**, **t**, **w**, **z**, **ı** (büyük ı), **I32**ve **I64**— ilgili bağımsız değişkenin "size" boyutunu — uzun veya kısa, 32-bit veya 64 bit, tek baytlı karakter veya geniş karakter — değiştirdikleri dönüştürme belirticisine göre belirtir. Bu boyut önekleri, *type* `printf` `wprintf` Aşağıdaki tabloda gösterildiği gibi bağımsız değişken boyutlarının yorumunu belirtmek için ve işlev aileleri içindeki tür karakterleriyle kullanılır. *Boyut* alanı bazı bağımsız değişken türleri için isteğe bağlıdır. Boyut ön eki belirtilmediğinde, biçimlendirici tamsayı bağımsız değişkenlerini kullanır — örneğin, imzalanmış veya imzasız **`char`** ,,, ve **`short`** **`int`** **`long`** numaralandırma türleri — 32 bitlik **`int`** türler, ve **`float`** , **`double`** ve **`long double`** kayan nokta bağımsız değişkenleri 64 bit tür olarak tüketilecektir **`double`** . Bu davranış, değişken bağımsız değişken listeleri için varsayılan bağımsız değişken yükseltme kurallarıyla eşleşir. Bağımsız değişken yükseltme hakkında daha fazla bilgi için bkz. [sonek Ifadelerinde](../cpp/postfix-expressions.md)üç nokta ve varsayılan bağımsız değişkenler. Her iki 32-bit ve 64 bit sistemde, bir 64-bit tamsayı bağımsız değişkeninin dönüştürme belirtimi **ll** veya **I64**boyut önekini içermelidir. Aksi takdirde, biçimlendirici davranışı tanımsızdır.

Bazı türler 32 bit ve 64 bit koddaki farklı boyutlardır. Örneğin, `size_t` x86 için derlenen kodda 32 bit uzunluğunda ve x64 için derlenmiş koddaki 64 bit olur. Değişken genişlikli türler için platformdan bağımsız biçimlendirme kodu oluşturmak için, değişken genişlikli bir bağımsız değişken boyut değiştiricisi kullanabilirsiniz. Alternatif olarak, 64 bitlik bir bağımsız değişken boyut değiştiricisi kullanın ve değişken genişlikli bağımsız değişken türünü 64 bit olarak yükseltin. Microsoft 'a özgü **ı** (büyük ı) bağımsız değişken boyut değiştiricisi, değişken genişlikli tamsayı bağımsız değişkenlerini işler, ancak taşınabilirlik için türe özgü **j**, **t**ve **z** değiştiricileri önerilir.

### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>Printf ve wprintf biçim türü Belirticilerinin boyut önekleri

|Belirtmek için|Ön ek kullan|Tür belirticisiyle|
|----------------|----------------|-------------------------|
|**`char`**<br />**`unsigned char`**|**ss**|**d**, **i**, **o**, **u**, **x**veya **x**|
|**`short int`**<br />**`short unsigned int`**|**olsun**|**d**, **i**, **o**, **u**, **x**veya **x**|
|**`__int32`**<br />**`unsigned __int32`**|**I32**|**d**, **i**, **o**, **u**, **x**veya **x**|
|**`__int64`**<br />**`unsigned __int64`**|**I64**|**d**, **i**, **o**, **u**, **x**veya **x**|
|`intmax_t`<br />`uintmax_t`|**j** veya **I64**|**d**, **i**, **o**, **u**, **x**veya **x**|
|**`long double`**|**l** (küçük harf l) veya **l**|**a**, **a**, **e**, **e**, **f**, **f**, **g**veya **g**|
|**`long int`**<br />**`long unsigned int`**|**l** (küçük harf l)|**d**, **i**, **o**, **u**, **x**veya **x**|
|**`long long int`**<br />**`unsigned long long int`**|**ll** (küçük harf ll)|**d**, **i**, **o**, **u**, **x**veya **x**|
|`ptrdiff_t`|**t** veya **ı** (büyük harf ı)|**d**, **i**, **o**, **u**, **x**veya **x**|
|`size_t`|**z** veya **ı** (büyük harf ı)|**d**, **i**, **o**, **u**, **x**veya **x**|
|Tek baytlık karakter|**olsun**|**c** veya **c**|
|Geniş karakter|**l** (küçük harf l) veya **w**|**c** veya **c**|
|Tek baytlık karakter dizesi|**olsun**|**s**, **s**veya **Z**|
|Geniş karakterli dize|**l** (küçük harf l) veya **w**|**s**, **s**veya **Z**|

`ptrdiff_t`Ve `size_t` türleri, **`__int32`** **`unsigned __int32`** 32 bitlik platformlarda ve **`__int64`** veya **`unsigned __int64`** 64 bit platformlarda bulunur. **I** (büyük ı), **j**, **t**ve **z** boyut önekleri, platformun doğru bağımsız değişken genişliğini alır.

Visual C++, **`long double`** farklı bir tür olsa da, aynı iç gösterimle sahiptir **`double`** .

Bir **HC** veya **HC** tür Belirleyicisi, **c** ve işlevleri ile c ile eşdeğerdir `printf` **C** `wprintf` . **LC**, **LC**, **WC**veya **WC** tür Belirleyicisi, **c** ve işlevleri ile c ile eşanlamlı olarak anlamlıdır `printf` **c** `wprintf` . Bir **HS** veya **HS** tür Belirleyicisi, işlevleri **içindeki** `printf` ve içindeki işlevleri ile eşanlamlıdır **S** `wprintf` . **Ls**, **ls**, **WS** veya **WS** tür Belirleyicisi, işlevleri içindeki **S** `printf` ve içindeki işlevleri ile eşanlamlıdır **s** `wprintf` .

> [!NOTE]
> **Microsoft 'a özgü:**\
> **I** (büyük ı), **I32**, **I64**ve **w** bağımsız DEĞIŞKEN boyut değiştirici önekleri Microsoft uzantılarıdır ve ISO C ile uyumlu değildir. Tür verileriyle kullanıldığında **h** ön eki, türü **`char`** ve **l** (küçük l) ön eki, **`double`** Microsoft uzantılarıdır.

## <a name="see-also"></a>Ayrıca bkz.

[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[printf_p Konumsal parametreler](../c-runtime-library/printf-p-positional-parameters.md)
