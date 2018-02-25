---
title: Normal ifadeler (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, regular expressions
- regular expressions, Visual C++
- regular expressions
ms.assetid: aafe202a-1d96-4b36-a270-d676dfd3c51c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce781d026712a8c93df6e8d177417f170092bfd2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="regular-expressions-c"></a>Normal İfadeler (C++)
C++ Standart Kitaplığı, birden çok normal ifade aynı destekler. Bu konu, normal ifadeler kullanırken kullanılabilir dilbilgisi farklılıkları açıklar.  
  
##  <a name="regexgrammar"></a> Normal ifade dilbilgisi  
Kullanılacak normal ifade dilbilgisi tarafından birini kullanarak belirtilen `std::regex_constants::syntax_option_type` numaralandırma değerleri. Bu normal ifade aynı std::regex_constants içinde tanımlanmıştır:

-   `ECMAScript`: Bu, JavaScript ve .NET dilleri tarafından kullanılan dilbilgisi en yakın olur.
-   `basic`: POSIX temel normal ifadeler veya BRE.
-   `extended`: Normal ifadeler veya ERE POSIX genişletilmiş.
-   `awk`: Bu `extended`, ancak ek çıkışları yazdırılamayan karakterler içeriyor.
-   `grep`: Bu `basic`, ancak yeni satır alternations ayırmak ('\n') karakteri de sağlar.
-   `egrep`: Bu `extended`, ancak yeni satır karakterlerini alternations ayırmak de sağlar.

Hiçbir dil bilgisi belirtilmemişse, varsayılan olarak, `ECMAScript` varsayılır. Yalnızca bir dilbilgisi belirtilebilir.  
  
Dilbilgisi yanı sıra birkaç bayrakları uygulanabilir:  
-   `icase`: Harf eşleştirirken yoksay.  
-   `nosubs`: İşaretli eşleşmeleri (diğer bir deyişle, parantezlerdeki ifadeler); yoksay hiçbir değişimler depolanır.  
-   `optimize`: Daha hızlı ve büyük yapım süre olası gider eşleşen olun.  
-   `collate`: Yerel ayara duyarlı alfabe düzeni dizilerini (örneğin, "[a-z]" biçiminde aralıkları) kullanın.  
  
Sıfır veya daha fazla bayrakları normal ifade altyapısı davranışı belirtmek için dilbilgisi ile birleştirilebilir. Yalnızca bayrakları belirtilen `ECMAScript` dilbilgisi kabul edilir.

### <a name="element"></a>Öğe  
 Bir öğe aşağıdaki şeylerden biri olabilir:  
  
-   Bir *sıradan karakter* hedef sırası aynı karakterle eşleşir.  
  
-   A *joker karakter* '.', hedef sırada bir satır başı karakteri dışındaki herhangi bir karakterle eşleşir.  
  
-   A *köşeli ayraç ifade* biçiminde "[`expr`]", bir karakter ya da ifadeyle tanımlanmış kümesindeki hedef sırası harmanlama öğesinde eşleşen `expr`, veya formun "[^`expr`]", bir karakter veya bir ifade tarafından tanımlanan kümesinde değil hedef sırası harmanlama öğesinde eşleşen `expr`.  
  
     İfade `expr` aşağıdakilerden herhangi bir birleşimini içerebilir:  
  
    -   Tek bir karakter. Tarafından tanımlanan ayarlamak için bu karakteri ekler `expr`.  
  
    -   A *karakter aralığı* biçiminde "`ch1`-`ch2`". Kapalı aralığındaki değerleri temsil edilen karakter ekler [`ch1`, `ch2`] tarafından tanımlanan kümesine `expr`.  
  
    -   A *karakter sınıfı* biçiminde "[:`name`:]". Karakter kümesi tarafından tanımlı adlandırılmış sınıfında ekler `expr`.  
  
    -   Bir *eşdeğer sınıf* biçiminde "[=`elt`=]". Eşdeğer harmanlama öğeleri ekler `elt` tarafından tanımlanan kümesine `expr`.  
  
    -   A *simgesi harmanlama* biçiminde "[.`elt`.]". Harmanlama öğesi ekler `elt` tarafından tanımlanan kümesine `expr`.  
  
-   Bir *bağlantı*. ' ^' yer işareti hedef dizinin başlangıcıyla eşleşir; '$' yer işareti hedef dizinin sonuyla eşleşir.  
  
 A *yakalama grup* biçiminde "( *alt* )", veya "\\( *alt* \\)" içinde `basic` ve `grep`, hangi karakterlerin sırasının yerleşimini sınırlayıcıları arasında deseni ile eşleşen hedef sırada eşleşir.  
  
-   Bir *kimlik kaçış* biçiminde "\\`k`", karakteri ile eşleşen `k` hedef dizisindeki.  
  
 Örnekler:  
  
-   "a", "a" hedef dizisiyle eşleşir, ancak "B", "b" veya "c" hedef dizileriyle eşleşmez.  
  
-   "." tüm a", "B", "b" ve "c" hedef dizileriyle eşleşir.  
  
-   "[b-z]", "b" ve "c" hedef dizileriyle eşleşir, ancak "a" veya "B" hedef dizileriyle eşleşmez.  
  
-   "[:lower:]" "a", "b"ve "c" hedef dizileriyle eşleşir, ancak "B" hedef dizisiyle eşleşmez.  
  
-   "(a)", "a" hedef dizisiyle eşleşir ve yakalama grubu 1'i "a" alt dizisiyle ilişkilendirir, ancak "B", "b" veya "c" hedef dizileriyle eşleşmez.  
  
 İçinde `ECMAScript`, `basic`, ve `grep`, bir öğenin de olabilir bir *geri başvuru* biçiminde "\\`dd`", burada `dd` bir dizi eşleşen bir ondalık değer N temsil eder hedef karakter sırası diğer bir deyişle tarafından n. eşleşen karakter dizisi aynı *yakalama grup*. Örneğin ilk (ve tek) yakalama grubu ilk "a" dizisini ve \1 son "a" dizisini eşlediğinden, "(a)\1", "aa" hedef dizisini eşlemez.  
  
 İçinde `ECMAScript`, bir öğenin de aşağıdakilerden biri olabilir:  
  
-   A *yakalama olmayan grup* biçiminde "(: *alt* )". Sınırlayıcı arasındaki desen tarafından eşleştirilen hedef dizideki karakterlerin dizisiyle eşleşir.  
  
-   Sınırlı bir *dosya biçimi kaçış* form "\f", "\n", "\r", "\t" veya "\v". Bunlar hedef dizide sırasıyla bir form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme ile eşleşir.  
  
-   A *pozitif assert* biçiminde "(= *alt* )". Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizinin karakterlerinin dizisiyle eşleşir, ancak hedef dizideki eşleme konumunu değiştirmez.  
  
-   A *negatif assert* formun "(! *subexpression* )". Sınırlayıcılar arasındaki desen tarafından eşleştirilen hedef dizinin karakterlerinin bir dizisini eşlemez ve hedef dizideki eşleme konumunu değiştirmez.  
  
-   A *onaltılık çıkış dizisi* biçiminde "\x`hh`". Hedef sırasındaki iki onaltılık basamak tarafından temsil edilen bir karakterle eşleşir `hh`.  
  
-   A *unicode kaçış sırası* biçiminde "\u`hhhh`". Hedef sırasındaki dört onaltılık basamak tarafından temsil edilen bir karakterle eşleşir `hhhh`.  
  
-   A *kontrol kaçış sırası* biçiminde "\c`k`". Karakter adlı Denetim karakterle eşleşir `k`.  
  
-   A *word sınır assert* "\b" biçiminde. Hedef sırası geçerli konumu hemen sonra olduğunda eşleşen bir *word sınır*.  
  
-   A *negatif word sınır assert* "\B" biçiminde. Hedef sırası geçerli konumu hemen sonra değilse eşleşen bir *word sınır*.  
  
-   A *dsw karakteri kaçış* formun "\d", "\D", "\s", "\S", "\w", "\W". Bir karakter sınıfı için kısa bir ad sağlar.  
  
 Örnekler:  
  
-   "(:a)" hedef sırası eşleşen "a", ancak "(:a) \1" hiçbir yakalama grubu 1 olduğundan geçersiz.  
  
-   "(=a) bir" hedef sırası eşleşen "a". Pozitif onay hedef dizideki ilk "a" dizileriyle eşleşir ve normal ifadedeki son "a" hedef dizideki ilk "a" dizileriyle eşleşir.  
  
-   "(!a) bir" hedef sırası eşleşmiyor "a".  
  
-   "a\b." hedef sırası eşleşen "bir ~", ancak hedef sırası "ab" eşleşmiyor.  
  
-   "a\B." hedef sırası "ab" ile eşleşir, ancak hedef sırası eşleşmiyor "bir ~".  
  
 İçinde `awk`, bir öğenin de aşağıdakilerden biri olabilir:  
  
-   A *dosya biçimi kaçış* biçiminde "\\\\", "\a", "\b", "\f", "\n", "\r", "\t" veya "\v". Bunlar hedef dizide sırasıyla ters eğik çizgi, uyarı, geri al, bir form besleme, yeni satır, satır başı, yatay sekme ve dikey sekme ile eşleşir.  
  
-   Bir *sekizli çıkış dizisi* biçiminde "\\`ooo`". Bir karakter, temsili bir, iki veya üç sekizli basamak tarafından temsil edilen değer hedef sırası eşleşen `ooo`.  
  
### <a name="repetition"></a>Yineleme  
 Dışında herhangi bir öğe bir *pozitif assert*, *negatif assert*, veya bir *bağlantı* yineleme sayısına göre izlenebilir. Yineleme sayısı en genel tür biçimdedir "{`min`,`max`}", veya "\\{`min`,`max`\\}" içinde `basic` ve `grep`. Yineleme sayısı bu formu tarafından izlenen bir öğesiyle eşleştiğinden en az `min` art arda oluşumu ve Hayır birden fazla `max` öğesi ile eşleşen bir dizi ardışık örnekleri. Örneğin, "a{2,3}"aa" hedef dizisini ve "aaa" hedef dizisiyle eşleşir, ancak "a" ya da "aaaa" hedef dizisiyle eşleşmez.  
  
 Bir yineleme sayısı aşağıdaki biçimlerden birini de alabilir:  
  
-   "{`min`}", veya "\\{`min`\\}" içinde `basic` ve `grep`. Eşdeğer "{`min`,`min`}".  
  
-   "{`min`,}", veya "\\{`min`,\\}" içinde `basic` ve `grep`. Eşdeğer "{`min`, sınırsız}".  
  
-   "*". "{0,unbounded}" biçimine denk.  
  
 Örnekler:  
  
-   "a{2}" "aa" hedef dizisiyle eşleşir, ancak "a" ya da "aaa" hedef dizisiyle eşleşmez.  
  
-   "a{2,}" "aa" hedef dizisiyle, "aaa" hedef dizisiyle vb. ile eşleşir, ancak "a" hedef dizisiyle eşleşmez.  
  
-   "a*", "" hedef dizisiyle, "a" hedef dizisiyle, "aa" hedef dizisiyle vb. ile eşleşir.  
  
 Tüm aynı için `basic` ve `grep`, bir yineleme sayısı ayrıca aşağıdaki biçimlerden birini alabilir:  
  
-   "?". "{0,1}" biçimine denk.  
  
-   "+". "{1, sınırsız}" eşdeğerdir.  
  
 Örnekler:  
  
-   "a?" hedef sırası eşleşen "" ve hedef sırası "a", ancak değil hedef sıra "aa".  
  
-   "a+", "a" hedef dizisiyle, "aa" hedef dizisiyle vb. ile eşleşir ancak "" hedef dizisiyle eşleşmez.  
  
 İçinde `ECMAScript`, yineleme sayısı tüm formları karakteriyle izlenebilir '', hangi atayan bir *doyumsuz olmayan yineleme*.  
  
### <a name="concatenation"></a>Bitiştirme  
 İle veya olmadan normal ifade öğeleri *yineleme sayısı*, form uzun normal ifadeler için birleştirilmiş. Sonuçta elde edilen ifade tek tek öğeler tarafından eşleştirilen dizilerin bir bitiştirmesi olan bir hedef dizisiyle eşleşir. Örneğin, "a{2,3}b", "aab" hedef dizisini ve "aaab" hedef dizisiyle eşleşir, ancak "ab" ya da "aaaab" hedef dizisiyle eşleşmez.  
  
### <a name="alternation"></a>Değişim  
 Tüm normal ifade aynı içinde `basic` ve `grep`, birleştirilmiş bir normal ifade karakteriyle izlenebilir ' &#124;' ve başka bir normal ifade birleştirilmiş. Herhangi bir sayıdaki bitişik normal ifadeler bu şekilde birleştirilebilir. Sonuçta elde edilen ifade, bitişik normal ifadelerin bir veya daha fazlasını eşleyen herhangi bir hedef dizisiyle eşleşir.  
  
 Birden fazla birleştirilmiş normal ifadeler hedef sırası eşleştiğinde `ECMAScript` eşleşme olarak dizisi eşleşen ilk birleştirilmiş bir normal ifade seçer (*ilk eşleşen*); diğer Normal ifade aynı seçin başarır bir *uzun eşleşme*. Örneğin, "ab &#124; cd" eşleşmeleri hedef sırası "ab" ve "abd" hedef sırası eşleşmeyen hedef sırası "cd" ancak veya hedef sırası "acd".  
  
 İçinde `grep` ve `egrep`, yeni satır karakteri ('\n') alternations ayırmak için kullanılabilir.  
  
### <a name="subexpression"></a>Subexpression  
 İçinde `basic` ve `grep`, bir alt bir yapıdır. Diğer normal ifade dilbilgisinde bir alt ifade bir değişimdir.  
  
##  <a name="grammarsummary"></a> Dilbilgisi özeti  
 Çeşitli normal ifade dilbilgisi sistemlerinde kullanılabilen özellikler aşağıdaki tabloda özetlenmiştir:  
  
|Öğe|Temel|genişletilmiş|ECMAScript|grep|egrep|awk|  
|-------------|---------|---------|----------|----------|-----------|---------|  
|Değişim kullanarak ' &#124;'||+|+||+|+|  
|'\n' kullanarak değişim||||+|+||  
|yer işareti|+|+|+|+|+|+|  
|yeniden başvuru|+||+|+|||  
|köşeli ayraç ifadesi|+|+|+|+|+|+|  
|"()" kullanan yakalama grubu||+|+||+|+|  
|yakalama grubunu kullanarak "\\(\\)"|+|||+|||  
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
|yineleme kullanarak "\\{\\}"|+|||+|||  
|'*' kullanarak yineleme|+|+|+|+|+|+|  
|'?' ve '+' kullanarak yineleme||+|+||+|+|  
|unicode çıkış dizisi|||+||||  
|joker karakter|+|+|+|+|+|+|  
|sözcük sınırı onayı|||+||||  
  
##  <a name="semanticdetails"></a> Anlam ayrıntıları  
  
### <a name="anchor"></a>Yer işareti  
 Bir yer işareti hedef dizideki bir karakter ile değil, konumla eşleşir. Bir '^', hedef dizenin başlangıcıyla eşleşir; bir '$' hedef dizenin sonuyla eşleşir.  
  
### <a name="back-reference"></a>Yeniden Başvuru  
 Ondalık değer H'ye ve ardından bir ters eğik çizgi geri başvurudur N. içeriğini eşleşen *yakalama grup*. N değeri, yeniden başvuruyu önceleyen yakalama gruplarının sayısından daha fazla olmamalıdır. İçinde `basic` ve `grep`, N değerini ters eğik çizgi izleyen ondalık basamak tarafından belirlenir. İçinde `ECMAScript`, N değerini ters eğik çizgi hemen izleyen tüm ondalık basamak tarafından belirlenir. Bu nedenle, içinde `basic` ve `grep`, normal ifade birden fazla dokuz yakalama Grup olsa bile N değeri hiçbir zaman birden fazla 9'dur. İçinde `ECMAScript`, N sınırsız değeridir.  
  
 Örnekler:  
  
-   "((a+) (b+))(c+) \3", "aabbbcbbb" hedef dizisiyle eşleşir. "\3" yeniden başvurusu, üçüncü yakalama grubundaki metni, diğer bir deyişle, "(b+)" öğesiyle eşleşir. "aabbbcbb" hedef dizisini eşlemez.  
  
-   "(a)\2" geçerli değildir.  
  
-   "((((a))) \10 b" farklı anlamları sahip `basic` ve `ECMAScript`. İçinde `basic` "\1" geri başvurudur. Yeniden başvuru ilk yakalama grubunun içeriğiyle eşleşir (diğer bir deyişle, "(b" ile başlayan ve ")" ile sonlanan ve yeniden başvurudan önce gelen öğeyi) ve son '0', '0' normal karakteriyle eşleşir. İçinde `ECMAScript`, "\10" geri başvurudur. Onuncu yakalama grubunu, diğer bir deyişle, en içtekiyle eşleşir.  
  
### <a name="bracket-expression"></a>Köşeli Ayraç İfadesi  
 Köşeli ayraç ifade karakter kümesini tanımlar ve *öğeleri harmanlama*. Köşeli ayraç ifadesi ' ^' karakteriyle başladığında, kümede hedef dizideki geçerli karakteri eşleyen bir öğe yoksa eşleme başarılı olur. Aksi halde, eşleme yalnızca kümedeki öğelerden biri hedef dizideki geçerli karakterle eşleşiyorsa başarılı olur.  
  
 Karakter kümesi herhangi bir bileşimini listeleyerek tanımlanabilir *tek tek karakterleri*, *karakter aralıkları*, *karakter sınıfları*, *eşdeğer sınıfları*, ve *simgeleri harmanlama*.  
  
### <a name="capture-group"></a>Yakalama Grubu  
 Bir yakalama grubu kendi içeriğini normal ifade dilbilgisi içinde tek bir birim olarak işaretler ve içeriğini eşleyen hedef metni etiketler. Her bir yakalama grubuyla ilişkili etiket, yakalama gruplarını işaretleyen sol parantezler, geçerli yakalama grubunu işaretleyen sol parantezler de dahil sayılarak belirlenen bir sayıdır. Bu uygulamada, yakalama gruplarının en yüksek sayısı 31'dir.  
  
 Örnekler:  
  
-   "ab+", "abb" hedef dizisiyle eşleşir, ancak "abab" hedef dizisiyle eşleşmez.  
  
-   "(ab)+", "abb" hedef dizisini eşlemez, ancak "abab" hedef dizisiyle eşleşir.  
  
-   "((a+)(b+))(c+)", "aabbbc" hedef dizisiyle eşleşir ve yakalama grubu 1'i "aabbb" alt dizisiyle, yakalama grubu 2'yi "aa" alt dizisiyle, yakalama grubu 3'ü "bbb" alt dizisiyle ve yakalama grubu 4'ü "c" alt dizisiyle ilişkilendirir.  
  
### <a name="character-class"></a>Karakter Sınıfı  
 Köşeli ayraç ifadelerindeki bir karakter sınıfı, adlandırılan sınıftaki tüm karakterleri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Bir karakter sınıfı oluşturmak için, ardından ":]" gelen sınıfın adının ardından "[:" kullanın. Karakter sınıfları adlarını çağırarak dahili olarak, tanınan `id = traits.lookup_classname`. Bir karakter `ch` varsa bu tür bir sınıfa ait `traits.isctype(ch, id)` true değerini döndürür. Varsayılan `regex_traits` şablonu aşağıdaki tabloda sınıf adlarını destekler.  
  
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
  
-   "[0-7]", { '0', '1', '2', '3', '4', '5', '6', '7' } karakterleri kümesini temsil eder. "0", "1" vb. hedef dizileriyle eşleşir, ancak "a" hedef dizisiyle eşleşmez.  
  
-   ASCII karakter kodlaması kullanan sistemlerde "[h-k]", {'h', 'i', 'j', 'k'} karakterlerinin kümesini temsil eder. "h", "i" vb. hedef dizileriyle eşleşir, ancak "\x8A" veya "0" hedef dizisiyle eşleşmez.  
  
-   EBCDIC karakter kodlaması kullanan sistemlerde "[h-k]", {'h', 'i', '\x8A', '\x8B', '\x8C', '\x8D', '\x8E', '\x8F', '\x90', 'j', 'k'} karakter kümesini temsil eder ('h', 0x88 olarak ve 'k', 0x92 olarak kodlanmıştır). "h", "i", "\x8A" vb. hedef dizileriyle eşleşir, ancak "0" hedef dizisiyle eşleşmez.  
  
-   "[-0-24]", { '-', '0', '1', '2', '4' } karakterleri kümesini temsil eder.  
  
-   "[0-2-]", { '0', '1', '2', '-' } karakterleri kümesini temsil eder.  
  
-   ASCII karakter kodlaması kullanan sistemlerde { '+', ',', '-' } karakterlerinin kümesini temsil eder.  
  
 Ancak, yerel ayar duyarlı aralıklar kullanıldığında, bir aralıktaki karakterler yerel ayara yönelik harmanlama kuralları tarafından belirlenir. Aralığın açıklamasındaki ilk karakterden sonrasını ve aralığın açıklamasındaki son karakterden öncesini harmanlayan karakterler küme içindedir. İki uçlu karakterler de kümededir.  
  
### <a name="collating-element"></a>Harmanlama Öğesi  
 Bir harmanlama öğesi tek bir karakter olarak ele alınan çoklu bir karakter dizisidir.  
  
### <a name="collating-symbol"></a>Harmanlama Sembolü  
 Köşeli ayraç ifadesinde harmanlama simgesi ekler bir *öğesi harmanlama* köşeli ayraç ifade tarafından tanımlanan kümesi. Harmanlama bir simge oluşturmak için "[." ardından "tarafından.]" harmanlama öğesi arkasından.  
  
### <a name="control-escape-sequence"></a>Denetim Çıkış Dizisi  
 Bir denetim çıkış dizisi, ardından 'a' - 'z' ya da 'A' - 'Z'' arası bir harf gelen 'c' harfinin ardından geldiği bir ters eğik çizgidir. Harf ile adlandırılan ASCI denetim karakteriyle eşleşir. Örneğin, "\ci" için "\x09" hedef sırası eşleşen \<ctrl-i > 0x09 değerine sahiptir.  
  
### <a name="dsw-character-escape"></a>DSW Karakter Çıkışı  
 Bir dsw karakter çıkışı, aşağıdaki tabloda gösterildiği gibi bir karakter sınıfının kısa adıdır.  
  
|Çıkış Sırası|Denk Adlandırılmış Sınıf|Varsayılan Adlandırılmış Sınıf|  
|---------------------|----------------------------|-------------------------|  
|"\d"|"[[:d:]]"|"[[:digit:]]"|  
|"\D"|"[^[:d:]]"|"[^[:digit:]]"|  
|"\s"|"[[:s:]]"|"[[:space:]]"|  
|"\S"|"[^[:s:]]"|"[^[:space:]]"|  
|"\w"|"[[:w:]]"|"[a-zA-Z0-9_]"*|  
|"\W"|"[^[:w:]]"|"[^a-zA-Z0-9_]"*|  
  
 *ASCII karakter kümesi  
  
### <a name="equivalence-class"></a>Denklik Sınıfı  
 Tüm karakterleri köşeli ayraç ifadesinde bir eşdeğer sınıf ekler ve *öğeleri harmanlama* harmanlama öğesi köşeli ayraç ifade tarafından tanımlanan kümesine eşdeğer sınıf tanımında eşdeğer olan. Bir denklik sınıfı oluşturmak için, ardından "=]" gelen bir harmanlama öğesinin ardından "[=" kullanın. Dahili olarak, iki harmanlama öğe `elt1` ve `elt2` eşdeğer ise `traits.transform_primary(elt1.begin(), elt1.end()) == traits.transform_primary(elt2.begin(), elt2.end())`.  
  
### <a name="file-format-escape"></a>Dosya Biçimi Çıkışı  
 Dosya biçimi kaçış oluşur normal C dil karakteri kaçış dizisi, "\\\\", "\a", "\b", "\f", "\n", "\r", "\t", "\v". Bunlar sırasıyla normal anlamları, diğer bir deyişle, ters eğik çizgi, uyarı, Geri Al, form besleme, satır başı karakteri, satır başı, yatay sekme ve dikey sekme içerir. İçinde `ECMAScript`, "\a" ve "\b" izin verilmez. ("\\\\" izin verilir, ancak bir kimlik kaçış dosya biçimi kaçış değil).  
  
### <a name="hexadecimal-escape-sequence"></a>Onaltılık Çıkış Dizisi  
 Onaltılık çıkış dizisi, ardından iki onaltılık basamağın (0-9a-fA-F) geldiği ve 'x' harfinin takip ettiği bir ters eğik çizgidir. İki basamak tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Örneğin, ASCII karakter kodlaması kullanıldığında "\x41", "A" hedef dizisiyle eşleşir.  
  
### <a name="identity-escape"></a>Kimlik Çıkışı  
 Kimlik çıkışı, ardından tek bir karakter gelen bir ters eğik çizgidir. Bu karakterle eşleşir. Karakter özel bir anlama sahip olduğunda gerekir, kimlik çıkışı kullanılarak özel anlam kaldırılır. Örneğin:  
  
-   "bir\*" hedef sırası "aaa" ile eşleşir, ancak hedef sırası eşleşmiyor "bir\*".  
  
-   "bir\\\*" hedef sırası eşleştirir ancak "aaa" hedef sırası eşleşmiyor "bir\*".  
  
 Bir kimlik çıkışında izin verilen karakterlerin kümesi, aşağıdaki tabloda gösterildiği gibi normal ifade dilbilgisine bağlıdır.  
  
|Dilbilgisi|İzin Verilen Kimlik Çıkışı Karakterleri|  
|-------------|----------------------------------------|  
|`basic`, `grep`|{ '(', ')', '{', '}', '.', '[', '\\', '\*', '^', '$' }|  
|`extended`, `egrep`|{ '(', ')', '{', '.', '[', '\\', '\*', '^', '$', '+', '?', '&#124;' }|  
|`awk`|`extended` plus { '"', '/' }|  
|`ECMAScript`|Bir tanımlayıcının parçası olabilenler dışındaki tüm karakterler. Genellikle, bu içerir harf, rakam, '$', '\_' ve unicode kaçış sıraları. Daha fazla bilgi için bkz. ECMAScript Dil Belirtimi.|  
  
### <a name="individual-character"></a>Tekil Karakter  
 Köşeli ayraç ifadelerindeki tekil karakter, söz konusu karakteri köşeli ayraç ifadesi tarafından tanımlanan karakter kümesine ekler. Baş taraf dışında bir köşeli ayraç ifadesinin herhangi bir yerindeki bir '^' kendisini temsil eder.  
  
 Örnekler:  
  
-   "[abc]" "a", "b" ve "c" hedef dizileriyle eşleşir, ancak "d" dizisiyle eşleşmez.  
  
-   "[^abc]", "d" hedef dizisiyle eşleşir, ancak "a", "b" veya "c" hedef dizileriyle eşleşmez.  
  
-   "[a^bc]", "a", "b", "c" ve "^" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.  
  
 Tüm normal ifade aynı içinde `ECMAScript`, bir ']' Açılış izleyen ilk karakteri ' [' veya bir başlangıç izleyen ilk karakterin ' ^', kendisini temsil eder.  
  
 Örnekler:  
  
-   köşeli ayraç ifadesini sonlandırmak için bir ']' olmadığından "[]a" geçersizdir.  
  
-   "[]abc]", "a", "b", "c" ve "]" hedef dizileriyle eşleşir, ancak "d" hedef dizisiyle eşleşmez.  
  
-   "[^]abc]", "d" hedef dizisiyle eşleşir, ancak "a", "b", "c", or "]" hedef dizileriyle eşleşmez.  
  
 İçinde `ECMAScript`, Kullan '\\]' karakteri temsil etmesi için ']' köşeli ayraç ifadesinde.  
  
 Örnekler:  
  
-   Köşeli ayraç ifadesi boş olduğundan, "[]a", "a" hedef dizisini işler.  
  
-   "[\\] abc]" "a", "b", "c", hedef sıraları eşleşen ve "]" ancak değil hedef sıra "d".  
  
### <a name="negative-assert"></a>Negatif Onay  
 Negatif onay kendi içeriği dışında bir şeyi eşlemez. Hedef dizideki hiçbir karakteri tüketmez. Örneğin, "(! aa)(a*)" hedef sırası eşleşen "a" ve ilişkilendirilmiş bir değişkene Grup 1 yakala "a". "aa" veya "aaa" hedef dizisini eşlemez.  
  
### <a name="negative-word-boundary-assert"></a>Negatif Sözcük Sınırı Onayı  
 Hedef geçerli dizedeki hemen sonra değilse negatif word sınır assert eşleşen bir *word sınır*.  
  
### <a name="non-capture-group"></a>Yakalama olmayan Grup  
 Bir yakalama olmayan grup kendi içeriğini normal ifade dilbilgisi içinde tek bir birim olarak işaretler ancak hedef metni etiketlemez. Örneğin, "(a)(:b)\*(c)" "abbc" hedef metinle eşleşen ve yakalama grubu 1 ile değişkene ilişkilendirir "bir"ve "c" değişkene Grup 2 yakalayın.  
  
### <a name="non-greedy-repetition"></a>Doyumsuz olmayan Yineleme  
 Doyumsuz olmayan bir yineleme, deseni eşleyen hedef dizinin en kısa alt dizisini tüketir. Doyumsuz bir yineleme en uzun olanı tüketir. Örneğin, "(a+) (bir\*b)" hedef sırası "aaab" ile eşleşir. Doyumsuz olmayan bir yineleme kullanıldığında, yakalama grubu 1'i hedef dizinin başındaki "a" alt dizisiyle ve yakalama grubu 2'yi hedef dizinin sonundaki "aab" alt dizisiyle ilişkilendirir. Doyumsuz eşleşme kullanıldığında, yakalama grubu 1'i "aaa" alt dizisiyle ve yakalama grubu 2'yi "b" alt dizisiyle ilişkilendirir.  
  
### <a name="octal-escape-sequence"></a>Sekizli Çıkış Dizisi  
 Sekizlik bir çıkış dizisi, ardından bir, iki veya üç sekizli basamak (0-7) gelen bir ters eğik çizgidir. Basamaklar tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Tüm basamakların '0' olması durumunda, dizi geçersizdir. Örneğin, ASCII karakter kodlaması kullanıldığında "\101", "A" hedef dizisiyle eşleşir.  
  
### <a name="ordinary-character"></a>Normal Karakter  
 Normal bir karakter geçerli dilbilgisi içinde özel bir anlamı olmayan herhangi geçerli bir karakterdir.  
  
 İçinde `ECMAScript`, şu karakterleri özel anlamları:  
  
-   ^  $  \  .  *  +  ?  (  )  [  ]  {  }  &#124;  
  
 İçinde `basic` ve `grep`, şu karakterleri özel anlamları:  
  
-   biçimindeki telefon numarasıdır.   [   \  
  
 Ayrıca, `basic` ve `grep`, belirli bir bağlamında kullanıldığında şu karakterleri özel anlamları:  
  
-   '\*' adındaki ilk karakter bir normal ifade veya bir başlangıç izleyen ilk karakterin olduğu durumların dışında tüm durumlarda özel bir anlamı yoktur ' ^' normal bir ifade veya ilk karakter olduğunda bir yakalama grup veya ilk karakter, bir başlangıç izleyen ' ^' yakalama grubunda.  
  
-   ' ^', normal bir ifadenin ilk karakteri olduğunda özel bir anlamı vardır.  
  
-   '$', normal bir ifadenin son karakteri olduğunda özel bir anlamı vardır.  
  
 İçinde `extended`, `egrep`, ve `awk`, şu karakterleri özel anlamları:  
  
-   biçimindeki telefon numarasıdır.   [   \   (   *   +   ?   {   &#124;  
  
 Ayrıca, `extended`, `egrep`, ve `awk`, belirli bir bağlamında kullanıldığında şu karakterleri özel anlamları.  
  
-   ')', önceleyen bir '(' eşlediğinde özel bir anlamı vardır.  
  
-   ' ^', normal bir ifadenin ilk karakteri olduğunda özel bir anlamı vardır.  
  
-   '$', normal bir ifadenin son karakteri olduğunda özel bir anlamı vardır.  
  
 Hedef dizideki aynı karakterle eşleşen bir normal karakter. Varsayılan olarak, iki karakter aynı değer tarafından temsil ediliyorsa, bu eşlemenin başarılı olduğu anlamına gelir. İki karakter duyarlı bir eşleşme `ch0` ve `ch1` eşleşiyorsa `traits.translate_nocase(ch0) == traits.translate_nocase(ch1)`. Yerel ayara duyarlı eşleme, iki karakter `ch0` ve `ch1` eşleşiyorsa `traits.translate(ch0) == traits.translate(ch1)`.  
  
### <a name="positive-assert"></a>Pozitif Onay  
 Pozitif onay kendi içeriğiyle eşleşir, ancak hedef dizideki herhangi bir karakteri tüketmez.  
  
 Örnekler:  
  
-   "(=aa) (bir\*)" hedef sırası "aaaa" ile eşleşen ve yakalama grubu 1 "aaaa" değişkene ile ilişkilendirir.  
  
-   "(aa) (bir\*)" hedef sırası "aaaa" ile eşleşen ve yakalama Grup 1 değişkene hedef sırası ve yakalama grubun hedef dizinin sonuna "aa" değişkene 2 başında "aa" ile ilişkilendirir.  
  
-   "(=aa)(a) &#124;(a)" hedef sırası eşleşen "a" ve ilişkilendirilmiş bir yakalama boş bir dizi 1 grubuyla (pozitif assert başarısız olduğundan) ve Grup 2 ile değişkene yakala "a". Ayrıca, "aa" hedef dizisiyle eşleşir ve yakalama grubu 1'i "aa" alt dizisiyle ve yakalama grubu 2'yi boş bir diziyle ilişkilendirir.  
  
### <a name="unicode-escape-sequence"></a>Unicode Çıkış Dizisi  
 Unicode çıkış dizisi, ardından dört onaltılık basamağın (0-9a-fA-F) geldiği ve 'u' harfinin takip ettiği bir ters eğik çizgidir. Dört basamak tarafından belirtilen değere sahip hedef dizideki bir karakterle eşleşir. Örneğin, ASCII karakter kodlaması kullanıldığında "\u0041", "A" hedef dizisiyle eşleşir.  
  
### <a name="wildcard-character"></a>Joker Karakter  
 Hedef ifadedeki, yeni bir satır dışında herhangi bir karakterle eşleşen bir joker karakter.  
  
### <a name="word-boundary"></a>Sözcük Sınırı  
 Bir sözcük sınırı aşağıdaki durumlarda oluşur:  
  
-   Geçerli karakteri hedef sırası başındaki ve sözcük karakterlerini biridir `A-Za-z0-9_.`  
  
-   Geçerli karakter konumu hedef dizinin sonunu aşar ve hedef dizideki son karakter sözcük karakterlerinden biridir.  
  
-   Geçerli karakter sözcük karakterlerinden biridir ve önceki karakter değildir.  
  
-   Geçerli karakter sözcük karakterlerinden biri değildir ve önceki karakter biridir.  
  
### <a name="word-boundary-assert"></a>Sözcük Sınırı Onayı  
 Hedef geçerli dizedeki hemen sonra olduğunda word sınır assert eşleşen bir *word sınır*.  
  
##  <a name="matchingandsearching"></a> Eşleşen ve arama  
 Bir hedef dizisiyle eşleşecek bir normal ifade için, normal ifadenin tamamının hedef dizinin tamamıyla eşleşmesi gerekir. Örneğin, "bcd" normal ifadesi "bcd" hedef dizisiyle eşleşir, ancak "abcd" ya da "bcde" hedef dizisiyle eşleşmez.  
  
 Normal bir ifade aramasının başarılı olması için normal ifadeyle eşleşen hedef dizide herhangi bir yerde bir alt dizi olmalıdır. Arama genellikle en soldaki eşleşen alt diziyi bulur.  
  
 Örnekler:  
  
-   Hedef dizideki "bcd" içindeki bir normal ifade "bcd" araması başarılı olur ve dizinin tamamıyla eşleşir. Hedef dizideki aynı "abcd" araması da başarılı olur ve son üç karakter ile eşleşir. Hedef dizideki aynı "bcde" araması da başarılı olur ve ilk üç karakter ile eşleşir.  
  
-   Hedef dizideki "bcdbcd" içindeki bir normal ifade araması başarılı olur ve ilk üç karakter ile eşleşir.  
  
 Bazı konumlardaki hedef diziyle eşleşen birden fazla alt dizi varsa, eşleşen deseni seçmenin iki yolu vardır. *İlk eşleşen* normal ifadeyle eşleştiğinde, ilk bulundu değişkene seçer. *En uzun eşleşen* o konumda eşleşen gördüğünüzden uzun değişkene seçer. En yüksek uzunlukta birden fazla alt dizi varsa, en uzun eşleşme ilk bulunanı seçer. Örneğin, ilk eşleşmeyi kullanıldığında, normal ifade araması "b &#124; bc" değişim sol şartını o değişkene; eşleştiğinden hedef sırası "ABCD ifadesinin" değişkene "b" ile eşleşir. Bu nedenle, ilk eşleşmeyi değişim sağ şartını denemez. En uzun eşleşme kullanıldığında, aynı "bc" araması eşleşir, çünkü "bc" "b" dizisinden uzundur.  
  
 Normal ifadenin sonuna ulaşılmamış olsa da, eşleşme başarısız olmadan hedef dizinin sonuna kadar gelirse kısmi eşleşme başarılı olur. Bu nedenle, kısmi eşleşmenin başarılı olmasının ardından hedef dizine karakter eklenmesi sonraki bir kısmi eşleşmenin başarısız olmasına neden olabilir. Ancak, kısmi eşleşmenin başarısız olmasının ardından hedef dizine karakter eklenmesi sonraki bir kısmi eşleşmenin başarılı olmasına neden olmayabilir. Örneğin, bir kısmi eşleşme ile "ab" "a" hedef dizisiyle eşleşir, ancak "ac" ile eşleşmez.  
  
##  <a name="formatflags"></a> Biçim bayrakları  
  
|ECMAScript Biçim Kuralları|sed Biçim Kuralları|Değiştirme Metni|  
|-----------------------------|----------------------|----------------------|  
|"$&"|"&"|Tüm normal ifadeyle eşleşen karakter dizisi (`[match[0].first, match[0].second)`)|  
|"$$"||"$"|  
||"\\&"|"&"|  
|"$\`" (dolar işareti ve ardından geri tırnakla)||Normal ifadeyle eşleşen değişkene önündeki karakter dizisi (`[match.prefix().first, match.prefix().second)`)|  
|"$`" (ardından ileri tırnak gelen dolar işareti)||Normal ifadeyle eşleşen değişkene izleyen karakter dizisi (`[match.suffix().first, match.suffix().second)`)|  
|"$n"|"\n"|Konumundaki yakalama grubuyla eşleşen karakter dizisi `n`, burada `n` 0 ile 9 arasında bir sayı (`[match[n].first, match[n].second)`)|  
||"\\\n"|"\n"|  
|"$nn"||Konumundaki yakalama grubuyla eşleşen karakter dizisi `nn`, burada `nn` 10 ile 99 arasında bir sayı (`[match[nn].first, match[nn].second)`)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)

