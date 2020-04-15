---
title: Normal İfadeler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- regular expressions [C++]
ms.assetid: aafe202a-1d96-4b36-a270-d676dfd3c51c
ms.openlocfilehash: a6ff0fafce9f4b3e029be053d27ca68d096ec108
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368520"
---
# <a name="regular-expressions-c"></a>Normal İfadeler (C++)

C++ standart kitaplığı birden çok normal ifade dilbilgisini destekler. Bu konu, normal ifadeler kullanırken kullanılabilen dilbilgisi varyasyonlarını tartışır.

## <a name="regular-expression-grammar"></a><a name="regexgrammar"></a>Normal İfade Dilbilgisi

Kullanılacak normal ifade dilbilgisi, numaralandırma değerlerinden `std::regex_constants::syntax_option_type` birinin kullanımıyla belirtilir. Bu normal ifade gramerleri std tanımlanır::regex_constants:

- `ECMAScript`: Bu, JavaScript ve .NET dilleri tarafından kullanılan dilbilgisine en yakın olandır.
- `basic`: POSIX temel düzenli ifadeler veya BRE.
- `extended`: POSIX düzenli ifadeler veya ERE genişletilmiş.
- `awk`: Bu `extended`, ancak olmayan yazdırma karakterleri için ek kaçışlar vardır.
- `grep`: Bu, `basic`ama aynı zamanda newline ('\n') karakterleri ayırmak için alternations sağlar.
- `egrep`: Bu, `extended`ama aynı zamanda yeni çizgi karakterleri alternations ayırmak için izin verir.

Varsayılan olarak, dilbilgisi belirtilmemişse, `ECMAScript` varsayılılır. Yalnızca bir dilbilgisi belirtilebilir.

Dilbilgisine ek olarak, birkaç bayrak uygulanabilir:

- `icase`: Eşleşme yaparken servis saygısını yok say.
- `nosubs`: İşaretli eşleşmeleri (diğer bir deyişle parantez içinde ifadeler) yoksay; hiçbir değişiklik depolanır.
- `optimize`: Daha fazla inşaat süresi olası pahasına, daha hızlı eşleştirme olun.
- `collate`: Yerele duyarlı harmanlama dizileri kullanın (örneğin, formun aralıkları "[a-z]").

Sıfır veya daha fazla bayrak, normal ifade altyapısı davranışını belirtmek için dilbilgisi ile birleştirilebilir. Yalnızca bayraklar belirtilirse, `ECMAScript` dilbilgisi olarak kabul edilir.

### <a name="element"></a>Öğe

Bir öğe aşağıdaki şeylerden biri olabilir:

- Hedef dizisinde aynı karakterle eşleşen sıradan bir *karakter.*

- Yeni bir satır dışında hedef dizideki herhangi bir karakterle eşleşen bir *joker karakter* '.' karakteri.

- "[]"`expr`biçiminin, hedef dizideki bir karakter veya harmanlama öğesiile eşleşen bir *parantez* ifadesi, `expr`aynı zamanda ifadeyle`expr`tanımlanan kümedeki "[^ ]" veya "[^ ]" formunda, hedef `expr`dizideki bir karakter veya bir harmanlama öğesiile eşleşen ifadedir.

   İfade `expr` aşağıdaki şeylerin herhangi bir birleşimini içerebilir:

  - Tek bir karakter. Bu karakteri ' `expr`ile tanımlanan kümeye ekler.

  - Formun *bir karakter* `ch1`-`ch2`aralığı " ". Kapalı aralıktaki değerlerle temsil edilen karakterleri [`ch1` `ch2`, ] tarafından `expr`tanımlanan kümeye ekler.

  - Formun *bir karakter sınıfı* `name`"[: :]". Adlandırılmış sınıftaki karakterleri `expr`' le tanımlanan kümeye ekler.

  - "[=`elt`=]" formunun *eşdeğerlik sınıfı.* `expr`Tarafından tanımlanan kümeye `elt` eşdeğer harmanlama öğeleri ekler.

  - "[. .]"`elt`formunun *harmanlama sembolü.* Tarafından tanımlanan kümeye harmanlama `elt` `expr`öğesini ekler.

- Bir *çapa.* ' ^' yer işareti hedef dizinin başlangıcıyla eşleşir; '$' yer işareti hedef dizinin sonuyla eşleşir.

"( *alt ifade* )" veya "\\( *alt ifade* \\)" şeklindeki `basic` ve `grep`hedef dizideki karakterlerin dizisini eşleştiren ve sınırlayıcılar arasındaki desenle eşleşen bir yakalama *grubu.*

- " " şeklindeki\\`k`bir kimlik `k` *kaçışı,* hedef sıradaki karakterle eşleşir.

