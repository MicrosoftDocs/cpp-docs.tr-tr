---
title: 2. Yönergeler
ms.date: 01/18/2019
ms.assetid: d1a69374-6c03-45fb-8c86-e91cea8adae8
ms.openlocfilehash: bf96d5ee6963a76c2b2462d5b3a0639c1141ea15
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894256"
---
# <a name="2-directives"></a>2. Yönergeler

Yönergeleri temel `#pragma` C ve C++ standartlarında tanımlanmış yönergeleri.  OpenMP C ve C++ API destekleyen derleyiciler etkinleştirir ve tüm OpenMP derleyici yönergeleri yorumu izin veren bir komut satırı seçeneği içerir.

## <a name="21-directive-format"></a>2.1 yönerge biçimi

Bir OpenMP yönergesi sözdizimi resmi dilbilgisi tarafından belirtilen [ek C](c-openmp-c-and-cpp-grammar.md)ve resmi olmayan adı şu şekilde:

```cpp
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

Her yönerge ile başlayan `#pragma omp`, aynı ada sahip diğer (OpenMP olmayan ya da satıcı uzantıları için OpenMP) pragma yönergeleri ile Çakışma olasılığını azaltmak için. Yönergenin rest derleyici yönergeleri C ve C++ standartları kurallarını izler. Önce ve sonra boşluk özellikle kullanılabilir `#`, ve bir yönergesi içinde sözcükleri ayırmak için boşluk bazen kullanılmalıdır. Ön işleme belirteci aşağıdaki `#pragma omp` Makro değişikliği tabi olan.

Yönergeleri büyük/küçük harfe duyarlıdır. Yan tümceleri yönergelerinde görüntülenme sırası önemli değildir. Şirket yönergeleri yan tümceleri, gerektiğinde her bir yan tümceye açıklamasında listelenen kısıtlamalarla tabi yinelenebilir. Varsa *değişken listesi* görünür bir yan tümcesinde, yalnızca değişkenleri belirtmeniz gerekir. Yalnızca bir *yönergesi adı* yönerge başına belirtilebilir.  Örneğin, aşağıdaki yönerge izin verilmiyor:

```cpp
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

Bir OpenMP yönergesinde yapısal bloğunun olmalıdır en fazla bir sonraki deyimi için geçerlidir.

## <a name="22-conditional-compilation"></a>2.2 koşullu derleme

`_OPENMP` Makro adı ondalık sabit olarak OpenMP uyumlu uygulamaları tarafından tanımlanan *yyyymm*, yıl ve ay onaylı belirtiminin olacak. Bu makro konu olmalıdır bir `#define` veya `#undef` ön işleme yönergesi.

