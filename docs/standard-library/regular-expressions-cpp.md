---
title: Normal İfadeler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Visual C++, regular expressions
- regular expressions, Visual C++
- regular expressions
ms.assetid: aafe202a-1d96-4b36-a270-d676dfd3c51c
ms.openlocfilehash: dafbe7c7ba10db2b0f34fdc6065c1475d63be284
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443476"
---
# <a name="regular-expressions-c"></a>Normal İfadeler (C++)

C++ Standart Kitaplığı birden çok normal ifade dilbilgisinde destekler. Bu konu, normal ifadeler kullanırken kullanılabilir dilbilgisi çeşitlemeleri açıklar.

## <a name="regexgrammar"></a> Normal ifade dilbilgisi

Normal ifade dilbilgisi kullanmak için aşağıdakilerden birini kullanarak belirtilir `std::regex_constants::syntax_option_type` sabit listesi değerleri. Bu normal ifade dilbilgisi içinde std::regex_constants tanımlanır:

- `ECMAScript`: Bu, JavaScript ve .NET dilleri tarafından kullanılan dilbilgisi en yakın olur.
- `basic`: POSIX temel normal ifadeler veya BRE.
- `extended`: Normal ifadeler veya ERE POSIX genişletilmiş.
- `awk`: Bu `extended`, ancak ek çıkışları yazdırılamayan karakterler içeriyor.
- `grep`: Bu `basic`, ancak yeni satır içinde değişimleri ayırmak ('\n') karakteri de sağlar.
- `egrep`: Bu `extended`, ancak aynı zamanda içinde değişimleri ayırmak yeni satır karakterleri verir.

Hiçbir dil bilgisi belirtilmemişse, varsayılan olarak `ECMAScript` varsayılır. Yalnızca bir dil bilgisi belirtilebilir.

Dilbilgisi yanı sıra birkaç bayrakları uygulanabilir:
- `icase`: Eşleştirirken çalışması yoksayar.
- `nosubs`: İşaretli eşleşir (diğer bir deyişle, parantezlerdeki ifadeler); yoksay hiçbir değişimler depolanır.
- `optimize`: Daha hızlı, büyük oluşturma zaman olası gider eşleşen olun.
- `collate`: Yerel ayar duyarlı olmayan harmanlama dizilerini (örneğin, "[a-z]" biçiminin aralıkları) kullanın.

Sıfır veya daha fazla bayrakları, normal ifade altyapısı davranışını belirtmek için dil bilgisi ile birleştirilebilir. Yalnızca belirtilen bayraklar `ECMAScript` dilbilgisi kabul edilir.

### <a name="element"></a>Öğe

Bir öğe aşağıdaki şeylerden biri olabilir:

- Bir *normal karakter* , hedef dizideki aynı karakterle eşleşir.

- A *joker karakter* '.', hedef dizideki bir yeni satır dışında herhangi bir karakterle eşleşir.

- A *köşeli ayraç ifadesi* biçiminin "[`expr`]", bir karakter veya harmanlama öğesi ifadesi tarafından tanımlanan kümesinde olan hedef dizideki eşleşen `expr`, ya da formun "[^`expr`]", bir karakter veya harmanlama öğesi ifadesi tarafından tanımlanan kümeye değil hedef dizideki eşleşen `expr`.

   İfade `expr` aşağıdakilerden herhangi bir birleşimini içerebilir:

   - Tek bir karakter. Bu karakter tarafından tanımlanan kümeye ekler `expr`.

   - A *karakter aralığı* biçiminin "`ch1`-`ch2`". Kapalı aralıktaki değerler tarafından temsil edilen karakterleri ekler [`ch1`, `ch2`] tarafından tanımlanan kümeye `expr`.

   - A *karakter sınıfı* biçiminin "[:`name`:]". Adlandırılmış sınıftaki karakterleri tarafından tanımlanan kümeye ekler `expr`.

   - Bir *denklik sınıfı* biçiminin "[=`elt`=]". Eşdeğer harmanlama öğelerini ekler `elt` tarafından tanımlanan kümeye `expr`.

   - A *harmanlama sembolü* biçiminin "[.`elt`.]". Harmanlama öğesi ekler `elt` tarafından tanımlanan kümeye `expr`.

- Bir *bağlantı*. ' ^' yer işareti hedef dizinin başlangıcıyla eşleşir; '$' yer işareti hedef dizinin sonuyla eşleşir.

A *yakalama grubu* biçiminin "( *subexpression* )", veya "\\( *subexpression* \\)" içinde `basic` ve `grep`, hangi Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizideki karakterlerin dizisiyle eşleşir.

- Bir *kimlik çıkışı* biçiminin "\\`k`", karakteriyle eşleşen `k` hedef dizideki.

