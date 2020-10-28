---
title: 'Biçim belirtimi sözdizimi: `printf` ve `wprintf` işlevleri'
description: Microsoft C çalışma zamanı `printf` ve işlevleri için Biçim belirleyicisi sözdizimini açıklar `wprintf`
ms.date: 10/26/2020
helpviewer_keywords:
- format specification fields for printf function
- printf function format specification fields
- flag directives, printf function
- type fields, printf function
- width fields, printf function
- precision fields, printf function
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
ms.openlocfilehash: 18642f650949e346fd3421b4a123acb4e84ed659
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907538"
---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>Biçim belirtim sözdizimi: printf ve wprintf işlevleri

Çeşitli `printf` ve `wprintf` işlevleri bir biçim dizesi ve isteğe bağlı bağımsız değişkenler alır ve çıktı için biçimlendirilen bir karakter dizisi üretir. Biçim dizesi, çıkışta bir bağımsız değişkeni biçimlendirmeyi açıklayan, çıkış veya kodlanmış *dönüştürme belirtimleri* için sabit karakter olan sıfır veya daha fazla *yönergeler* içerir. Bu makalede, dönüştürme belirtimlerini biçim dizesinde kodlamak için kullanılan söz dizimi açıklanmaktadır. Bu işlevlerin listesi için bkz. [akış g/ç](../c-runtime-library/stream-i-o.md).

Bir dönüştürme belirtimi, bu formdaki isteğe bağlı ve gerekli alanlardan oluşur:

**%** [ [*bayraklar*](#flags)] [ [*Genişlik*](#width)] [. [*duyarlık*](#precision)] [ [*Boyut*](#size)] [*tür*](#type)

Dönüştürme belirtiminin her alanı, belirli bir biçim seçeneğini veya dönüştürme belirticisini belirten bir karakterdir veya bir sayıdır. Gerekli *tür* alanı bir bağımsız değişkene uygulanacak dönüştürme türünü belirtir. İsteğe bağlı *bayraklar* , *Genişlik* ve *duyarlık* alanları, baştaki boşluklar, sıfır, bloklama ve görünen duyarlık gibi ek biçim yönlerini denetler. *Boyut* alanı tüketilen ve dönüştürülen bağımsız değişkenin boyutunu belirtir.

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

Biçim dizesini izleyen bağımsız değişkenler, karşılık gelen *tür* karakterine ve isteğe bağlı [Boyut](#size) önekine göre yorumlanır. Ve `char` kullanılarak belirtilen karakter türleri `wchar_t` **`c`** **`C`** ve tek baytlı ve çok baytlı ya da geniş karakter dizeleri için dönüşümler **`s`** **`S`** , kullanılan biçimlendirme işlevine bağlı olarak veya kullanılarak belirtilir. Ve kullanılarak belirtilen karakter ve dize bağımsız değişkenleri, ve ailesi işlevleri **`c`** **`s`** `char` `char*` `printf` veya as `wchar_t` `wchar_t*` `wprintf` ailesi işlevleri olarak yorumlanır. Ve kullanılarak belirtilen karakter ve dize bağımsız değişkenleri, ve ailesi işlevleri **`C`** **`S`** `wchar_t` `wchar_t*` `printf` veya as `char` `char*` `wprintf` ailesi işlevleri olarak yorumlanır. Bu davranış, Microsoft 'a özgüdür.

,,, Ve çeşitleri gibi tamsayı türleri,,,,, `short` `int` `long` `long long` `unsigned` ve kullanılarak belirtilir **`d`** **`i`** **`o`** **`u`** **`x`** **`X`** . ,, Ve gibi kayan nokta türleri,,,,,, `float` `double` **`long double`** ve kullanılarak belirtilir **`a`** **`A`** **`e`** **`E`** **`f`** **`F`** **`g`** **`G`** . Varsayılan olarak, bir *Boyut* öneki tarafından değiştirilmedikleri takdirde, tamsayı bağımsız değişkenleri `int` türüne zorlanır ve kayan nokta bağımsız değişkenleri öğesine zorlanır `double` . 64 bitlik sistemlerde, bir `int` 32 bit değeridir; bu nedenle, **ll** veya **I64** *Boyut* öneki kullanılmadığı takdirde, 64 bit tamsayılar çıktı için biçimlendirildiklerinde kesilir. Tarafından belirtilen işaretçi türleri, **`p`** platform için varsayılan işaretçi boyutunu kullanır.

> [!NOTE]
> **Microsoft 'a özgü:**\
> , **`Z`** **`c`** **`C`** **`s`** Ve işlevleri ile birlikte kullanıldıkları zaman tür karakteri ve,, ve  **`S`** tür karakterlerinin davranışı `printf` `wprintf` Microsoft uzantılarıdır. ISO C standardı, **`c`** **`s`** dar karakterler ve dizeler için ve **`C`** **`S`** tüm biçimlendirme işlevlerinde geniş karakter ve dizeler için ve sürekli olarak kullanır.

### <a name="type-field-characters"></a>Tür alanı karakterleri

|Tür karakteri|Bağımsız Değişken|Çıkış biçimi|
|--------------------|--------------|-------------------|
|**`c`**|Karakter|`printf`İşlevleriyle kullanıldığında, tek baytlık bir karakter belirtir; `wprintf` işlevlerle kullanıldığında, geniş bir karakter belirtir.|
|**`C`**|Karakter|`printf`İşlevleriyle kullanıldığında, geniş bir karakter belirtir; `wprintf` işlevlerle kullanıldığında, tek baytlık bir karakter belirtir.|
|**`d`**|Tamsayı|İşaretli ondalık tam sayı.|
|**`i`**|Tamsayı|İşaretli ondalık tam sayı.|
|**`o`**|Tamsayı|İşaretsiz sekizlik tamsayı.|
|**`u`**|Tamsayı|İşaretsiz ondalık tamsayı.|
|**`x`**|Tamsayı|İşaretsiz onaltılık tamsayı; " `abcdef` " kullanır.|
|**`X`**|Tamsayı|İşaretsiz onaltılık tamsayı; " `ABCDEF` " kullanır.|
|**`e`**|Kayan nokta|[-] *`d.dddd`* __E ±__ ] biçimindeki işaretli değer *`dd`* \[ *`d`* , burada *`d`* bir ondalık basamak, *`dddd`* belirtilen duyarlığa bağlı olarak bir veya daha fazla ondalık basamak, ya da varsayılan olarak altı *`dd`* \[ *`d`* veya üç ondalık basamak, üs 'un [Çıkış biçimine](../c-runtime-library/set-output-format.md) ve boyutuna bağlıdır.|
|**`E`**|Kayan nokta|**`e`** **`E`** Üs öğesini tanıtmaktansa hariç biçimiyle aynıdır **`e`** .|
|**`f`**|Kayan nokta|[-]. Biçimindeki işaretli değer *`dddd`* __.__ *`dddd`* , burada *`dddd`* bir veya daha fazla ondalık basamak. Ondalık ayırıcıdan önceki basamakların sayısı, sayının büyüklüğüne ve ondalık ayırıcıdan sonraki basamak sayısı, istenen duyarlığa veya altıya göre varsayılan olarak değişir.|
|**`F`**|Kayan nokta|**`f`** Sonsuzluk ve Nan çıkışının büyük harfli olduğu durumlar dışında, biçimiyle aynıdır.|
|**`g`**|Kayan nokta|**`f`** **`e`** Belirlenen değer ve duyarlık için daha küçük olduğu için, işaretli değerler veya biçiminde görüntülenir. **`e`** Biçim yalnızca değerin üs değeri-4 ' ten küçük ya da *duyarlık* bağımsız değişkeninden büyük veya ona eşit olduğunda kullanılır. Sondaki sıfırlar kesilir ve ondalık nokta yalnızca bir veya daha fazla basamak bunu izlemişse görünür.|
|**`G`**|Kayan nokta|Biçim ile özdeş, **`g`** hariç olmak **`E`** yerine **`e`** üs (uygun olduğunda) öğesini tanıtır.|
|**`a`**|Kayan nokta|*[-] 0xh. sshh*__p ±__ biçimindeki işaretli onaltılık çift duyarlıklı kayan nokta değeri; *`dd`* burada *h. hhhh* , Mantis 'in onaltılık basamaklardır (küçük harfli harfler kullanılarak) ve *`dd`* üs için bir veya daha fazla basamaktan oluşur. Duyarlık, noktadan sonraki basamak sayısını belirtir.|
|**`A`**|Kayan nokta|*[-] 0xh. sshh*__P ±__ biçimindeki işaretli onaltılık çift duyarlıklı kayan nokta değeri; *`dd`* burada *h. hhhh* , Mantis 'in onaltılık basamaklardır (büyük harfler kullanılarak) ve *gg* üs için bir veya daha fazla sayı şeklindedir. Duyarlık, noktadan sonraki basamak sayısını belirtir.|
|**`n`**|Tamsayı işaretçisi|Akışın veya arabelleğin şimdiye kadar başarıyla yazıldığı karakter sayısı. Bu değer, adresi bağımsız değişken olarak verilen tamsayı olarak depolanır. Gösterilen tamsayının boyutu bir bağımsız değişken boyut belirtimi öneki tarafından denetlenebilir. **`n`** Belirleyici varsayılan olarak devre dışıdır; bilgi için önemli güvenlik notuna bakın.|
|**`p`**|İşaretçi türü|Bağımsız değişkenini onaltılık rakamlarla bir adres olarak görüntüleyin.|
|**`s`**|Dize|`printf`İşlevleriyle kullanıldığında, tek baytlık veya çok baytlı bir karakter dizesi belirtir; `wprintf` işlevlerle kullanıldığında, geniş karakterli bir dize belirtir. Karakterler ilk null karaktere kadar veya *duyarlık* değerine ulaşılana kadar görüntülenir.|
|**`S`**|Dize|`printf`İşlevleriyle kullanıldığında, geniş karakterli bir dize belirtir; `wprintf` işlevlerle kullanıldığında, tek baytlık veya çok baytlı bir karakter dizesi belirtir. Karakterler ilk null karaktere kadar veya *duyarlık* değerine ulaşılana kadar görüntülenir.|
|**`Z`**|`ANSI_STRING` veya `UNICODE_STRING` Yapı|[`ANSI_STRING`](/windows/win32/api/ntdef/ns-ntdef-string) [`UNICODE_STRING`](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) Bağımsız değişken olarak bir veya yapısının adresi geçirildiğinde, yapının alanı tarafından işaret edilen arabellekte bulunan dizeyi görüntüler `Buffer` . Bir bağımsız değişken belirtmek için bir *Boyut* değiştirici öneki kullanın **`w`** `UNICODE_STRING` — Örneğin, `%wZ` . `Length`Yapının alanı, dizenin bayt cinsinden uzunluğa ayarlanmalıdır. `MaximumLength`Yapının alanı, arabelleğin bayt cinsinden uzunluğa ayarlanmalıdır.<br /><br />Genellikle, **`Z`** tür karakteri yalnızca, ve gibi bir dönüştürme belirtimi kullanan sürücü hata ayıklama işlevlerinde kullanılır `dbgPrint` `kdPrint` .|

Visual Studio 2015 ' den başlayarak, bir kayan nokta dönüştürme tanımlayıcısına (,,,,,,,) karşılık gelen bağımsız değişken **`a`** **`A`** **`e`** **`E`** **`f`** **`F`** **`g`** **`G`** sonsuz, sonsuz veya NaN ise, biçimlendirilen çıkış C99 standardına uyar. Bu tablo, biçimlendirilen çıktıyı listeler:

|Değer|Çıkış|
|-----------|------------|
|sonsuz|`inf`|
|Sessiz NaN|`nan`|
|Sinyal NaN|`nan(snan)`|
|Belirsiz NaN|`nan(ind)`|

Bu değerlerden herhangi birine bir işaret ön eki uygulanabilir. Bir kayan nokta *türü* dönüştürme tanımlayıcı karakteri büyük harfle ayarlanırsa, çıktı büyük harflerle de biçimlendirilir. Örneğin, Biçim belirleyicisi `%F` yerine ise `%f` , bir sonsuzluk yerine olarak biçimlendirilir `INF` `inf` . `scanf`İşlevler ayrıca bu dizeleri ayrıştırarak, bu değerler ve işlevleri arasında gidiş dönüş yapabilir `printf` `scanf` .

Visual Studio 2015 ' den önce, CRT sonsuz, sonsuz ve NaN değerlerinin çıkışı için farklı, standart olmayan bir biçim kullandı:

|Değer|Çıkış|
|-----------|------------|
|+ sonsuzluk|`1.#INF`*rastgele rakamlar*|
|-sonsuzluk|`-1.#INF`*rastgele rakamlar*|
|Sonsuz (sessiz NaN ile aynı)|*basamak* `.#IND` *rastgele rakamlar*|
|NaN|*basamak* `.#NAN` *rastgele rakamlar*|

Bunlardan herhangi biri bir işaret tarafından ön ekli olabilir ve bazı durumlarda bazen olağandışı etkiler ile alan genişliğine ve duyarlığına bağlı olarak farklı şekilde biçimlendirilir. Örneğin, `printf("%.2f\n", INFINITY)` `1.#J` *#INF* , iki hassaslığa "yuvarlayarak" olacağı için yazdırır.

> [!NOTE]
> Ya da öğesine karşılık gelen bağımsız `%s` değişken `%S` ya da `Buffer` karşılık gelen bağımsız değişken alanı `%Z` bir null işaretçiyse, "(null)" görüntülenir.

> [!NOTE]
> Tüm üstel formatlarda, görüntülenecek üs en az basamak sayısı iki, yalnızca gerekliyse üç değer kullanılır. [`_set_output_format`](../c-runtime-library/set-output-format.md)İşlevini kullanarak, Visual Studio 2013 ve daha önce yazılan kodla geriye dönük uyumluluk için, görüntülenecek basamak sayısını üç olarak ayarlayabilirsiniz.

> [!IMPORTANT]
> `%n`Biçim doğal olarak güvenli olmadığı için varsayılan olarak devre dışıdır. `%n`Bir biçim dizesinde karşılaşılırsa, [parametre doğrulama](../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Desteğini etkinleştirmek için `%n` bkz [`_set_printf_count_output`](../c-runtime-library/reference/set-printf-count-output.md) ..

<a name="flags"></a>

## <a name="flag-directives"></a>Bayrak yönergeleri

Bir dönüştürme belirtiminde ilk isteğe bağlı alan *bayrak yönergeleri* , sıfır veya daha fazla bayrak karakteri ve işaret, boşluk, öndeki sıfırlar, ondalık noktaları ve sekizli ve onaltılık ön ekleri denetim çıktısını belirtir. Bir dönüştürme belirtiminde birden fazla bayrak yönergesi görünebilir ve bayrak karakterleri herhangi bir sırada görünebilir.

### <a name="flag-characters"></a>Bayrak karakterleri

|Bayrak|Anlamı|Varsayılan|
|----------|-------------|-------------|
|**`-`**|Sonucu verilen alan genişliği içinde sola hizalayın.|Sağa Hizala.|
|**`+`**|İmzalı bir tür ise çıkış değeri öneki için bir işaret (+ veya-) kullanın.|İmza yalnızca negatif işaretli değerler için görünür (-).|
|**`0`**|*Width* 'in öneki varsa **`0`** , en düşük genişliğe ulaşılana kadar baştaki sıfır eklenir. Hem hem **`0`** de **`-`** görünürse, yok **`0`** sayılır. **`0`** Bir tamsayı biçimi ( **`i`** ,,,,, **`u`** ) için belirtilmişse **`x`** **`X`** **`o`** **`d`** ve bir duyarlık belirtimi de varsa — Örneğin, yok `%04.d` **`0`** sayılır. **`0`** **`a`** Ya da **`A`** kayan nokta biçimi için belirtilmişse, ya da öneki sonrasında öndeki sıfırlar Mantis `0x` `0X` .|Doldurma yok.|
|**boş (' ')**|İmzalanmışsa ve pozitifse çıkış değerini önek olarak almak için boş kullanın. Blank ve + bayraklarının her ikisi de görünürse boş değer yok sayılır.|Boş görünür.|
|**`#`**|,, Veya biçimiyle kullanıldığında, **`o`** **`x`** **`X`** **`#`** bayrak `0` `0x` `0X` sıfır dışında bir çıkış değeri öneki için sırasıyla, veya olarak kullanır.|Boş görünür.|
||,,,, **`e`** **`E`** **`f`** **`F`** **`a`** , Veya biçimiyle kullanıldığında, **`A`** **`#`** bayrak çıkış değerini ondalık bir nokta içerecek şekilde zorlar.|Ondalık noktası yalnızca basamak varsa görünür.|
||**`g`** Veya **`G`** biçimiyle kullanıldığında, **`#`** bayrak çıkış değerini ondalık bir nokta içerecek şekilde zorlar ve sondaki sıfırların kesilmesine engel olur.<br /><br /> ,,, Veya ile kullanıldığında yoksayılır **`c`** **`d`** **`i`** **`u`** **`s`** .|Ondalık noktası yalnızca basamak varsa görünür. Sondaki sıfırlar kesilir.|

<a name="width"></a>

## <a name="width-specification"></a>Genişlik belirtimi

Bir dönüştürme belirtiminde, isteğe bağlı genişlik belirtim alanı herhangi bir *bayrak* karakterinden sonra görüntülenir. *Width* bağımsız değişkeni, çıktı olan minimum karakter sayısını denetleyen negatif olmayan bir ondalık tamsayıdır. Çıkış değerindeki karakter sayısı belirtilen genişlikle azsa, **`-`** En düşük genişliğe ulaşılana kadar sol hizalama bayrağının () belirtildiğine bağlı olarak, değerlerin soluna veya sağına eklenir. *Width* 'in öneki 0 ise, en düşük genişliğe ulaşılana kadar, baştaki sıfırlar tamsayı veya kayan nokta dönüştürmelerine eklenir, ancak dönüştürme sonsuz veya NaN olur.

Genişlik belirtimi hiçbir koşulda değerin kesilmesine neden olmaz. Çıkış değerindeki karakter sayısı belirtilen genişden büyükse veya *Genişlik* sağlanmazsa, değerin tüm karakterleri çıkış olur ve *duyarlık* belirtimine tabidir.

Genişlik belirtimi bir yıldız işareti () ise `*` , `int` bağımsız değişken listesindeki bir bağımsız değişken değeri sağlar. *Width* bağımsız değişkeni, bu örnekte gösterildiği gibi bağımsız değişken listesinde biçimlendirilmekte olan değerden önce gelmelidir:

`printf("%0*d", 5, 3);  /* 00003 is output */`

Dönüştürme belirtiminde eksik veya küçük bir *Genişlik* değeri, çıkış değerinin kesilmesine neden olmaz. Dönüştürmenin sonucu *Width* değerinden daha genişse, alan dönüştürme sonucunu içerecek şekilde genişler.

<a name="precision"></a>

## <a name="precision-specification"></a>Duyarlık belirtimi

Bir dönüştürme belirtiminde, üçüncü isteğe bağlı alan duyarlık belirtimidir. `.`Dönüştürme türüne bağlı olarak, bir nokta () ve ardından negatif olmayan bir ondalık tamsayı ile oluşur, dize karakterlerinin sayısını, ondalık basamak sayısını veya çıkış yapılacak önemli basamak sayısını belirtir.

Genişlik belirtiminin aksine duyarlık belirtimi, çıkış değerinin kesilmesine veya kayan noktalı bir değerin yuvarlamasına neden olabilir. *Duyarlık* 0 olarak belirtilmişse ve dönüştürülecek değer 0 ise, bu örnekte gösterildiği gibi, sonuç hiçbir karakter çıktısı değildir:

`printf( "%.0d", 0 );      /* No characters output */`

Duyarlık belirtimi bir yıldız işareti () ise `*` , `int` bağımsız değişken listesindeki bir bağımsız değişken değeri sağlar. Bağımsız değişken listesinde *duyarlık* bağımsız değişkeni, bu örnekte gösterildiği gibi, biçimlendirilen değerden önce gelmelidir:

`printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`

Aşağıdaki tabloda gösterildiği gibi, *tür* karakteri duyarlık *ya da varsayılan duyarlık yorumunu* belirler *precision* .

### <a name="how-precision-values-affect-type"></a>Duyarlık değerlerinin türü nasıl etkiler

|Tür|Anlamı|Varsayılan|
|----------|-------------|-------------|
|**`a`** , **`A`**|Duyarlık, noktadan sonraki basamak sayısını belirtir.|Varsayılan duyarlık 13 ' dir. Duyarlık 0 ise, bayrak kullanılmadığı takdirde hiçbir ondalık noktası yazdırılmaz **`#`** .|
|**`c`** , **`C`**|Duyarlık hiçbir etkiye sahip değildir.|Karakter yazdırılır.|
|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** , **`X`**|Duyarlık, yazdırılacak en az basamak sayısını belirtir. Bağımsız değişkendeki basamak sayısı *duyarlıktan* küçükse, çıkış değeri sıfırlı sola doldurulur. Basamak sayısı *duyarlık* değerini aştığında değer kesilmez.|Varsayılan duyarlık 1 ' dir.|
|**`e`** , **`E`**|Duyarlık, ondalık ayırıcıdan sonra yazdırılacak basamakların sayısını belirtir. Son basılan basamak yuvarlanır.|Varsayılan duyarlık 6 ' dır. *Duyarlık* 0 ise veya nokta ( `.` ) bundan sonra bir sayı olmadan görünürse, hiçbir ondalık noktası yazdırılmaz.|
|**`f`** , **`F`**|Duyarlık değeri, ondalık ayırıcıdan sonraki basamak sayısını belirtir. Ondalık bir nokta görünürse, önce en az bir basamak görüntülenir. Değer, uygun basamak sayısına yuvarlanır.|Varsayılan duyarlık 6 ' dır. *Duyarlık* 0 ise veya nokta ( `.` ) onu takip eden bir sayı olmadan görünürse, hiçbir ondalık noktası yazdırılmaz.|
|**`g`** , **`G`**|Duyarlık, yazdırılan en fazla önemli basamak sayısını belirtir.|Altı önemli basamak yazdırılır ve sondaki sıfırlar kesilir.|
|**`s`** , **`S`**|Duyarlık, yazdırılacak en fazla karakter sayısını belirtir. *Duyarlık* fazla olan karakterler yazdırılmıyor.|Null karakter bulunana kadar karakterler yazdırılır.|

<a name="size"></a>

## <a name="argument-size-specification"></a>Bağımsız değişken boyutu belirtimi

Bir dönüştürme belirtiminde, *Boyut* alanı *tür* dönüştürme belirticisi için bir bağımsız değişken uzunluğu değiştiricisidir. *Boyut* *alanı,,* ,,, **`hh`** **`h`** **`j`** **`l`** (küçük harf L),, **`L`** ,, **`ll`** **`t`** **`w`** , **`z`** , **`I`** (büyük ı),, **`I32`** ve, **`I64`** değiştirdikleri dönüştürme belirticisine bağlı olarak, ilgili bağımsız değişkenin "Boyut" değerini (uzun veya kısa, 32-bit veya 64 bit, tek baytlı karakter veya geniş karakter) belirler. Bu boyut önekleri, *type* `printf` `wprintf` Aşağıdaki tabloda gösterildiği gibi bağımsız değişken boyutlarının yorumunu belirtmek için ve işlev aileleri içindeki tür karakterleriyle kullanılır. *Boyut* alanı bazı bağımsız değişken türleri için isteğe bağlıdır. Boyut ön eki belirtilmediğinde, biçimlendirici tamsayı bağımsız değişkenlerini kullanır — örneğin, imzalanmış veya imzasız `char` ,,, ve `short` `int` `long` numaralandırma türleri — 32 bitlik `int` türler, ve `float` , `double` ve `long double` kayan nokta bağımsız değişkenleri 64 bit tür olarak tüketilecektir `double` . Bu davranış, değişken bağımsız değişken listeleri için varsayılan bağımsız değişken yükseltme kurallarıyla eşleşir. Bağımsız değişken yükseltme hakkında daha fazla bilgi için bkz. [sonek Ifadelerinde](../cpp/postfix-expressions.md)üç nokta ve varsayılan bağımsız değişkenler. Her iki 32-bit ve 64 bit sistemde, bir 64-bit tamsayı bağımsız değişkeninin dönüştürme belirtimi veya ' nin boyut önekini içermelidir **`ll`** **`I64`** . Aksi takdirde, biçimlendirici davranışı tanımsızdır.

Bazı türler 32 bit ve 64 bit koddaki farklı boyutlardır. Örneğin, `size_t` x86 için derlenen kodda 32 bit uzunluğunda ve x64 için derlenmiş koddaki 64 bit olur. Değişken genişlikli türler için platformdan bağımsız biçimlendirme kodu oluşturmak için, değişken genişlikli bir bağımsız değişken boyut değiştiricisi kullanabilirsiniz. Bunun yerine, 64 bitlik bir bağımsız değişken boyut değiştiricisi kullanın ve değişken genişlikli bağımsız değişken türünü 64 bit olarak yükseltin. Microsoft 'a özgü **`I`** (büyük ı) bağımsız değişken boyut değiştiricisi, değişken genişlikli tamsayı bağımsız değişkenlerini işler, ancak **`j`** **`t`** taşınabilirliği için türe özgü, ve **`z`** değiştiriciler önerilir.

### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>Printf ve wprintf Format-Type belirticileri için boyut önekleri

|Belirtmek için|Ön ek kullan|Tür belirticisiyle|
|----------------|----------------|-------------------------|
|`char`<br />`unsigned char`|**`hh`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`**|
|`short int`<br />`short unsigned int`|**`h`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`**|
|`__int32`<br />`unsigned __int32`|**`I32`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`**|
|`__int64`<br />`unsigned __int64`|**`I64`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`**|
|`intmax_t`<br />`uintmax_t`|**`j`** veya **`I64`**|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`**|
|`long double`|**`l`** (küçük harf L) veya **`L`**|**`a`** , **`A`** , **`e`** , **`E`** , **`f`** , **`F`** , **`g`** veya **`G`**|
|`long int`<br />`long unsigned int`|**`l`** (küçük harf L) |**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`** |
|`long long int`<br />`unsigned long long int`|**`ll`**  (küçük harf LL)|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`**|
|`ptrdiff_t`|**`t`** or **`I`** (büyük harf ı)|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`**|
|`size_t`|**`z`** or **`I`** (büyük harf ı)|**`d`** , **`i`** , **`o`** , **`u`** , **`x`** veya **`X`**|
|Tek baytlık karakter|**`h`**|**`c`** veya **`C`**|
|Geniş karakter|**`l`** (küçük harf L) veya **`w`**|**`c`** veya **`C`**|
|Tek baytlık karakter dizesi|**`h`**|**`s`** , **`S`** , veya **`Z`**|
|Geniş karakterli dize|**`l`** (küçük harf L) veya **`w`**|**`s`** , **`S`** , veya **`Z`**|

`ptrdiff_t`Ve `size_t` türleri, `__int32` `unsigned __int32` 32 bitlik platformlarda ve `__int64` veya `unsigned __int64` 64 bit platformlarda bulunur. **`I`** (Büyük ı), **`j`** , **`t`** ve **`z`** Boyut önekleri, platformun doğru bağımsız değişken genişliğini alır.

Visual C++, `long double` farklı bir tür olsa da, aynı iç gösterimle sahiptir `double` .

**`hc`** Veya **`hC`** tür Belirleyicisi, işlevlerde **`c`** `printf` ve işlevlerde ile eş anlamlı olur **`C`** `wprintf` . **`lc`** ,, **`lC`** **`wc`** Veya **`wC`** tür Belirleyicisi, **`C`** `printf` işlevlerde ve işlevlerde ile eş anlamlı olur **`c`** `wprintf` . **`hs`** Veya **`hS`** tür Belirleyicisi, işlevlerde **`s`** `printf` ve işlevlerde ile eş anlamlı olur **`S`** `wprintf` . **`ls`** ,, **`lS`** **`ws`** Veya **`wS`** tür Belirleyicisi, **`S`** `printf` işlevlerde ve işlevlerde ile eşanlamlıdır **`s`** `wprintf` .

> [!NOTE]
> **Microsoft 'a özgü:**\
> **`I`** (Büyük ı), **`I32`** , **`I64`** ve **`w`** bağımsız değişken boyutu değiştirici önekleri MICROSOFT uzantılarıdır ve ISO C ile uyumlu değildir. Türü veri ile kullanıldığında **`h`** `char` ve **`l`** (küçük harfli L) ön eki, `double` Microsoft uzantılarıdır.

## <a name="see-also"></a>Ayrıca bkz.

[`printf, _printf_l, wprintf, _wprintf_l`](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\
[`printf_s, _printf_s_l, wprintf_s, _wprintf_s_l`](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)\
[`printf_p` Konumsal parametreler](../c-runtime-library/printf-p-positional-parameters.md)
