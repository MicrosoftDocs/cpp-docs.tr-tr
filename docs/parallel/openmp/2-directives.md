---
title: 2. Yönergeler
ms.date: 01/18/2019
ms.assetid: d1a69374-6c03-45fb-8c86-e91cea8adae8
ms.openlocfilehash: 125d2d83b277e62d007e3a208e426ea717d52790
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417091"
---
# <a name="2-directives"></a>2. Yönergeler

Yönergeler, C ve C++ standartları içinde tanımlanan `#pragma` yönergeleri temel alır.  OpenMP C ve C++ API 'yi destekleyen derleyiciler, tüm OpenMP derleyicisi yönergelerinin yorumunu etkinleştiren ve yorumlamayı sağlayan bir komut satırı seçeneği içerir.

## <a name="21-directive-format"></a>2,1 yönerge biçimi

Bir OpenMP yönergesinin sözdizimi, [Ek C](c-openmp-c-and-cpp-grammar.md)'de dilbilgisinde ve resmi olarak aşağıdaki gibi belirtilmiştir:

```cpp
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

Her yönerge, aynı ada sahip diğer (OpenMP veya satıcı uzantıları ile OpenMP) pragma yönergeleriyle çakışma olasılığını azaltmak için `#pragma omp`ile başlar. Yönergesinin geri kalanı, derleyici yönergelerinin C ve C++ standartlarının kurallarını izler. Özellikle, `#`önce ve sonra beyaz boşluk kullanılabilir ve bazen bir yönergedeki sözcükleri ayırmak için beyaz boşluk kullanılması gerekir. `#pragma omp` izleyen ön işleme belirteçleri, makro değiştirme 'ye tabidir.

Yönergeler büyük/küçük harfe duyarlıdır. Yan tümcelerin yönergeler bölümünde görünme sırası önemli değildir. Yönergelerden yan tümceler gerektiğinde tekrarlanabilir ve her bir yan tümcenin açıklamasında listelenen kısıtlamalara tabidir. Bir yan tümcesinde *değişken listesi* görünürse, yalnızca değişkenleri belirtmelidir. Her yönerge için yalnızca bir *Yönerge adı* belirtilebilir.  Örneğin, aşağıdaki yönergeye izin verilmez:

```cpp
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

Bir OpenMP yönergesi, yapılandırılmış bir blok olması gereken en fazla bir başarılı ifade için geçerlidir.

## <a name="22-conditional-compilation"></a>2,2 Koşullu derleme

`_OPENMP` makro adı,, onaylanan belirtiminin yılı ve ayı olacak şekilde, OpenMP uyumlu uygulamalar tarafından ondalık sabit *yyyymm*olarak tanımlanır. Bu makro `#define` veya `#undef` ön işleme yönergesinin konusu olmamalıdır.