Örnekler:

- "a", "a" hedef dizisiyle eşleşir, ancak "B", "b" veya "c" hedef dizileriyle eşleşmez.

- "." tüm a", "B", "b" ve "c" hedef dizileriyle eşleşir.

- "[b-z]", "b" ve "c" hedef dizileriyle eşleşir, ancak "a" veya "B" hedef dizileriyle eşleşmez.

- "[:lower:]" "a", "b"ve "c" hedef dizileriyle eşleşir, ancak "B" hedef dizisiyle eşleşmez.

- "(a)", "a" hedef dizisiyle eşleşir ve yakalama grubu 1'i "a" alt dizisiyle ilişkilendirir, ancak "B", "b" veya "c" hedef dizileriyle eşleşmez.

`ECMAScript`"" `basic` `grep`şeklindeki bir öğe, hedef dizideki bir\\`dd`karakter `dd` dizisiyle eşleşen ondalık değeri temsil eden " " şeklindeki bir *geri referans* da *olabilir.* Örneğin ilk (ve tek) yakalama grubu ilk "a" dizisini ve \1 son "a" dizisini eşlediğinden, "(a)\1", "aa" hedef dizisini eşlemez.

In `ECMAScript`, bir öğe de aşağıdaki şeylerden biri olabilir:

- "(?: *subexpression* )" formunun *ele geçirilemeyen bir grubu.* Sınırlayıcı arasındaki desen tarafından eşleştirilen hedef dizideki karakterlerin dizisiyle eşleşir.

- "\f", "\n", "\r", "\t" veya "\v" formunun sınırlı dosya *biçimi kaçışı.* Bunlar hedef dizide sırasıyla bir form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme ile eşleşir.

- "(= *subexpression* )" formunun olumlu bir *iddiası.* Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizinin karakterlerinin dizisiyle eşleşir, ancak hedef dizideki eşleme konumunu değiştirmez.

- Formun *olumsuz bir iddia* "(! *alt ifade* )". Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizinin karakterlerinin bir dizisini eşlemez ve hedef dizideki eşleme konumunu değiştirmez.

- Formun *bir hexadecimal kaçış* dizisi`hh`"\x ". İki hexadecimal basamakla temsil edilen hedef dizideki bir `hh`karakterle eşleşir.

- Formun *tek kodlu kaçış sırası* `hhhh`"\u ". Dört hexadecimal basamakla temsil edilen hedef dizideki bir `hhhh`karakterle eşleşir.

- "\c`k`" formunun *bir kontrol kaçış sırası.* Karakter `k`tarafından adlandırılan denetim karakteri eşleşir.

- "\b" formunun *sözcük sınırı ileri sürülebilir.* Hedef dizideki geçerli konum *bir sözcük sınırından*hemen sonra olduğunda eşleşir.

- "\B" formunun *negatif sözcük sınırı ileri sürülebilir.* Hedef dizideki geçerli konum *bir sözcük sınırından*hemen sonra olmadığında eşleşir.

- "\d", "\D", "\s", "\S", "\w", "\W" şeklinde ki *dsw karakter kaçışı.* Bir karakter sınıfı için kısa bir ad sağlar.

Örnekler:

- "(?:a)", "a" hedef dizisiyle eşleşir, ancak yakalama grubu 1 olmadığından "(?:a)\1" geçersizdir.

- "(=a)a" hedef sırası "a" ile eşleşir. Pozitif onay hedef dizideki ilk "a" dizileriyle eşleşir ve normal ifadedeki son "a" hedef dizideki ilk "a" dizileriyle eşleşir.

- "(!a)a" hedef sırası "a" ile eşleşmiyor.

- "a\b." hedef sırası "a~" ile eşleşir, ancak hedef sırası "ab" ile eşleşmez.

- "a\B." hedef sırası "ab" ile eşleşir, ancak hedef sıra "a~" ile eşleşmez.

In `awk`, bir öğe de aşağıdaki şeylerden biri olabilir:

- "",\\\\"\a", "\b", "\f", "\n", "\r", "\t" veya "\v" şeklindeki *dosya biçimi kaçışı.* Bunlar hedef dizide sırasıyla ters eğik çizgi, uyarı, geri al, bir form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme ile eşleşir.

- Formun *sekizli kaçış sekansı* "\\`ooo`". Temsili bir, iki veya üç sekizli basamak tarafından temsil edilen değer olan `ooo`hedef dizideki bir karakterle eşleşir.

### <a name="repetition"></a>Yineleme

