---
title: Normal İfadeler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- regular expressions [C++]
ms.assetid: aafe202a-1d96-4b36-a270-d676dfd3c51c
ms.openlocfilehash: db5a7eacc136b3f30187692c7ea10792b84eb3fc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451385"
---
# <a name="regular-expressions-c"></a>Normal İfadeler (C++)

C++ Standart kitaplık birden çok normal ifade dilbilgisinde desteklenir. Bu konu, normal ifadeler kullanılırken kullanılabilen dilbilgisi çeşitlemelerini açıklamaktadır.

## <a name="regexgrammar"></a>Normal Ifade dilbilgisi

Kullanılacak normal ifade dilbilgisi, `std::regex_constants::syntax_option_type` sabit listesi değerlerinden birinin kullanımıyla belirlenir. Bu normal ifade dilbilgisi bilgileri std:: regex_constants içinde tanımlanmıştır:

- `ECMAScript`: Bu, JavaScript ve .NET dilleri tarafından kullanılan dilbilgisine en yakındır.
- `basic`: POSIX temel normal ifadeleri veya BRE.
- `extended`: POSIX genişletilmiş normal ifadeler veya @.
- `awk`: `extended`Bu, ancak yazdırılmayan karakterler için ek kaçış içerir.
- `grep`: `basic`Bu, ancak satır (' \n ') karakterlerinin farklı değişimlere de izin verir.
- `egrep`: `extended`Bu, ancak yeni satır karakterlerinin farklı değişimlere de izin verir.

Varsayılan olarak, hiçbir dilbilgisi belirtilmemişse `ECMAScript` varsayılır. Yalnızca bir dilbilgisi belirtilebilir.

Dilbilgisine ek olarak, çeşitli bayraklar uygulanabilir:
- `icase`: Eşleşirken büyük/küçük harf durumunu yoksay.
- `nosubs`: İşaretli eşleşmeleri yoksay (yani, parantez içindeki ifadeler); hiçbir değiştirme depolanmaz.
- `optimize`: Daha fazla oluşturma süresinin olası masrafına göre daha hızlı eşleme yapın.
- `collate`: Yerel ayara duyarlı harmanlama dizilerini kullanın (örneğin, "[a-z]" biçiminde aralıklar).

Normal ifade altyapısı davranışını belirtmek için, dilbilgisi ile sıfır veya daha fazla bayrak birleştirilebilir. Yalnızca bayraklar belirtilmişse, `ECMAScript` dilbilgisi olarak kabul edilir.

### <a name="element"></a>Öğe

Bir öğe aşağıdaki şeylerden biri olabilir:

- Hedef dizideki aynı karakterle eşleşen *sıradan bir karakter* .

- Bir yeni satır dışında hedef dizideki herhangi bir karakterle eşleşen bir *joker karakter* '. '.

- "[`expr`]" Biçimindeki bir *köşeli ayraç ifadesi* , ifadesi `expr`tarafından tanımlanan küme içinde de veya bir karakterle eşleşen "[^`expr`]" biçiminde olan hedef dizide bulunan bir karakter veya harmanlama öğesiyle eşleşen bir karakter veya hedef dizide, ifadesi `expr`tarafından tanımlanan küme içinde olmayan bir harmanlama öğesi.

   İfade `expr` aşağıdaki öğelerin herhangi bir birleşimini içerebilir:

   - Tek bir karakter. Bu karakteri tarafından `expr`tanımlanan kümesine ekler.

   - "`ch1`"Formununbir *karakter aralığı.* -`ch2` [`ch1` `expr`, `ch2`] Kapalı aralığındaki değerlere göre temsil edilen karakterleri tarafından tanımlanan kümesine ekler.

   - "[:`name`:]" Biçiminde bir *karakter sınıfı* . Adlandırılmış sınıftaki karakterleri tarafından `expr`tanımlanan kümesine ekler.

   - "[=`elt`=]" Biçiminin bir *denklik sınıfı* . `elt` Tarafından`expr`tanımlanan kümesine eşdeğer olan harmanlama öğelerini ekler.

   - "[.`elt`.]" Biçiminin *harmanlama simgesi* . Harmanlama öğesini `elt` tarafından `expr`tanımlanan kümesine ekler.

- Bir *tutturucu*. ' ^' yer işareti hedef dizinin başlangıcıyla eşleşir; '$' yer işareti hedef dizinin sonuyla eşleşir.

"(Alt *ifade* )"\\veya içinde `basic` "`grep`(alt *ifade* \\)" biçiminde bir *yakalama grubu* , ile eşleşen hedef dizideki karakterlerin dizisiyle eşleşir. Sınırlayıcılar arasındaki desenler.

- Hedef dizideki karakterle eşleşen "\\`k`" biçiminde bir *kimlik kaçış* karakteri `k` .

Örnekler:

- "a", "a" hedef dizisiyle eşleşir, ancak "B", "b" veya "c" hedef dizileriyle eşleşmez.

- "." tüm a", "B", "b" ve "c" hedef dizileriyle eşleşir.

- "[b-z]", "b" ve "c" hedef dizileriyle eşleşir, ancak "a" veya "B" hedef dizileriyle eşleşmez.

- "[:lower:]" "a", "b"ve "c" hedef dizileriyle eşleşir, ancak "B" hedef dizisiyle eşleşmez.