```cpp
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Satıcılar, OpenMP 'ye uzantılar tanımladıklarında, önceden tanımlanmış ek makrolar belirtebilir.

## <a name="23-parallel-construct"></a>2,3 paralel yapı

Aşağıdaki yönerge, paralel olarak birçok iş parçacığı tarafından yürütülecek programın bir bölgesi olan paralel bölgeyi tanımlar. Bu yönerge, paralel yürütmeyi Başlatan temel yapısıdır.

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
- `reduction(` *işleci* *değişken listesi* `:``)`
- `num_threads(` *tamsayı ifadesi* `)`

Bir iş parçacığı bir paralel yapıyı aldığında, aşağıdaki durumlardan biri geçerliyse iş parçacığı grubu oluşturulur:

- `if` yan tümce yok.
- `if` ifadesi sıfır dışında bir değer olarak değerlendirilir.

Bu iş parçacığı, iş parçacığı sayısı 0 ve takımda ana iş parçacığı dahil tüm iş parçacıkları olan ekibin ana iş parçacığı haline gelir. `if` ifadesinin değeri sıfırsa bölge serileştirilir.

İstenen iş parçacığı sayısını öğrenmek için aşağıdaki kurallar sırayla kabul edilir. Koşulu karşılandığında ilk kural uygulanır:

1. `num_threads` yan tümcesi varsa, tamsayı ifadesinin değeri istenen iş parçacığı sayısıdır.

1. `omp_set_num_threads` Kitaplığı işlevi çağrılırsa, en son yürütülen çağrıda bağımsız değişkenin değeri, istenen iş parçacığı sayısıdır.

1. Ortam değişkeni `OMP_NUM_THREADS` tanımlanmışsa, bu ortam değişkeninin değeri istenen iş parçacığı sayısıdır.

1. Yukarıdaki yöntemlerin hiçbiri kullanılmazsa, istenen iş parçacığı sayısı uygulama tanımlı olur.

`num_threads` yan tümcesi mevcutsa, `omp_set_num_threads` Kitaplığı işlevi veya `OMP_NUM_THREADS` ortam değişkeni tarafından istenen iş parçacığı sayısının yalnızca uygulandığı paralel bölge için yerini alır. Daha sonra paralel bölgeler bundan etkilenmez.

Paralel bölgeyi çalıştıran iş parçacıklarının sayısı Ayrıca, iş parçacığı sayısının dinamik ayarlamasının etkin olup olmamasına bağlıdır. Dinamik ayarlama devre dışıysa, istenen iş parçacığı sayısı paralel bölgeyi yürütür. Dinamik ayarlama etkinse, istenen iş parçacığı sayısı, paralel bölgeyi yürütebilecek iş parçacığı sayısı üst sınırıdır.

İş parçacığı sayısı için dinamik ayarlama devre dışı bırakıldığı ve paralel bölge için istenen iş parçacığı sayısı, çalışma zamanı sisteminin sağlayabileceği sayıdan daha fazla olduğu için bir paralel bölge ile karşılaşılırsa, programın davranışı uygulama tanımlı. Uygulama, örneğin programın yürütülmesini kesintiye uğratan veya paralel bölgeyi seri hale getirebilecek olabilir.

`omp_set_dynamic` Kitaplığı işlevi ve `OMP_DYNAMIC` ortam değişkeni, iş parçacığı sayısını dinamik olarak ayarlamayı etkinleştirmek ve devre dışı bırakmak için kullanılabilir.

Belirli bir zamanda iş parçacıklarını barındıran fiziksel işlemcilerin sayısı uygulama tanımlı ' dır. Oluşturulduktan sonra ekipteki iş parçacığı sayısı, bu paralel bölgenin süresi boyunca sabit kalır. Kullanıcı tarafından açık olarak veya bir paralel bölgeden diğerine otomatik olarak değiştirilebilir.

Paralel bölgenin dinamik kapsamı içinde yer alan deyimler her bir iş parçacığı tarafından yürütülür ve her bir iş parçacığı diğer iş parçacıklarından farklı olan deyimlerin yolunu yürütebilirler. Paralel bir bölgenin sözcük kapsamı dışında karşılaşılan yönergeler yalnız bırakılmış yönergeler olarak adlandırılır.

Paralel bölgenin sonunda örtük bir engel vardır. Yalnızca ekibin ana iş parçacığı, bir paralel bölgenin sonunda yürütmeye devam eder.

Bir takımda bir paralel bölgeyi yürüten bir iş parçacığı başka bir paralel yapı ile karşılaştığında, yeni bir takım oluşturur ve bu yeni ekibin ana kopyası olur. İç içe paralel bölgeler varsayılan olarak serileştirilir. Sonuç olarak, varsayılan olarak, iç içe bir paralel bölge, bir iş parçacığından oluşan bir takım tarafından yürütülür. Varsayılan davranış, çalışma zamanı kitaplığı işlevi `omp_set_nested` ya da ortam değişkeni `OMP_NESTED`kullanılarak değiştirilebilir. Ancak, iç içe bir paralel bölgeyi çalıştıran bir ekipteki iş parçacığı sayısı uygulama tanımlı ' dır.

`parallel` yönergesine yönelik kısıtlamalar aşağıdaki gibidir:

- En çok, yönergede bir `if` yan tümcesi görünebilir.

- İf ifadesi veya `num_threads` ifadesinin içinde herhangi bir yan etkilerden oluşan bir durum belirlenmediğini belirtir.

- Paralel bir bölgenin içinde yürütülen bir `throw`, yürütmenin aynı yapısal bloğun dinamik kapsamı içinde sürdürülmesine neden olmalıdır ve özel durumu oluşturan aynı iş parçacığı tarafından yakalanmalıdır.

- Yönergede yalnızca tek bir `num_threads` yan tümcesi görünebilir. `num_threads` ifadesi paralel bölgenin bağlamı dışında değerlendirilir ve pozitif bir tamsayı değeri olarak değerlendirilmelidir.

- `if` ve `num_threads` yan tümcelerinin değerlendirilme sırası belirtilmemiş.

### <a name="cross-references"></a>Çapraz başvurular

- `private`, `firstprivate`, `default`, `shared`, `copyin`ve `reduction` yan tümceleri ([Bölüm 2.7.2](#272-data-sharing-attribute-clauses))
- [Omp_num_threads](4-environment-variables.md#42-omp_num_threads) ortam değişkeni
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) Kitaplığı işlevi
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) ortam değişkeni
- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) işlevi
- [OMP_NESTED](4-environment-variables.md#44-omp_nested) ortam değişkeni
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) Kitaplığı işlevi

## <a name="24-work-sharing-constructs"></a>2,4 iş paylaşımı yapıları

Bir iş paylaşımı yapısı, ilişkili deyimin yürütmesini, bu takımın karşılaştığı ekip üyeleri arasında dağıtır. İş paylaşım yönergeleri yeni iş parçacıkları başlatamaz ve bir iş paylaşımı yapısına giriş üzerinde örtük bir engel yoktur.

Çalışma paylaşımı yapıları ve `barrier` yönergelerinin sırası, bir takımda bulunan her iş parçacığı için aynı olmalıdır.

OpenMP aşağıdaki iş paylaşımı yapılarını tanımlar ve bu yapılar aşağıdaki bölümlerde açıklanmıştır:

- [for](#241-for-construct) yönergesi
- [sections](#242-sections-construct) yönergesi
- [tek](#243-single-construct) yönerge

### <a name="241-for-construct"></a>2.4.1 for yapısı

`for` yönergesi, ilişkili döngünün yinelemelerinin paralel olarak yürütüleceğini belirten yinelemeli bir iş paylaşımı yapısı tanımlar. `for` döngüsünün yinelemelerini, bağlandığı paralel yapıyı yürüten ekipte zaten mevcut olan iş parçacıkları arasında dağıtılır. `for` yapısının sözdizimi aşağıdaki gibidir:

```cpp
#pragma omp for [clause[[,] clause] ... ] new-line for-loop
```

Yan tümcesi aşağıdakilerden biridir:

- `private(` *değişken listesi* `)`
- `firstprivate(` *değişken listesi* `)`
- `lastprivate(` *değişken listesi* `)`
- `reduction(` *işleci* *değişken listesi* `:` `)`
- `ordered`
- `schedule(` *türü* [`,` *chunk_size*] `)`
- `nowait`

`for` yönergesi karşılık gelen `for` döngüsünün yapısına kısıtlamalar koyar. Özellikle, karşılık gelen `for` döngüsünün kurallı şekli olmalıdır:

`for (` *init-expr* `;` *var mantıksal-op b* `;` *incr-Expr* `)`

*init-expr*<br/>
Aşağıdakilerden biri:

- *var* = *lb*
- *tamsayı türü var* = *lb*

*incr-Expr*<br/>
Aşağıdakilerden biri:

- `++` *var*
- *var* `++`
- `--` *var*
- *var* `--`
- *var* `+=` *incr*
- *var* `-=` *incr*
- *var* `=` *var* `+` *incr*
- *var* `=` *incr* `+` *var*
- *var* `=` *var* `-` *incr*

*var*<br/>
İşaretli bir tamsayı değişkeni. Bu değişken başka bir şekilde paylaşılırsa, `for`süresince özel olarak özel olarak yapılır. `for` ifadesinin gövdesi içinde bu değişkeni değiştirmeyin. Değişken belirtilmediği takdirde `lastprivate`, döngüden sonraki değeri belirsiz olur.

*mantıksal işlem*<br/>
Aşağıdakilerden biri:

- `<`
- `<=`
- `>`
- `>=`

*lb*, *b*ve *incr*<br>
Sabit tamsayı ifadelerini döngüye sokun. Bu ifadelerin değerlendirmesi sırasında eşitleme yoktur, bu nedenle değerlendirilen yan etkiler belirsiz sonuçlar üretir.

Kurallı form, döngü yineleme sayısının döngüye girişte hesaplanmasını sağlar. Bu hesaplama, integral promosyonları sonrasında *var*türündeki değerlerle yapılır. Özellikle, *b* `-` *lb* `+` *incr* değeri bu tür içinde gösterilemez, sonuç belirsiz olur. Ayrıca, *mantıksal op* `<` veya `<=`ise, *incr-Expr* , döngünün her yinelemesinde *var* olmasına neden olmalıdır.   *Mantıksal op* `>` veya `>=`ise, *incr-Expr* , döngünün her yinelemesinde *var* olmasının daha küçük olmasına neden olmalıdır.

`schedule` yan tümcesi, `for` döngüsünün yinelemelerinin takım iş parçacıkları arasında nasıl bölüneceğini belirtir. Bir programın doğruluğu, belirli bir yinelemeyi yürüten iş parçacığına bağlı olmamalıdır. *Chunk_size*değeri, belirtilmişse pozitif bir değer içeren bir döngü sabit tamsayı ifadesi olmalıdır. Bu ifadenin değerlendirmesi sırasında eşitleme yoktur, bu nedenle değerlendirilen yan etkiler belirsiz sonuçlar üretir. Zamanlama *türü* aşağıdaki değerlerden biri olabilir:

Tablo 2-1: `schedule` yan tümce *türü* değerleri

|||
|-|-|
|static|`schedule(static,` *chunk_size* `)` belirtildiğinde, yinelemeler *chunk_size*tarafından belirtilen boyuttaki parçalara bölünür. Parçalar, iş parçacığı numarası sırasına göre bir kez, takım iş parçacığına bir hepsini bir kez daha kez atanır. *Chunk_size* belirtilmediğinde, yineleme alanı her iş parçacığına bir öbek atandığında, boyutu yaklaşık olarak eşit olan parçalara bölünür.|
|dinamik|`schedule(dynamic,` *chunk_size* `)` belirtildiğinde, yinelemeler, her biri *chunk_size* yineleme içeren bir dizi öbekte ayrılır. Her bir öbek, bir atamayı bekleyen bir iş parçacığına atanır. İş parçacığı, yineleme öbekini yürütür ve sonra bir öbek atanıncaya kadar bir sonraki atamaya bekler. Atanacak son öbekte daha az sayıda yineleme olabilir. *Chunk_size* belirtilmediğinde, varsayılan olarak 1 olur.|
|temelli|`schedule(guided,` *chunk_size* `)` belirtildiğinde, yinelemeler, azalan boyutlara sahip öbeklerdeki iş parçacıklarına atanır. Bir iş parçacığı atanmış yineleme öbeğini bitirdiğinde, hiçbiri ayrılana kadar dinamik olarak başka bir öbek atanır. 1 *chunk_size* için, her öbekin boyutu, iş parçacığı sayısına bölünen atanmamış yineleme sayısının yaklaşık olarak sayısıdır. Bu boyutlar neredeyse üstel olarak 1 ' i azaltır. *K* değeri 1 ' den büyük olan bir *chunk_size* için, en son öbekin *k* yinelemeden daha az yineleme olması dışında, Boyutlar neredeyse katlanarak *k*olarak azalır. *Chunk_size* belirtilmediğinde, varsayılan olarak 1 olur.|
|çalışma zamanı|`schedule(runtime)` belirtildiğinde, zamanlamaya yönelik karar, çalışma zamanına kadar ertelenir. `OMP_SCHEDULE`ortam değişkeni ayarlanarak öbeklerin zamanlama *türü* ve boyutu çalışma zamanında seçilebilir. Bu ortam değişkeni ayarlanmamışsa, sonuçta elde edilen zamanlama uygulama tanımlı olur. `schedule(runtime)` belirtildiğinde *chunk_size* belirtilmemelidir.|

Açıkça tanımlanmış bir `schedule` yan tümcesinin yokluğu altında, varsayılan `schedule` uygulama tanımlı olur.

OpenMP uyumlu bir program doğru yürütme için belirli bir zamanlamaya dayanmamalıdır. Bir programın, farklı derleyicilerde aynı zamanlama *türünün* uygulamalarında çeşitliliğe sahip olması mümkün olduğundan, yukarıda verilen açıklamaya uygun bir zamanlama *türüne* güvenmemelidir. Açıklamalar, belirli bir durum için uygun zamanlamayı seçmek üzere kullanılabilir.

`ordered` yönergeleri `for` yapısına bağladığı zaman `ordered` yan tümcesi bulunmalıdır.

Bir `nowait` yan tümcesi belirtilmediği takdirde `for` yapısının sonunda örtük bir engel vardır.

`for` yönergesine yönelik kısıtlamalar aşağıdaki gibidir:

- `for` döngüsü yapısal bir blok olmalıdır ve ayrıca, yürütülmesi bir `break` ifadesiyle sonlandırılmamalıdır.

- Bir `for` yönergesiyle ilişkili `for` döngüsünün döngü denetim ifadelerinin değerleri, ekipteki tüm iş parçacıkları için aynı olmalıdır.

- `for` döngüsü yineleme değişkeni, işaretli bir tamsayı türüne sahip olmalıdır.

- `for` yönergesinde yalnızca tek bir `schedule` yan tümcesi görünebilir.

- `for` yönergesinde yalnızca tek bir `ordered` yan tümcesi görünebilir.

- `for` yönergesinde yalnızca tek bir `nowait` yan tümcesi görünebilir.

- *Chunk_size*, *lb*, *b*veya *incr* ifadeleri içinde herhangi bir yan etkilerin ne zaman oluşması veya ne sıklıkla oluşması belirtilmemiş olur.

- *Chunk_size* ifadesinin değeri, ekipteki tüm iş parçacıkları için aynı olmalıdır.

#### <a name="cross-references"></a>Çapraz başvurular

- `private`, `firstprivate`, `lastprivate`ve `reduction` yan tümceleri ([Bölüm 2.7.2](#272-data-sharing-attribute-clauses))
- [Omp_schedule](4-environment-variables.md#41-omp_schedule) ortam değişkeni
- [sıralı](#266-ordered-construct) yapı
- [Schedule](d-using-the-schedule-clause.md) yan tümcesi

### <a name="242-sections-construct"></a>2.4.2 sections bölüm yapısı

`sections` yönergesi, bir ekipteki iş parçacıkları arasında bölünecek bir yapı kümesi belirten yinelenmeyen bir iş paylaşımı yapısını tanımlar. Her bölüm ekipteki bir iş parçacığı tarafından bir kez yürütülür. `sections` yönergesinin sözdizimi şöyledir:

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
- `reduction(` *işleci* *değişken listesi* `:``)`
- `nowait`

Her bölümün önünde bir `section` yönergesi bulunur, ancak `section` yönergesi ilk bölüm için isteğe bağlıdır. `section` yönergeleri `sections` yönergesinin sözcük temelli kapsamı içinde görünmelidir. Bir `nowait` belirtilmedikçe `sections` yapının sonunda örtülü bir engel vardır.

`sections` yönergesine yönelik kısıtlamalar aşağıdaki gibidir:

- `section` yönergesi, `sections` yönergesinin sözcük temelli kapsamı dışında görünmemelidir.

- `sections` yönergesinde yalnızca tek bir `nowait` yan tümcesi görünebilir.

#### <a name="cross-references"></a>Çapraz başvurular

- `private`, `firstprivate`, `lastprivate`ve `reduction` yan tümceleri ([Bölüm 2.7.2](#272-data-sharing-attribute-clauses))

### <a name="243-single-construct"></a>2.4.3 tek yapı

`single` yönergesi, ilişkili yapılandırılmış bloğun takımda yalnızca bir iş parçacığı tarafından yürütüldüğünü belirten bir yapıyı tanımlar (ana iş parçacığı olması gerekmez). `single` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

Yan tümcesi aşağıdakilerden biridir:

- `private(` *değişken listesi* `)`
- `firstprivate(` *değişken listesi* `)`
- `copyprivate(` *değişken listesi* `)`
- `nowait`

Bir `nowait` yan tümcesi belirtilmedikçe `single` oluşturulduktan sonra örtülü bir engel vardır.

`single` yönergesine yönelik kısıtlamalar aşağıdaki gibidir:

- `single` yönergesinde yalnızca tek bir `nowait` yan tümcesi görünebilir.
- `copyprivate` yan tümcesi `nowait` yan tümcesiyle kullanılmamalıdır.

#### <a name="cross-references"></a>Çapraz başvurular

- `private`, `firstprivate`ve `copyprivate` yan tümceleri ([Bölüm 2.7.2](#272-data-sharing-attribute-clauses))

## <a name="25-combined-parallel-work-sharing-constructs"></a>2,5 Birleşik paralel iş paylaşım yapıları

Birleşik paralel iş paylaşımı yapıları, yalnızca bir iş paylaşımı yapısına sahip bir paralel bölge belirtmeye yönelik kısayollardır. Bu yönergelerin semantiği, açıkça bir `parallel` yönergesini ve ardından tek bir iş paylaşımı yapısını belirtmekle aynıdır.

Aşağıdaki bölümlerde Birleşik paralel iş paylaşımı yapıları açıklanır:

- [for yönergesi için Parallel](#251-parallel-for-construct)
- [Parallel sections](#252-parallel-sections-construct) yönergesi

### <a name="251-parallel-for-construct"></a>Yapı için 2.5.1 paralel

`parallel for` yönergesi, yalnızca tek bir `for` yönergesini içeren bir `parallel` bölgesinin kısayoludur. `parallel for` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Bu yönerge, `parallel` yönergesinin tüm yan tümcelerini ve `for` yönergesini, aynı anlamlara ve kısıtlamalara sahip `nowait` yan tümcesi haricinde sağlar. Semantiği, doğrudan bir `for` yönergesi tarafından izlenen bir `parallel` yönergesini açıkça belirtmekle aynıdır.

#### <a name="cross-references"></a>Çapraz başvurular

- [Parallel](#23-parallel-construct) yönergesi
- [for](#241-for-construct) yönergesi
- [Veri özniteliği yan tümceleri](#272-data-sharing-attribute-clauses)

### <a name="252-parallel-sections-construct"></a>2.5.2 Parallel sections paralel bölüm yapısı

`parallel sections` yönergesi, yalnızca tek bir `sections` yönergesine sahip bir `parallel` bölgesi belirtmek için kısayol formu sağlar. Semantiği, doğrudan bir `sections` yönergesi tarafından izlenen bir `parallel` yönergesini açıkça belirtmekle aynıdır. `parallel sections` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

*Yan tümcesi* , `nowait` yan tümcesi hariç `parallel` ve `sections` yönergeleri tarafından kabul edilen yan tümcelerden biri olabilir.

#### <a name="cross-references"></a>Çapraz başvurular

- [Parallel](#23-parallel-construct) yönergesi
- [sections](#242-sections-construct) yönergesi

## <a name="26-master-and-synchronization-directives"></a>2,6 ana ve eşitleme yönergeleri

Aşağıdaki bölümlerde şunlar açıklanır:

- [ana](#261-master-construct) yapı
- [kritik](#262-critical-construct) yapı
- [engel](#263-barrier-directive) yönergesi
- [atomik](#264-atomic-construct) yapı
- [Flush](#265-flush-directive) yönergesi
- [sıralı](#266-ordered-construct) yapı

### <a name="261-master-construct"></a>2.6.1 ana yapısı

`master` yönergesi, ekibin ana iş parçacığı tarafından yürütülen yapısal bir blok belirten bir yapıyı tanımlar. `master` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp master new-linestructured-block
```