*Pozitif bir assert,* negatif *assert*veya *bir çapa* dışında herhangi bir öğe bir yineleme sayısı tarafından izlenebilir. Yineleme sayısının en genel türü "{`min``max`, }",\\`min`veya`max`\\" `basic` { `grep`, }" şeklinde ve . Bu yineleme sayısı biçimi tarafından izlenen bir öğe, en az `min` ardışık olaylarla eşleşir ve öğeyle eşleşen bir dizinin `max` ardışık oluşumlarından daha fazlası yoktur. Örneğin, "a{2,3}" hedef dizisi "aa" ve hedef sırası "aaa" eşleşir, ancak hedef sırası "a" veya hedef sırası "aaaa" eşleşmez.

Bir yineleme sayısı aşağıdaki biçimlerden birini de alabilir:

- "{`min`}",\\veya`min`\\" `basic` { `grep`}" içinde ve . "{`min`,`min`}" ile eşdeğerdir.

- "{`min`,}",\\veya`min`\\" { `basic` `grep`, }" içinde ve . "{`min`,sınırsız}" eşdeğeridir.

- "\*". "{0,unbounded}" biçimine denk.

Örnekler:

- "a{2}" hedef dizisi "aa" ile eşleşir, ancak hedef sırası "a" veya hedef sırası "aaa" ile eşleşmez.

- "a{2,}" hedef dizisi "aa", hedef sırası "aaa" ve benzeri eşleşir, ancak hedef dizisi "a" eşleşmiyor.

- "a\*" hedef sıra "", hedef sırası "a", hedef dizisi "aa" ve benzeri eşleşir.

Dışında `basic` tüm gramerler için ve `grep`, bir yineleme sayısı da aşağıdaki formlardan birini alabilir:

- "?". " "a'ya{0,1}eşdeğerdir.

- "+". "{1,sınırsız}" eşdeğeri.

Örnekler:

- "a?" hedef sırası "" ve hedef sırası "a" eşleşir, ancak hedef sırası "aa" eşleşir.

- "a+", "a" hedef dizisiyle, "aa" hedef dizisiyle vb. ile eşleşir ancak "" hedef dizisiyle eşleşmez.

' `ECMAScript`de, tekrar sayısının tüm biçimleri açgözlü olmayan bir *tekrarı*belirleyen '?' karakteri tarafından izlenebilir.

### <a name="concatenation"></a>Bitiştirme

Yineleme sayıları olan veya *olmayan*normal ifade öğeleri, daha uzun düzenli ifadeler oluşturmak için biraraya gelebilir. Sonuçta elde edilen ifade tek tek öğeler tarafından eşleştirilen dizilerin bir bitiştirmesi olan bir hedef dizisiyle eşleşir. Örneğin, "a{2,3}b" hedef sırası "aab" ve hedef sırası "aaab" eşleşir, ancak hedef sırası "ab" veya hedef dizisi "aaaab" eşleşmiyor.

### <a name="alternation"></a>Değişim

Dışında `basic` tüm düzenli ifade `grep`gramerlerinde ve , bir concatenated düzenli ifade karakteri '&#124;' ve başka bir concatenated normal ifade tarafından takip edilebilir. Herhangi bir sayıdaki bitişik normal ifadeler bu şekilde birleştirilebilir. Sonuçta elde edilen ifade, bitişik normal ifadelerin bir veya daha fazlasını eşleyen herhangi bir hedef dizisiyle eşleşir.

Bir birinden fazla uyumlu normal ifade hedef sırayla eşleştiğinde, `ECMAScript` diziyle eşleşme *(ilk eşleşme)* ile eşleşen uyumlu normal ifadelerin ilkini seçer; diğer normal ifade gramerleri *en uzun eşleşmeyi*başaran ı seçin. Örneğin, "ab&#124;cd", hedef sırası "ab" ve hedef sırası "cd" ile eşleşir, ancak hedef sırası "abd" veya hedef sırası "acd" ile eşleşmez.

içinde `grep` `egrep`ve , yeni bir çizgi karakteri ('\n') alternations ayırmak için kullanılabilir.

### <a name="subexpression"></a>Subexpression

Içinde `basic` `grep`ve , bir alt ifade bir concatenation olduğunu. Diğer normal ifade dilbilgisinde bir alt ifade bir değişimdir.

## <a name="grammar-summary"></a><a name="grammarsummary"></a>Dilbilgisi Özeti

Çeşitli normal ifade dilbilgisi sistemlerinde kullanılabilen özellikler aşağıdaki tabloda özetlenmiştir:

|Öğe|Temel|genişletilmiş|Ecmascript|grep|egrep|awk|
|-------------|---------|---------|----------|----------|-----------|---------|
|'&#124;' kullanarak değiştirme||+|+||+|+|
|'\n' kullanarak değişim||||+|+||
|yer işareti|+|+|+|+|+|+|
|yeniden başvuru|+||+|+|||
|köşeli ayraç ifadesi|+|+|+|+|+|+|
|"()" kullanan yakalama grubu||+|+||+|+|
|"\\(\\)" kullanarak yakalama grubu|+|||+|||
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
|" "{}kullanarak tekrar||+|+||+|+|
|"\\{\\}" kullanarak yineleme|+|||+|||
|' '\*kullanarak yineleme|+|+|+|+|+|+|
|'?' ve '+' kullanarak yineleme||+|+||+|+|
|unicode çıkış dizisi|||+||||
|joker karakter|+|+|+|+|+|+|
|sözcük sınırı onayı|||+||||

## <a name="semantic-details"></a><a name="semanticdetails"></a>Anlamsal Detaylar

### <a name="anchor"></a>Yer işareti

Bir yer işareti hedef dizideki bir karakter ile değil, konumla eşleşir. Bir '^', hedef dizenin başlangıcıyla eşleşir; bir '$' hedef dizenin sonuyla eşleşir.

### <a name="back-reference"></a>Yeniden Başvuru

Geri başvuru, ondalık değer N tarafından izlenen bir ters eğik çizgidir. Nth *yakalama grubunun*içeriğiyle eşleşiyor. N değeri, yeniden başvuruyu önceleyen yakalama gruplarının sayısından daha fazla olmamalıdır. Ve `basic` `grep`, N değeri ters eğik çizgi izleyen ondalık basamak tarafından belirlenir. N'nin `ECMAScript`değeri, ters eğik çizgiyi hemen izleyen tüm ondalık basamaklar tarafından belirlenir. Bu nedenle, ve `basic` `grep`, N değeri asla 9'dan fazla, normal ifade dokuzdan fazla yakalama grupları olsa bile. In `ECMAScript`, N değeri sınırsızdır.

Örnekler:

- "((a+) (b+))(c+) \3", "aabbbcbbb" hedef dizisiyle eşleşir. "\3" yeniden başvurusu, üçüncü yakalama grubundaki metni, diğer bir deyişle, "(b+)" öğesiyle eşleşir. "aabbbcbb" hedef dizisini eşlemez.

- "(a)\2" geçerli değildir.

- "(b(((((((((a)))))\10" içinde ve içinde `basic` `ECMAScript`farklı anlamlara sahiptir. Arkadaki `basic` başvuru "\1"dir. Yeniden başvuru ilk yakalama grubunun içeriğiyle eşleşir (diğer bir deyişle, "(b" ile başlayan ve ")" ile sonlanan ve yeniden başvurudan önce gelen öğeyi) ve son '0', '0' normal karakteriyle eşleşir. In `ECMAScript`, arka başvuru "\10". Onuncu yakalama grubunu, diğer bir deyişle, en içtekiyle eşleşir.

### <a name="bracket-expression"></a>Köşeli Ayraç İfadesi

Köşeli ayraç ifadesi bir karakter kümesini ve *öğeleri harmanlamayı*tanımlar. Köşeli ayraç ifadesi ' ^' karakteriyle başladığında, kümede hedef dizideki geçerli karakteri eşleyen bir öğe yoksa eşleme başarılı olur. Aksi halde, eşleme yalnızca kümedeki öğelerden biri hedef dizideki geçerli karakterle eşleşiyorsa başarılı olur.

Karakter kümesi *tek tek karakterler,* *karakter aralıkları, karakter sınıfları,* *eşdeğerlik sınıfları*ve *harmanlama sembolleri*herhangi bir kombinasyonu listeleyerek tanımlanabilir. *character classes*

### <a name="capture-group"></a>Yakalama Grubu

Bir yakalama grubu kendi içeriğini normal ifade dilbilgisi içinde tek bir birim olarak işaretler ve içeriğini eşleyen hedef metni etiketler. Her bir yakalama grubuyla ilişkili etiket, yakalama gruplarını işaretleyen sol parantezler, geçerli yakalama grubunu işaretleyen sol parantezler de dahil sayılarak belirlenen bir sayıdır. Bu uygulamada, yakalama gruplarının en yüksek sayısı 31'dir.

Örnekler:

- "ab+", "abb" hedef dizisiyle eşleşir, ancak "abab" hedef dizisiyle eşleşmez.

- "(ab)+", "abb" hedef dizisini eşlemez, ancak "abab" hedef dizisiyle eşleşir.

- "((a+)(b+))(c+)", "aabbbc" hedef dizisiyle eşleşir ve yakalama grubu 1'i "aabbb" alt dizisiyle, yakalama grubu 2'yi "aa" alt dizisiyle, yakalama grubu 3'ü "bbb" alt dizisiyle ve yakalama grubu 4'ü "c" alt dizisiyle ilişkilendirir.