Örnekler:

- "a", "a" hedef dizisiyle eşleşir, ancak "B", "b" veya "c" hedef dizileriyle eşleşmez.

- "." tüm a", "B", "b" ve "c" hedef dizileriyle eşleşir.

- "[b-z]", "b" ve "c" hedef dizileriyle eşleşir, ancak "a" veya "B" hedef dizileriyle eşleşmez.

- "[:lower:]" "a", "b"ve "c" hedef dizileriyle eşleşir, ancak "B" hedef dizisiyle eşleşmez.

- "(a)", "a" hedef dizisiyle eşleşir ve yakalama grubu 1'i "a" alt dizisiyle ilişkilendirir, ancak "B", "b" veya "c" hedef dizileriyle eşleşmez.

İçinde `ECMAScript`, `basic`, ve `grep`, bir öğe ayrıca olabilir bir *geri başvuru* formun "\\`dd`" burada `dd` bir dizisi ile eşleşen bir ondalık değer N temsil eder karakter hedef sıra diğer bir deyişle n. tarafından eşleşen karakter dizisi ile aynı *yakalama grubu*. Örneğin ilk (ve tek) yakalama grubu ilk "a" dizisini ve \1 son "a" dizisini eşlediğinden, "(a)\1", "aa" hedef dizisini eşlemez.

İçinde `ECMAScript`, bir öğe aşağıdaki şeylerden biri de olabilir:

- A *yakalama olmayan grup* biçiminin "(?: *subexpression* )". Sınırlayıcı arasındaki desen tarafından eşleştirilen hedef dizideki karakterlerin dizisiyle eşleşir.

- Sınırlı *dosya biçimi çıkışı* , form "\f", "\n", "\r", "\t" veya "\v". Bunlar hedef dizide sırasıyla bir form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme ile eşleşir.

- A *pozitif onay* biçiminin "(= *subexpression* )". Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizinin karakterlerinin dizisiyle eşleşir, ancak hedef dizideki eşleme konumunu değiştirmez.

- A *subexpression* biçiminin "(! *subexpression* )". Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizinin karakterlerinin bir dizisini eşlemez ve hedef dizideki eşleme konumunu değiştirmez.

- A *onaltılı çıkış dizisi* biçiminin "\x`hh`". İki onaltılık basamak tarafından temsil edilen hedef dizideki bir karakterle eşleşen `hh`.

- A *unicode çıkış dizisi* biçiminin "\u`hhhh`". Dört onaltılık basamak tarafından temsil edilen hedef dizideki bir karakterle eşleşen `hhhh`.

- A *denetim çıkış dizisi* biçiminin "\c`k`". Karakteri tarafından adlandırılan Denetim karakteriyle eşleşir `k`.

- A *sözcük sınırı onayı* "\b" biçiminin. Hedef dizideki geçerli konum hemen ardından geldiğinde eşleşen bir *sözcük sınırı*.

- A *negatif sözcük sınırı onayı* "\B" biçiminin. Hedef dizideki geçerli konum hemen sonra değilse eşleşen bir *sözcük sınırı*.

- A *dsw karakter çıkışı* form "\d", "\D", "\s", "\S", "\w", "\W". Bir karakter sınıfı için kısa bir ad sağlar.

Örnekler:

- "(?:a)", "a" hedef dizisiyle eşleşir, ancak yakalama grubu 1 olmadığından "(?:a)\1" geçersizdir.

- "(=a) bir" hedef dizisiyle eşleşir "a". Pozitif onay hedef dizideki ilk "a" dizileriyle eşleşir ve normal ifadedeki son "a" hedef dizideki ilk "a" dizileriyle eşleşir.

- "(!a) bir" hedef dizisiyle eşleşmez "a".

- "a\b." Hedef dizisiyle eşleşir "bir ~", "ab" hedef dizisiyle eşleşmez.

- "a\B." "ab" hedef dizisiyle eşleşir, ancak hedef dizisini eşlemez "bir ~".

İçinde `awk`, bir öğe aşağıdaki şeylerden biri de olabilir:

- A *dosya biçimi çıkışı* biçiminin "\\\\", "\a", "\b", "\f", "\n", "\r", "\t" veya "\v". Bunlar hedef dizide sırasıyla ters eğik çizgi, uyarı, geri al, bir form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme ile eşleşir.

- Bir *sekizli çıkış dizisi* biçiminin "\\`ooo`". Temsili bir, iki veya üç sekizli basamak tarafından temsil edilen değeri olan hedef dizideki bir karakterle eşleşir `ooo`.

### <a name="repetition"></a>Yineleme