Ekipteki diğer iş parçacıkları ilişkili yapısal bloğu yürütmez. Ana yapıdan giriş veya çıkış yapmadan önce örtük bir engel yoktur.

### <a name="262-critical-construct"></a>2.6.2 Critical kritik yapı

`critical` yönergesi, ilişkili yapılandırılmış bloğunun yürütülmesini aynı anda tek bir iş parçacığına kısıtlayan bir yapıyı tanımlar. `critical` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp critical [(name)]  new-linestructured-block
```

Kritik bölgeyi tanımlamak için, isteğe bağlı bir *ad* kullanılabilir. Kritik bir bölgeyi tanımlamak için kullanılan tanımlayıcılar dış bağlantıya sahiptir ve Etiketler, Etiketler, Üyeler ve normal tanımlayıcılar tarafından kullanılan ad alanlarından ayrı bir ad alanı içinde bulunur.

İş parçacığı, başka bir iş parçacığı aynı ada sahip bir kritik bölge (programda herhangi bir yerde) yürütülene kadar kritik bir bölgenin başlangıcında bekler. Adlandırılmamış `critical` tüm yönergeler aynı belirtilmemiş ada eşlenir.

### <a name="263-barrier-directive"></a>2.6.3 engel yönergesi

`barrier` yönergesi, bir ekipteki tüm iş parçacıklarını eşitler. Bu sorunla karşılaşıldığında, ekipteki her iş parçacığı tüm diğerleri bu noktaya ulaşana kadar bekler. `barrier` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp barrier new-line
```