```cpp
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Satıcılar için OpenMP uzantıları tanımlarsanız, bunlar ek önceden tanımlı makrolar belirtebilirsiniz.

## <a name="23-parallel-construct"></a>2.3 parallel yapı

Aşağıdaki yönerge bir bölgesi paralel birçok iş parçacığı tarafından yürütülecek program bir paralel bölgenin tanımlar. Bu yönerge, Paralel yürütme başlatan temel bir yapıdır.

```cpp
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block
```

*Yan tümcesi* aşağıdakilerden biridir:

- `if(` *skaler ifade* `)`
- `private(` *değişken listesi* `)`
- `firstprivate(` *değişken listesi* `)`
- `default(shared | none)`
- `shared(` *değişken listesi* `)`
- `copyin(` *değişken listesi* `)`
- `reduction(` *İşleç* `:` *değişken listesi*  `)`
- `num_threads(` *tamsayı ifadesi* `)`

Bir iş parçacığı için paralel bir yapı alır, aşağıdaki durumlarda biri true ise, bir takım iş parçacıkları oluşturulur:

- Hayır `if` yan tümcesi varsa.
- `if` İfadeyi sıfır dışında bir değeri hesaplar.

Bu iş parçacığı bir iş parçacığı numarası 0 ile takım ana iş parçacığı haline gelir ve takım ana iş parçacığı dahil olmak üzere tüm iş parçacıklarının bölge paralel olarak çalıştırmak. Varsa değerini `if` ifade sıfırsa, bölge sıralanır.

İstenen iş parçacığı sayısını belirlemek için aşağıdaki kurallar sırayla değerlendirilir. Koşulu karşılandığında ilk kural uygulanacak:

1. Varsa `num_threads` yan tümcesi varsa, ardından istenen iş parçacığı sayısını ifade tamsayı değeridir.

1. Varsa `omp_set_num_threads` kitaplığı işlevi çağrılır, ardından istenen iş parçacığı sayısını en yakın zamanda yürütülen çağrısında bağımsız değişken değeridir.

1. Ortam değişkenini `OMP_NUM_THREADS` tanımlanır, bu ortam değişkeninin değerini ise istenen iş parçacığı sayısı.

1. Yukarıdaki yöntemlerin hiçbiri kullanılıyorsa, uygulama tanımlı istenen iş parçacığı sayısı.

Varsa `num_threads` yan tümcesi varsa sonra tarafından istenen iş parçacığı sayısını sürümlereni `omp_set_num_threads` kitaplığı işlevi veya `OMP_NUM_THREADS` yalnızca uygulanan için paralel bölge için ortam değişkeni. Daha sonra paralel bölgeleri bundan etkilenmez.

Paralel bölgenin yürütme iş parçacığı sayısı ayrıca iş parçacığı sayısını yerleştirmenin dinamik ayarına etkin üzerine bağlıdır. Yerleştirmenin dinamik ayarına devre dışıysa, istenen iş parçacığı sayısını paralel bölgenin yürütün. Yerleştirmenin dinamik ayarına etkinse, istenen iş parçacığı sayısı en fazla paralel bölgenin yürütebilir iş parçacığı sayısı olan.

Bir paralel bölgenin iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakıldı ve paralel bölge için istenen iş parçacığı sayısını çalışma zamanı sistemi sağladığınız sayısından fazla karşılaşılırsa, davranıştır programı uygulama tanımlı. Bir uygulama gibi programın yürütülmesini kesme olabilir veya paralel bölgenin serileştirmek.

`omp_set_dynamic` Kitaplığı işlevi ve `OMP_DYNAMIC` ortam değişkeni, etkinleştirmek ve iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakmak için kullanılabilir.

Aslında iş parçacığı herhangi bir zamanda barındıran fiziksel işlemcilerin sayısını uygulama tanımlanır. Takım iş parçacıkları sayısı oluşturulduktan sonra bir paralel bölgenin süresi boyunca sabit kalır. Kullanıcı tarafından açıkça veya otomatik olarak bir paralel bölgenin başka bir çalışma zamanı sistemi tarafından değiştirilebilir.

Dinamik kapsamını paralel bölgenin içinde yer alan ifadeleri her iş parçacığı tarafından yürütülür ve diğer iş parçacıklarından farklı bir yol deyimlerinin her iş parçacığı yürütebilirsiniz. Bir paralel bölgenin dışında sözcük kapsamını karşılaştı yönergeleri yalnız bırakılmış yönergeleri olarak adlandırılır.

Bir paralel bölgenin sonunda örtük bir engel var. Yalnızca ana iş parçacığı ekibin sonunda bir paralel bölgenin, yürütme devam eder.

Bir iş parçacığında bir paralel bölgenin yürütülürken bir ekibin paralel bir başka yapının karşılaşırsa, yeni bir takım oluşturur ve bu yeni takım ana olur. İç içe geçmiş paralel bölgeleri varsayılan olarak serileştirilir. Sonuç olarak, varsayılan olarak, iç içe geçmiş bir paralel bölgenin bir iş parçacığından oluşan bir ekip tarafından yürütülür. Çalışma Zamanı Kitaplığı işlevi'ni kullanarak varsayılan davranış değiştirilebilir `omp_set_nested` veya ortam değişkenini `OMP_NESTED`. Ancak, iç içe geçmiş bir paralel bölgenin yürüten iş parçacığı ekip uygulama tanımlı sayısıdır.

Kısıtlamaları `parallel` yönerge aşağıdaki gibidir:

- En fazla bir `if` yönergesindeki yan tümcesi görünebilir.

- Eğer içinde etkileri herhangi yan olmadığını belirtilmemiş ifade veya `num_threads` ifade oluşur.

- A `throw` yürütülen içinde bir paralel bölgenin içinde aynı yapısal bloğunun dinamik kapsamını sürdürmek yürütme neden ve özel durum oluşturdu aynı iş parçacığı tarafından yakalanmalıdır.

- Yalnızca tek bir `num_threads` yönergesindeki yan tümcesi görünebilir. `num_threads` Deyimi bir paralel bölgenin bağlamı dışında değerlendirilir ve bir pozitif tamsayı değer olarak değerlendirilmesi gerekir.

- Değerlendirilme sırasını `if` ve `num_threads` yan tümceleri belirtilmez.

### <a name="cross-references"></a>Çapraz başvuruları

- `private`, `firstprivate`, `default`, `shared`, `copyin`, ve `reduction` yan tümceleri ([bölümünde 2.7.2](#272-data-sharing-attribute-clauses))
- [OMP_NUM_THREADS](4-2-omp-num-threads.md) ortam değişkeni
- [omp_set_dynamic](3-1-7-omp-set-dynamic-function.md) kitaplığı işlevi
- [Omp_dynamıc](4-3-omp-dynamic.md) ortam değişkeni
- [omp_set_nested](3-1-9-omp-set-nested-function.md) işlevi
- [OMP_NESTED](4-4-omp-nested.md) ortam değişkeni
- [omp_set_num_threads](3-1-1-omp-set-num-threads-function.md) kitaplığı işlevi

## <a name="24-work-sharing-constructs"></a>2.4 iş paylaşım yapıları

Bir iş paylaşımı yapısı karşılaştığınızda takım üyeleri arasında ilişkili deyimin yürütme dağıtır. Yeni iş parçacıkları iş paylaşım yönergelerinin başlatma ve girişi için bir iş paylaşımı yapısı zımni hiçbir engel yok.

Bir dizi iş paylaşım yapıları ve `barrier` karşılaştı yönergeleri her iş parçacığında bir takım için aynı olması gerekir.

Aşağıdaki iş paylaşım yapıları OpenMP tanımlar ve bu yapılar aşağıdaki bölümlerde açıklanmıştır:

- [için](#241-for-construct) yönergesi
- [bölümler](#242-sections-construct) yönergesi
- [tek](#243-single-construct) yönergesi

### <a name="241-for-construct"></a>2.4.1 yapı için

`for` Yönergesi ilişkili döngü yinelemesi paralel olarak yürütülen belirten bir yinelemeli iş paylaşımı yapısı tanımlar. Yinelemeleri `for` döngü bağlar, paralel yapı yürütme takımda zaten iş parçacıkları arasında dağıtılır. Söz dizimi `for` yapısı şu şekildedir:

```cpp
#pragma omp for [clause[[,] clause] ... ] new-line for-loop
```

Yan tümcesi aşağıdakilerden biridir:

- `private(` *değişken listesi* `)`
- `firstprivate(` *değişken listesi* `)`
- `lastprivate(` *değişken listesi* `)`
- `reduction(` *İşleç* `:` *değişken listesi* `)`
- `ordered`
- `schedule(` *kind* [`,` *chunk_size*] `)`
- `nowait`

`for` Yönergesi yerleştirir kısıtlamaları yapısına karşılık gelen `for` döngü. Özellikle, karşılık gelen `for` döngü kurallı şekli olması gerekir:

`for (` *init-expr* `;` *var op mantıksal b* `;` *ıncr-expr* `)`

*init-expr*<br/>
Aşağıdakilerden biri:

- *Varyasyon* = *lb*
- *tamsayı türü var* = *lb*

*incr-expr*<br/>
Aşağıdakilerden biri:

- `++` *var*
- *var* `++`
- `--` *var*
- *var* `--`
- *Varyasyon* `+=` *ıncr*
- *Varyasyon* `-=` *ıncr*
- *Varyasyon* `=` *var* `+` *ıncr*
- *Varyasyon* `=` *ıncr* `+` *var*
- *Varyasyon* `=` *var* `-` *ıncr*

*var*<br/>
Bir işaretli tamsayı değişken. Bu değişken aksi paylaşılabilir değilse, örtük olarak özel süresince yapılan `for`. Gövdesi içinde bu değişkeni değiştirmeyin `for` deyimi. Değişken belirtilmediği sürece `lastprivate`, döngü belirsiz olduğunda değeri.

*mantıksal işlem*<br/>
Aşağıdakilerden biri:

- `<`
- `<=`
- `>`
- `>=`

*lb*, *b*, ve *ıncr*<br>
Tamsayı sabit ifadeleri döngü. Değerlendirilen tüm yan etkileri belirsiz sonuçlar için eşitleme sırasında bu ifadelerin değerlendirme yoktur.

Kurallı biçimi döngüde girişine hesaplanmasını döngü yinelemesi sayısını sağlar. Bu hesaplama türündeki değerlerle yapılan *var*, integral yükseltmeler sonra. Özellikle, değerini *b* `-` *lb* `+` *ıncr* sonuç türü belirsiz olması gösterilemez. Daha fazla, ise *op mantıksal* olduğu `<` veya `<=`, ardından *ıncr-expr* koymasına *var* döngünün her yinelenişinde artırmak için.   Varsa *op mantıksal* olduğu `>` veya `>=`, ardından *ıncr-expr* koymasına *var* döngü her yinelemede daha küçük almak için.

`schedule` Yan tümcesi belirtir nasıl yinelemeleri `for` döngü takım iş parçacıkları arasında bölünür. Belirli bir yinelemeye hangi iş parçacığının yürütür üzerinde bir program doğruluğunu bağımlı olmamalıdır. Değerini *chunk_size*, belirtilmişse, pozitif bir değer ile bir döngü sabit tamsayı ifade olmalıdır. Değerlendirilen tüm yan etkileri belirsiz sonuçlar için eşitleme bu ifadesi değerlendirmesi sırasında yoktur. Zamanlama *tür* aşağıdaki değerlerden biri olabilir:

Tablo 2-1: `schedule` yan tümcesi *tür* değerleri

|||
|-|-|
|static|Zaman `schedule(static,` *chunk_size* `)` belirtilirse, yinelemeleri tarafından belirtilen bir boyut parçalara bölünmüştür *chunk_size*. Öbekleri ettirirsiniz iş parçacığı numarası sırasına göre takım iş parçacıkları statik olarak atanır. Hiçbir *chunk_size* belirtilirse, yineleme alanı ile her bir iş parçacığı için atanmış bir öbek boyutu, yaklaşık olarak eşit olan parçalara bölünür.|
|dinamik|Zaman `schedule(dynamic,` *chunk_size* `)` belirtilirse, yinelemeleri parçalar halinde her içeren bir dizi bölünmüştür *chunk_size* yineleme. Her öbek için bir atama bekleyen iş parçacığı atanır. İş parçacığı öbek tekrar yürütür ve atanacak hiçbir öbekleri kalana kadar sonraki ataması için bekler. Atanacak son öbek yinelemelerin daha küçük bir sayı olabilir. Hiçbir *chunk_size* belirtilirse, varsayılan olarak, 1 olur.|
|Destekli|Zaman `schedule(guided,` *chunk_size* `)` belirtilirse, yinelemeleri öbek boyutları azaltma ile iş parçacıklarının atanır. Bir iş parçacığı kendi atanan öbek yinelemelerin sona erdiğinde, none sol kadar dinamik olarak başka bir öbek atanır. İçin bir *chunk_size* 1, her öbek boyutu yaklaşık iş parçacıklarının sayıya bölünen atanmamış yinelemeler sayısıdır. Bu boyutları 1 neredeyse katlanarak azaltın. İçin bir *chunk_size* değerle *k* 1 ' den büyük boyutları neredeyse katlanarak ye azaltmak *k*son öbek daha az olabilir, ancak *k* yineleme. Hiçbir *chunk_size* belirtilirse, varsayılan olarak, 1 olur.|
|çalışma zamanı|Zaman `schedule(runtime)` belirtilirse, ilgili planlama çalışma zamanına kadar ertelenmiş karar. Zamanlama *tür* ve Öbek boyutu seçilebilir çalışma zamanında ortam değişkenini ayarlayarak `OMP_SCHEDULE`. Bu ortam değişken ayarlanmadıysa, sonuçta elde edilen zamanlama uygulama tarafından tanımlanır. Zaman `schedule(runtime)` belirtilen *chunk_size* belirtilmemelidir.|

Açıkça tanımlanmış olmadığında `schedule` yan tümcesi, varsayılan `schedule` uygulama tarafından tanımlanır.

OpenMP uyumlu bir program, doğru yürütme için belirli bir zamanlamaya göre güvenmemelisiniz. Bir zamanlamaya göre bir program güvenmemelisiniz *tür* aynı zamanlama uygulamalarında Çeşitlemeler olmasını mümkün olduğu için tam olarak yukarıda verilen açıklama uyumludur *tür* arasında farklı derleyicileri. Açıklamalar, belirli bir durum için uygun olan zamanlamayı seçin için kullanılabilir.

`ordered` Yan tümcesi bulunmalıdır ne zaman `ordered` bağlanma yönergeleri `for` oluşturun.

Sonunda örtük bir engel olan bir `for` sürece oluşturmak bir `nowait` yan tümcesi belirtildi.

Kısıtlamaları `for` yönerge aşağıdaki gibidir:

- `for` Döngü yapısal bloğunun olmalıdır ve ayrıca, yürütme ile bitmelidir değil bir `break` deyimi.

- Döngü değerlerini denetim ifadeleri `for` döngü ile ilişkili bir `for` yönergesi takım iş parçacıkları için aynı olması gerekir.

- `for` Döngüsünün yineleme değişkeni işaretli bir tamsayı türü olmalıdır.

- Yalnızca tek bir `schedule` yan tümcesi görüntülenebilir bir `for` yönergesi.

- Yalnızca tek bir `ordered` yan tümcesi görüntülenebilir bir `for` yönergesi.

- Yalnızca tek bir `nowait` yan tümcesi görüntülenebilir bir `for` yönergesi.

- Belirtilmeyen if veya ne sıklıkta içindeki tüm yan etkiler olan *chunk_size*, *lb*, *b*, veya *ıncr* ifadeleri oluşur.

- Değerini *chunk_size* ifade takımın tüm iş parçacıkları için aynı olması gerekir.

#### <a name="cross-references"></a>Çapraz başvuruları

- `private`, `firstprivate`, `lastprivate`, ve `reduction` yan tümceleri ([bölümünde 2.7.2](#272-data-sharing-attribute-clauses))
- [OMP_SCHEDULE](4-1-omp-schedule.md) ortam değişkeni
- [Sıralı](#266-ordered-construct) oluşturun
- [zamanlama](d-using-the-schedule-clause.md) yan tümcesi

### <a name="242-sections-construct"></a>2.4.2 bölümleri yapısı

`sections` Yönergesi, bir takım iş parçacıkları arasında bölünmesi gereken yapıları kümesini belirten bir noniterative iş paylaşımı yapısı tanımlar. Her bölüm, takım bir iş parçacığı tarafından bir kez yürütülür. Söz dizimi `sections` yönerge aşağıdaki gibidir:

```cpp
#pragma omp sections [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block ]
...
}
```

Yan tümcesi aşağıdakilerden biridir:

- `private(` *değişken listesi* `)`
- `firstprivate(` *değişken listesi* `)`
- `lastprivate(` *değişken listesi* `)`
- `reduction(` *İşleç* `:` *değişken listesi*  `)`
- `nowait`

Her bölümde öncesinde bir `section` yönergesi, ancak `section` yönergesi, ilk bölüm için isteğe bağlıdır. `section` Yönergeleri sözcük kapsamı içinde görünmelidir `sections` yönergesi. Sonunda örtük bir engel olan bir `sections` sürece oluşturmak bir `nowait` belirtilir.

Kısıtlamaları `sections` yönerge aşağıdaki gibidir:

- A `section` yönergesi değil sözcük kapsamı dışında görünmelidir `sections` yönergesi.

- Yalnızca tek bir `nowait` yan tümcesi görüntülenebilir bir `sections` yönergesi.

#### <a name="cross-references"></a>Çapraz başvuruları

- `private`, `firstprivate`, `lastprivate`, ve `reduction` yan tümceleri ([bölümünde 2.7.2](#272-data-sharing-attribute-clauses))

### <a name="243-single-construct"></a>2.4.3 single yapı

`single` Yönergesi ilişkili yapısal bloğunun (mutlaka ana iş parçacığı) takım yalnızca bir iş parçacığı tarafından yürütülür belirten bir yapı tanımlar. Söz dizimi `single` yönerge aşağıdaki gibidir:

```cpp
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