- "(a)", "a" hedef dizisiyle eşleşir ve yakalama grubu 1'i "a" alt dizisiyle ilişkilendirir, ancak "B", "b" veya "c" hedef dizileriyle eşleşmez.

, `ECMAScript`\\ `dd` Ve ' de bir öğesi,"`dd`" biçiminde bir *geri başvuru* da olabilir; burada, hedefteki bir karakter dizisiyle eşleşen bir ondalık değer N temsil eder `grep` `basic` Nth *Capture grubu*tarafından eşleştirilen karakterlerin dizisiyle aynı olan sıra. Örneğin ilk (ve tek) yakalama grubu ilk "a" dizisini ve \1 son "a" dizisini eşlediğinden, "(a)\1", "aa" hedef dizisini eşlemez.

' `ECMAScript`De, bir öğesi aşağıdaki işlemlerden biri de olabilir:

- "(?: Alt *ifade* )" biçimindeki *yakalama olmayan Grup* . Sınırlayıcı arasındaki desen tarafından eşleştirilen hedef dizideki karakterlerin dizisiyle eşleşir.

- "\F", "\n", "\r", "\t" veya "\v" biçimindeki sınırlı bir *dosya biçimi kaçış* . Bunlar hedef dizide sırasıyla bir form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme ile eşleşir.

- "(= Alt *ifade* )" formunun *pozitif bir onayı* . Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizinin karakterlerinin dizisiyle eşleşir, ancak hedef dizideki eşleme konumunu değiştirmez.

- Formun *negatif bir onayı* "(! *subexpression* )". Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizinin karakterlerinin bir dizisini eşlemez ve hedef dizideki eşleme konumunu değiştirmez.

- "\X`hh`" formunun *onaltılı kaçış dizisi* . İki onaltılık basamakla `hh`temsil edilen hedef dizideki bir karakterle eşleşir.

- "\U`hhhh`" formunun *Unicode kaçış dizisi* . Dört onaltılık basamakla `hhhh`temsil edilen hedef dizideki bir karakterle eşleşir.

- "\C`k`" formunun *Denetim kaçış dizisi* . Karakteri `k`tarafından adlandırılan denetim karakteriyle eşleşir.

- "\B" biçiminin bir *sözcük sınırı onayı* . Hedef dizideki geçerli konum bir *sözcük sınırının*hemen ardından olduğunda eşleşir.

- "\B" formu için *negatif bir sözcük sınırı onayı* . Hedef dizideki geçerli konum bir *sözcük sınırının*hemen ardından olmadığında eşleşir.

- "\D", "\d", "\s", "\s", "\w", "\w" biçiminde bir *DSW karakter kaçış karakteri* . Bir karakter sınıfı için kısa bir ad sağlar.

Örnekler:

- "(?:a)", "a" hedef dizisiyle eşleşir, ancak yakalama grubu 1 olmadığından "(?:a)\1" geçersizdir.

- "(= a) a", "a" hedef dizisiyle eşleşir. Pozitif onay hedef dizideki ilk "a" dizileriyle eşleşir ve normal ifadedeki son "a" hedef dizideki ilk "a" dizileriyle eşleşir.

- "(! a) a", "a" hedef dizisiyle eşleşmez.

- A\B. "a ~" hedef dizisiyle eşleşir, ancak "AB" hedef dizisiyle eşleşmez.

- A\B. "AB" hedef dizisiyle eşleşir, ancak "a ~" hedef dizisiyle eşleşmez.

' `awk`De, bir öğesi aşağıdaki işlemlerden biri de olabilir:

- "\\","\A", "\b", "\f", "\n", "\r", "\t" veya "\v" biçimindeki bir *dosya biçimi kaçış.* \\ Bunlar hedef dizide sırasıyla ters eğik çizgi, uyarı, geri al, bir form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme ile eşleşir.

- "\\"Formunun *sekizli kaçış dizisi* `ooo`. Temsili bir, iki veya üç sekizli basamakla `ooo`temsil edilen değer olan hedef dizideki bir karakterle eşleşir.

### <a name="repetition"></a>Yineleme

*Pozitif bir onaylama*, *negatif*bir onay veya bir *tutturucu* dışında herhangi bir öğe, bir yineleme sayısı ile izlenebilir. En genel`min`yineleme sayısı türü, ve`max``max`\\\\`min` içinde`grep`"{,}" veya "{,}" biçimini alır. `basic` Bu yineleme sayısı biçimi tarafından izlenen bir öğe, en az `min` art arda oluşumlarla eşleşir ve öğesiyle eşleşen bir dizinin art arda oluşumlarından `max` daha fazlasını içermez. Örneğin, "a{2,3}", "AA" hedef dizisiyle ve "aaa" hedef dizisiyle eşleşir, ancak "a" hedef dizisiyle veya "aaaa" hedef dizisiyle eşleşmez.

Bir yineleme sayısı aşağıdaki biçimlerden birini de alabilir:

- ve`min`\\`min`\\içinde "{}"veya"{}".`basic` `grep` "{`min`,`min`}" İle eşdeğerdir.

- ve`min`\\`min`\\içinde "{,}"veya"{,}".`basic` `grep` "{`min`, Sınırlandırılmamış}" ile eşdeğerdir.