Ekipteki tüm iş parçacıkları engelyle karşılaşdıktan sonra, ekipteki her iş parçacığı, bariyer yönergesinin paralel olan deyimlerini yürütmeye başlar. `barrier` yönergesinin sözdiziminin bir parçası olarak bir C dili bildirisi olmadığından, bir program içindeki yerleşimi üzerinde bazı kısıtlamalar vardır. Biçimsel dilbilgisi hakkında daha fazla bilgi için bkz. [Ek C](c-openmp-c-and-cpp-grammar.md). Aşağıdaki örnekte bu kısıtlamalar gösterilmektedir.

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

### <a name="264-atomic-construct"></a>2.6.4 atomik yapı

`atomic` yönergesi, belirli bir bellek konumunun, birden çok, eşzamanlı yazma iş parçacığı olasılığa karşı ortaya çıkarmak yerine, otomatik olarak güncelleştirilmesini sağlar. `atomic` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp atomic new-lineexpression-stmt
```

İfade deyimi aşağıdaki formlardan birine sahip olmalıdır:

- *x binop* `=` *Expr*
- *x* `++`
- `++` *x*
- *x* `--`
- `--` *x*

Önceki ifadelerde:

- *x* skaler türü olan bir lvalue deyimidir.

- *Expr* skaler türü olan bir ifadedir ve *x*tarafından belirlenen nesneye başvurmuyor.

- *binop* , aşırı yüklenmiş bir operatör değildir ve `+`, `*`, `-`, `/`, `&`, `^`, `|`, `<<`veya `>>`biridir.

Uygulama tanımlı olsa da, bir uygulamanın tüm `atomic` yönergelerini aynı benzersiz *ada*sahip `critical` yönergeleriyle değiştirmesinin yanı da `atomic` yönergesi daha iyi iyileştirmeye izin verir. Genellikle atomik güncelleştirmeyi en az ek yük ile gerçekleştirebileceğiniz donanım yönergeleri sağlanır.

Yalnızca *x* tarafından atanan nesnenin yükü ve deposu atomik; *ifadenin* değerlendirmesi atomik değildir. Yarış koşullarından kaçınmak için, bu konumdaki tüm güncelleştirmelerin, yarış koşullarından muaf olmadığı bilinenler hariç `atomic` yönergesiyle korunması gerekir.

`atomic` yönergesine yönelik kısıtlamalar aşağıdaki gibidir:

- Program genelinde x depolama konumu için tüm Atomik başvuruların, uyumlu bir türü olması gerekir.

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

### <a name="265-flush-directive"></a>2.6.5 Flush yönergesi

Açık veya zımni `flush` yönergesi, bir ekipteki tüm iş parçacıklarının bellekte bulunan belirli nesnelerin (aşağıda belirtilen) tutarlı bir görünümüne sahip olduğundan emin olmak için uygulamanın gerekli olduğu bir "çapraz iş parçacığı" sıra noktasını belirtir. Bu, bu nesnelere başvuran ifadelerin önceki değerlendirmelerinin tamamlandığını ve sonraki değerlendirmeler henüz başlamamasıdır. Örneğin, derleyicilerin nesnelerin değerlerini yazmaçlara, bellekten geri yüklemesi gerekir ve donanımın, yazma arabelleklerini belleğe temizlemesi ve nesnelerin değerlerini bellekten yeniden yüklemesi gerekebilir.

`flush` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp flush [(variable-list)]  new-line
```