Dışında herhangi bir öğe bir *pozitif onay*, *subexpression*, veya bir *bağlantı* bir yineleme sayısı gelebilir. En genel yineleme sayısı türü alır "{`min`,`max`}", veya "\\{`min`,`max`\\}" içinde `basic` ve `grep`. Bu yineleme biçiminin durumunun tarafından izlenen bir öğeyle eşleşir en az `min` oluşumunu ve Hayır birden fazla `max` oluşumunu öğeyle eşleşen bir dizi. Örneğin, "bir{2,3}" "a" ya da hedef dizideki "aaaa" "aa" hedef dizisiyle ve "aaa" hedef dizisiyle, ancak hedef dizisiyle eşleşmez, eşleşir.

Bir yineleme sayısı aşağıdaki biçimlerden birini de alabilir:

- "{`min`}", veya "\\{`min`\\}" içinde `basic` ve `grep`. Eşdeğer "{`min`,`min`}".

- "{`min`,}", veya "\\{`min`,\\}" içinde `basic` ve `grep`. Eşdeğer "{`min`, unbounded}".

- "\*". "{0,unbounded}" biçimine denk.

Örnekler:

- "bir{2}" hedef dizisiyle eşleşmez, ancak "aa" hedef dizisiyle, "a" veya "aaa" hedef dizisiyle eşleşir.

- "bir{2,}" "aa" hedef dizisiyle, "aaa" hedef dizisiyle vb. ile eşleşir, ancak hedef dizisini eşlemez "a".

- "bir\*" hedef dizisiyle eşleşir "", hedef sıra "a", "aa" hedef dizisiyle ve benzeri.

Dışındaki tüm dilbilgisi için `basic` ve `grep`, bir yineleme sayısı aşağıdaki biçimlerden birini de alabilir:

- "?". Eşdeğer "{0,1}".

- "+". "{1, unbounded}" ile eşdeğerdir.

Örnekler:

- "a?" Hedef dizisiyle eşleşir "" ve "a", ancak "değil aa" hedef dizisiyle.

- "a+", "a" hedef dizisiyle, "aa" hedef dizisiyle vb. ile eşleşir ancak "" hedef dizisiyle eşleşmez.

İçinde `ECMAScript`, yineleme sayısının tüm biçimlerinin karakteriyle izlenebilir '?', gösteren bir *doyumsuz olmayan yineleme*.

### <a name="concatenation"></a>Bitiştirme

Normal ifade öğeleri içeren veya içermeyen *yineleme sayısı*, form daha uzun ifadeleri biçimlendirmek için birleştirilebilir. Sonuçta elde edilen ifade tek tek öğeler tarafından eşleştirilen dizilerin bir bitiştirmesi olan bir hedef dizisiyle eşleşir. Örneğin, "bir{2,3}b", "aab" hedef dizisini ve "aaab" hedef dizisiyle eşleşir, ancak "ab" hedef dizisini ya "da aaaab" hedef dizisiyle eşleşmez.

### <a name="alternation"></a>Değişim

Dışında tüm normal ifade dilbilgisinde `basic` ve `grep`, bitişik normal bir ifade karakteriyle izlenebilir '&#124;' ve diğer bitişik normal ifadeler. Herhangi bir sayıdaki bitişik normal ifadeler bu şekilde birleştirilebilir. Sonuçta elde edilen ifade, bitişik normal ifadelerin bir veya daha fazlasını eşleyen herhangi bir hedef dizisiyle eşleşir.

Birden fazla bitişik normal ifadele hedef diziyi eşlediğinde `ECMAScript` eşleşme olarak dizisi ile eşleşen ilk bitişik normal ifadelerin seçer (*ilk eşleşen*); diğer Normal ifade dilbilgisinde seçin elde eden *en uzun eşleşme*. Örneğin, "ab&#124;cd" "ab" hedef dizisini ve "cd" hedef dizisiyle eşleşir, ancak "abd" hedef dizisini ya da "acd" hedef dizisiyle eşleşmez.

İçinde `grep` ve `egrep`, yeni satır karakteri ('\n') içinde değişimleri ayırmak için kullanılabilir.

### <a name="subexpression"></a>Subexpression

İçinde `basic` ve `grep`, bir alt ifade bir bitiştirmedir. Diğer normal ifade dilbilgisinde bir alt ifade bir değişimdir.

## <a name="grammarsummary"></a> Dilbilgisi özeti

Çeşitli normal ifade dilbilgisi sistemlerinde kullanılabilen özellikler aşağıdaki tabloda özetlenmiştir:

|Öğe|Temel|genişletilmiş|ECMAScript|grep|egrep|awk|
|-------------|---------|---------|----------|----------|-----------|---------|
|kullanarak Değişim '&#124;'||+|+||+|+|
|'\n' kullanarak değişim||||+|+||
|yer işareti|+|+|+|+|+|+|
|yeniden başvuru|+||+|+|||
|köşeli ayraç ifadesi|+|+|+|+|+|+|
|"()" kullanan yakalama grubu||+|+||+|+|
|kullanan yakalama grubu "\\(\\)"|+|||+|||
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
|kullanarak yineleme "{}"||+|+||+|+|
|kullanarak yineleme "\\{\\}"|+|||+|||
|kullanarak yineleme '\*'|+|+|+|+|+|+|
|'?' ve '+' kullanarak yineleme||+|+||+|+|
|unicode çıkış dizisi|||+||||
|joker karakter|+|+|+|+|+|+|
|sözcük sınırı onayı|||+||||

## <a name="semanticdetails"></a> Anlamsal Ayrıntılar

### <a name="anchor"></a>Yer işareti

Bir yer işareti hedef dizideki bir karakter ile değil, konumla eşleşir. Bir '^', hedef dizenin başlangıcıyla eşleşir; bir '$' hedef dizenin sonuyla eşleşir.

### <a name="back-reference"></a>Yeniden Başvuru

Ardından bir ondalık n değeri ters eğik çizgi geri bir başvurudur N. içeriğiyle eşleşir *yakalama grubu*. N değeri, yeniden başvuruyu önceleyen yakalama gruplarının sayısından daha fazla olmamalıdır. İçinde `basic` ve `grep`, N değeri ters eğik çizgiyi takip eden ondalık basamak tarafından belirlenir. İçinde `ECMAScript`, N değeri ters eğik çizgiyi hemen takip eden tüm ondalık basamaklar tarafından belirlenir. Bu nedenle `basic` ve `grep`, normal ifade birden fazla dokuz yakalama grubundan olsa bile, N değeri hiçbir zaman birden fazla 9'dur. İçinde `ECMAScript`, N değeri sınırsızdır.

Örnekler:

- "((a+) (b+))(c+) \3", "aabbbcbbb" hedef dizisiyle eşleşir. "\3" yeniden başvurusu, üçüncü yakalama grubundaki metni, diğer bir deyişle, "(b+)" öğesiyle eşleşir. "aabbbcbb" hedef dizisini eşlemez.

- "(a)\2" geçerli değildir.

- "(b (((a))) \10" içinde farklı anlamları vardır `basic` ve `ECMAScript`. İçinde `basic` "\1" geri başvurudur. Yeniden başvuru ilk yakalama grubunun içeriğiyle eşleşir (diğer bir deyişle, "(b" ile başlayan ve ")" ile sonlanan ve yeniden başvurudan önce gelen öğeyi) ve son '0', '0' normal karakteriyle eşleşir. İçinde `ECMAScript`, "\10" geri başvurudur. Onuncu yakalama grubunu, diğer bir deyişle, en içtekiyle eşleşir.

### <a name="bracket-expression"></a>Köşeli Ayraç İfadesi

Bir köşeli ayraç ifadesi karakter kümesini tanımlar ve *harmanlama öğelerini*. Köşeli ayraç ifadesi ' ^' karakteriyle başladığında, kümede hedef dizideki geçerli karakteri eşleyen bir öğe yoksa eşleme başarılı olur. Aksi halde, eşleme yalnızca kümedeki öğelerden biri hedef dizideki geçerli karakterle eşleşiyorsa başarılı olur.

Karakter kümesi, herhangi bir birleşimi listelenerek tanımlanabilir *karakterlerin tek tek*, *karakter aralıkları*, *karakter sınıfları*, *eşdeğerlik sınıflar*, ve *sembollerinin*.

### <a name="capture-group"></a>Yakalama Grubu

Bir yakalama grubu kendi içeriğini normal ifade dilbilgisi içinde tek bir birim olarak işaretler ve içeriğini eşleyen hedef metni etiketler. Her bir yakalama grubuyla ilişkili etiket, yakalama gruplarını işaretleyen sol parantezler, geçerli yakalama grubunu işaretleyen sol parantezler de dahil sayılarak belirlenen bir sayıdır. Bu uygulamada, yakalama gruplarının en yüksek sayısı 31'dir.

Örnekler:

- "ab+", "abb" hedef dizisiyle eşleşir, ancak "abab" hedef dizisiyle eşleşmez.

- "(ab)+", "abb" hedef dizisini eşlemez, ancak "abab" hedef dizisiyle eşleşir.

- "((a+)(b+))(c+)", "aabbbc" hedef dizisiyle eşleşir ve yakalama grubu 1'i "aabbb" alt dizisiyle, yakalama grubu 2'yi "aa" alt dizisiyle, yakalama grubu 3'ü "bbb" alt dizisiyle ve yakalama grubu 4'ü "c" alt dizisiyle ilişkilendirir.