- "\*". "{0,unbounded}" biçimine denk.

Örnekler:

- "a{2}", "AA" hedef dizisiyle eşleşir, ancak "a" hedef dizisiyle veya "aaa" hedef dizisiyle eşleşmez.

- "a{2,}", "AA" hedef dizisiyle, "aaa" hedef dizisiyle eşleşir, ancak "a" hedef dizisiyle eşleşmez.

- "a\*", "" hedef dizisiyle, "a" hedef dizisiyle, "AA" hedef dizisiyle vb. eşleşir.

`basic` Ve`grep`dışındaki tüm dilmars için, bir yineleme sayısı aşağıdaki formlardan birini de alabilir:

- "?". "{0,1}" İle eşdeğerdir.

- "+". "{1, sınırsız}" ile eşdeğerdir.

Örnekler:

- "a?" "" hedef dizisiyle ve "a" hedef dizisiyle eşleşir, ancak "AA" hedef dizisiyle eşleşmez.

- "a+", "a" hedef dizisiyle, "aa" hedef dizisiyle vb. ile eşleşir ancak "" hedef dizisiyle eşleşmez.

' `ECMAScript`De, tüm yineleme sayısı biçimleri, *doyumsuz olmayan bir yineleme*atayan '? ' karakteri ile izlenebilir.

### <a name="concatenation"></a>Bitiştirme

*Yineleme sayımlarına*sahip veya olmayan normal ifade öğeleri, daha uzun normal ifadeler oluşturacak şekilde birleştirilebilir. Sonuçta elde edilen ifade tek tek öğeler tarafından eşleştirilen dizilerin bir bitiştirmesi olan bir hedef dizisiyle eşleşir. Örneğin, "a{2,3}b", "AAB" hedef dizisiyle ve "aaab" hedef dizisiyle eşleşir, ancak "AB" hedef dizisiyle veya "aaaab" hedef dizisiyle eşleşmez.

### <a name="alternation"></a>Değişim

Ve `basic` dışındaki`grep`tüm normal ifade dilbilgisinde, art arda eklenmiş bir normal ifadeye sonra '&#124;' karakteri ve başka bir birleştirilmiş normal ifade gelebilir. Herhangi bir sayıdaki bitişik normal ifadeler bu şekilde birleştirilebilir. Sonuçta elde edilen ifade, bitişik normal ifadelerin bir veya daha fazlasını eşleyen herhangi bir hedef dizisiyle eşleşir.

Art arda eklenen normal ifadelerden birden fazla, hedef sırayla eşleştiğinde, `ECMAScript` eşleşme (*ilk eşleşme*) olarak sırayla eşleşen birleştirilmiş normal ifadelerin ilkini seçer; diğer normal ifade dilbilgisinde, *en uzun eşleşmeyi*elde eden birini seçer. Örneğin, "AB&#124;CD", "AB" hedef dizisiyle ve "CD" hedef dizisiyle eşleşir, ancak "ABD" hedef dizisiyle veya "ACD" hedef dizisiyle eşleşmez.

`grep` Ve`egrep`' de, bir yeni satır karakteri (' \n ') değişim ayırmak için kullanılabilir.

### <a name="subexpression"></a>Subexpression

`basic` Ve`grep`' de bir alt ifade bir birleştirme işlemi olur. Diğer normal ifade dilbilgisinde bir alt ifade bir değişimdir.

## <a name="grammarsummary"></a>Dilbilgisi özeti

Çeşitli normal ifade dilbilgisi sistemlerinde kullanılabilen özellikler aşağıdaki tabloda özetlenmiştir:

|Öğe|basit|genişletilmiş|ECMAScript|grep|egrep|awk|
|-------------|---------|---------|----------|----------|-----------|---------|
|'&#124;' kullanarak değişim||+|+||+|+|
|'\n' kullanarak değişim||||+|+||
|yer işareti|+|+|+|+|+|+|
|yeniden başvuru|+||+|+|||
|köşeli ayraç ifadesi|+|+|+|+|+|+|
|"()" kullanan yakalama grubu||+|+||+|+|
|"\\(\\)" kullanarak Grup yakala|+|||+|||
|denetim çıkış dizisi|||+||||
|dsw karakter çıkışı|||+||||
|dosya biçimi çıkışı|||+|||+|
|onaltılık çıkış dizisi|||+||||
|kimlik çıkışı|+|+|+|+|+|+|
|negatif onay|||+||||
|negatif sözcük sınırı onayı|||+||||
|yakalama olmayan grup|||+||||
|doyumsuz olmayan yineleme|||+||||
|sekizli çıkış dizisi||||||+|
|normal karakter|+|+|+|+|+|+|
|pozitif onay|||+||||
|"{}" kullanarak yineleme||+|+||+|+|
|"\\{\\}" kullanarak yineleme|+|||+|||
|'\*' kullanarak yineleme|+|+|+|+|+|+|
|'?' ve '+' kullanarak yineleme||+|+||+|+|
|unicode çıkış dizisi|||+||||
|joker karakter|+|+|+|+|+|+|
|sözcük sınırı onayı|||+||||

## <a name="semanticdetails"></a>Anlamsal Ayrıntılar

### <a name="anchor"></a>Yer işareti