Eşitleme gerektiren nesneler değişkenlere göre atananlardan sonra, bu değişkenler isteğe bağlı *değişken listesinde*belirlenebilir. *Değişken listesinde*bir işaretçi varsa, işaretçinin başvurduğu nesne değil işaretçi kendisi temizlenir.

*Değişken listesi* olmayan bir `flush` yönergesi, erişilemeyen nesneler hariç tüm paylaşılan nesneleri otomatik depolama süresiyle eşitler. (Bunun nedeni, *değişken listesi*olan bir `flush` daha fazla yüke sahip olabilir.) *Değişken listesi* olmayan bir `flush` yönergesi aşağıdaki yönergeler için kapsanır:

- `barrier`
- `critical` giriş ve çıkış sırasında çıkış
- `ordered` giriş ve çıkış sırasında çıkış
- `parallel` giriş ve çıkış sırasında çıkış
- `for` 'den çıkışta
- `sections` 'den çıkışta
- `single` 'den çıkışta
- `parallel for` giriş ve çıkış sırasında çıkış
- `parallel sections` giriş ve çıkış sırasında çıkış

Bir `nowait` yan tümcesi varsa yönerge örtülü değildir. `flush` yönergesinin aşağıdakilerden herhangi biri için açık olmadığını not edilmelidir:

- `for` girişi sırasında
- `master` giriş veya çıkış sırasında çıkış
- `sections` girişi sırasında
- `single` girişi sırasında

Geçici nitelenmiş tür içeren bir nesnenin değerine erişen bir başvuru, bu nesneyi önceki sıra noktasında belirten bir `flush` yönergesi gibi davranır. Bir nesnenin değerini geçici nitelenmiş tür ile değiştiren bir başvuru, sonraki sıra noktasında bu nesneyi belirten `flush` yönerge gibi davranır.

`flush` yönergesinin sözdiziminin bir parçası olarak bir C dili bildirisi olmadığından, bir program içindeki yerleşimi üzerinde bazı kısıtlamalar vardır. Biçimsel dilbilgisi hakkında daha fazla bilgi için bkz. [Ek C](c-openmp-c-and-cpp-grammar.md). Aşağıdaki örnekte bu kısıtlamalar gösterilmektedir.

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

`flush` yönergesine yönelik kısıtlamalar aşağıdaki gibidir:

- `flush` yönergesinde belirtilen değişken bir başvuru türüne sahip olmamalıdır.

### <a name="266-ordered-construct"></a>2.6.6 sıralı yapı