### <a name="character-class"></a>Karakter Sınıfı

Köşeli ayraç ifadelerindeki bir karakter sınıfı, adlandırılan sınıftaki tüm karakterleri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Bir karakter sınıfı oluşturmak için, ardından ":]" gelen sınıfın adının ardından "[:" kullanın. Dahili olarak, karakter sınıflarının adları çağrılarak tanınır `id = traits.lookup_classname`. Bir karakter `ch` böyle bir sınıfa `traits.isctype(ch, id)` true değerini döndürür. Varsayılan `regex_traits` şablonu aşağıdaki tablodaki sınıf adlarını destekler.

|Sınıf Adı|Açıklama|
|----------------|-----------------|
|"alnum"|küçük harfler, büyük harfler ve rakamlar|
|"alpha"|küçük harfler ve büyük harfler|
|"blank"|boşluk veya sekme|
|"cntrl"|*dosya biçimi çıkışı* karakter|
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

Köşeli ayraç ifadesindeki bir harmanlama sembolü ekler bir *harmanlama öğesi* köşeli ayraç ifadesi tarafından tanımlanan kümeye. Bir harmanlama sembolü oluşturmak için "[." peşinden ".]" gelen harmanlama öğesinin ardından.

### <a name="control-escape-sequence"></a>Denetim Çıkış Dizisi

Bir denetim çıkış dizisi, ardından 'a' - 'z' ya da 'A' - 'Z'' arası bir harf gelen 'c' harfinin ardından geldiği bir ters eğik çizgidir. Harf ile adlandırılan ASCI denetim karakteriyle eşleşir. Örneğin, "\ci" için "\x09" hedef dizisiyle eşleşir \<ctrl-i > 0x09 değerine sahip.

### <a name="dsw-character-escape"></a>DSW Karakter Çıkışı

Bir dsw karakter çıkışı, aşağıdaki tabloda gösterildiği gibi bir karakter sınıfının kısa adıdır.

|Çıkış Sırası|Denk Adlandırılmış Sınıf|Varsayılan Adlandırılmış Sınıf|
|---------------------|----------------------------|-------------------------|
|"\d"|"[[:d:]]"|"[[:digit:]]"|
|"\D"|"[^[:d:]]"|"[^[:digit:]]"|
|"\s"|"[[:s:]]"|"[[:space:]]"|
|"\S"|"[^[:s:]]"|"[^[:space:]]"|
|"\w"|"[[:w:]]"|"[a-zA-Z0-9_]"\*|
|"\W"|"[^[:w:]]"|"[^ a-zA-Z0-9_]"\*|

\*ASCII karakter kümesi

### <a name="equivalence-class"></a>Denklik Sınıfı

Tüm karakterleri köşeli ayraç ifadesindeki bir denklik sınıfı ekler ve *harmanlama öğelerini* köşeli ayraç ifadesi tarafından tanımlanan kümeye denklik sınıfı açıklamasındaki harmanlama öğesine denk. Bir denklik sınıfı oluşturmak için, ardından "=]" gelen bir harmanlama öğesinin ardından "[=" kullanın. Dahili olarak, iki harmanlama öğesi `elt1` ve `elt2` eşdeğer olup olmadığını `traits.transform_primary(elt1.begin(), elt1.end()) == traits.transform_primary(elt2.begin(), elt2.end())`.

### <a name="file-format-escape"></a>Dosya Biçimi Çıkışı

Bir dosya biçimi çıkışı, normal C dili karakter kaçış dizileri, oluşan "\\\\", "\a", "\b", "\f", "\n", "\r", "\t", "\v". Bunlar normal anlamlara, diğer bir deyişle, ters eğik çizgi, uyarı, Geri Al, form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme sırasıyla içerir. İçinde `ECMAScript`, "\a" ve "\b" izin verilmez. ("\\\\" izin verilir, ancak kimlik çıkışı, dosya biçimi çıkışı değil).

### <a name="hexadecimal-escape-sequence"></a>Onaltılık Çıkış Dizisi

Onaltılık çıkış dizisi, ardından iki onaltılık basamağın (0-9a-fA-F) geldiği ve 'x' harfinin takip ettiği bir ters eğik çizgidir. İki basamak tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Örneğin, ASCII karakter kodlaması kullanıldığında "\x41", "A" hedef dizisiyle eşleşir.

### <a name="identity-escape"></a>Kimlik Çıkışı

Kimlik çıkışı, ardından tek bir karakter gelen bir ters eğik çizgidir. Bu karakterle eşleşir. Karakter özel bir anlama sahip olduğunda gerekir, kimlik çıkışı kullanılarak özel anlam kaldırılır. Örneğin:

- "bir\*" "aaa" hedef dizisiyle eşleşir, ancak hedef dizisini eşlemez "bir\*".

- "bir\\\*", "aaa" hedef dizisiyle eşleşmez ancak hedef dizisiyle eşleşir "bir\*".

Bir kimlik çıkışında izin verilen karakterlerin kümesi, aşağıdaki tabloda gösterildiği gibi normal ifade dilbilgisine bağlıdır.

|Dilbilgisi|İzin Verilen Kimlik Çıkışı Karakterleri|
|-------------|----------------------------------------|
|`basic`, `grep`|{ '(', ')', '{', '}', '.', '[', '\\', '\*', '^', '$' }|
|`extended`, `egrep`|{ '(', ')', '{', '.', '[', '\\', '\*', '^', '$', '+', '?', '&#124;' }|
|`awk`|`extended` artı {' "', '/'}|
|`ECMAScript`|Bir tanımlayıcının parçası olabilenler dışındaki tüm karakterler. Genellikle bu içerir harf, rakam, '$', '\_' ve unicode kaçış dizileri. Daha fazla bilgi için bkz. ECMAScript Dil Belirtimi.|

### <a name="individual-character"></a>Tekil Karakter

Köşeli ayraç ifadelerindeki tekil karakter, söz konusu karakteri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Baş taraf dışında bir köşeli ayraç ifadesinin herhangi bir yerindeki bir '^' kendisini temsil eder.

Örnekler:

- "[abc]" "a", "b" ve "c" hedef dizileriyle eşleşir, ancak "d" dizisiyle eşleşmez.

- "[^abc]", "d" hedef dizisiyle eşleşir, ancak "a", "b" veya "c" hedef dizileriyle eşleşmez.

- "[a^bc]", "a", "b", "c" ve "^" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.

Dışında tüm normal ifade dilbilgisinde `ECMAScript`, bir ']' Açılış izleyen ilk karakter ' [' veya ilk karakter bir ilk ' ^', kendisini temsil eder.

Örnekler:

- köşeli ayraç ifadesini sonlandırmak için bir ']' olmadığından "[]a" geçersizdir.

- "[]abc]", "a", "b", "c" ve "]" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.

- "[^]abc]", "d" hedef dizisiyle eşleşir, ancak "a", "b", "c", or "]" hedef dizileriyle eşleşmez.

İçinde `ECMAScript`, Kullan '\\]' karakterini temsil etmek için ']' köşeli ayraç ifadesindeki.

Örnekler:

- Köşeli ayraç ifadesi boş olduğundan, "[]a", "a" hedef dizisini işler.

- "[\\] [abc]" "a", "b", "c" hedef dizileriyle eşleşir ve "]", ancak "hedef d" dizisiyle eşleşmez.

### <a name="negative-assert"></a>Negatif Onay

Negatif onay kendi içeriği dışında bir şeyi eşlemez. Hedef dizideki hiçbir karakteri tüketmez. Örneğin, "(!aa) (bir\*)" hedef dizisiyle eşleşir "a" ve associates yakalama grubu 1 i "a". "aa" veya "aaa" hedef dizisini eşlemez.

### <a name="negative-word-boundary-assert"></a>Negatif Sözcük Sınırı Onayı

Hedef dizideki geçerli konum hemen sonra değilse bir negatif sözcük sınırı onayı eşleşir bir *sözcük sınırı*.

### <a name="non-capture-group"></a>Yakalama olmayan Grup

Bir yakalama olmayan grup kendi içeriğini normal ifade dilbilgisi içinde tek bir birim olarak işaretler ancak hedef metni etiketlemez. Örneğin, "(a)(?:b)\*(c)" "abbc" hedef metni eşleşir ve yakalama grubu 1 i ilişkilendirir "bir"ve yakalama grubu 2 yi "c".

### <a name="non-greedy-repetition"></a>Doyumsuz olmayan Yineleme

Doyumsuz olmayan bir yineleme, deseni eşleyen hedef dizinin en kısa alt dizisini tüketir. Doyumsuz bir yineleme en uzun olanı tüketir. Örneğin, "(a+) (bir\*b)" "aaab" hedef dizisiyle eşleşir. Doyumsuz olmayan bir yineleme kullanıldığında, yakalama grubu 1'i hedef dizinin başındaki "a" alt dizisiyle ve yakalama grubu 2'yi hedef dizinin sonundaki "aab" alt dizisiyle ilişkilendirir. Doyumsuz eşleşme kullanıldığında, yakalama grubu 1'i "aaa" alt dizisiyle ve yakalama grubu 2'yi "b" alt dizisiyle ilişkilendirir.