Bir yer işareti hedef dizideki bir karakter ile değil, konumla eşleşir. Bir '^', hedef dizenin başlangıcıyla eşleşir; bir '$' hedef dizenin sonuyla eşleşir.

### <a name="back-reference"></a>Yeniden Başvuru

Geri başvuru, sonunda ondalık değeri N olan bir ters eğik çizgidir. N. *yakalama grubunun*içeriğiyle eşleşir. N değeri, yeniden başvuruyu önceleyen yakalama gruplarının sayısından daha fazla olmamalıdır. `basic` Ve`grep`' de, N değeri ters eğik çizgiden sonraki ondalık basamağa göre belirlenir. İçinde `ECMAScript`, N değeri, ters eğik çizgiyi hemen izleyen tüm ondalık basamakların belirlenir. Bu nedenle, `basic` ve `grep`' de, normal ifadede dokuz ' dan fazla yakalama grubuna sahip olsa bile N değeri hiçbir şekilde 9 ' dan daha fazla. İçinde `ECMAScript`, N değeri sınırsız olur.

Örnekler:

- "((a+) (b+))(c+) \3", "aabbbcbbb" hedef dizisiyle eşleşir. "\3" yeniden başvurusu, üçüncü yakalama grubundaki metni, diğer bir deyişle, "(b+)" öğesiyle eşleşir. "aabbbcbb" hedef dizisini eşlemez.

- "(a)\2" geçerli değildir.

- "(b ( `basic` `ECMAScript`(((((((((((((((((((((((((((((((((( `basic` "\ 1" geri başvurusunda bulunur. Yeniden başvuru ilk yakalama grubunun içeriğiyle eşleşir (diğer bir deyişle, "(b" ile başlayan ve ")" ile sonlanan ve yeniden başvurudan önce gelen öğeyi) ve son '0', '0' normal karakteriyle eşleşir. İçinde `ECMAScript`, geri başvurusu "\ 10" ' dur. Onuncu yakalama grubunu, diğer bir deyişle, en içtekiyle eşleşir.

### <a name="bracket-expression"></a>Köşeli Ayraç İfadesi

Köşeli ayraç ifadesi bir karakter kümesini ve *harmanlama öğelerini*tanımlar. Köşeli ayraç ifadesi ' ^' karakteriyle başladığında, kümede hedef dizideki geçerli karakteri eşleyen bir öğe yoksa eşleme başarılı olur. Aksi halde, eşleme yalnızca kümedeki öğelerden biri hedef dizideki geçerli karakterle eşleşiyorsa başarılı olur.

Karakter kümesi, *tek tek karakterlerin*, *karakter aralıklarının*, *karakter sınıflarının*, *denklik sınıfların*ve *harmanlama simgelerinin*herhangi bir birleşimi listelenerek tanımlanabilir.

### <a name="capture-group"></a>Yakalama Grubu

Bir yakalama grubu kendi içeriğini normal ifade dilbilgisi içinde tek bir birim olarak işaretler ve içeriğini eşleyen hedef metni etiketler. Her bir yakalama grubuyla ilişkili etiket, yakalama gruplarını işaretleyen sol parantezler, geçerli yakalama grubunu işaretleyen sol parantezler de dahil sayılarak belirlenen bir sayıdır. Bu uygulamada, yakalama gruplarının en yüksek sayısı 31'dir.

Örnekler:

- "ab+", "abb" hedef dizisiyle eşleşir, ancak "abab" hedef dizisiyle eşleşmez.

- "(ab)+", "abb" hedef dizisini eşlemez, ancak "abab" hedef dizisiyle eşleşir.

- "((a+)(b+))(c+)", "aabbbc" hedef dizisiyle eşleşir ve yakalama grubu 1'i "aabbb" alt dizisiyle, yakalama grubu 2'yi "aa" alt dizisiyle, yakalama grubu 3'ü "bbb" alt dizisiyle ve yakalama grubu 4'ü "c" alt dizisiyle ilişkilendirir.

### <a name="character-class"></a>Karakter Sınıfı

Köşeli ayraç ifadelerindeki bir karakter sınıfı, adlandırılan sınıftaki tüm karakterleri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Bir karakter sınıfı oluşturmak için, ardından ":]" gelen sınıfın adının ardından "[:" kullanın. Dahili olarak, karakter sınıflarının adları çağırarak `id = traits.lookup_classname`tanınır. Bir karakter `ch` , `traits.isctype(ch, id)` true döndürürse bu tür bir sınıfa aittir. Varsayılan `regex_traits` şablon, aşağıdaki tablodaki sınıf adlarını destekler.

|Sınıf Adı|Açıklama|
|----------------|-----------------|
|"alnum"|küçük harfler, büyük harfler ve rakamlar|
|"alpha"|küçük harfler ve büyük harfler|
|"blank"|boşluk veya sekme|
|"cntrl"|*dosya biçimi kaçış* karakterleri|
|"digit"|basamaklar|
|"graph"|küçük harfler, büyük harfler, rakamlar ve noktalama işareti|
|"lower"|küçük harfler|
|"print"|küçük harfler, büyük harfler, rakamlar, noktalama işareti ve boşluk|
|"punct"|noktalama işareti|
|"space"|space|
|"upper|büyük harf karakterler|
|"xdigit"|basamaklar, 'a', 'b', 'c', 'd', 'e', 'f', 'A', 'B', 'C', 'D', 'E', 'F'|
|"d"|basamakla aynı|
|"s"|boşlukla aynı|
|"w"|alnum'la aynı|