`ordered` yönergesini izleyen yapısal bir blok, yinelemeleri sıralı bir döngüde yürütülecek sırada yürütülür. `ordered` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp ordered new-linestructured-block
```

`ordered` yönergesi `for` veya `parallel for` yapısının dinamik kapsamı içinde olmalıdır. `ordered` yapı bağlamadığı `for` veya `parallel for` yönergesi, [Bölüm 2.4.1](#241-for-construct)bölümünde açıklandığı gibi belirtilmiş bir `ordered` yan tümcesine sahip olmalıdır. Bir `for` veya `parallel for` yapısının `ordered` yan tümcesiyle yürütülmesi halinde `ordered` yapıları, döngünün sıralı yürütmesinde yürütülemeyecek sırayla yürütülür.

`ordered` yönergesine yönelik kısıtlamalar aşağıdaki gibidir:

- `for` yapı içeren bir döngünün yinelemesi aynı sıralı yönergeyi birden çok kez yürütmemelidir ve birden fazla `ordered` yönergesini yürütmemelidir.

## <a name="27-data-environment"></a>2,7 veri ortamı

Bu bölümde, paralel bölgelerin yürütülmesi sırasında veri ortamının denetlenmesi için aşağıdaki gibi bir yönerge ve çeşitli yan tümceler sunulmaktadır:

- Dosya kapsamı, ad alanı kapsamı veya statik blok kapsamı değişkenlerini bir iş parçacığına yerel hale getirmek için [threadprivate](#271-threadprivate-directive) yönergesi sağlanır.

- Paralel veya iş paylaşım yapılarının süresi için değişkenlerin paylaşım özniteliklerini denetleyen yönergeler üzerinde belirtilenebilir yan tümceler, [Bölüm 2.7.2](#272-data-sharing-attribute-clauses)' de açıklanmaktadır.

### <a name="271-threadprivate-directive"></a>2.7.1 threadprivate yönergesi

`threadprivate` yönergesi, *değişken listesinde* belirtilen adlandırılmış dosya kapsamı, ad alanı kapsamı veya statik blok kapsamı değişkenlerini bir iş parçacığına özel olarak yapar. *değişken listesi* , türü eksik olmayan bir değişkenlerin virgülle ayrılmış listesidir. `threadprivate` yönergesinin sözdizimi şöyledir:

```cpp
#pragma omp threadprivate(variable-list) new-line
```

Bir `threadprivate` değişkeninin her kopyası bir kez başlatılır, bu kopyaya ilk başvurmadan önce programdaki belirtilmemiş bir noktada ve her zamanki şekilde (örn. ana kopya programın seri yürütmesinde başlatılacağından). Bir nesneye bir `threadprivate` değişkeninin açık başlatıcısında başvuruluyorsa ve nesnenin değeri değişkenin bir kopyasına ilk başvurudan önce değiştirilirse, davranış belirtilmemiş olur.

Herhangi bir özel değişkende olduğu gibi, iş parçacığı başka bir iş parçacığının `threadprivate` nesnenin kopyasına başvurmamalıdır. Programın seri bölgeleri ve ana bölgeleri sırasında, başvurular ana iş parçacığının nesnenin kopyasına olur.

İlk paralel bölge yürütüldükten sonra, `threadprivate` nesnelerdeki verilerin yalnızca dinamik iş parçacığı mekanizması devre dışı bırakılmışsa ve iş parçacığı sayısı tüm paralel bölgelerde değişmeden kalırsa kalıcı hale getirilmesi garanti edilir.

`threadprivate` yönergesine yönelik kısıtlamalar aşağıdaki gibidir:

- Dosya kapsamı veya ad alanı kapsamı değişkenlerine yönelik bir `threadprivate` yönergesi herhangi bir tanım veya bildirimin dışında görünmelidir ve listesindeki değişkenlerin herhangi birine yönelik tüm başvuruları sözcüksel olarak önce kullanmalıdır.

- Dosya veya ad alanı kapsamındaki `threadprivate` yönergesinin *değişken listesindeki* her değişken, yönergeden önce gelen dosya veya ad alanı kapsamındaki bir değişken bildirimine başvurmalıdır.

- Statik blok kapsamı değişkenlerine yönelik bir `threadprivate` yönergesi, iç içe kapsamda değil, değişkenin kapsamında görünmelidir. Yönerge, listesindeki değişkenlerin herhangi birine yapılan tüm başvuruları sözcüksel olarak önüne almalıdır.

- Blok kapsamındaki bir `threadprivate` yönergesinin *değişken listesindeki* her değişken, aynı kapsamdaki, yönergeden önce gelen bir değişken bildirimine başvurmalıdır. Değişken bildirimi statik depolama sınıfı belirticisini kullanmalıdır.

- Bir değişken bir çeviri birimindeki `threadprivate` yönergesinde belirtilmişse, bildirildiği her çeviri birimindeki bir `threadprivate` yönergesinde belirtilmelidir.

- `threadprivate` değişken `copyin`, `copyprivate`, `schedule`, `num_threads`veya `if` yan tümcesi dışında herhangi bir yan tümce içinde görünmemelidir.

- `threadprivate` değişkenin adresi bir adres sabiti değil.

- `threadprivate` değişken, tamamlanmamış bir tür veya başvuru türüne sahip olmamalıdır.

- POD olmayan sınıf türüne sahip bir `threadprivate` değişkeni, açık bir başlatıcı ile bildirilirse, erişilebilir ve belirsiz bir kopya oluşturucusuna sahip olmalıdır.

Aşağıdaki örnek, bir başlatıcıda görünen bir değişkenin, belirtilmeyen davranışa neden olabileceği ve ayrıca yardımcı bir nesne ve kopya Oluşturucu kullanarak bu sorundan kaçınmak için nasıl değişiklik yapılacağını gösterir.

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

#### <a name="cross-references"></a>Çapraz başvurular

- [dinamik iş parçacıkları](3-run-time-library-functions.md#317-omp_set_dynamic-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) ortam değişkeni

### <a name="272-data-sharing-attribute-clauses"></a>2.7.2 veri paylaşımı öznitelik yan tümceleri

Bir kullanıcının Bölge süresince değişkenlerin paylaşım özniteliklerini denetlemesine izin veren yan tümceleri kabul eden çeşitli yönergeler. Öznitelik yan tümcelerini paylaşma özelliği, yalnızca yan tümcesinin göründüğü yönergedeki sözcük kapsamı için geçerlidir. Tüm yönergeler üzerinde aşağıdaki yan tümceciklerine izin verilmez. Belirli bir yönergede geçerli olan yan tümceler listesi, yönergesiyle açıklanmıştır.

Bir paralel veya iş paylaşım yapısıyla karşılaşıldığında ve değişken bir paylaşım özniteliği yan tümcesinde veya `threadprivate` yönergesinde belirtilmemişse, değişken paylaşılır. Paralel bir bölgenin dinamik kapsamı içinde belirtilen statik değişkenler paylaşılır. Yığın ile ayrılmış bellek (örneğin, C 'de `malloc()` veya C++ içinde C++`new` işleci) paylaşılır. (Ancak, bu belleğin işaretçisi özel veya paylaşılan olabilir.) Paralel bir bölgenin dinamik kapsamı içinde belirtilen otomatik depolama süresine sahip değişkenler özeldir.

Yan tümcelerinin çoğu, görünür olan değişkenlerin virgülle ayrılmış bir listesi olan *değişken listesi* bağımsız değişkenini kabul eder. Bir veri paylaşımı öznitelik yan tümcesinde başvurulan bir değişkenin bir şablondan türetilmiş bir türü varsa ve programda bu değişkene başka bir başvuru yoksa, davranış tanımsızdır.

Yönerge yan tümceleri içinde görünen tüm değişkenler görünür olmalıdır. Yan tümceler gerektiği şekilde tekrarlanabilir, ancak bir değişken birden fazla yan tümce içinde belirtilemez, ancak bir değişken hem `firstprivate` hem de `lastprivate` yan tümcesinde belirlenebilir.

Aşağıdaki bölümlerde veri paylaşımı özniteliği yan tümceleri açıklanır:

- [private](#2721-private)
- [firstprivate](#2722-firstprivate)
- [lastprivate](#2723-lastprivate)
- [Paylaşılan](#2724-shared)
- [default](#2725-default)
- [reduction](#2726-reduction)
- [copyin](#2727-copyin)
- [copyprivate](#2728-copyprivate)

#### <a name="2721-private"></a>2.7.2.1 private

`private` yan tümcesi, değişken listesindeki değişkenleri bir ekipteki her iş parçacığına özel olacak şekilde bildirir. `private` yan tümcesinin sözdizimi şöyledir:

```cpp
private(variable-list)
```

`private` yan tümcesinde belirtilen bir değişkenin davranışı aşağıdaki gibidir. Yapı için otomatik depolama süresine sahip yeni bir nesne ayrılır. Yeni nesnenin boyutu ve hizalaması, değişkenin türüne göre belirlenir. Bu ayırma, ekipteki her iş parçacığı için bir kez gerçekleşir ve gerekirse bir sınıf nesnesi için varsayılan oluşturucu çağrılır; Aksi takdirde, ilk değer belirsiz olur.  Değişkenin başvurduğu özgün nesne, yapı girişi sırasında belirsiz bir değere sahiptir, yapının dinamik kapsamı içinde değiştirilmemelidir ve yapıdan çıkıldığında belirsiz bir değere sahip olur.

Yönerge yapısının sözlü kapsamı içinde, değişkeni iş parçacığı tarafından ayrılan yeni özel nesneye başvurur.

`private` yan tümcesine yönelik kısıtlamalar aşağıdaki gibidir:

- `private` yan tümcesinde belirtilen bir sınıf türüne sahip bir değişken, erişilebilir, belirsiz bir varsayılan oluşturucuya sahip olmalıdır.

- Bir `private` yan tümcesinde belirtilen değişken, `mutable` üyesi olan bir sınıf türüne sahip olmadığı için `const`nitelikli bir türe sahip olmamalıdır.

- `private` yan tümcesinde belirtilen değişken, tamamlanmamış bir tür veya başvuru türüne sahip olmamalıdır.

- Bir `parallel` yönergesinin `reduction` yan tümcesinde görünen değişkenler, paralel yapıyı bağlayan bir iş paylaşımı yönergesinde bir `private` yan tümcesinde belirtilemez.

#### <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

`firstprivate` yan tümcesi, `private` yan tümcesi tarafından sağlanan işlevselliğin bir üst kümesini sağlar. `firstprivate` yan tümcesinin sözdizimi şöyledir:

```cpp
firstprivate(variable-list)
```

*Değişken listesinde* belirtilen değişkenlerde, [Bölüm 2.7.2.1](#2721-private)' de açıklandığı gibi `private` yan tümce semantiği vardır. Başlatma veya oluşturma, iş parçacığının yapının yürütülmesinden önce iş parçacığı başına bir kez yapılmış gibi olur. Paralel bir yapı üzerindeki bir `firstprivate` yan tümcesi için, yeni özel nesnenin başlangıçtaki değeri, onunla karşılaştığı iş parçacığının paralel yapısıyla hemen önce var olan özgün nesnenin değeridir. İş paylaşımı yapısında bir `firstprivate` yan tümcesi için, iş paylaşımı yapısını yürüten her iş parçacığının yeni özel nesnesinin ilk değeri, aynı iş parçacığının iş paylaşım yapısıyla karşılaştığı zaman noktadan önce var olan özgün nesnenin değeridir. Bunlara ek olarak, C++ nesneler için, her iş parçacığının yeni özel nesnesi özgün nesneden oluşturulan kopyadır.

`firstprivate` yan tümcesine yönelik kısıtlamalar aşağıdaki gibidir:

- `firstprivate` yan tümcesinde belirtilen değişken, tamamlanmamış bir tür veya başvuru türüne sahip olmamalıdır.

- `firstprivate` olarak belirtilen bir sınıf türüne sahip bir değişken, erişilebilir, belirsiz bir kopya oluşturucusuna sahip olmalıdır.

- Bir paralel bölge içinde özel olan veya bir `parallel` yönergesinin `reduction` yan tümcesinde görünen değişkenler, paralel yapıyı bağlayan bir iş paylaşımı yönergesinde bir `firstprivate` yan tümcesinde belirtilemez.

#### <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

`lastprivate` yan tümcesi, `private` yan tümcesi tarafından sağlanan işlevselliğin bir üst kümesini sağlar. `lastprivate` yan tümcesinin sözdizimi şöyledir:

```cpp
lastprivate(variable-list)
```

*Değişken listesinde* belirtilen değişkenlerde `private` yan tümce semantiği vardır. Bir iş paylaşımı yapısını tanımlayan yönergede bir `lastprivate` yan tümcesi göründüğünde, ilişkili döngünün sıralı son yinelemesinden her bir `lastprivate` değişkeninin değeri veya sözcüksel son bölüm yönergesi değişkenin özgün nesnesine atanır. `for` veya `parallel for`son yinelemesi veya `sections` ya da `parallel sections` yönergesinin sözcüksel son bölümü tarafından bir değer atanmamış değişkenler, yapıdan sonra belirsiz değerler içermelidir. Atanmamış alt nesnelerin, yapı sonrasında belirsiz bir değeri de vardır.

`lastprivate` yan tümcesine yönelik kısıtlamalar aşağıdaki gibidir:

- `private` için tüm kısıtlamalar geçerlidir.

- `lastprivate` olarak belirtilen bir sınıf türüne sahip bir değişken, erişilebilir, belirsiz bir kopya atama işlecine sahip olmalıdır.

- Bir paralel bölge içinde özel olan veya bir `parallel` yönergesinin `reduction` yan tümcesinde görünen değişkenler, paralel yapıyı bağlayan bir iş paylaşımı yönergesinde bir `lastprivate` yan tümcesinde belirtilemez.

#### <a name="2724-shared"></a>2.7.2.4 shared

Bu yan tümce, bir takımda bulunan tüm iş parçacıkları arasındaki *değişken listesinde* görünen değişkenleri paylaşır. Bir ekibin içindeki tüm iş parçacıkları `shared` değişkenleri için aynı depolama alanına erişir.

`shared` yan tümcesinin sözdizimi şöyledir:

```cpp
shared(variable-list)
```

#### <a name="2725-default"></a>2.7.2.5 default

`default` yan tümcesi, kullanıcının değişkenlerin veri paylaşım özniteliklerini etkilemesini sağlar. `default` yan tümcesinin sözdizimi şöyledir:

```cpp
default(shared | none)
```

`default(shared)` belirtmek, `threadprivate` veya `const`nitelenmiş olmadığı durumlar dışında, bir `shared` yan tümcesinde görünür olan her değişkenin açıkça listelenmesi ile eşdeğerdir. Açık bir `default` yan tümcesinin yokluğu altında, varsayılan davranış `default(shared)` belirtilmiş gibi aynıdır.

`default(none)` belirtmek için aşağıdaki en az bir tane, paralel yapının sözcük biçiminde bir değişkene her başvuru için true olmalıdır:

- Değişken, başvuruyu içeren bir yapının veri paylaşımı özniteliği yan tümcesinde açıkça listelenir.

- Değişken, paralel yapı içinde bildirilmiştir.

- Değişken `threadprivate`.

- Değişkenin `const`nitelenmiş bir türü vardır.

- Değişken, bir `for` veya `parallel for` yönergesini hemen izleyen `for` döngüsünün döngü denetim değişkenidir ve değişken başvurusu döngünün içinde görünür.

Bir ın `firstprivate`, `lastprivate`veya `reduction` yan tümcesinde bir değişken belirtmek kapsayan bağlamdaki değişkene örtülü başvuruya neden olur. Bu tür örtük başvurular, yukarıda listelenen gereksinimlere de tabidir.

`parallel` yönergesinde yalnızca tek bir `default` yan tümcesi belirtilebilir.

Bir değişkenin varsayılan veri paylaşımı özniteliği, aşağıdaki örnekte gösterildiği gibi `private`, `firstprivate`, `lastprivate`, `reduction`ve `shared` yan tümceleri kullanılarak geçersiz kılınabilir:

```cpp
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```

#### <a name="2726-reduction"></a>2.7.2.6 reduction

Bu yan tümce, işleç *op*ile *değişken listesinde*görünen skaler değişkenlerde bir azalma gerçekleştirir. `reduction` yan tümcesinin sözdizimi şöyledir:

`reduction(` *op* `:` *değişken listesi* `)`

Aşağıdaki formlardan birine sahip bir ifade için genellikle bir azaltma belirtilir:

- *x* `=` *x* *op* *Expr*
- *x* *binop* `=` *Expr*
- *x* `=` *Expr* *op* *x* (çıkarma hariç)
- *x* `++`
- `++` *x*
- *x* `--`
- `--` *x*

burada:

*sayı*<br/>
Listede belirtilen azaltma değişkenlerinden biri.

*değişken listesi*<br/>
Skalar azaltma değişkenlerinin virgülle ayrılmış listesi.

*ifadeyi*<br/>
*X*başvurusu olmayan skaler türü olan bir ifade.

*üs*<br/>
Aşırı yüklenmiş bir operatör değil, `+`, `*`, `-`, `&`, `^`, `|`, `&&`veya `||`.

*binop*<br/>
Aşırı yüklenmiş bir operatör değil, `+`, `*`, `-`, `&`, `^`veya `|`.

Aşağıda `reduction` yan tümcesinin bir örneği verilmiştir:

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

Örnekte gösterildiği gibi, bir işleç bir işlev çağrısının içinde gizli olabilir. Kullanıcı, `reduction` yan tümcesinde belirtilen işlecin azaltma işlemiyle eşleştiğinden dikkatli olmalıdır.

`||` işlecinin sağ işleneninde bu örnekteki yan etkileri olmasa da, bunlara izin verilir, ancak dikkatli olarak kullanılmalıdır. Bu bağlamda, döngünün sıralı yürütmesi sırasında gerçekleşmeyecek olan bir yan etkisi paralel yürütme sırasında gerçekleşebilir. Bu fark, yineleme yürütme sırası belirsiz olduğu için oluşabilir.

İşleci, azaltma için derleyici tarafından kullanılan özel değişkenlerin başlangıç değerini belirlemede ve sonlandırma işlecini belirlemede kullanılır. İşleci açıkça belirtmek, azaltma bildiriminin yapının sözcük dışı olmasını sağlar. Yönergede herhangi bir sayıda `reduction` yan tümce belirtilebilir, ancak bu yönerge için en fazla bir `reduction` yan tümcesinde bir değişken görünebilir.

`private` yan tümcesi kullanılmış gibi her bir iş parçacığı için *değişken-liste* içindeki her değişkenin özel bir kopyası oluşturulur. Özel kopya işlecine göre başlatılır (aşağıdaki tabloya bakın).

`reduction` yan tümcesinin belirtildiği bölgenin sonunda, özgün nesne, özgün değerini, belirtilen işleci kullanarak özel kopyaların her birinin son değeriyle birleştirmenin sonucunu yansıtacak şekilde güncelleştirilir. Azaltma işleçleri tüm ilişkilendirilebilir (çıkarma hariç) ve derleyici son değerin hesaplamasını serbestçe yeniden ilişkilendirebilirsiniz. (Çıkarma azaltmanın kısmi sonuçları, son değeri oluşturmak için eklenir.)

İlk iş parçacığı kapsayan yan tümcesine ulaştığında özgün nesnenin değeri belirsiz hale gelir ve azaltma hesaplaması tamamlanana kadar bu şekilde kalır.  Normalde hesaplama, yapının sonunda tamamlanacaktır; Ancak, `reduction` yan tümcesi `nowait` uygulanmış bir yapı üzerinde kullanılıyorsa, tüm iş parçacıklarının `reduction` yan tümcesini tamamladığına emin olmak için bir engel eşitlemesi gerçekleştirilene kadar özgün nesnenin değeri belirsiz olarak kalır.

Aşağıdaki tabloda, geçerli olan işleçler ve bunların kurallı başlatma değerleri listelenmektedir. Gerçek başlatma değeri, azaltma değişkeninin veri türüyle tutarlı olacak.

|İşleç|Başlatma|
|--------------|--------------------|
|`+`|0|
|`*`|1\.|
|`-`|0|
|`&`|~0|
|`|`|0|
|`^`|0|
|`&&`|1\.|
|`||`|0|

`reduction` yan tümcesine yönelik kısıtlamalar aşağıdaki gibidir:

- `reduction` yan tümcesindeki değişkenlerin türü, azaltma işleci için, işaretçi türleri ve başvuru türleri hiçbir şekilde izin verilmeyen durumlar dışında geçerli olmalıdır.

- `reduction` yan tümcesinde belirtilen bir değişken `const`nitelenmemelidir.

- Bir paralel bölge içinde özel olan veya bir `parallel` yönergesinin `reduction` yan tümcesinde görünen değişkenler, paralel yapıyı bağlayan bir iş paylaşımı yönergesinde bir `reduction` yan tümcesinde belirtilemez.

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

`copyin` yan tümcesi, paralel bölgeyi yürüten ekipteki her iş parçacığının `threadprivate` değişkenlerine aynı değeri atamak için bir mekanizma sağlar. `copyin` yan tümcesinde belirtilen her değişken için, ekibin ana iş parçacığındaki değişkenin değeri, atama ölçütü olarak paralel bölgenin başlangıcında iş parçacığı özel kopyalara kopyalanır. `copyin` yan tümcesinin sözdizimi şöyledir:

```cpp