### <a name="character-class"></a>Karakter Sınıfı

Köşeli ayraç ifadelerindeki bir karakter sınıfı, adlandırılan sınıftaki tüm karakterleri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Bir karakter sınıfı oluşturmak için, ardından ":]" gelen sınıfın adının ardından "[:" kullanın. Dahili olarak, karakter sınıflarının `id = traits.lookup_classname`adları arayarak tanınır. Bir `ch` karakter, doğru döndürürse `traits.isctype(ch, id)` böyle bir sınıfa aittir. Varsayılan `regex_traits` şablon, aşağıdaki tablodaki sınıf adlarını destekler.

|Sınıf Adı|Açıklama|
|----------------|-----------------|
|"alnum"|küçük harfler, büyük harfler ve rakamlar|
|"alpha"|küçük harfler ve büyük harfler|
|"blank"|boşluk veya sekme|
|"cntrl"|*dosya biçimi kaçış* karakterleri|
|"digit"|rakamlar|
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

Köşeli ayraç ifadesinde bir harmanlama sembolü, parantez ifadesi yle tanımlanan kümeye *bir harmanlama öğesi* ekler. Harmanlama sembolü oluşturmak için "[." ardından ".]" ard.)"

### <a name="control-escape-sequence"></a>Denetim Çıkış Dizisi

Bir denetim çıkış dizisi, ardından 'a' - 'z' ya da 'A' - 'Z'' arası bir harf gelen 'c' harfinin ardından geldiği bir ters eğik çizgidir. Harf ile adlandırılan ASCI denetim karakteriyle eşleşir. Örneğin, "\ci" hedef sıra "\x09" \<ile eşleşir, çünkü ctrl-i> değeri 0x09'dur.

### <a name="dsw-character-escape"></a>DSW Karakter Çıkışı

Bir dsw karakter çıkışı, aşağıdaki tabloda gösterildiği gibi bir karakter sınıfının kısa adıdır.

|Çıkış Sırası|Denk Adlandırılmış Sınıf|Varsayılan Adlandırılmış Sınıf|
|---------------------|----------------------------|-------------------------|
|"\d"|"[[:d:]]"|"[[:digit:]]"|
|"\D"|"[^[:d:]]"|"[^[:digit:]]"|
|"\s"|"[[:s:]]"|"[[:space:]]"|
|"\S"|"[^[:s:]]"|"[^[:space:]]"|
|"\w"|"[[:w:]]"|"[a-zA-Z0-9_]"\*|
|"\W"|"[^[:w:]]"|"[^a-zA-Z0-9_]"\*|

\*ASCII karakter seti

### <a name="equivalence-class"></a>Denklik Sınıfı

Bir parantez ifadesindeki eşdeğerlik sınıfı, eşitlik sınıfı tanımındaki harman öğesine eşdeğer tüm karakterleri ve *toplu öğeleri* parantez ifadesiyle tanımlanan kümeye ekler. Bir denklik sınıfı oluşturmak için, ardından "=]" gelen bir harmanlama öğesinin ardından "[=" kullanın. Dahili olarak, iki `elt1` harmanlama öğesi ve `elt2` eğer `traits.transform_primary(elt1.begin(), elt1.end()) == traits.transform_primary(elt2.begin(), elt2.end())`eşdeğerdir.

### <a name="file-format-escape"></a>Dosya Biçimi Çıkışı

Dosya biçimi kaçış, her zamanki C dili karakter\\\\kaçış dizilerinden oluşur, " ", ",\a", "\b", "\f", "\n", "\r", "\t", "\v". Bunlar, sırasıyla ters eğik çizgi, uyarı, arka boşluk, form beslemesi, yeni satır, satır başı, yatay sekme ve dikey sekme gibi olağan anlamlara sahiptir. `ECMAScript`"\a" ve "\b" olarak izin verilmez. ("\\\\" izin verilir, ama bir kimlik kaçış değil, bir dosya biçimi kaçış).

### <a name="hexadecimal-escape-sequence"></a>Onaltılık Çıkış Dizisi

Onaltılık çıkış dizisi, ardından iki onaltılık basamağın (0-9a-fA-F) geldiği ve 'x' harfinin takip ettiği bir ters eğik çizgidir. İki basamak tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Örneğin, ASCII karakter kodlaması kullanıldığında "\x41", "A" hedef dizisiyle eşleşir.

### <a name="identity-escape"></a>Kimlik Çıkışı

Kimlik çıkışı, ardından tek bir karakter gelen bir ters eğik çizgidir. Bu karakterle eşleşir. Karakter özel bir anlama sahip olduğunda gerekir, kimlik çıkışı kullanılarak özel anlam kaldırılır. Örneğin:

- "a\*" hedef dizisi "aaa" ile eşleşir, ancak\*hedef sıra "a " ile eşleşmez.

- "a\\\*" hedef dizisi "aaa" ile eşleşmez, ancak\*hedef sıra "a " ile eşleşir.

Bir kimlik çıkışında izin verilen karakterlerin kümesi, aşağıdaki tabloda gösterildiği gibi normal ifade dilbilgisine bağlıdır.

|Dilbilgisi|İzin Verilen Kimlik Çıkışı Karakterleri|
|-------------|----------------------------------------|
|`basic`, `grep`|{ '(', ')', '{', '}', '.', '[', '\\', '\*', '^', '$' }|
|`extended`, `egrep`|{'(', ')', '{', '.', '[', ',\\',\*'^', '$', '+', '?', '&#124;' }|
|`awk`|`extended`artı { '',,', '/' }|
|`ECMAScript`|Bir tanımlayıcının parçası olabilenler dışındaki tüm karakterler. Genellikle, bu harfleri, rakamları, '$', ' 've\_unicode kaçış dizilerini içerir. Daha fazla bilgi için bkz. ECMAScript Dil Belirtimi.|

### <a name="individual-character"></a>Tekil Karakter

Köşeli ayraç ifadelerindeki tekil karakter, söz konusu karakteri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Baş taraf dışında bir köşeli ayraç ifadesinin herhangi bir yerindeki bir '^' kendisini temsil eder.

Örnekler:

- "[abc]" "a", "b" ve "c" hedef dizileriyle eşleşir, ancak "d" dizisiyle eşleşmez.

- "[^abc]", "d" hedef dizisiyle eşleşir, ancak "a", "b" veya "c" hedef dizileriyle eşleşmez.

- "[a^bc]", "a", "b", "c" ve "^" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.

']' açılışını `ECMAScript`izleyen ilk karakter '[' veya başharfi '^' izleyen ilk karakter olması dışında tüm normal ifade gramerlerinde kendisini temsil eder.

Örnekler:

- köşeli ayraç ifadesini sonlandırmak için bir ']' olmadığından "[]a" geçersizdir.

- "[]abc]", "a", "b", "c" ve "]" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.

- "[^]abc]", "d" hedef dizisiyle eşleşir, ancak "a", "b", "c", or "]" hedef dizileriyle eşleşmez.

Parantez `ECMAScript`ifadesinde\\']' karakterini temsil etmek için ' ]' kullanın.

Örnekler:

- Köşeli ayraç ifadesi boş olduğundan, "[]a", "a" hedef dizisini işler.

- "[[]abc]"\\hedef dizileri "a", "b", "c" ve "]" ile eşleşir, ancak hedef sırası "d" ile eşleşmez.

### <a name="negative-assert"></a>Negatif Onay

Negatif onay kendi içeriği dışında bir şeyi eşlemez. Hedef dizideki hiçbir karakteri tüketmez. Örneğin, "(!aa)(a\*)" hedef sıra "a" ile eşleşir ve grup 1'i "a" alt dizisiyle yakalar. "aa" veya "aaa" hedef dizisini eşlemez.

### <a name="negative-word-boundary-assert"></a>Negatif Sözcük Sınırı Onayı

Hedef dizedeki geçerli konum *bir sözcük sınırından*hemen sonra değilse negatif sözcük sınırı öne sürüle çatla.

### <a name="non-capture-group"></a>Yakalama olmayan Grup

Bir yakalama olmayan grup kendi içeriğini normal ifade dilbilgisi içinde tek bir birim olarak işaretler ancak hedef metni etiketlemez. Örneğin, "(a)(?:b)\*(c)" hedef metin "abbc" ile eşleşir ve ortaklar grup 1'i "a" alt dizisiyle yakalar ve grup 2'yi "c" alt sırasını yakalar.

### <a name="non-greedy-repetition"></a>Doyumsuz olmayan Yineleme

Doyumsuz olmayan bir yineleme, deseni eşleyen hedef dizinin en kısa alt dizisini tüketir. Doyumsuz bir yineleme en uzun olanı tüketir. Örneğin, "(a+)(a\*b)" hedef sırası "aaab" ile eşleşir. Doyumsuz olmayan bir yineleme kullanıldığında, yakalama grubu 1'i hedef dizinin başındaki "a" alt dizisiyle ve yakalama grubu 2'yi hedef dizinin sonundaki "aab" alt dizisiyle ilişkilendirir. Doyumsuz eşleşme kullanıldığında, yakalama grubu 1'i "aaa" alt dizisiyle ve yakalama grubu 2'yi "b" alt dizisiyle ilişkilendirir.

### <a name="octal-escape-sequence"></a>Sekizli Çıkış Dizisi

Sekizlik bir çıkış dizisi, ardından bir, iki veya üç sekizli basamak (0-7) gelen bir ters eğik çizgidir. Basamaklar tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Tüm basamakların '0' olması durumunda, dizi geçersizdir. Örneğin, ASCII karakter kodlaması kullanıldığında "\101", "A" hedef dizisiyle eşleşir.

### <a name="ordinary-character"></a>Normal Karakter

Normal bir karakter geçerli dilbilgisi içinde özel bir anlamı olmayan herhangi geçerli bir karakterdir.

Ayrıca, `ECMAScript`aşağıdaki karakterlerin özel anlamları vardır:

- ^  $  \  .  \*+  ?  ( \[ ) ] { } &#124;

Ve `basic` `grep`, aşağıdaki karakterlerin özel anlamları vardır:

- .   \[   \

Ayrıca `basic` içinde `grep`ve , aşağıdaki karakterler belirli bir bağlamda kullanıldığında özel anlamları vardır:

- '\*' ' normal bir ifadedeki ilk karakter veya normal bir ifadedeki ilk '^' karakterini izleyen ilk karakter veya bir yakalama grubunun ilk karakteri veya bir yakalama grubundaki ilk '^' karakterini izleyen ilk karakter dışında her durumda özel bir anlamı vardır.

- ' ^', normal bir ifadenin ilk karakteri olduğunda özel bir anlamı vardır.

- '$', normal bir ifadenin son karakteri olduğunda özel bir anlamı vardır.

, `extended` `egrep`, `awk`ve , aşağıdaki karakterlerin özel anlamları vardır:

- .   \[\   (   \*   +   ?   { &#124;

`extended`Ayrıca, `egrep`, `awk`ve , aşağıdaki karakterler belirli bir bağlamda kullanıldığında özel anlamları vardır.

- ')', önceleyen bir '(' eşlediğinde özel bir anlamı vardır.

- ' ^', normal bir ifadenin ilk karakteri olduğunda özel bir anlamı vardır.

- '$', normal bir ifadenin son karakteri olduğunda özel bir anlamı vardır.

Hedef dizideki aynı karakterle eşleşen bir normal karakter. Varsayılan olarak, iki karakter aynı değer tarafından temsil ediliyorsa, bu eşlemenin başarılı olduğu anlamına gelir. Bir büyük/küçük harf duyarsız eşleşmesinde, iki karakter `ch0` ve `ch1` eşleşmiyor eğer `traits.translate_nocase(ch0) == traits.translate_nocase(ch1)`. Yerel duyarlı bir eşleşmede, iki `ch0` `ch1` karakter `traits.translate(ch0) == traits.translate(ch1)`ve eşleştir.

### <a name="positive-assert"></a>Pozitif Onay

Pozitif onay kendi içeriğiyle eşleşir, ancak hedef dizideki herhangi bir karakteri tüketmez.

Örnekler:

- "(=aa)(a\*)" hedef dizisi "aaaa" ile eşleşir ve grup 1'i "aaaa" alt dizisiyle yakalar.

- "(aa)(a\*)" hedef dizisi "aaaa" ile eşleşir ve ortaklar hedef sıranın başında "aa" alt dizisi ile grup 1'i yakalar ve hedef sıranın sonundaki "aa" alt dizisiyle grup 2'yi yakalar.

- "(=aa)(a)&#124;(a)" hedef dizisi "a" ile eşleşir ve ortaklar grup 1'i boş bir sırayla yakalar (pozitif assert başarısız olduğu için) ve grup 2'yi "a" alt dizisiyle yakalar. Ayrıca, "aa" hedef dizisiyle eşleşir ve yakalama grubu 1'i "aa" alt dizisiyle ve yakalama grubu 2'yi boş bir diziyle ilişkilendirir.

### <a name="unicode-escape-sequence"></a>Unicode Çıkış Dizisi

Unicode çıkış dizisi, ardından dört onaltılık basamağın (0-9a-fA-F) geldiği ve 'u' harfinin takip ettiği bir ters eğik çizgidir. Dört basamak tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Örneğin, ASCII karakter kodlaması kullanıldığında "\u0041", "A" hedef dizisiyle eşleşir.

### <a name="wildcard-character"></a>Joker Karakter

Hedef ifadedeki, yeni bir satır dışında herhangi bir karakterle eşleşen bir joker karakter.

### <a name="word-boundary"></a>Sözcük Sınırı

Bir sözcük sınırı aşağıdaki durumlarda oluşur:

- Geçerli karakter hedef dizinin başındadır ve sözcük karakterlerinden biridir`A-Za-z0-9_.`

- Geçerli karakter konumu hedef dizinin sonunu aşar ve hedef dizideki son karakter sözcük karakterlerinden biridir.

- Geçerli karakter sözcük karakterlerinden biridir ve önceki karakter değildir.

- Geçerli karakter sözcük karakterlerinden biri değildir ve önceki karakter biridir.

### <a name="word-boundary-assert"></a>Sözcük Sınırı Onayı

Sözcük sınırı, hedef dizedeki geçerli konum *bir sözcük sınırından*hemen sonra olduğunda eşleşir.

## <a name="matching-and-searching"></a><a name="matchingandsearching"></a>Eşleştirme ve Arama

Bir hedef dizisiyle eşleşecek bir normal ifade için, normal ifadenin tamamının hedef dizinin tamamıyla eşleşmesi gerekir. Örneğin, "bcd" normal ifadesi "bcd" hedef dizisiyle eşleşir, ancak "abcd" ya da "bcde" hedef dizisiyle eşleşmez.

Normal bir ifade aramasının başarılı olması için normal ifadeyle eşleşen hedef dizide herhangi bir yerde bir alt dizi olmalıdır. Arama genellikle en soldaki eşleşen alt diziyi bulur.

Örnekler:

- Hedef dizideki "bcd" içindeki bir normal ifade "bcd" araması başarılı olur ve dizinin tamamıyla eşleşir. Hedef dizideki aynı "abcd" araması da başarılı olur ve son üç karakter ile eşleşir. Hedef dizideki aynı "bcde" araması da başarılı olur ve ilk üç karakter ile eşleşir.

- Hedef dizideki "bcdbcd" içindeki bir normal ifade araması başarılı olur ve ilk üç karakter ile eşleşir.

Bazı konumlardaki hedef diziyle eşleşen birden fazla alt dizi varsa, eşleşen deseni seçmenin iki yolu vardır. *İlk eşleşme,* normal ifade eşleştiğinde ilk bulunan alt sırayı seçer. *En uzun eşleşme,* o konumda eşleşenlerden en uzun alt sırayı seçer. En yüksek uzunlukta birden fazla alt dizi varsa, en uzun eşleşme ilk bulunanı seçer. Örneğin, ilk eşleşme kullanıldığında, "abcd" hedef dizisindeki "b&#124;bc" normal ifadesinin aranması "b" alt dizisiyle eşleşir, çünkü alternasyonun sol terimi bu alt sıraya eşleşir; bu nedenle, ilk maç değiştirme sağ terimi denemez. En uzun eşleşme kullanıldığında, aynı "bc" araması eşleşir, çünkü "bc" "b" dizisinden uzundur.

Normal ifadenin sonuna ulaşılmamış olsa da, eşleşme başarısız olmadan hedef dizinin sonuna kadar gelirse kısmi eşleşme başarılı olur. Bu nedenle, kısmi eşleşmenin başarılı olmasının ardından hedef dizine karakter eklenmesi sonraki bir kısmi eşleşmenin başarısız olmasına neden olabilir. Ancak, kısmi eşleşmenin başarısız olmasının ardından hedef dizine karakter eklenmesi sonraki bir kısmi eşleşmenin başarılı olmasına neden olmayabilir. Örneğin, bir kısmi eşleşme ile "ab" "a" hedef dizisiyle eşleşir, ancak "ac" ile eşleşmez.

## <a name="format-flags"></a><a name="formatflags"></a>Bayrakları Biçimlendir

|ECMAScript Biçim Kuralları|sed Biçim Kuralları|Değiştirme Metni|
|-----------------------------|----------------------|----------------------|
|"$&"|"&"|Tüm normal ifadeyle eşleşen karakter`[match[0].first, match[0].second)`dizisi ( )|
|"$$"||"$"|
||"\\&"|"&"|
|"$\`" (dolar işareti ve ardından geri teklif)|| Normal ifadeyle eşleşen alt diziden önce gelen`[match.prefix().first, match.prefix().second)`karakter dizisi ( )|
|"$`" (ardından ileri tırnak gelen dolar işareti)||Normal ifadeyle eşleşen alt sırayı izleyen`[match.suffix().first, match.suffix().second)`karakter dizisi ( )|
|"$n"|"\n"|0 ile 9 arasında bir `n`sayı `n` olan konumda ki yakalama`[match[n].first, match[n].second)`grubuyla eşleşen karakter dizisi ( )|
||"\\\n"|"\n"|
|"$nn"||10 ile 99 arasında `nn`bir `nn` sayı olan konumda ki yakalama`[match[nn].first, match[nn].second)`grubuyla eşleşen karakter dizisi ( )|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplık Genel Bakış](../standard-library/cpp-standard-library-overview.md)