### <a name="character-range"></a>Karakter Aralığı

Köşeli ayraç ifadelerindeki bir karakter aralığı, aralıktaki tüm karakterleri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Bir karakter aralığı oluşturmak için, '-' karakterini aralıktaki ilk ve son karakterlerin arasına yerleştirin. Bunu yapmak, ilk karakterin sayısal değerinden büyük veya ona eşit ve son karakterin sayısal değerinden küçük veya ona eşit sayısal bir değere sahip tüm karakterleri kümeye yerleştirir. Bu eklenen karakter kümesinin karakterlerin platforma özgü temsiline bağlı olduğunu unutmayın. '-' karakteri köşeli ayraçlı bir ifadenin başında veya sonunda ya da bir karakter aralığının ilk ve son aralığı şeklinde oluşursa, kendisini temsil eder.

Örnekler:

- "[0-7]", { '0', '1', '2', '3', '4', '5', '6', '7' } karakterleri kümesini temsil eder. "0", "1" vb. hedef dizileriyle eşleşir, ancak "a" hedef dizisiyle eşleşmez.

- ASCII karakter kodlaması kullanan sistemlerde "[h-k]", {'h', 'i', 'j', 'k'} karakterlerinin kümesini temsil eder. "h", "i" vb. hedef dizileriyle eşleşir, ancak "\x8A" veya "0" hedef dizisiyle eşleşmez.

- EBCDIC karakter kodlaması kullanan sistemlerde "[h-k]", {'h', 'i', '\x8A', '\x8B', '\x8C', '\x8D', '\x8E', '\x8F', '\x90', 'j', 'k'} karakter kümesini temsil eder ('h', 0x88 olarak ve 'k', 0x92 olarak kodlanmıştır). "h", "i", "\x8A" vb. hedef dizileriyle eşleşir, ancak "0" hedef dizisiyle eşleşmez.

- "[-0-24]", { '-', '0', '1', '2', '4' } karakterleri kümesini temsil eder.

- "[0-2-]", { '0', '1', '2', '-' } karakterleri kümesini temsil eder.

- ASCII karakter kodlaması kullanan sistemlerde { '+', ',', '-' } karakterlerinin kümesini temsil eder.

Ancak, yerel ayar duyarlı aralıklar kullanıldığında, bir aralıktaki karakterler yerel ayara yönelik harmanlama kuralları tarafından belirlenir. Aralığın açıklamasındaki ilk karakterden sonrasını ve aralığın açıklamasındaki son karakterden öncesini harmanlayan karakterler küme içindedir. İki uçlu karakterler de kümededir.

### <a name="collating-element"></a>Harmanlama Öğesi

Bir harmanlama öğesi tek bir karakter olarak ele alınan çoklu bir karakter dizisidir.

### <a name="collating-symbol"></a>Harmanlama Sembolü

Köşeli ayraç ifadesindeki harmanlama sembolü, köşeli ayraç ifadesi tarafından tanımlanan kümesine bir *harmanlama öğesi* ekler. Harmanlama simgesi oluşturmak için "[." kullanın ardından, ".]" tarafından izlenen harmanlama öğesi.

### <a name="control-escape-sequence"></a>Denetim Çıkış Dizisi

Bir denetim çıkış dizisi, ardından 'a' - 'z' ya da 'A' - 'Z'' arası bir harf gelen 'c' harfinin ardından geldiği bir ters eğik çizgidir. Harf ile adlandırılan ASCI denetim karakteriyle eşleşir. Örneğin, "\cı", "\x09" hedef dizisiyle eşleşir, çünkü \<CTRL-ı > 0x09 değerine sahiptir.

### <a name="dsw-character-escape"></a>DSW Karakter Çıkışı

Bir dsw karakter çıkışı, aşağıdaki tabloda gösterildiği gibi bir karakter sınıfının kısa adıdır.

|Çıkış Sırası|Denk Adlandırılmış Sınıf|Varsayılan Adlandırılmış Sınıf|
|---------------------|----------------------------|-------------------------|
|"\d"|"[[:d:]]"|"[[:digit:]]"|
|"\D"|"[^[:d:]]"|"[^[:digit:]]"|
|"\s"|"[[:s:]]"|"[[:space:]]"|
|"\S"|"[^[:s:]]"|"[^[:space:]]"|
|"\w"|"[[:w:]]"|"[a-zA-z0-9_]"\*|
|"\W"|"[^[:w:]]"|"[^ a-zA-z0-9_]"\*|

\*ASCII karakter kümesi

### <a name="equivalence-class"></a>Denklik Sınıfı

Köşeli ayraç ifadesinde bir denklik sınıfı, denklik sınıf tanımındaki harmanlama öğesine denk gelen tüm karakterleri ve *harmanlama öğelerini* köşeli ayraç ifadesi tarafından tanımlanan kümesine ekler. Bir denklik sınıfı oluşturmak için, ardından "=]" gelen bir harmanlama öğesinin ardından "[=" kullanın. Dahili olarak, iki harmanlama `elt1` öğesi `elt2` ve ise `traits.transform_primary(elt1.begin(), elt1.end()) == traits.transform_primary(elt2.begin(), elt2.end())`eşdeğerdir.