copyin(
variable-list
)
```

`copyin` yan tümcesine yönelik kısıtlamalar aşağıdaki gibidir:

- `copyin` yan tümcesinde belirtilen bir değişken, erişilebilir, belirsiz bir kopya atama işlecine sahip olmalıdır.

- `copyin` yan tümcesinde belirtilen bir değişken `threadprivate` değişken olmalıdır.

#### <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

`copyprivate` yan tümcesi, bir ekibin bir üyesinden diğer üyelere bir değer yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Bu tür paylaşılan bir değişkenin sağlanması zor olur (örneğin, her düzeyde farklı bir değişken gerektiren bir özyineleme). `copyprivate` yan tümcesi yalnızca `single` yönergesinde yer alabilir.

`copyprivate` yan tümcesinin sözdizimi şöyledir:

```cpp

copyprivate(
variable-list
)
```

Değişken listesindeki değişkenlerde `copyprivate` yan tümcesinin etkisi, `single` yapısıyla ilişkili yapılandırılmış bloğunun yürütülmesinden sonra ve ekipteki iş parçacıklarından önce, yapının sonundaki engelden ayrılmadan önce oluşur. Ardından, tüm diğer iş parçacıklarında, *değişken listesindeki*her bir değişken için, bu değişken yapının yapısal bloğunu yürüten iş parçacığında karşılık gelen değişkenin değeri ile tanımlanır (atama ölçütü olarak).

`copyprivate` yan tümcesine yönelik kısıtlamalar aşağıdaki gibidir:

- `copyprivate` yan tümcesinde belirtilen bir değişken, aynı `single` yönergesi için `private` veya `firstprivate` yan tümcesinde görünmemelidir.

- Paralel bölgenin dinamik kapsamında bir `copyprivate` yan tümcesiyle `single` yönergesine karşılaşılırsa, `copyprivate` yan tümcesinde belirtilen tüm değişkenlerin kapsayan bağlamda özel olması gerekir.

- `copyprivate` yan tümcesinde belirtilen bir değişken, erişilebilir bir kopya atama işlecine sahip olmalıdır.

## <a name="28-directive-binding"></a>2,8 yönerge bağlama

Yönergelerin dinamik bağlamasının aşağıdaki kurallara uyması gerekir:

- `for`, `sections`, `single`, `master`ve `barrier` yönergeleri, Bu yönergede mevcut olabilecek tüm `parallel`yan tümcelerinden bağımsız olarak, bir tane varsa dinamik olarak kapsayan `if` bağlar. Şu anda yürütülen bir paralel bölge yoksa, yönergeler yalnızca ana iş parçacığından oluşan bir takım tarafından yürütülür.

- `ordered` yönergesi dinamik olarak kapsayan `for`bağlar.

- `atomic` yönergesi, yalnızca geçerli takımın değil, tüm iş parçacıklarındaki `atomic` yönergeleriyle ilgili olarak özel erişim uygular.

- `critical` yönergesi, yalnızca geçerli takımın değil, tüm iş parçacıklarındaki `critical` yönergeleriyle ilgili olarak özel erişim uygular.

- Bir yönerge hiçbir yerde, en yakın dinamik olarak kapsayan `parallel`dışındaki herhangi bir yönergeyi bağlanamaz.

## <a name="29-directive-nesting"></a>2,9 Yönerge iç içe

Yönergelerin dinamik iç içe geçirilmesi aşağıdaki kurallara uymalıdır:

- Başka bir `parallel` içinde dinamik olarak `parallel` yönerge, iç içe paralellik etkin olmadığı müddetçe, yalnızca geçerli iş parçacığından oluşan yeni bir takım oluşturur.

- aynı `parallel` bağlanan `for`, `sections`ve `single` yönergelerinin birbirini iç içe olmasına izin verilmez.

- aynı ada sahip `critical` yönergelerinin birbirini iç içe olmasına izin verilmez. Bu kısıtlamanın kilitlenmeyi engellemek için yeterli olmadığını unutmayın.

- `for`, `sections`ve `single` yönergelere, yönergeler bölgelerle aynı `ordered`bağlansa `critical`, `master` ve `parallel` bölgelerin dinamik kapsamı içinde izin verilmez.

- yönergeler bölgelerle aynı `single`bağlansa, `for`, `ordered`, `sections`, `master`, `critical` ve `parallel` bölgelerin dinamik kapsamında `barrier` yönergelere izin verilmez.

- `master` yönergeleri iş paylaşımı yönergeleriyle aynı `parallel` bağlansa, `for`, `sections`ve `single` yönergelerinin dinamik kapsamında `master` yönergelere izin verilmez.

- yönergeler bölgelerle aynı `parallel` bağlansa, `critical` bölgelerin dinamik kapsamında `ordered` yönergelere izin verilmez.

- Paralel bir bölgenin içinde dinamik olarak yürütülene izin verilen herhangi bir yönerge, paralel bir bölgenin dışında yürütüldüğünde de izin verilir. Kullanıcı tarafından belirtilen paralel bölgenin dışında dinamik olarak yürütüldüğünde, yönerge yalnızca ana iş parçacığından oluşan bir takım tarafından yürütülür.