### <a name="octal-escape-sequence"></a>Sekizli Çıkış Dizisi

Sekizlik bir çıkış dizisi, ardından bir, iki veya üç sekizli basamak (0-7) gelen bir ters eğik çizgidir. Basamaklar tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Tüm basamakların '0' olması durumunda, dizi geçersizdir. Örneğin, ASCII karakter kodlaması kullanıldığında "\101", "A" hedef dizisiyle eşleşir.

### <a name="ordinary-character"></a>Normal Karakter

Normal bir karakter geçerli dilbilgisi içinde özel bir anlamı olmayan herhangi geçerli bir karakterdir.

İçinde `ECMAScript`, aşağıdaki karakterlerin özel anlamları vardır:

- ^  $  \  .  \*  +  ?  (  )  \[  ]  {  }&#124;

İçinde `basic` ve `grep`, aşağıdaki karakterlerin özel anlamları vardır:

- biçimindeki telefon numarasıdır.   \[   \

Ayrıca `basic` ve `grep`, belirli bir bağlamda kullanıldıklarında aşağıdaki karakterlerin özel anlamları vardır:

- '\*' normal bir ifadedeki ilk karakter ya da bir ilk ilk karakter olduğu zaman dışında tüm durumlarda özel bir anlamı vardır ' ^' veya normal bir ifadede, ilk karakteri olduğunda bir yakalama grubu veya ilk karakter, bir ilk ' ^' bir yakalama grubundaki.

- ' ^', normal bir ifadenin ilk karakteri olduğunda özel bir anlamı vardır.

- '$', normal bir ifadenin son karakteri olduğunda özel bir anlamı vardır.

İçinde `extended`, `egrep`, ve `awk`, aşağıdaki karakterlerin özel anlamları vardır:

- biçimindeki telefon numarasıdır.   \[   \   (   \*   +   ?   {   &#124;

Ayrıca `extended`, `egrep`, ve `awk`, belirli bir bağlamda kullanıldıklarında aşağıdaki karakterlerin özel anlamları vardır.

- ')', önceleyen bir '(' eşlediğinde özel bir anlamı vardır.

- ' ^', normal bir ifadenin ilk karakteri olduğunda özel bir anlamı vardır.

- '$', normal bir ifadenin son karakteri olduğunda özel bir anlamı vardır.

Hedef dizideki aynı karakterle eşleşen bir normal karakter. Varsayılan olarak, iki karakter aynı değer tarafından temsil ediliyorsa, bu eşlemenin başarılı olduğu anlamına gelir. Büyük küçük harf duyarlı eşleme, iki karakter `ch0` ve `ch1` eşleşiyorsa `traits.translate_nocase(ch0) == traits.translate_nocase(ch1)`. Yerel ayar duyarlı eşleme, iki karakter `ch0` ve `ch1` eşleşiyorsa `traits.translate(ch0) == traits.translate(ch1)`.

### <a name="positive-assert"></a>Pozitif Onay

Pozitif onay kendi içeriğiyle eşleşir, ancak hedef dizideki herhangi bir karakteri tüketmez.

Örnekler:

- "(=aa) (bir\*)" "aaaa" hedef dizisiyle eşleşir ve yakalama grubu 1 i "aaaa" ilişkilendirir.

- "(aa) (bir\*)" "aaaa" hedef dizisiyle eşleşir ve yakalama grubu 1 ', hedef dizisiyle ve yakalama grubu 2'hedef dizinin sonundaki "aa" alt dizisiyle başındaki "aa" alt dizisiyle ilişkilendirir.

- "(=aa)(a)&#124;(a)" hedef dizisiyle eşleşir "a" ve associates yakalama grubu 1 boş bir diziyle (pozitif onay başarısız olduğundan) ve yakalama grubu 2 yi "a". Ayrıca, "aa" hedef dizisiyle eşleşir ve yakalama grubu 1'i "aa" alt dizisiyle ve yakalama grubu 2'yi boş bir diziyle ilişkilendirir.

### <a name="unicode-escape-sequence"></a>Unicode Çıkış Dizisi

Unicode çıkış dizisi, ardından dört onaltılık basamağın (0-9a-fA-F) geldiği ve 'u' harfinin takip ettiği bir ters eğik çizgidir. Dört basamak tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Örneğin, ASCII karakter kodlaması kullanıldığında "\u0041", "A" hedef dizisiyle eşleşir.

### <a name="wildcard-character"></a>Joker Karakter

Hedef ifadedeki, yeni bir satır dışında herhangi bir karakterle eşleşen bir joker karakter.

### <a name="word-boundary"></a>Sözcük Sınırı

Bir sözcük sınırı aşağıdaki durumlarda oluşur:

- Geçerli karakter hedef dizinin başındaki ve sözcük karakterlerinden biri `A-Za-z0-9_.`

- Geçerli karakter konumu hedef dizinin sonunu aşar ve hedef dizideki son karakter sözcük karakterlerinden biridir.

- Geçerli karakter sözcük karakterlerinden biridir ve önceki karakter değildir.

- Geçerli karakter sözcük karakterlerinden biri değildir ve önceki karakter biridir.

### <a name="word-boundary-assert"></a>Sözcük Sınırı Onayı

Hedef dizideki geçerli konum hemen ardından geldiğinde sözcük sınırı onayı eşleşir bir *sözcük sınırı*.

## <a name="matchingandsearching"></a> Eşleştirme ve arama

Bir hedef dizisiyle eşleşecek bir normal ifade için, normal ifadenin tamamının hedef dizinin tamamıyla eşleşmesi gerekir. Örneğin, "bcd" normal ifadesi "bcd" hedef dizisiyle eşleşir, ancak "abcd" ya da "bcde" hedef dizisiyle eşleşmez.

Normal bir ifade aramasının başarılı olması için normal ifadeyle eşleşen hedef dizide herhangi bir yerde bir alt dizi olmalıdır. Arama genellikle en soldaki eşleşen alt diziyi bulur.

Örnekler:

- Hedef dizideki "bcd" içindeki bir normal ifade "bcd" araması başarılı olur ve dizinin tamamıyla eşleşir. Hedef dizideki aynı "abcd" araması da başarılı olur ve son üç karakter ile eşleşir. Hedef dizideki aynı "bcde" araması da başarılı olur ve ilk üç karakter ile eşleşir.

- Hedef dizideki "bcdbcd" içindeki bir normal ifade araması başarılı olur ve ilk üç karakter ile eşleşir.

Bazı konumlardaki hedef diziyle eşleşen birden fazla alt dizi varsa, eşleşen deseni seçmenin iki yolu vardır. *İlk eşleşen* normal ifade eşleştiğinde ilk bulunan alt diziyi seçer. *En uzun eşleşme* gördüğünüzden o konumda eşleşen en uzun alt diziyi seçer. En yüksek uzunlukta birden fazla alt dizi varsa, en uzun eşleşme ilk bulunanı seçer. Örneğin, ilk eşleşme kullanıldığında, normal ifade araması "b&#124;bc" değişimin sol terim o alt diziyi; eşleştiği için hedef sırası "abcd" "b" alt dizisiyle eşleşir. Bu nedenle ilk eşleşme değişimin sağ terimi denemez. En uzun eşleşme kullanıldığında, aynı "bc" araması eşleşir, çünkü "bc" "b" dizisinden uzundur.

Normal ifadenin sonuna ulaşılmamış olsa da, eşleşme başarısız olmadan hedef dizinin sonuna kadar gelirse kısmi eşleşme başarılı olur. Bu nedenle, kısmi eşleşmenin başarılı olmasının ardından hedef dizine karakter eklenmesi sonraki bir kısmi eşleşmenin başarısız olmasına neden olabilir. Ancak, kısmi eşleşmenin başarısız olmasının ardından hedef dizine karakter eklenmesi sonraki bir kısmi eşleşmenin başarılı olmasına neden olmayabilir. Örneğin, bir kısmi eşleşme ile "ab" "a" hedef dizisiyle eşleşir, ancak "ac" ile eşleşmez.

## <a name="formatflags"></a> Biçim bayrakları

|ECMAScript Biçim Kuralları|sed Biçim Kuralları|Değiştirme Metni|
|-----------------------------|----------------------|----------------------|
|"$&"|"&"|Normal ifadenin eşleşen karakter dizisi (`[match[0].first, match[0].second)`)|
|"$$"||"$"|
||"\\&"|"&"|
|"$\`" (arka ardından tırnak gelen dolar tarafından)||Normal ifadeyle eşleşen alt diziyi önündeki karakter dizisi (`[match.prefix().first, match.prefix().second)`)|
|"$`" (ardından ileri tırnak gelen dolar işareti)||Normal ifadeyle eşleşen alt diziyi takip eden karakter dizisi (`[match.suffix().first, match.suffix().second)`)|
|"$n"|"\n"|Konumundaki yakalama grubuyla eşleşen karakter dizisi `n`burada `n` 0 ile 9 arasında bir sayı (`[match[n].first, match[n].second)`)|
||"\\\n"|"\n"|
|"$nn"||Konumundaki yakalama grubuyla eşleşen karakter dizisi `nn`burada `nn` 10 ile 99 arasında bir sayı (`[match[nn].first, match[nn].second)`)|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