### <a name="file-format-escape"></a>Dosya Biçimi Çıkışı

Bir dosya biçimi kaçış, olağan C dili karakter kaçış dizileri, "\\\\", "\a", "\b", "\f", "\n", "\r", "\t", "\v" ile oluşur. Bunlar, sırasıyla, ters eğik çizgi, uyarı, geri al, form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme gibi olağan anlamlara sahiptir. İçinde `ECMAScript`, "\a" ve "\b" kullanımına izin verilmez. ("\\\\" kullanımına izin verilir, ancak bir dosya biçimi kaçış değil, bir kimlik kaçış olur).

### <a name="hexadecimal-escape-sequence"></a>Onaltılık Çıkış Dizisi

Onaltılık çıkış dizisi, ardından iki onaltılık basamağın (0-9a-fA-F) geldiği ve 'x' harfinin takip ettiği bir ters eğik çizgidir. İki basamak tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Örneğin, ASCII karakter kodlaması kullanıldığında "\x41", "A" hedef dizisiyle eşleşir.

### <a name="identity-escape"></a>Kimlik Çıkışı

Kimlik çıkışı, ardından tek bir karakter gelen bir ters eğik çizgidir. Bu karakterle eşleşir. Karakter özel bir anlama sahip olduğunda gerekir, kimlik çıkışı kullanılarak özel anlam kaldırılır. Örneğin:

- "a\*", "aaa" hedef dizisiyle eşleşir, ancak "a\*" hedef dizisiyle eşleşmez.

- "a\\\*", "aaa" hedef dizisiyle eşleşmez, ancak "a\*" hedef dizisiyle eşleşir.

Bir kimlik çıkışında izin verilen karakterlerin kümesi, aşağıdaki tabloda gösterildiği gibi normal ifade dilbilgisine bağlıdır.

|Dilbilgisi|İzin Verilen Kimlik Çıkışı Karakterleri|
|-------------|----------------------------------------|
|`basic`, `grep`|{ '(', ')', '{', '}', '.', '[', '\\', '\*', '^', '$' }|
|`extended`, `egrep`|{ '(', ')', '{', '.', '[', '\\', '\*', '^', '$', '+', '?', '&#124;' }|
|`awk`|`extended`artı {' "', '/'}|
|`ECMAScript`|Bir tanımlayıcının parçası olabilenler dışındaki tüm karakterler. Genellikle, bu harfler, rakamlar, ' $ ', '\_' ve Unicode kaçış dizilerini içerir. Daha fazla bilgi için bkz. ECMAScript Dil Belirtimi.|

### <a name="individual-character"></a>Tekil Karakter

Köşeli ayraç ifadelerindeki tekil karakter, söz konusu karakteri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Baş taraf dışında bir köşeli ayraç ifadesinin herhangi bir yerindeki bir '^' kendisini temsil eder.

Örnekler:

- "[abc]" "a", "b" ve "c" hedef dizileriyle eşleşir, ancak "d" dizisiyle eşleşmez.

- "[^abc]", "d" hedef dizisiyle eşleşir, ancak "a", "b" veya "c" hedef dizileriyle eşleşmez.

- "[a^bc]", "a", "b", "c" ve "^" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.

Tüm normal ifade dilbilgisinde `ECMAScript`, '] ', ' [' açılışını izleyen ilk karakter ise veya başlangıçtaki ' ^ ' öğesini izleyen ilk karakter ise, kendisini temsil eder.

Örnekler:

- köşeli ayraç ifadesini sonlandırmak için bir ']' olmadığından "[]a" geçersizdir.

- "[]abc]", "a", "b", "c" ve "]" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.

- "[^]abc]", "d" hedef dizisiyle eşleşir, ancak "a", "b", "c", or "]" hedef dizileriyle eşleşmez.

İçinde `ECMAScript`, köşeli ayraç\\ifadesinde '] ' karakterini temsil etmek için '] ' kullanın.

Örnekler:

- Köşeli ayraç ifadesi boş olduğundan, "[]a", "a" hedef dizisini işler.

- "[\\] ABC]", "a", "b", "c" ve "]" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.

### <a name="negative-assert"></a>Negatif Onay

Negatif onay kendi içeriği dışında bir şeyi eşlemez. Hedef dizideki hiçbir karakteri tüketmez. Örneğin, "(! AA) (a\*)", "a" hedef dizisiyle eşleşir ve yakalama grubu 1 ' i "a" alt dizisiyle ilişkilendirir. "aa" veya "aaa" hedef dizisini eşlemez.

### <a name="negative-word-boundary-assert"></a>Negatif Sözcük Sınırı Onayı

Hedef dizedeki geçerli konum bir *sözcük sınırının*hemen ardından değilse, negatif bir sözcük sınırı onayı eşleşir.

### <a name="non-capture-group"></a>Yakalama olmayan Grup

Bir yakalama olmayan grup kendi içeriğini normal ifade dilbilgisi içinde tek bir birim olarak işaretler ancak hedef metni etiketlemez. Örneğin, "(a) (?: b)\*(c)", "abbc" hedef metniyle eşleşir ve yakalama grubu 1 ' i "a" alt dizisiyle ve yakalama grubu 2 ' yi "c" alt dizisiyle ilişkilendirir.