Yan tümcesi aşağıdakilerden biridir:

- `private(` *değişken listesi* `)`
- `firstprivate(` *değişken listesi* `)`
- `copyprivate(` *değişken listesi* `)`
- `nowait`

Sonra örtük bir engel var. `single` sürece oluşturmak bir `nowait` yan tümcesi belirtildi.

Kısıtlamaları `single` yönerge aşağıdaki gibidir:

- Yalnızca tek bir `nowait` yan tümcesi görüntülenebilir bir `single` yönergesi.
- `copyprivate` Yan tümcesi olmayan kullanılmalıdır `nowait` yan tümcesi.

#### <a name="cross-references"></a>Çapraz başvuruları

- `private`, `firstprivate`, ve `copyprivate` yan tümceleri ([bölümünde 2.7.2](#272-data-sharing-attribute-clauses))

## <a name="25-combined-parallel-work-sharing-constructs"></a>2.5 birleşik paralel iş paylaşım yapıları

Birleşik paralel iş paylaşım yapıları yalnızca bir iş paylaşımı yapısı sahip bir paralel bölgenin belirtmek için kısayollar içindir. Bu yönergeler semantiği açıkça belirtmekle aynı olan bir `parallel` yönergesi, tek bir iş paylaşımı yapısı tarafından izlenen.

Aşağıdaki bölümlerde, birleşik paralel iş paylaşım yapıları açıklanmaktadır:

- [için paralel](#251-parallel-for-construct) yönergesi
- [Paralel bölümleri](#252-parallel-sections-construct) yönergesi

### <a name="251-parallel-for-construct"></a>2.5.1 yapı için parallel

`parallel for` Yönergesi olduğu için bir kısayol bir `parallel` içeren tek bir bölge `for` yönergesi. Söz dizimi `parallel for` yönerge aşağıdaki gibidir:

```cpp
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Bu yönerge yan tümcesinden sağlayan `parallel` yönergesi ve `for` dışında yönerge `nowait` aynı anlamlara ve kısıtlamalar yan tümcesi. Açıkça belirtmekle aynı semantikler, bir `parallel` yönergesi hemen arkasından bir `for` yönergesi.

#### <a name="cross-references"></a>Çapraz başvuruları

- [Paralel](#23-parallel-construct) yönergesi
- [için](#241-for-construct) yönergesi
- [Veri özniteliği yan tümceleri](#272-data-sharing-attribute-clauses)

### <a name="252-parallel-sections-construct"></a>2.5.2 parallel bölümleri yapısı

`parallel sections` Yönergesi belirtmek için bir kısayol form sağlar bir `parallel` sahip tek bir bölge `sections` yönergesi. Açıkça belirtmekle aynı semantikler, bir `parallel` yönergesi hemen arkasından bir `sections` yönergesi. Söz dizimi `parallel sections` yönerge aşağıdaki gibidir:

```cpp
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

*Yan tümcesi* kabul eden yan tümceleri herhangi birini `parallel` ve `sections` yönergeleri dışında `nowait` yan tümcesi.

#### <a name="cross-references"></a>Çapraz başvuruları

- [Paralel](#23-parallel-construct) yönergesi
- [bölümler](#242-sections-construct) yönergesi

## <a name="26-master-and-synchronization-directives"></a>2.6 ana ve eşitleme yönergeleri

Aşağıdaki bölümlerde açıklanmıştır:

- [Ana](#261-master-construct) oluşturun
- [Kritik](#262-critical-construct) oluşturun
- [engel](#263-barrier-directive) yönergesi
- [atomik](#264-atomic-construct) oluşturun
- [Flush](#265-flush-directive) yönergesi
- [Sıralı](#266-ordered-construct) oluşturun

### <a name="261-master-construct"></a>2.6.1 master yapı

`master` Yönergesi takım ana iş parçacığı tarafından yürütülen bir yapısal bloğunun belirten bir yapı tanımlar. Söz dizimi `master` yönerge aşağıdaki gibidir:

```cpp
#pragma omp master new-linestructured-block
```

Takımın diğer iş parçacıkları ilişkili yapısal bloğunun yürütün yok. Giriş veya çıkış master yapı'zımni hiçbir engel yok.

### <a name="262-critical-construct"></a>2.6.2 critical yapı

`critical` Yönergesi ilişkili yapısal bloğunun yürütülmesi için tek bir iş parçacığı aynı anda kısıtlayan bir yapı tanımlar. Söz dizimi `critical` yönerge aşağıdaki gibidir:

```cpp
#pragma omp critical [(name)]  new-linestructured-block
```

İsteğe bağlı *adı* kritik bölge tanımlamak için kullanılabilir. Kritik bir bölge tanımlamak için kullanılan tanımlayıcıları dış bağlantısı vardır ve etiketler, etiketler, üyeleri ve sıradan tanımlayıcıları tarafından kullanılan ad alanları'ndan ayrı bir ad alanı bulunan.

Bir iş parçacığı bir kritik bölgede (herhangi bir yere program) aynı ada sahip başka bir iş parçacığı yürütülmekte olan kritik bir bölge başında bekler. Adlandırılmamış tüm `critical` yönergeleri aynı belirtilmeyen adına eşleyin.

### <a name="263-barrier-directive"></a>2.6.3 barrier yönergesi

`barrier` Yönergesi, bir takım tüm iş parçacıklarının eşitler. Diğer tüm bu noktaya ulaşıncaya kadar karşılaştığında, takımın her iş parçacığında bekler. Söz dizimi `barrier` yönerge aşağıdaki gibidir:

```cpp
#pragma omp barrier new-line
```

Takım tüm iş parçacıklarının engeli karşılaşılmış sonra takım içindeki her iş parçacığı paralel barrier yönergesi sonra deyim yürütmeye başlar. Çünkü `barrier` yönergesi sözdizimi bir parçası olarak bir C dili deyimi yoksa, bir program içindeki yerleşimi bazı kısıtlamalar vardır. Resmi dilbilgisi hakkında daha fazla bilgi için bkz: [ek C](c-openmp-c-and-cpp-grammar.md). Aşağıdaki örnek bu kısıtlamaları gösterir.

```cpp
/* ERROR - The barrier directive cannot be the immediate
*          substatement of an if statement
*/
if (x!=0)
   #pragma omp barrier
...

/* OK - The barrier directive is enclosed in a
*      compound statement.
*/
if (x!=0) {
   #pragma omp barrier
}
```

### <a name="264-atomic-construct"></a>2.6.4 atomic yapı

`atomic` Yönergesi sağlar belirli bellek konumu birden fazla olasılığını gösterme yerine atomik olarak, bir biçimde güncelleştirilir eşzamanlı iş parçacığı yazma. Söz dizimi `atomic` yönerge aşağıdaki gibidir:

```cpp
#pragma omp atomic new-lineexpression-stmt
```

İfade deyimi aşağıdaki biçimlerden birine sahip olmalıdır:

- *x binop* `=` *ifade*
- *x* `++`
- `++` *x*
- *x* `--`
- `--` *x*

Önceki ifadelerinde:

- *x* skalar türü ile bir lvalue ifadesidir.

- *Expr* skaler türüne sahip ifade ve tarafından belirlenen nesnede başvuru olmayan *x*.

- *binop* aşırı yüklenmiş bir işleç değil ve biri `+`, `*`, `-`, `/`, `&`, `^`, `|`, `<<`, veya `>>`.

Bu uygulama tüm olup yerini alır uygulama tanımlı olmasına rağmen `atomic` yönergeleri ile `critical` aynı benzersiz yönergeleri *adı*, `atomic` izinleri daha iyi bir iyileştirme yönergesi . Genellikle donanım yönergeleri atomik güncelleştirme en az bir ek yükü ile gerçekleştirebilirsiniz.

Yalnızca Yük ve tarafından belirlenen nesnede deposu *x* olan atomik; değerlendirmesi *expr* atomik değildir. Yarış durumları önlemek için tüm güncelleştirmeleri paralel konumunun ile korunması gerektiğini `atomic` yarış koşulları ücretsiz olduğu bilinen dışındaki yönergesi.

Kısıtlamaları `atomic` yönerge aşağıdaki gibidir:

- Tüm atomik başvuruları program boyunca depolama konumuna x uyumlu bir tür olması gerekir.

#### <a name="examples"></a>Örnekler

```cpp
extern float a[], *p = a, b;
/* Protect against races among multiple updates. */
#pragma omp atomic
a[index[i]] += b;
/* Protect against races with updates through a. */
#pragma omp atomic
p[i] -= 1.0f;

extern union {int n; float x;} u;
/* ERROR - References through incompatible types. */
#pragma omp atomic
u.n++;
#pragma omp atomic
u.x -= 1.0f;
```

### <a name="265-flush-directive"></a>2.6.5 flush yönergesi

`flush` Yönergesi, açık veya zımni, uygulama takım tüm iş parçacıklarının belirli nesneleri (aşağıda bellekte belirtilen) tutarlı bir görünümünü sağlamak için gereken bir "iş parçacıkları arası" dizi noktası belirtir. Bu nesneleri başvurmak ifadeleri önceki değerlendirme tamamlandıktan sonraki değerlendirmeler henüz başlamamış anlamına gelir. Örneğin, derleyiciler nesneleri değerlerini kayıtları için bellek geri yüklemeniz gerekir ve donanım yazma arabelleklerini belleğe ve değerlerini bellekten nesneleri yeniden yüklemeniz gerekebilir.

Söz dizimi `flush` yönerge aşağıdaki gibidir:

```cpp
#pragma omp flush [(variable-list)]  new-line
```

Eşitleme iste nesneleri tüm değişkenleri tarafından belirlenebilir sonra değişkenlere isteğe bağlı olarak belirtilebilir. *değişken listesi*. Mevcut bir işaretçi ise *değişken listesi*işaretçi Temizlenen, işaretçiyi nesnenin değil başvuruyor.

A `flush` yönerge olmadan bir *değişken listesi* erişilemeyen nesneleri hariç tüm paylaşılan nesneleri otomatik depolama süresi ile eşitler. (Daha fazla yüke sahip büyük olasılıkla budur bir `flush` ile bir *değişken listesi*.) A `flush` olmadan yönerge bir *değişken listesi* için aşağıdaki yönergeleri gösterilir:

- `barrier`
- Giriş ve çıkış ' `critical`
- Giriş ve çıkış ' `ordered`
- Giriş ve çıkış ' `parallel`
- Çıkın `for`
- Çıkın `sections`
- Çıkın `single`
- Giriş ve çıkış ' `parallel for`
- Giriş ve çıkış ' `parallel sections`

Yönergesi, örtük değil bir `nowait` yan tümcesi varsa. Not edilmesi gereken, `flush` yönergesi için aşağıdakilerden birini kapsanan değil:

- Girdi için `for`
- Giriş veya çıkış ' `master`
- Girdi için `sections`
- Girdi için `single`

Bir geçici nitelikli türe sahip bir nesne değeri erişen bir başvuru yokmuş gibi davranan bir `flush` yönergesi bu nesnede önceki bir dizi noktası belirtme. Bir geçici nitelikli türe sahip bir nesne değerini değiştiren bir başvuru yokmuş gibi davranan bir `flush` yönergesi bu nesnede izleyen bir dizi noktası belirtme.

Çünkü `flush` yönergesi sözdizimi bir parçası olarak bir C dili deyimi yoksa, bir program içindeki yerleşimi bazı kısıtlamalar vardır. Resmi dilbilgisi hakkında daha fazla bilgi için bkz: [ek C](c-openmp-c-and-cpp-grammar.md). Aşağıdaki örnek bu kısıtlamaları gösterir.

```cpp
/* ERROR - The flush directive cannot be the immediate
*          substatement of an if statement.
*/
if (x!=0)
   #pragma omp flush (x)
...

/* OK - The flush directive is enclosed in a
*      compound statement
*/
if (x!=0) {
   #pragma omp flush (x)
}
```

Kısıtlamaları `flush` yönerge aşağıdaki gibidir:

- Belirtilen bir değişken bir `flush` yönergesi değil bir başvuru türü olmalıdır.

### <a name="266-ordered-construct"></a>2.6.6 ordered yapı

Yapısal bloğunun aşağıdaki bir `ordered` yönergesi, yinelemeler yürütülebilir bir sıralı döngüde sırayla yürütülür. Söz dizimi `ordered` yönerge aşağıdaki gibidir:

```cpp
#pragma omp ordered new-linestructured-block
```

Bir `ordered` yönergesi içinde dinamik kapsamı olmalıdır bir `for` veya `parallel for` oluşturun. `for` Veya `parallel for` hangi yönerge `ordered` yapısı bağlamalar olmalıdır bir `ordered` açıklandığı belirtilen yan tümcesi [bölümünde 2.4.1](#241-for-construct). Yürütülmesi bir `for` veya `parallel for` ile oluşturmak bir `ordered` yan tümcesi `ordered` yapıları yürütüldüğünde kesinlikle, bunlar yürütülebilir döngünün bir sıralı yürütme sırada.

Kısıtlamaları `ordered` yönerge aşağıdaki gibidir:

- Yineleme döngüsü ile bir `for` yapısı gerekir değil yürütün aynı ordered yönergesi birden çok kez ve onu birden fazla yürütmeli değil `ordered` yönergesi.

## <a name="27-data-environment"></a>2.7 veri ortamı

Bu bölüm, bir yönerge ve veri ortamı paralel bölgeleri yürütülmesi sırasında şu şekilde denetlemek için birkaç yan tümceleri sunar:

- A `threadprivate` yönergesi dosya kapsam, ad alanı kapsamında veya blok kapsamı statik değişkenleri bir iş parçacığına yerel hale getirmek için sağlanır (aşağıdaki bölüme bakın).

- Paralel veya iş paylaşım yapıları süresi boyunca değişkenlerin paylaşım öznitelikleri denetlemek için yönergeleri belirtilebilir yan tümceleri içinde açıklanmıştır [bölümünde 2.7.2](#272-data-sharing-attribute-clauses).

### <a name="271-threadprivate-directive"></a>2.7.1 threadprivate yönergesi

`threadprivate` Yönergesi yapar adlandırılmış dosya kapsam, ad alanı kapsamında veya belirtilen blok kapsamı statik değişkenler *değişken listesi* özel bir iş parçacığına. *değişken listesi* bir eksik tür olmayan değişkenlerin virgülle ayrılmış listesidir. Söz dizimi `threadprivate` yönerge aşağıdaki gibidir:

```cpp
#pragma omp threadprivate(variable-list) new-line
```

Her bir kopyasını bir `threadprivate` değişkeni başlatılır bir kez bu kopyayı olan ilk başvurunun önce program ve her zamanki şekilde belirtilmeyen bir noktada (yani, ana kopyayı programının bir seri yürütme başlatılması gibi). Bir nesnenin açık bir Başlatıcısı içinde başvuruluyorsa unutmayın bir `threadprivate` değişkenin bir kopyası olan ilk başvurunun önce değişken ve nesnenin değeri değiştirildiğinde, ardından davranıştır belirtilmemiş.

Herhangi bir özel değişken ile başka bir iş parçacığının kopyasını bir iş parçacığı başvurmamalıdır gibi bir `threadprivate` nesne. Seri bölgelerde ve programın ana bölge sırasında başvuruları ana iş parçacığının Kopyala nesnesinin olur.

İlk paralel bölgenin yürütüldükten sonra verileri `threadprivate` nesneleri yalnızca dinamik mekanizması iş parçacıkları, devre dışı bırakıldı ve iş parçacığı sayısı için tüm paralel bölgeleri değişmeden kalır kalıcı hale getirmek için garantisi.

Kısıtlamaları `threadprivate` yönerge aşağıdaki gibidir:

- A `threadprivate` yönergesi dosya kapsam veya isim uzayı kapsam değişkenleri için herhangi bir tanım veya bildirimi dışında görünmelidir ve tüm başvuruları herhangi bir değişken, listesinde sözcüksel olarak gelmelidir.

- Her bir değişken *değişken listesi* , bir `threadprivate` yönergesi dosya veya ad alanı kapsamında bir Değişken bildiriminde sözcüksel olarak yönergesi önündeki dosya veya ad alanı kapsamında başvurmalıdır.

- A `threadprivate` blok kapsamı statik değişkenler yönergesi bir değişkenin kapsamını ve iç içe kapsam içinde değil görünmesi gerekir. Yönergesi, tüm başvuruları herhangi bir değişken sözcüksel olarak kendi listesinde gelmelidir.

- Her bir değişken *değişken listesi* , bir `threadprivate` yönergesi blok kapsamında aynı kapsamda yönergesi sözcüksel olarak önce gelen bir Değişken bildiriminde başvurmalıdır. Değişken bildirimi statik depolama sınıfı tanımlayıcısı kullanmanız gerekir.

- Bir değişken belirtilmişse bir `threadprivate` bir çeviri birimindeki yönergesi içinde belirtilmelidir bir `threadprivate` bunu bildirilen her çeviri biriminde yönergesi.

- A `threadprivate` değişkeni dışında herhangi bir yan tümcesinde değil görünmelidir `copyin`, `copyprivate`, `schedule`, `num_threads`, veya `if` yan tümcesi.

- Adresini bir `threadprivate` değişken adresi sabit değil.

- A `threadprivate` değişken tamamlanmamış bir türü veya bir başvuru türü değil olmalıdır.

- A `threadprivate` açık bir başlatıcı ile bildirilirse, değişken POD harici sınıf türünde bir erişilebilir, açık bir kopya Oluşturucu olması gerekir.

Aşağıdaki örnek nasıl, bir başlatıcı içinde görüntülenen bir değişken değiştirme belirtilmeyen davranışlara neden olabilir ve ayrıca bir yardımcı nesnesi ve bir kopya Oluşturucusu kullanarak bu sorunu önlemek nasıl gösterir.

```cpp
int x = 1;
T a(x);
const T b_aux(x); /* Capture value of x = 1 */
T b(b_aux);
#pragma omp threadprivate(a, b)

void f(int n) {
   x++;
   #pragma omp parallel for
   /* In each thread:
   * Object a is constructed from x (with value 1 or 2?)
   * Object b is copy-constructed from b_aux
   */
   for (int i=0; i<n; i++) {
      g(a, b); /* Value of a is unspecified. */
   }
}
```

#### <a name="cross-references"></a>Çapraz başvuruları

- [dinamik iş parçacıkları](3-1-7-omp-set-dynamic-function.md)
- [Omp_dynamıc](4-3-omp-dynamic.md) ortam değişkeni

### <a name="272-data-sharing-attribute-clauses"></a>2.7.2 veri paylaşım öznitelik yan tümceleri

Birkaç yönergeleri bölge süresi boyunca değişkenlerin paylaşım öznitelikleri kontrol etmesine yan tümceleri kabul edin. Paylaşım öznitelik yan tümceleri yalnızca yan tümcesi görünen yönerge sözcük kapsamını değişkenlerde geçerlidir. Aşağıdaki yan tümceleri tüm tüm yönergeler verilir. Belirli bir yönergesinde geçersiz bir yan tümce listesi yönergesiyle açıklanmıştır.

Bir değişken bir paralel olduğunda görünür veya iş paylaşımı yapısı karşılaşıldığında değişkeni bir paylaşım öznitelik yan tümcesinde belirtilen değil ise veya `threadprivate` yönergesi, ardından değişken paylaşılır. Dinamik kapsamını bir paralel bölgenin içinde bildirilen statik değişkenler paylaşılır. Yığın bellek ayrılmış (örneğin, kullanarak `malloc()` C veya C++ veya `new` c++ işleci) paylaşılır. (Bu bellek işaretçisi ancak, özel veya paylaşılan olabilir.) Dinamik kapsamını bir paralel bölgenin içinde bildirilen otomatik depolama süresine sahip değişkenleri özeldir.

Yan tümceleri çoğunu kabul bir *değişken listesi* bağımsız değişken görülebilir değişkenlerin virgülle ayrılmış listesidir. Bir değişken başvurulan bir şablondan türetilmiş bir tür veri paylaşım öznitelik yan tümce içeriyor ve bu değişken programdaki diğer başvuru vardır, tanımsız bir davranıştır.

Yönerge yan tümceleri içinde görüntülenen tüm değişkenleri görünür olmalıdır. Yan tümceleri yinelenen gerektiğinde, ancak birden fazla yan tümcesinde bir değişken her ikisinde de belirtilmesi dışında hiçbir değişken belirtilebilir bir `firstprivate` ve `lastprivate` yan tümcesi.

Aşağıdaki bölümlerde, veri paylaşım öznitelik yan tümceleri açıklanır:

- [private](#2721-private)
- [firstprivate](#2722-firstprivate)
- [lastprivate](#2723-lastprivate)
- [Paylaşılan](#2724-shared)
- [default](#2725-default)
- [reduction](#2726-reduction)
- [copyin](#2727-copyin)
- [copyprivate](#2728-copyprivate)

#### <a name="2721-private"></a>2.7.2.1 private

`private` Yan tümcesi bir takım içindeki her iş parçacığı için özel olarak değişken listesi değişkenlerinde bildirir. Söz dizimi `private` yan tümcesi şu şekildedir:

```cpp
private(variable-list)
```

Belirtilen değişken davranışını bir `private` yan tümcesi aşağıdaki gibidir. Otomatik depolama süresine sahip yeni bir nesne için yapı ayrılır. Boyutu ve hizalama yeni nesnenin değişken türüne göre belirlenir. Bu ayırma, takım içindeki her iş parçacığı için bir kez gerçekleşir ve sınıf nesnesi için gerekirse bir varsayılan oluşturucu çağrılır. Aksi takdirde ilk belirsiz değerdir.  Değişkeni tarafından başvurulan özgün nesne girişte yapısı için belirsiz bir değere sahip, yapı dinamik kapsam içinde değiştirilmemelidir ve yapı gelen Çıkışta belirsiz bir değere sahip.

Yönerge yapısı sözcük kapsamını, iş parçacığı tarafından ayrılan yeni özel nesne değişkeni başvuruyor.

Kısıtlamaları `private` yan tümcesi aşağıdaki gibidir:

- Belirtilen sınıf türüne sahip bir değişken bir `private` yan tümcesi bir erişilebilir, açık bir varsayılan oluşturucusu olmalıdır.

- Belirtilen bir değişken bir `private` yan tümcesi değil olmalıdır bir `const`-yetkili türü tür bir sınıf sahip olmadığı sürece bir `mutable` üyesi.

- Belirtilen bir değişken bir `private` yan tümcesi eksik bir türü veya bir başvuru türü değil olmalıdır.

- Görünen değişkenleri `reduction` yan tümcesi bir `parallel` yönergesi belirtilemez bir `private` iş paylaşım için paralel yapı bağlayan bir yönerge yan tümcesi.

#### <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

`firstprivate` Yan tümcesi tarafından sağlanan bir işlevselliğin sağlar `private` yan tümcesi. Söz dizimi `firstprivate` yan tümcesi şu şekildedir:

```cpp
firstprivate(variable-list)
```

Belirtilen değişkenler *değişken listesi* sahip `private` açıklandığı yan tümcesi semantiğini [bölümünde 2.7.2.1](#2721-private). Yapı iş parçacığının yürütülmesini önce iş parçacığı başına bir kez yapıldığını gibi oluşturma ve başlatma gerçekleşir. İçin bir `firstprivate` paralel bir yapısı yan tümcesi, ilk yeni özel nesne değeri karşılaştığı iş parçacığı için paralel yapı hemen önce var olan orijinal nesnenin değeri. İçin bir `firstprivate` yan tümcesi bir iş paylaşımı yapısı, ilk iş paylaşımı yapısı yürütülen her bir iş parçacığı için yeni özel nesne değeri aynı karşılaştığı iş parçacığı belirli bir noktaya önce var olan orijinal nesnenin değeri İş paylaşımı yapısı. Ayrıca, C++ nesneler için yeni özel her iş parçacığı için orijinal nesnenin kopya nesnedir.

Kısıtlamaları `firstprivate` yan tümcesi aşağıdaki gibidir:

- Belirtilen bir değişken bir `firstprivate` yan tümcesi eksik bir türü veya bir başvuru türü değil olmalıdır.

- Bir değişken olarak belirtilen sınıf türüyle `firstprivate` erişilebilir, açık bir kopya oluşturucuya sahip olmalıdır.

- Bir paralel bölgenin içinde özel olmayan veya, görünen değişkenleri `reduction` yan tümcesi bir `parallel` yönergesi belirtilemez bir `firstprivate` iş paylaşım için paralel yapı bağlayan bir yönerge yan tümcesi.

#### <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

`lastprivate` Yan tümcesi tarafından sağlanan bir işlevselliğin sağlar `private` yan tümcesi. Söz dizimi `lastprivate` yan tümcesi şu şekildedir:

```cpp
lastprivate(variable-list)
```

Belirtilen değişkenler *değişken listesi* sahip `private` yan tümcesi semantiği. Olduğunda bir `lastprivate` yan tümcesi görünür değeri her bir iş paylaşımı yapısı tanımlayan yönergesinde `lastprivate` ilişkili döngü ya da sözcüksel olarak son bölüm yönergesi, sıralı olarak son yinelenmesinden değişkeninden atanır değişkenin özgün nesne. Bir değer tarafından son yinelemeyi atanmamış değişkenleri `for` veya `parallel for`, veya sözcüksel olarak son Kısım `sections` veya `parallel sections` yönergesi, sonra yapısı belirsiz değerlere sahip olur. Atanmamış alt nesnelerinin, ayrıca sonra yapısı belirsiz bir değere sahip.

Kısıtlamaları `lastprivate` yan tümcesi aşağıdaki gibidir:

- İçin tüm kısıtlamalar `private` uygulayın.

- Bir değişken olarak belirtilen sınıf türüyle `lastprivate` bir erişilebilir, açık kopya atama işleci olması gerekir.

- Bir paralel bölgenin içinde özel olmayan veya, görünen değişkenleri `reduction` yan tümcesi bir `parallel` yönergesi belirtilemez bir `lastprivate` iş paylaşım için paralel yapı bağlayan bir yönerge yan tümcesi.

#### <a name="2724-shared"></a>2.7.2.4 shared

Bu yan tümce görünen değişkenlerini paylaşır *değişken listesi* ekip tüm iş parçacıkları arasında. Bir takım içindeki tüm iş parçacıkları için aynı depolama alanına erişim `shared` değişkenleri.

Söz dizimi `shared` yan tümcesi şu şekildedir:

```cpp
shared(variable-list)
```

#### <a name="2725-default"></a>2.7.2.5 default

`default` Yan tümcesi değişkenlerin veri paylaşımı öznitelikleri etkiler kullanıcıya izin verir. Söz dizimi `default` yan tümcesi şu şekildedir:

```cpp
default(shared | none)
```

Belirtme `default(shared)` açıkça görünür her bir değişken listesi için eşdeğer bir gruba bir `shared` yan tümcesi olduğu sürece `threadprivate` veya `const`-tam. Açık bir olmadığında `default` yan tümcesi, varsayılan davranış, aynı ise `default(shared)` belirtildi.

Belirtme `default(none)` aşağıdakilerden en az birini sözcük ölçüde paralel yapısının bir değişkende yapılan her gönderme true olmasını gerektirir:

- Değişken bir veri paylaşım öznitelik yan tümcesinde başvuru içeren bir yapısı açıkça listelenir.

- Değişkeni içinde paralel yapısı bildirilir.

- Bu değişken `threadprivate`.

- Değişkenin bir `const`-tam türü.

- For döngüsü denetim değişkeniyle değişkendir bir `for` hemen takip eden döngü bir `for` veya `parallel for` yönergesi ve değişken başvurusu, döngünün içinde görünür.

Bir değişken belirterek bir `firstprivate`, `lastprivate`, veya `reduction` kapalı bir yönerge yan tümcesi değişkeni örtük bir başvuru kapsayan bağlamda neden olur. Örtük tür başvurular da, yukarıda listelenen gereksinimlerin tabidir.

Yalnızca tek bir `default` yan tümcesi belirtilebilir bir `parallel` yönergesi.

Bir değişkenin varsayılan kullanarak veri paylaşım öznitelik kılınabilir `private`, `firstprivate`, `lastprivate`, `reduction`, ve `shared` yan tümceleri, aşağıdaki örnekte gösterildiği gibi:

```cpp
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```

#### <a name="2726-reduction"></a>2.7.2.6 reduction

Bu yan tümce görünen skalar değişkenler bir azaltma gerçekleştirir *değişken listesi*, işleciyle *op*. Söz dizimi `reduction` yan tümcesi şu şekildedir:

`reduction(` *OP* `:` *değişken listesi* `)`

Azaltma, genellikle aşağıdaki biçimlerden birini içeren bir ifade için belirtilir:

- *x* `=` *x* *op* *ifade*
- *x* *binop* `=` *ifade*
- *x* `=` *expr* *op* *x* (dışında çıkarma)
- *x* `++`
- `++` *x*
- *x* `--`
- `--` *x*

burada:

*x*<br/>
Azaltma değişkenleri listesinde belirtilen biri.

*değişken listesi*<br/>
Skalar azalma değişkenlerin virgülle ayrılmış listesi.

*ifade*<br/>
Başvuru olmayan skalar türü ile bir ifade *x*.

*OP*<br/>
Aşırı yüklenmiş bir işleç değil ancak biri `+`, `*`, `-`, `&`, `^`, `|`, `&&`, veya `||`.

*binop*<br/>
Aşırı yüklenmiş bir işleç değil ancak biri `+`, `*`, `-`, `&`, `^`, veya `|`.

Aşağıdaki örneğidir `reduction` yan tümcesi:

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

Örnekte gösterildiği gibi bir işleç işlev çağrısı içinde gizlenmiş olabilir. Kullanıcı, belirtilen işlecin dikkatli olmanız gerekir `reduction` yan tümcesi, azaltma işlemi eşleşir.

Ancak sağ işleneninin `||` işleci Bu örnekte yan etkileri varsa, izin ancak dikkatli kullanılmalıdır. Bu bağlamda sıralı döngü yürütülmesi sırasında oluşan değil kesin bir yan etkisi, Paralel yürütme sırasında ortaya çıkabilir. Bu fark, tekrar yürütme sırası belirsiz olduğundan ortaya çıkabilir.

İşleci, azaltma için derleyici tarafından kullanılan tüm özel değişkenler ilk değerini belirlemek ve sonlandırma işleci belirlemek için kullanılır. İşleci açıkça belirtilmesi azaltma deyim yapısı sözcük kapsamı dışında olmasını sağlar. Herhangi bir sayıda `reduction` yönergesindeki yan tümceleri belirtilebilir, ancak bir değişkeni en fazla bir listede görünebilir `reduction` yan tümcesi bu yönergesi.

Her bir değişken özel bir kopyasını *değişken listesi* , her iş parçacığında oluşturulan gibi `private` yan tümcesi kullanılmış. Özel kopyalama işleci göre başlatılır (aşağıdaki tabloya bakın).

Hangi bölgeyi sonunda `reduction` yan tümcesi belirtilmiş, özgün nesne özgün değerine her belirtilen işlecini kullanarak özel kopyaları son değeri ile birleştirilmesinin sonucu yansıtacak şekilde güncelleştirilir. Azaltma işleçleri (çıkarma dışında) tüm ilişkilendirilir ve derleyici serbestçe son değeri hesaplama yeniden ilişkilendirin. (Bir çıkarma azaltma kısmi sonuçları son değer oluşturmak için eklenir.)

Orijinal nesnenin değeri ilk iş parçacığında içeren yan tümcesi ulaşır ve azaltma hesaplama işlemi tamamlanana kadar bunu kalırsa belirsiz hale gelir.  Normalde, hesaplama yapısı sonunda tamamlanmış olacaktır; Ancak, `reduction` yan tümcesi, bir yapı hangi ınternationalized `nowait` olan tüm iş parçacıklarının tamamladığınızdaneminolmakiçinbirengelleeşitlemegerçekleştirilenkadardauygulanan,orijinalnesnenindeğeribelirsizkalır`reduction`yan tümcesi.

Aşağıdaki tabloda, geçerli işleçler ve canonical başlatma değerlerini listeler. Gerçek başlangıç değerini azaltma değişkeni, veri türü ile tutarlı olur.

|İşleç|Başlatma|
|--------------|--------------------|
|`+`|0|
|`*`|1.|
|`-`|0|
|`&`|~0|
|`|`|0|
|`^`|0|
|`&&`|1.|
|`||`|0|

Kısıtlamaları `reduction` yan tümcesi aşağıdaki gibidir:

- Değişken türünü `reduction` işaretçi türleri ve başvuru türleri hiçbir zaman izin verilir, ancak yan tümcesi azaltma işleci için geçerli olmalıdır.

- Belirtilen değişken `reduction` yan tümcesi olmalıdır `const`-tam.

- Bir paralel bölgenin içinde özel olmayan veya, görünen değişkenleri `reduction` yan tümcesi bir `parallel` yönergesi belirtilemez bir `reduction` iş paylaşım için paralel yapı bağlayan bir yönerge yan tümcesi.

   ```cpp
   #pragma omp parallel private(y)
   { /* ERROR - private variable y cannot be specified
                in a reduction clause */
      #pragma omp for reduction(+: y)
      for (i=0; i<n; i++)
         y += b[i];
   }

   /* ERROR - variable x cannot be specified in both
              a shared and a reduction clause */
   #pragma omp parallel for shared(x) reduction(+: x)
   ```

#### <a name="2727-copyin"></a>2.7.2.7 copyin

`copyin` Yan tümcesi için aynı değer atamak için bir mekanizma sağlar `threadprivate` paralel bölgenin yürütme takım içindeki her iş parçacığı için değişkenleri. Belirtilen her bir değişken için bir `copyin` yan tümcesi, takımın ana iş parçacığında bir değişkenin değerini kopyalanır, atama gibi paralel bölge başına iş parçacığı özel kopya tarafından. Söz dizimi `copyin` yan tümcesi şu şekildedir:

```cpp

copyin(
variable-list
)
```

Kısıtlamaları `copyin` yan tümcesi aşağıdaki gibidir:

- Belirtilen değişken `copyin` yan tümcesi bir erişilebilir, açık kopya atama işleci olması gerekir.

- Belirtilen değişken `copyin` yan tümcesi olmalıdır bir `threadprivate` değişkeni.

#### <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

`copyprivate` Yan tümcesi bir değer diğer üyeleri, takımın bir üyesi yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Paylaşılan bir değişken sağlayan (örneğin, farklı bir değişken her düzeyde gerektiren özyineleme) zor olduğunda için paylaşılan bir değişken değeri kullanarak bir alternatiftir. `copyprivate` Yan tümcesi üzerinde yalnızca görüntülenebilir `single` yönergesi.

Söz dizimi `copyprivate` yan tümcesi şu şekildedir:

```cpp

copyprivate(
variable-list
)
```

Etkisini `copyprivate` yan tümcesi değişkeni-listesinde değişkenlerde gerçekleşir ilişkili yapısal bloğunun yürütülmesi sonrasında `single` oluşturmak, önce tüm iş parçacıklarının takım yapısı sonunda engel kaldı. Ardından, her bir değişken için takım diğer iş parçacıklarını *değişken listesi*, bu değişken (atama gibi) karşılık gelen değer ile tanımlanan olur yapısı yürütülen iş parçacığının değişkene yapılandırılmış Blok.

Kısıtlamaları `copyprivate` yan tümcesi aşağıdaki gibidir:

- Belirtilen değişken `copyprivate` yan tümcesi içinde değil görünmelidir bir `private` veya `firstprivate` aynı yan tümcesinde `single` yönergesi.

- Varsa bir `single` yönergesi ile bir `copyprivate` yan tümcesi bir paralel bölgenin içinde dinamik kapsamı ile karşılaşıldı, tüm değişkenleri belirtilen `copyprivate` yan tümcesi kapsayan bağlamda özel olmalıdır.

- Belirtilen değişken `copyprivate` yan tümcesi bir erişilebilir belirsiz kopya atama işleci olması gerekir.

## <a name="28-directive-binding"></a>2.8 yönerge bağlama

Dinamik bağlama yönergeleri şu kurallara uymalıdır:

- `for`, `sections`, `single`, `master`, Ve `barrier` yönergeleri bağlamak için dinamik olarak kapsayan `parallel`, bir bağımsız olarak herhangi bir değeri varsa, `if` üzerinde mevcut yan tümcesi yönergesi. Herhangi bir paralel bölgenin şu anda yürütülmekte olan, yönergeleri ana iş parçacığı yalnızca oluşan bir ekip tarafından yürütülür.

- `ordered` Yönergesi bağlar dinamik olarak kapsayan `for`.

- `atomic` Yönergesi ile ilişkilendirilebilmesi için özel erişim zorlar `atomic` tüm iş parçacıkları, yalnızca geçerli takım yönergeleri.

- `critical` Yönergesi ile ilişkilendirilebilmesi için özel erişim zorlar `critical` tüm iş parçacıkları, yalnızca geçerli takım yönergeleri.

- Bir yönerge hiçbir zaman en yakın dışında herhangi bir yönerge dinamik olarak adlarınıza bağlayabileceğiniz kapsayan `parallel`.

## <a name="29-directive-nesting"></a>2.9 yönerge iç içe koyma

Dinamik iç içe geçmiş yönergeleri şu kurallara uymalıdır:

- A `parallel` dinamik olarak iç yönerge `parallel` yalnızca geçerli iş parçacığı oluşur, yeni bir takım paralellik iç içe geçmiş sürece etkin mantıksal olarak oluşturur.

- `for`, `sections`, ve `single` aynı bağlama yönergeleri `parallel` diğer içinde iç içe geçmiş izin verilmez.

- `critical` aynı ada sahip yönergeleri, diğer içinde iç içe geçmiş izin verilmez. Bu kısıtlama kilitlenmeyi önlemek için yeterli olmadığını unutmayın.

- `for`, `sections`, ve `single` yönergeleri dinamik kapsam izin olmayan `critical`, `ordered`, ve `master` yönergeleri aynı bağlarsanız bölgeleri `parallel` bölgeleri olarak.

- `barrier` yönergeleri dinamik kapsam izin olmayan `for`, `ordered`, `sections`, `single`, `master`, ve `critical` yönergeleri aynı bağlarsanız bölgeleri `parallel` bölgeleri olarak.

- `master` yönergeleri dinamik kapsam izin olmayan `for`, `sections`, ve `single` yönergeleri, `master` yönergeleri bağlamak için aynı `parallel` iş paylaşım yönergelerinin olarak.

- `ordered` yönergeleri izin verilmiyor dinamik kapsam `critical` yönergeleri aynı bağlarsanız bölgeleri `parallel` bölgeleri olarak.

- Dinamik olarak bir paralel bölgenin içinde çalıştırıldığında verilen tüm yönergesi, bir paralel bölgenin dışında yürütüldüğünde de izin verilir. Dinamik olarak bir kullanıcı tarafından belirtilen paralel bölgenin dışında yürütüldüğünde yönergesi yalnızca ana iş parçacığı oluşan bir ekip tarafından yürütülür.