### <a name="non-greedy-repetition"></a>Doyumsuz olmayan Yineleme

Doyumsuz olmayan bir yineleme, deseni eşleyen hedef dizinin en kısa alt dizisini tüketir. Doyumsuz bir yineleme en uzun olanı tüketir. Örneğin, "(a +) (a\*b)", "aaab" hedef dizisiyle eşleşir. Doyumsuz olmayan bir yineleme kullanıldığında, yakalama grubu 1'i hedef dizinin başındaki "a" alt dizisiyle ve yakalama grubu 2'yi hedef dizinin sonundaki "aab" alt dizisiyle ilişkilendirir. Doyumsuz eşleşme kullanıldığında, yakalama grubu 1'i "aaa" alt dizisiyle ve yakalama grubu 2'yi "b" alt dizisiyle ilişkilendirir.

### <a name="octal-escape-sequence"></a>Sekizli Çıkış Dizisi

Sekizlik bir çıkış dizisi, ardından bir, iki veya üç sekizli basamak (0-7) gelen bir ters eğik çizgidir. Basamaklar tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Tüm basamakların '0' olması durumunda, dizi geçersizdir. Örneğin, ASCII karakter kodlaması kullanıldığında "\101", "A" hedef dizisiyle eşleşir.

### <a name="ordinary-character"></a>Normal Karakter

Normal bir karakter geçerli dilbilgisi içinde özel bir anlamı olmayan herhangi geçerli bir karakterdir.

İçinde `ECMAScript`, aşağıdaki karakterlerin özel anlamları vardır:

- ^  $  \  .  \*+  ?  (  )  \[  ]  {  }&#124;

`basic` Ve`grep`' de, aşağıdaki karakterlerin özel anlamları vardır:

- biçimindeki telefon numarasıdır.   \[   \

Ayrıca, `basic` ve `grep`içinde, belirli bir bağlamda kullanıldıklarında aşağıdaki karakterlerin özel anlamları vardır:

- '\*', normal bir ifadede ilk karakter olduğu veya normal bir ifadede ilk ' ^ ' izleyen ilk karakter ya da bir yakalama grubunun ilk karakteri veya ilk karakter olduğu zaman hariç tüm durumlarda özel bir anlam içeriyor. bir yakalama grubundaki başlangıçtaki ' ^ ' öğesini izler.

- ' ^', normal bir ifadenin ilk karakteri olduğunda özel bir anlamı vardır.

- '$', normal bir ifadenin son karakteri olduğunda özel bir anlamı vardır.

, `extended` Veiçinde`awk`, aşağıdaki karakterlerin özel anlamları vardır: `egrep`

- biçimindeki telefon numarasıdır.   \[\   (   \*   +   ?   {   &#124;

Ayrıca, `extended`ve `egrep`içinde, `awk`, ve içinde, belirli bir bağlamda kullanıldıklarında aşağıdaki karakterlerin özel anlamları vardır.

- ')', önceleyen bir '(' eşlediğinde özel bir anlamı vardır.

- ' ^', normal bir ifadenin ilk karakteri olduğunda özel bir anlamı vardır.

- '$', normal bir ifadenin son karakteri olduğunda özel bir anlamı vardır.

Hedef dizideki aynı karakterle eşleşen bir normal karakter. Varsayılan olarak, iki karakter aynı değer tarafından temsil ediliyorsa, bu eşlemenin başarılı olduğu anlamına gelir. Büyük/küçük harf duyarsız bir eşleşmedir, `ch0` iki `ch1` karakter ve `traits.translate_nocase(ch0) == traits.translate_nocase(ch1)`ile eşleşir. Bir yerel ayara duyarlı eşleşmedir, iki karakter `ch0` ve `ch1` ile eşleşir `traits.translate(ch0) == traits.translate(ch1)`.

### <a name="positive-assert"></a>Pozitif Onay

Pozitif onay kendi içeriğiyle eşleşir, ancak hedef dizideki herhangi bir karakteri tüketmez.

Örnekler:

- "(= AA) (a\*)", "aaaa" hedef dizisiyle eşleşir ve yakalama grubu 1 ' i "aaaa" alt dizisiyle ilişkilendirir.

- "(AA) (a\*)", "aaaa" hedef dizisiyle eşleşir ve yakalama grubu 1 ' i hedef dizinin başındaki "AA" alt dizisiyle ilişkilendirir ve hedef dizinin sonundaki "AA" alt dizisiyle yakalama grubu 2 ' nı yakalar.

- "(= AA) (a)&#124;(a)", "a" hedef dizisiyle eşleşir ve yakalama grubu 1 ' i boş bir sırayla ilişkilendirir (pozitif onay başarısız olduğu için) ve "a" alt dizisiyle birlikte "a" adlı bir yakalama grubu 2. Ayrıca, "aa" hedef dizisiyle eşleşir ve yakalama grubu 1'i "aa" alt dizisiyle ve yakalama grubu 2'yi boş bir diziyle ilişkilendirir.

### <a name="unicode-escape-sequence"></a>Unicode Çıkış Dizisi

Unicode çıkış dizisi, ardından dört onaltılık basamağın (0-9a-fA-F) geldiği ve 'u' harfinin takip ettiği bir ters eğik çizgidir. Dört basamak tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Örneğin, ASCII karakter kodlaması kullanıldığında "\u0041", "A" hedef dizisiyle eşleşir.

### <a name="wildcard-character"></a>Joker Karakter

Hedef ifadedeki, yeni bir satır dışında herhangi bir karakterle eşleşen bir joker karakter.

### <a name="word-boundary"></a>Sözcük Sınırı

Bir sözcük sınırı aşağıdaki durumlarda oluşur:

- Geçerli karakter, hedef dizinin başlangıcında ve sözcük karakterlerinden biridir`A-Za-z0-9_.`

- Geçerli karakter konumu hedef dizinin sonunu aşar ve hedef dizideki son karakter sözcük karakterlerinden biridir.

- Geçerli karakter sözcük karakterlerinden biridir ve önceki karakter değildir.

- Geçerli karakter sözcük karakterlerinden biri değildir ve önceki karakter biridir.

### <a name="word-boundary-assert"></a>Sözcük Sınırı Onayı

Hedef dizedeki geçerli konum bir *sözcük sınırının*hemen ardından olduğunda bir sözcük sınırı onayı eşleşir.

## <a name="matchingandsearching"></a>Eşleştirme ve arama

Bir hedef dizisiyle eşleşecek bir normal ifade için, normal ifadenin tamamının hedef dizinin tamamıyla eşleşmesi gerekir. Örneğin, "bcd" normal ifadesi "bcd" hedef dizisiyle eşleşir, ancak "abcd" ya da "bcde" hedef dizisiyle eşleşmez.

Normal bir ifade aramasının başarılı olması için normal ifadeyle eşleşen hedef dizide herhangi bir yerde bir alt dizi olmalıdır. Arama genellikle en soldaki eşleşen alt diziyi bulur.

Örnekler:

- Hedef dizideki "bcd" içindeki bir normal ifade "bcd" araması başarılı olur ve dizinin tamamıyla eşleşir. Hedef dizideki aynı "abcd" araması da başarılı olur ve son üç karakter ile eşleşir. Hedef dizideki aynı "bcde" araması da başarılı olur ve ilk üç karakter ile eşleşir.

- Hedef dizideki "bcdbcd" içindeki bir normal ifade araması başarılı olur ve ilk üç karakter ile eşleşir.

Bazı konumlardaki hedef diziyle eşleşen birden fazla alt dizi varsa, eşleşen deseni seçmenin iki yolu vardır. *İlk eşleştirme* , normal ifade eşleştiğinde ilk olarak bulunan alt diziyi seçer. *En uzun eşleşme* , bu konumda eşleşen olanlardan en uzun alt diziyi seçer. En yüksek uzunlukta birden fazla alt dizi varsa, en uzun eşleşme ilk bulunanı seçer. Örneğin, ilk eşleşme kullanıldığında, "abcd" hedef dizisindeki "b&#124;BC" normal ifadesi için arama, "b" alt dizisiyle eşleşir, çünkü değişim koşulunun sol tarafı bu alt diziyle eşleşiyor; Bu nedenle, ilk eşleşme değişim terimini denemez. En uzun eşleşme kullanıldığında, aynı "bc" araması eşleşir, çünkü "bc" "b" dizisinden uzundur.

Normal ifadenin sonuna ulaşılmamış olsa da, eşleşme başarısız olmadan hedef dizinin sonuna kadar gelirse kısmi eşleşme başarılı olur. Bu nedenle, kısmi eşleşmenin başarılı olmasının ardından hedef dizine karakter eklenmesi sonraki bir kısmi eşleşmenin başarısız olmasına neden olabilir. Ancak, kısmi eşleşmenin başarısız olmasının ardından hedef dizine karakter eklenmesi sonraki bir kısmi eşleşmenin başarılı olmasına neden olmayabilir. Örneğin, bir kısmi eşleşme ile "ab" "a" hedef dizisiyle eşleşir, ancak "ac" ile eşleşmez.

## <a name="formatflags"></a>Biçim bayrakları

|ECMAScript Biçim Kuralları|sed Biçim Kuralları|Değiştirme Metni|
|-----------------------------|----------------------|----------------------|
|"$&"|"&"|Tüm normal ifade (`[match[0].first, match[0].second)`) ile eşleşen karakter dizisi|
|"$$"||"$"|
||"\\&"|"&"|
|"$\`" (dolar işareti sonrasında arka tırnak işareti)||Normal ifadeyle (`[match.prefix().first, match.prefix().second)`) eşleşen alt dizinin önündeki karakter sırası|
|"$`" (ardından ileri tırnak gelen dolar işareti)||Normal ifadeyle (`[match.suffix().first, match.suffix().second)`) eşleşen alt diziyi izleyen karakter sırası|
|"$n"|"\n"|Konumunda `n`yakalama grubuyla eşleşen karakter dizisi; burada `n` 0 ile 9 (`[match[n].first, match[n].second)`) arasında bir sayıdır|
||"\\\n"|"\n"|
|"$nn"||Konumunda `nn`yakalama grubuyla eşleşen karakter dizisi, burada `nn` 10 ile 99 (`[match[nn].first, match[nn].second)`) arasında bir sayıdır|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)
