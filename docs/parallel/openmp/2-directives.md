---
title: 2. Yönergeler
ms.date: 01/18/2019
ms.assetid: d1a69374-6c03-45fb-8c86-e91cea8adae8
ms.openlocfilehash: c3aadcf34e013c66dec81ca4b09dce4144294ac3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228407"
---
# <a name="2-directives"></a>2. Yönergeler

Yönergeler `#pragma` , C ve C++ standartları içinde tanımlanan yönergeleri temel alır.  OpenMP C ve C++ API 'sini destekleyen derleyiciler, tüm OpenMP derleyicisi yönergelerinin yorumunu etkinleştiren ve yorumlamayı sağlayan bir komut satırı seçeneği içerir.

## <a name="21-directive-format"></a>2,1 yönerge biçimi

Bir OpenMP yönergesinin sözdizimi, [Ek C](c-openmp-c-and-cpp-grammar.md)'de dilbilgisinde ve resmi olarak aşağıdaki gibi belirtilmiştir:

```cpp
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

Her yönerge `#pragma omp` , aynı ada sahip diğer (OpenMP veya satıcı uzantıları olarak OpenMP) pragma yönergeleriyle çakışma olasılığını azaltmak için ile başlar. Yönergesinin geri kalanı, derleyici yönergeleri için C ve C++ standartları kurallarını izler. Özellikle, beyaz boşluk, ve sonrasında kullanılabilir `#` ve bazen bir yönergedeki sözcükleri ayırmak için boşluk kullanılması gerekir. Sonrasında ön işleme belirteçleri `#pragma omp` makro değiştirme 'ye tabidir.

Yönergeler büyük/küçük harfe duyarlıdır. Yan tümcelerin yönergeler bölümünde görünme sırası önemli değildir. Yönergelerden yan tümceler gerektiğinde tekrarlanabilir ve her bir yan tümcenin açıklamasında listelenen kısıtlamalara tabidir. Bir yan tümcesinde *değişken listesi* görünürse, yalnızca değişkenleri belirtmelidir. Her yönerge için yalnızca bir *Yönerge adı* belirtilebilir.  Örneğin, aşağıdaki yönergeye izin verilmez:

```cpp
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

Bir OpenMP yönergesi, yapılandırılmış bir blok olması gereken en fazla bir başarılı ifade için geçerlidir.

## <a name="22-conditional-compilation"></a>2,2 Koşullu derleme

`_OPENMP`Makro adı, OpenMP uyumlu uygulamalar tarafından, onaylanan belirtiminin yılı ve ayı olacak şekilde, Decimal sabit *yyyymm*olarak tanımlanır. Bu makro bir `#define` veya `#undef` ön işleme yönergesinin konusu olmamalıdır.

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

- `if(`*skaler ifade*`)`
- `private(`*değişken listesi*`)`
- `firstprivate(`*değişken listesi*`)`
- `default(shared | none)`
- `shared(`*değişken listesi*`)`
- `copyin(`*değişken listesi*`)`
- `reduction(`*işleci* `:` *değişken listesi*  `)`
- `num_threads(`*tamsayı ifadesi*`)`

Bir iş parçacığı bir paralel yapıyı aldığında, aşağıdaki durumlardan biri geçerliyse iş parçacığı grubu oluşturulur:

- Hiçbir `if` yan tümce yok.
- `if`İfade sıfır dışında bir değer olarak değerlendirilir.

Bu iş parçacığı, iş parçacığı sayısı 0 ve takımda ana iş parçacığı dahil tüm iş parçacıkları olan ekibin ana iş parçacığı haline gelir. `if`İfadenin değeri sıfırsa bölge serileştirilir.

İstenen iş parçacığı sayısını öğrenmek için aşağıdaki kurallar sırayla kabul edilir. Koşulu karşılandığında ilk kural uygulanır:

1. `num_threads`Yan tümce varsa, tamsayı ifadesinin değeri istenen iş parçacığı sayısıdır.

1. `omp_set_num_threads`Kitaplık işlevi çağrılırsa, en son yürütülen çağrının bağımsız değişkeninin değeri, istenen iş parçacığı sayısıdır.

1. Ortam değişkeni `OMP_NUM_THREADS` tanımlanmışsa, bu ortam değişkeninin değeri istenen iş parçacığı sayısıdır.

1. Yukarıdaki yöntemlerin hiçbiri kullanılmazsa, istenen iş parçacığı sayısı uygulama tanımlı olur.

`num_threads`Yan tümcesi mevcutsa, kitaplık işlevi veya ortam değişkeni tarafından istenen iş parçacığı sayısının yerini `omp_set_num_threads` `OMP_NUM_THREADS` yalnızca uygulandığı paralel bölge için yerine geçer. Daha sonra paralel bölgeler bundan etkilenmez.

Paralel bölgeyi çalıştıran iş parçacıklarının sayısı Ayrıca, iş parçacığı sayısının dinamik ayarlamasının etkin olup olmamasına bağlıdır. Dinamik ayarlama devre dışıysa, istenen iş parçacığı sayısı paralel bölgeyi yürütür. Dinamik ayarlama etkinse, istenen iş parçacığı sayısı, paralel bölgeyi yürütebilecek iş parçacığı sayısı üst sınırıdır.

İş parçacığı sayısı için dinamik ayarlama devre dışı bırakıldığı ve paralel bölge için istenen iş parçacığı sayısı, çalışma zamanı sisteminin sağlayabileceği sayıdan daha fazla olduğu için bir paralel bölge ile karşılaşılırsa, programın davranışı uygulama tanımlı olur. Uygulama, örneğin programın yürütülmesini kesintiye uğratan veya paralel bölgeyi seri hale getirebilecek olabilir.

`omp_set_dynamic`Kitaplık işlevi ve `OMP_DYNAMIC` ortam değişkeni, iş parçacığı sayısının dinamik ayarlamasını etkinleştirmek ve devre dışı bırakmak için kullanılabilir.

Belirli bir zamanda iş parçacıklarını barındıran fiziksel işlemcilerin sayısı uygulama tanımlı ' dır. Oluşturulduktan sonra ekipteki iş parçacığı sayısı, bu paralel bölgenin süresi boyunca sabit kalır. Kullanıcı tarafından açık olarak veya bir paralel bölgeden diğerine otomatik olarak değiştirilebilir.

Paralel bölgenin dinamik kapsamı içinde yer alan deyimler her bir iş parçacığı tarafından yürütülür ve her bir iş parçacığı diğer iş parçacıklarından farklı olan deyimlerin yolunu yürütebilirler. Paralel bir bölgenin sözcük kapsamı dışında karşılaşılan yönergeler yalnız bırakılmış yönergeler olarak adlandırılır.

Paralel bölgenin sonunda örtük bir engel vardır. Yalnızca ekibin ana iş parçacığı, bir paralel bölgenin sonunda yürütmeye devam eder.

Bir takımda bir paralel bölgeyi yürüten bir iş parçacığı başka bir paralel yapı ile karşılaştığında, yeni bir takım oluşturur ve bu yeni ekibin ana kopyası olur. İç içe paralel bölgeler varsayılan olarak serileştirilir. Sonuç olarak, varsayılan olarak, iç içe bir paralel bölge, bir iş parçacığından oluşan bir takım tarafından yürütülür. Varsayılan davranış, çalışma zamanı kitaplığı işlevi ya da ortam değişkeni kullanılarak değiştirilebilir `omp_set_nested` `OMP_NESTED` . Ancak, iç içe bir paralel bölgeyi çalıştıran bir ekipteki iş parçacığı sayısı uygulama tanımlı ' dır.

`parallel`Yönergeyle kısıtlamalar aşağıdaki gibidir:

- En çok, `if` yönergede bir yan tümce bulunabilir.

- İf ifadesi veya ifadesinin içinde herhangi bir yan etkeniz gerçekleşmeksizin, bu belirtilmemiş olur `num_threads` .

- `throw`Paralel bir bölgenin içinde yürütülen bir yürütme, yürütmenin aynı yapısal bloğun dinamik kapsamı içinde sürdürülmesine neden olmalıdır ve özel durumu oluşturan aynı iş parçacığı tarafından yakalanmalıdır.

- Yönergede yalnızca tek bir `num_threads` yan tümce görünebilir. `num_threads`İfade, paralel bölgenin bağlamı dışında değerlendirilir ve pozitif bir tamsayı değeri olarak değerlendirilmelidir.

- `if`Ve yan tümcelerinin değerlendirilme sırası `num_threads` belirtilmemiş.

### <a name="cross-references"></a>Çapraz başvurular

- `private`, `firstprivate` ,,, `default` `shared` `copyin` , ve `reduction` yan tümceleri ([Bölüm 2.7.2](#272-data-sharing-attribute-clauses))
- [Omp_num_threads](4-environment-variables.md#42-omp_num_threads) ortam değişkeni
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) Kitaplığı işlevi
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) ortam değişkeni
- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) işlevi
- [OMP_NESTED](4-environment-variables.md#44-omp_nested) ortam değişkeni
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) Kitaplığı işlevi

## <a name="24-work-sharing-constructs"></a>2,4 iş paylaşımı yapıları

Bir iş paylaşımı yapısı, ilişkili deyimin yürütmesini, bu takımın karşılaştığı ekip üyeleri arasında dağıtır. İş paylaşım yönergeleri yeni iş parçacıkları başlatamaz ve bir iş paylaşımı yapısına giriş üzerinde örtük bir engel yoktur.

Çalışma paylaşımı yapıları ve yönergelerden oluşan sıra, `barrier` bir takımda bulunan her iş parçacığında aynı olmalıdır.

OpenMP aşağıdaki iş paylaşımı yapılarını tanımlar ve bu yapılar aşağıdaki bölümlerde açıklanmıştır:

- [for](#241-for-construct) yönergesi
- [sections](#242-sections-construct) yönergesi
- [tek](#243-single-construct) yönerge

### <a name="241-for-construct"></a>2.4.1 for yapısı

`for`Yönergesi, ilişkili döngünün yinelemelerinin paralel olarak yürütüleceğini belirten yinelemeli bir iş paylaşımı yapısı tanımlar. Döngünün yinelemelerini, `for` bağlandığı paralel yapıyı yürüten ekipte zaten mevcut olan iş parçacıkları arasında dağıtılır. `for`Yapının sözdizimi şöyledir:

```cpp
#pragma omp for [clause[[,] clause] ... ] new-line for-loop
```

Yan tümcesi aşağıdakilerden biridir:

- `private(`*değişken listesi*`)`
- `firstprivate(`*değişken listesi*`)`
- `lastprivate(`*değişken listesi*`)`
- `reduction(`*işleci* `:` *değişken listesi*`)`
- `ordered`
- `schedule(`*tür* [ `,` *chunk_size*]`)`
- `nowait`

`for`Yönergesi karşılık gelen döngünün yapısına kısıtlamalar koyar `for` . Özellikle, karşılık gelen `for` döngünün kurallı şekli olmalıdır:

`for (`*init-expr* `;` *var mantıksal-op b* `;` *incr-Expr*`)`

*init-expr*<br/>
Aşağıdakilerden biri:

- *var*  =  *lb*
- *tamsayı türü var*  =  *lb*

*incr-Expr*<br/>
Aşağıdakilerden biri:

- `++`*var*
- *var*`++`
- `--`*var*
- *var*`--`
- *var* `+=` *INR*
- *var* `-=` *INR*
- *var* `=` *var* `+` *INR*
- *var* `=` *INR* `+` *var*
- *var* `=` *var* `-` *INR*

*l*<br/>
İşaretli bir tamsayı değişkeni. Bu değişken başka bir şekilde paylaşılırsa, süresi için örtük olarak özel olarak yapılır `for` . Bu değişkeni deyimin gövdesinde değiştirmeyin `for` . Değişken belirtilmediği takdirde `lastprivate` , döngüden sonraki değeri belirsiz olur.

*mantıksal işlem*<br/>
Aşağıdakilerden biri:

- `<`
- `<=`
- `>`
- `>=`

*lb*, *b*ve *incr*<br>
Sabit tamsayı ifadelerini döngüye sokun. Bu ifadelerin değerlendirmesi sırasında eşitleme yoktur, bu nedenle değerlendirilen yan etkiler belirsiz sonuçlar üretir.

Kurallı form, döngü yineleme sayısının döngüye girişte hesaplanmasını sağlar. Bu hesaplama, integral promosyonları sonrasında *var*türündeki değerlerle yapılır. Özellikle, *b* `-` *lb* `+` *incr* değeri bu tür içinde temsil ediediliyorsa, sonuç belirsiz olur. Daha ayrıntılı olarak, *mantıksal op* `<` veya ise `<=` *incr-Expr* , döngünün her yinelemesinde *var* olmasına neden olmalıdır.   *Mantıksal op* `>` veya ise `>=` , *incr-Expr* , döngünün her yinelemesinde *var* olmasına neden olmalıdır.

`schedule`Yan tümcesi, `for` döngünün yinelemelerinin takım iş parçacıkları arasında nasıl bölüneceğini belirtir. Bir programın doğruluğu, belirli bir yinelemeyi yürüten iş parçacığına bağlı olmamalıdır. *Chunk_size*değeri, belirtilmişse pozitif bir değer içeren bir döngü sabit tamsayı ifadesi olmalıdır. Bu ifadenin değerlendirmesi sırasında eşitleme yoktur, bu nedenle değerlendirilen yan etkiler belirsiz sonuçlar üretir. Zamanlama *türü* aşağıdaki değerlerden biri olabilir:

Tablo 2-1: `schedule` yan tümce *türü* değerleri

|||
|-|-|
|static|`schedule(static,` *Chunk_size* `)` belirtildiğinde, yinelemeler *chunk_size*belirtilen boyut öbeklerine bölünür. Parçalar, iş parçacığı numarası sırasına göre bir kez, takım iş parçacığına bir hepsini bir kez daha kez atanır. *Chunk_size* belirtilmediğinde, yineleme alanı her iş parçacığına bir öbek atandığında, boyutu yaklaşık olarak eşit olan parçalara bölünür.|
|dinamik|`schedule(dynamic,` *Chunk_size* `)` belirtildiğinde, yinelemeler, her biri *chunk_size* yineleme içeren bir dizi yığından ayrılır. Her bir öbek, bir atamayı bekleyen bir iş parçacığına atanır. İş parçacığı, yineleme öbekini yürütür ve sonra bir öbek atanıncaya kadar bir sonraki atamaya bekler. Atanacak son öbekte daha az sayıda yineleme olabilir. *Chunk_size* belirtilmediğinde, varsayılan olarak 1 olur.|
|temelli|`schedule(guided,` *Chunk_size* `)` belirtildiğinde, yinelemeler, azalan boyutlarla öbeklerdeki iş parçacıklarına atanır. Bir iş parçacığı atanmış yineleme öbeğini bitirdiğinde, hiçbiri ayrılana kadar dinamik olarak başka bir öbek atanır. 1 *chunk_size* için, her öbekin boyutu, iş parçacığı sayısına bölünen atanmamış yineleme sayısının yaklaşık olarak sayısıdır. Bu boyutlar neredeyse üstel olarak 1 ' i azaltır. *K* değeri 1 ' den büyük olan bir *chunk_size* için, en son öbekin *k* yinelemeden daha az yineleme olması dışında, Boyutlar neredeyse katlanarak *k*olarak azalır. *Chunk_size* belirtilmediğinde, varsayılan olarak 1 olur.|
|çalışma zamanı|`schedule(runtime)`Belirtildiğinde, zamanlama ile ilgili karar, çalışma zamanına kadar ertelenir. Öbeklerin zamanlama *türü* ve boyutu, ortam değişkeni ayarlanarak çalışma zamanında seçilebilir `OMP_SCHEDULE` . Bu ortam değişkeni ayarlanmamışsa, sonuçta elde edilen zamanlama uygulama tanımlı olur. Belirtildiğinde `schedule(runtime)` *chunk_size* belirtilmemelidir.|

Açıkça tanımlanmış bir yan tümce yokluğunda `schedule` , varsayılan değer `schedule` uygulama tanımlı ' dır.

OpenMP uyumlu bir program doğru yürütme için belirli bir zamanlamaya dayanmamalıdır. Bir programın, farklı derleyicilerde aynı zamanlama *türünün* uygulamalarında çeşitliliğe sahip olması mümkün olduğundan, yukarıda verilen açıklamaya uygun bir zamanlama *türüne* güvenmemelidir. Açıklamalar, belirli bir durum için uygun zamanlamayı seçmek üzere kullanılabilir.

`ordered` `ordered` Yönergeler yapıyı bağladığı zaman yan tümcesi bulunmalıdır `for` .

`for`Bir yan tümce belirtilmediği takdirde bir yapının sonunda örtülü bir engel vardır `nowait` .

`for`Yönergeyle kısıtlamalar aşağıdaki gibidir:

- `for`Döngü yapısal bir blok olmalıdır ve ayrıca, yürütülmesi bir ifadesiyle sonlandırılmamalıdır **`break`** .

- `for`Bir yönergeyle ilişkili döngünün döngü denetim ifadelerinin değerleri, `for` ekipteki tüm iş parçacıkları için aynı olmalıdır.

- `for`Loop yineleme değişkeni, işaretli bir tamsayı türüne sahip olmalıdır.

- Bir yönergede yalnızca tek bir `schedule` yan tümce görünebilir `for` .

- Bir yönergede yalnızca tek bir `ordered` yan tümce görünebilir `for` .

- Bir yönergede yalnızca tek bir `nowait` yan tümce görünebilir `for` .

- *Chunk_size*, *lb*, *b*veya *incr* ifadeleri içinde herhangi bir yan etkilerin ne zaman oluşması veya ne sıklıkla oluşması belirtilmemiş olur.

- *Chunk_size* ifadesinin değeri, ekipteki tüm iş parçacıkları için aynı olmalıdır.

#### <a name="cross-references"></a>Çapraz başvurular

- `private`, `firstprivate` , `lastprivate` , ve `reduction` yan tümceleri ([Bölüm 2.7.2](#272-data-sharing-attribute-clauses))
- [Omp_schedule](4-environment-variables.md#41-omp_schedule) ortam değişkeni
- [sıralı](#266-ordered-construct) yapı
- [Schedule](d-using-the-schedule-clause.md) yan tümcesi

### <a name="242-sections-construct"></a>2.4.2 sections bölüm yapısı

`sections`Yönergesi, bir ekipteki iş parçacıkları arasında bölünecek bir yapı kümesi belirten yinelenmeyen bir iş paylaşımı yapısını tanımlar. Her bölüm ekipteki bir iş parçacığı tarafından bir kez yürütülür. Yönergesinin sözdizimi aşağıdaki gibidir `sections` :

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

- `private(`*değişken listesi*`)`
- `firstprivate(`*değişken listesi*`)`
- `lastprivate(`*değişken listesi*`)`
- `reduction(`*işleci* `:` *değişken listesi*  `)`
- `nowait`

Her bölümde öncesinde bir yönerge bulunur `section` , ancak `section` yönerge ilk bölüm için isteğe bağlıdır. `section`Yönergelerin, yönergesinin sözcük kapsamı içinde yer almalıdır `sections` . `sections`Bir yapının sonunda, bir, belirtilmediyse, örtülü bir engel vardır `nowait` .

`sections`Yönergeyle kısıtlamalar aşağıdaki gibidir:

- Yönerge `section` , yönergenin sözcük kapsamı dışında görünmemelidir `sections` .

- Bir yönergede yalnızca tek bir `nowait` yan tümce görünebilir `sections` .

#### <a name="cross-references"></a>Çapraz başvurular

- `private`, `firstprivate` , `lastprivate` , ve `reduction` yan tümceleri ([Bölüm 2.7.2](#272-data-sharing-attribute-clauses))

### <a name="243-single-construct"></a>2.4.3 tek yapı

`single`Yönergesi, ilişkili yapılandırılmış bloğun takımda yalnızca bir iş parçacığı tarafından yürütüldüğünü belirten bir yapı tanımlar (ana iş parçacığı olması gerekmez). Yönergesinin sözdizimi aşağıdaki gibidir `single` :

```cpp
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

Yan tümcesi aşağıdakilerden biridir:

- `private(`*değişken listesi*`)`
- `firstprivate(`*değişken listesi*`)`
- `copyprivate(`*değişken listesi*`)`
- `nowait`

`single`Bir yan tümce belirtilmediği takdirde, yapıdan sonra örtük bir engel vardır `nowait` .

`single`Yönergeyle kısıtlamalar aşağıdaki gibidir:

- Bir yönergede yalnızca tek bir `nowait` yan tümce görünebilir `single` .
- `copyprivate`Yan tümce `nowait` yan tümcesiyle kullanılmamalıdır.

#### <a name="cross-references"></a>Çapraz başvurular

- `private`, `firstprivate` , ve `copyprivate` yan tümceleri ([Bölüm 2.7.2](#272-data-sharing-attribute-clauses))

## <a name="25-combined-parallel-work-sharing-constructs"></a>2,5 Birleşik paralel iş paylaşım yapıları

Birleşik paralel iş paylaşımı yapıları, yalnızca bir iş paylaşımı yapısına sahip bir paralel bölge belirtmeye yönelik kısayollardır. Bu yönergelerin semantiği, bir `parallel` yönergeyi ve ardından tek bir iş paylaşımı yapısı tarafından açıkça belirtilerek aynıdır.

Aşağıdaki bölümlerde Birleşik paralel iş paylaşımı yapıları açıklanır:

- [for yönergesi için Parallel](#251-parallel-for-construct)
- [Parallel sections](#252-parallel-sections-construct) yönergesi

### <a name="251-parallel-for-construct"></a>Yapı için 2.5.1 paralel

`parallel for`Yönergesi `parallel` yalnızca tek bir yönerge içeren bir bölgenin kısayoludur `for` . Yönergesinin sözdizimi aşağıdaki gibidir `parallel for` :

```cpp
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Bu yönerge, `parallel` `for` `nowait` aynı anlamlara ve sınırlamalara sahip yan tümce hariç, yönergedeki tüm yan tümceleri ve yönergeyi sağlar. Semantiği, açıkça bir yönerge tarafından izlenen bir yönergeyi açıkça belirtmekle aynıdır `parallel` `for` .

#### <a name="cross-references"></a>Çapraz başvurular

- [Parallel](#23-parallel-construct) yönergesi
- [for](#241-for-construct) yönergesi
- [Veri özniteliği yan tümceleri](#272-data-sharing-attribute-clauses)

### <a name="252-parallel-sections-construct"></a>2.5.2 Parallel sections paralel bölüm yapısı

`parallel sections`Yönergesi `parallel` yalnızca tek bir yönergesi olan bölge belirtmek için bir kısayol formu sağlar `sections` . Semantiği, açıkça bir yönerge tarafından izlenen bir yönergeyi açıkça belirtmekle aynıdır `parallel` `sections` . Yönergesinin sözdizimi aşağıdaki gibidir `parallel sections` :

```cpp
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

*Yan* tümcesi, `parallel` `sections` yan tümcesi dışında ve yönergeleri tarafından kabul edilen yan tümcelerden biri olabilir `nowait` .

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

`master`Yönergesi, ekibin ana iş parçacığı tarafından yürütülen yapısal bir blok belirten bir yapı tanımlar. Yönergesinin sözdizimi aşağıdaki gibidir `master` :

```cpp
#pragma omp master new-linestructured-block
```

Ekipteki diğer iş parçacıkları ilişkili yapısal bloğu yürütmez. Ana yapıdan giriş veya çıkış yapmadan önce örtük bir engel yoktur.

### <a name="262-critical-construct"></a>2.6.2 Critical kritik yapı

`critical`Yönergesi, ilişkili yapısal bloğunun yürütülmesini aynı anda tek bir iş parçacığına kısıtlayan bir yapı tanımlar. Yönergesinin sözdizimi aşağıdaki gibidir `critical` :

```cpp
#pragma omp critical [(name)]  new-linestructured-block
```

Kritik bölgeyi tanımlamak için, isteğe bağlı bir *ad* kullanılabilir. Kritik bir bölgeyi tanımlamak için kullanılan tanımlayıcılar dış bağlantıya sahiptir ve Etiketler, Etiketler, Üyeler ve normal tanımlayıcılar tarafından kullanılan ad alanlarından ayrı bir ad alanı içinde bulunur.

İş parçacığı, başka bir iş parçacığı aynı ada sahip bir kritik bölge (programda herhangi bir yerde) yürütülene kadar kritik bir bölgenin başlangıcında bekler. Adlandırılmamış tüm `critical` yönergeler aynı belirtilmemiş ada eşlenir.

### <a name="263-barrier-directive"></a>2.6.3 engel yönergesi

`barrier`Yönergesi, bir ekipteki tüm iş parçacıklarını eşitler. Bu sorunla karşılaşıldığında, ekipteki her iş parçacığı tüm diğerleri bu noktaya ulaşana kadar bekler. Yönergesinin sözdizimi aşağıdaki gibidir `barrier` :

```cpp
#pragma omp barrier new-line
```

Ekipteki tüm iş parçacıkları engelyle karşılaşdıktan sonra, ekipteki her iş parçacığı, bariyer yönergesinin paralel olan deyimlerini yürütmeye başlar. `barrier`Yönergesinin sözdiziminin bir parçası olarak bir C dili bildirisi olmadığından, bir program içindeki yerleşimi üzerinde bazı kısıtlamalar vardır. Biçimsel dilbilgisi hakkında daha fazla bilgi için bkz. [Ek C](c-openmp-c-and-cpp-grammar.md). Aşağıdaki örnekte bu kısıtlamalar gösterilmektedir.

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

`atomic`Yönergesi, belirli bir bellek konumunun, birden çok, eşzamanlı yazma iş parçacığı olasılığa karşı ortaya çıkarmak yerine, sıradan olarak güncelleştirilmesini sağlar. Yönergesinin sözdizimi aşağıdaki gibidir `atomic` :

```cpp
#pragma omp atomic new-lineexpression-stmt
```

İfade deyimi aşağıdaki formlardan birine sahip olmalıdır:

- *x binop* `=` *Expr*
- *x*`++`
- `++` *x*
- *x*`--`
- `--` *x*

Önceki ifadelerde:

- *x* skaler türü olan bir lvalue deyimidir.

- *Expr* skaler türü olan bir ifadedir ve *x*tarafından belirlenen nesneye başvurmuyor.

- *binop* , aşırı yüklenmiş bir operatör değildir ve,,,,,,, `+` `*` `-` `/` `&` `^` `|` `<<` , veya `>>` ' den biridir.

Uygulama tanımlı olsa da, bir uygulamanın tüm `atomic` yönergeleri `critical` aynı benzersiz *ada*sahip yönergelerden değiştirse de, `atomic` yönerge iyileştirilmesine izin verir. Genellikle atomik güncelleştirmeyi en az ek yük ile gerçekleştirebileceğiniz donanım yönergeleri sağlanır.

Yalnızca *x* tarafından atanan nesnenin yükü ve deposu atomik; *ifadenin* değerlendirmesi atomik değildir. Yarış koşullarından kaçınmak için, bu konumdaki tüm güncelleştirmeler, `atomic` yarış koşullarından muaf oldukları bilinenler haricinde yönergesiyle korunmalıdır.

`atomic`Yönergeyle kısıtlamalar aşağıdaki gibidir:

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

`flush`Açık veya örtük olarak belirtilen yönerge, bir ekipteki tüm iş parçacıklarının bellekte belirli nesnelerin (aşağıda belirtilen) tutarlı bir görünümüne sahip olduğundan emin olmak için uygulamanın gerekli olduğu bir "çapraz iş parçacığı" sıra noktasını belirtir. Bu, bu nesnelere başvuran ifadelerin önceki değerlendirmelerinin tamamlandığını ve sonraki değerlendirmeler henüz başlamamasıdır. Örneğin, derleyicilerin nesnelerin değerlerini yazmaçlara, bellekten geri yüklemesi gerekir ve donanımın, yazma arabelleklerini belleğe temizlemesi ve nesnelerin değerlerini bellekten yeniden yüklemesi gerekebilir.

Yönergesinin sözdizimi aşağıdaki gibidir `flush` :

```cpp
#pragma omp flush [(variable-list)]  new-line
```

Eşitleme gerektiren nesneler değişkenlere göre atananlardan sonra, bu değişkenler isteğe bağlı *değişken listesinde*belirlenebilir. *Değişken listesinde*bir işaretçi varsa, işaretçinin başvurduğu nesne değil işaretçi kendisi temizlenir.

`flush` *Değişken listesi* olmayan bir yönerge, erişilemeyen nesneler hariç tüm paylaşılan nesneleri otomatik depolama süresiyle eşitler. (Bu, bir `flush` *değişken listesi*ile öğesinden daha fazla yüke neden olabilir.) `flush` *Değişken listesi* olmayan bir yönerge aşağıdaki yönergeler için kapsanır:

- `barrier`
- Giriş ve çıkış`critical`
- Giriş ve çıkış`ordered`
- Giriş ve çıkış`parallel`
- Çıkışta`for`
- Çıkışta`sections`
- Çıkışta`single`
- Giriş ve çıkış`parallel for`
- Giriş ve çıkış`parallel sections`

Bir yan tümce varsa yönerge örtük değildir `nowait` . `flush`Yönergenin aşağıdakilerden herhangi biri için açık olmadığından not edilmelidir:

- Girişi sırasında`for`
- Giriş veya çıkış`master`
- Girişi sırasında`sections`
- Girişi sırasında`single`

Geçici nitelenmiş tür içeren bir nesnenin değerine erişen bir başvuru, `flush` Bu nesneyi önceki sıra noktasında belirten bir yönerge gibi davranır. Bir nesnenin değerini geçici nitelenmiş tür ile değiştiren bir başvuru, `flush` sonraki sıra noktasında bu nesneyi belirten bir yönerge gibi davranır.

`flush`Yönergesinin sözdiziminin bir parçası olarak bir C dili bildirisi olmadığından, bir program içindeki yerleşimi üzerinde bazı kısıtlamalar vardır. Biçimsel dilbilgisi hakkında daha fazla bilgi için bkz. [Ek C](c-openmp-c-and-cpp-grammar.md). Aşağıdaki örnekte bu kısıtlamalar gösterilmektedir.

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

`flush`Yönergeyle kısıtlamalar aşağıdaki gibidir:

- Yönergede belirtilen değişken `flush` bir başvuru türüne sahip olmamalıdır.

### <a name="266-ordered-construct"></a>2.6.6 sıralı yapı

Bir yönergeyi izleyen yapısal blok, `ordered` yinelemeleri sıralı bir döngüde yürütülecek sırada yürütülür. Yönergesinin sözdizimi aşağıdaki gibidir `ordered` :

```cpp
#pragma omp ordered new-linestructured-block
```

Bir `ordered` yönerge bir veya yapısının dinamik kapsamı içinde olmalıdır `for` `parallel for` . `for` `parallel for` Yapı bağlamadığı or yönergesinin, `ordered` `ordered` [Bölüm 2.4.1](#241-for-construct)' de açıklandığı gibi belirtilen bir yan tümcesine sahip olması gerekir. `for`Yan tümcesiyle bir veya yapının yürütülmesi halinde `parallel for` `ordered` `ordered` yapılar, döngünün sıralı yürütmesinde yürütülemeyecek sırayla yürütülür.

`ordered`Yönergeyle kısıtlamalar aşağıdaki gibidir:

- Yapı içeren bir döngünün yinelemesi `for` aynı sıralı yönergeyi birden çok kez yürütmemelidir ve birden fazla yönerge yürütmemelidir `ordered` .

## <a name="27-data-environment"></a>2,7 veri ortamı

Bu bölümde, paralel bölgelerin yürütülmesi sırasında veri ortamının denetlenmesi için aşağıdaki gibi bir yönerge ve çeşitli yan tümceler sunulmaktadır:

- Dosya kapsamı, ad alanı kapsamı veya statik blok kapsamı değişkenlerini bir iş parçacığına yerel hale getirmek için [threadprivate](#271-threadprivate-directive) yönergesi sağlanır.

- Paralel veya iş paylaşım yapılarının süresi için değişkenlerin paylaşım özniteliklerini denetleyen yönergeler üzerinde belirtilenebilir yan tümceler, [Bölüm 2.7.2](#272-data-sharing-attribute-clauses)' de açıklanmaktadır.

### <a name="271-threadprivate-directive"></a>2.7.1 threadprivate yönergesi

`threadprivate`Yönergesi, *değişken listesinde* belirtilen adlandırılmış dosya kapsamı, ad alanı kapsamı veya statik blok kapsamı değişkenlerini bir iş parçacığına getirir. *değişken listesi* , türü eksik olmayan bir değişkenlerin virgülle ayrılmış listesidir. Yönergesinin sözdizimi aşağıdaki gibidir `threadprivate` :

```cpp
#pragma omp threadprivate(variable-list) new-line
```

Bir değişkenin her kopyası bir `threadprivate` kez başlatılır, bu kopyaya ilk başvurudan önce programdaki belirtilmemiş bir noktada ve her zamanki şekilde başlatılır (yani, ana kopya programın seri yürütmesinde başlatılacağından). Bir nesneye bir değişkenin açık başlatıcısında başvuruluyorsa `threadprivate` ve nesnenin değeri değişkenin bir kopyasına ilk başvurudan önce değiştirilirse, davranış belirtilmemiş olur.

Herhangi bir özel değişkende olduğu gibi, bir iş parçacığı başka bir iş parçacığının nesnenin kopyasına başvurmamalıdır `threadprivate` . Programın seri bölgeleri ve ana bölgeleri sırasında, başvurular ana iş parçacığının nesnenin kopyasına olur.

İlk paralel bölge yürütüldükten sonra, `threadprivate` nesnelerdeki verilerin yalnızca dinamik iş parçacığı mekanizması devre dışı bırakılmışsa ve iş parçacıklarının sayısı tüm paralel bölgelerde değişmeden kalırsa kalıcı hale getirilmesi garanti edilir.

`threadprivate`Yönergeyle kısıtlamalar aşağıdaki gibidir:

- `threadprivate`Dosya kapsamı veya ad alanı kapsamı değişkenlerine yönelik bir yönerge, herhangi bir tanım veya bildirimin dışında görünmelidir ve listesindeki değişkenlerin herhangi birine ait tüm başvuruları sözcüksel olarak önünde olmalıdır.

- Dosya veya ad alanı kapsamındaki bir yönergenin *değişken listesindeki* her değişken `threadprivate` , yönergeden önce gelen dosya veya ad alanı kapsamındaki bir değişken bildirimine başvurmalıdır.

- `threadprivate`Statik blok kapsamı değişkenlerine yönelik bir yönerge, iç içe kapsamda değil, değişkenin kapsamında görünmelidir. Yönerge, listesindeki değişkenlerin herhangi birine yapılan tüm başvuruları sözcüksel olarak önüne almalıdır.

- Blok kapsamındaki bir yönergenin *değişken listesindeki* her değişken, `threadprivate` yönergeden önce gelen bir değişken bildirimine başvurmalıdır. Değişken bildirimi statik depolama sınıfı belirticisini kullanmalıdır.

- Bir değişken bir `threadprivate` çeviri birimindeki yönergede belirtilmişse, `threadprivate` bildirildiği her çeviri birimindeki bir yönergede belirtilmelidir.

- Bir `threadprivate` değişken,,, `copyin` `copyprivate` `schedule` `num_threads` veya `if` yan tümcesi dışında herhangi bir yan tümce içinde görünmemelidir.

- Bir `threadprivate` değişkenin adresi bir adres sabiti değildir.

- `threadprivate`Değişken, tamamlanmamış bir tür veya başvuru türüne sahip olmamalıdır.

- `threadprivate`Pod olmayan sınıf türüne sahip bir değişken, açık bir başlatıcı ile bildirilirse, erişilebilir ve belirsiz bir kopya oluşturucusuna sahip olmalıdır.

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

Bir paralel veya iş paylaşım yapısıyla karşılaşıldığında ve değişken bir paylaşım özniteliği yan tümcesinde veya yönergesinde belirtilmemişse, değişken `threadprivate` paylaşılır. Paralel bir bölgenin dinamik kapsamı içinde belirtilen statik değişkenler paylaşılır. Yığın ile ayrılmış bellek (örneğin, `malloc()` C veya c++ ' da veya **`new`** c++ ' ta işleç) paylaşılır. (Ancak, bu belleğin işaretçisi özel veya paylaşılan olabilir.) Paralel bir bölgenin dinamik kapsamı içinde belirtilen otomatik depolama süresine sahip değişkenler özeldir.

Yan tümcelerinin çoğu, görünür olan değişkenlerin virgülle ayrılmış bir listesi olan *değişken listesi* bağımsız değişkenini kabul eder. Bir veri paylaşımı öznitelik yan tümcesinde başvurulan bir değişkenin bir şablondan türetilmiş bir türü varsa ve programda bu değişkene başka bir başvuru yoksa, davranış tanımsızdır.

Yönerge yan tümceleri içinde görünen tüm değişkenler görünür olmalıdır. Yan tümceler gerektiği şekilde tekrarlanabilir, ancak bir değişken birden fazla yan tümce içinde belirtilemez, ancak bir değişken hem a hem de `firstprivate` `lastprivate` yan tümcesinde belirlenebilir.

Aşağıdaki bölümlerde veri paylaşımı özniteliği yan tümceleri açıklanır:

- [özelleştirme](#2721-private)
- [firstprivate](#2722-firstprivate)
- [lastprivate](#2723-lastprivate)
- [Paylaşılan](#2724-shared)
- [default](#2725-default)
- [reduction](#2726-reduction)
- [copyin](#2727-copyin)
- [copyprivate](#2728-copyprivate)

#### <a name="2721-private"></a>2.7.2.1 private

`private`Yan tümcesi, değişken listesindeki değişkenleri bir takımda bulunan her iş parçacığına özel olacak şekilde bildirir. `private`Yan tümcesinin sözdizimi şöyledir:

```cpp
private(variable-list)
```

Yan tümcesinde belirtilen bir değişkenin davranışı aşağıdaki gibidir `private` . Yapı için otomatik depolama süresine sahip yeni bir nesne ayrılır. Yeni nesnenin boyutu ve hizalaması, değişkenin türüne göre belirlenir. Bu ayırma, ekipteki her iş parçacığı için bir kez gerçekleşir ve gerekirse bir sınıf nesnesi için varsayılan oluşturucu çağrılır; Aksi takdirde, ilk değer belirsiz olur.  Değişkenin başvurduğu özgün nesne, yapı girişi sırasında belirsiz bir değere sahiptir, yapının dinamik kapsamı içinde değiştirilmemelidir ve yapıdan çıkıldığında belirsiz bir değere sahip olur.

Yönerge yapısının sözlü kapsamı içinde, değişkeni iş parçacığı tarafından ayrılan yeni özel nesneye başvurur.

Yan tümcesine yönelik kısıtlamalar `private` aşağıdaki gibidir:

- Bir yan tümcesinde belirtilen sınıf türüne sahip bir değişken `private` , erişilebilir, belirsiz bir varsayılan oluşturucuya sahip olmalıdır.

- Bir yan tümcesinde belirtilen değişken, bir `private` **`const`** üyesi olan bir sınıf türüne sahip olmadığı takdirde nitelenmiş türde olmamalıdır `mutable` .

- Bir yan tümcesinde belirtilen değişken, `private` tamamlanmamış bir tür veya başvuru türüne sahip olmamalıdır.

- `reduction`Bir yönergenin yan tümcesinde görünen değişkenler, `parallel` `private` paralel yapıyı bağlayan iş paylaşımı yönergesinde bir yan tümce içinde belirtilemez.

#### <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

`firstprivate`Yan tümcesi, yan tümcesinin sağladığı işlevselliğin bir üst kümesini sağlar `private` . `firstprivate`Yan tümcesinin sözdizimi şöyledir:

```cpp
firstprivate(variable-list)
```

*Değişken listesinde* belirtilen değişkenlerde `private` , [Bölüm 2.7.2.1](#2721-private)' de açıklandığı gibi yan tümce semantiği vardır. Başlatma veya oluşturma, iş parçacığının yapının yürütülmesinden önce iş parçacığı başına bir kez yapılmış gibi olur. Paralel bir `firstprivate` yapı üzerindeki bir yan tümce için, yeni özel nesnenin başlangıçtaki değeri, onunla karşılaştığı iş parçacığının paralel yapısıyla hemen önce var olan özgün nesnenin değeridir. İş paylaşımı yapısında bir `firstprivate` yan tümce için, iş paylaşımı yapısını yürüten her iş parçacığının yeni özel nesnesinin ilk değeri, aynı iş parçacığının iş paylaşım yapısıyla karşılaştığı zaman noktadan önce var olan özgün nesnenin değeridir. Ayrıca, C++ nesneleri için, her iş parçacığının yeni özel nesnesi özgün nesneden oluşturulan kopyadır.

Yan tümcesine yönelik kısıtlamalar `firstprivate` aşağıdaki gibidir:

- Bir yan tümcesinde belirtilen değişken, `firstprivate` tamamlanmamış bir tür veya başvuru türüne sahip olmamalıdır.

- Olarak belirtilen bir sınıf türüne sahip bir değişken `firstprivate` , erişilebilir, belirsiz bir kopya oluşturucusuna sahip olmalıdır.

- Bir paralel bölge içinde özel olan veya `reduction` bir yönergenin yan tümcesinde görünen değişkenler, `parallel` `firstprivate` paralel yapıyı bağlayan iş paylaşımı yönergesinin yan tümcesinde belirtilemez.

#### <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

`lastprivate`Yan tümcesi, yan tümcesinin sağladığı işlevselliğin bir üst kümesini sağlar `private` . `lastprivate`Yan tümcesinin sözdizimi şöyledir:

```cpp
lastprivate(variable-list)
```

*Değişken listesinde* belirtilen değişkenlerin `private` yan tümce anlamları. Yönergede bir `lastprivate` iş paylaşımı yapısını tanımlayan bir yan tümce göründüğünde, `lastprivate` ilişkili döngünün sıralı son yinelemesinden her bir değişkenin değeri veya sözcüksel son bölüm yönergesi değişkenin özgün nesnesine atanır. Veya yönergesinin son yinelemesi tarafından bir değer atanmamış değişkenler veya yönergesinin, `for` `parallel for` veya yönergesinin en son tekrarında `sections` `parallel sections` belirsiz değerler vardır. Atanmamış alt nesnelerin, yapı sonrasında belirsiz bir değeri de vardır.

Yan tümcesine yönelik kısıtlamalar `lastprivate` aşağıdaki gibidir:

- İçin tüm kısıtlamalar `private` geçerlidir.

- Olarak belirtilen bir sınıf türüne sahip bir değişken `lastprivate` , erişilebilir, belirsiz bir kopya atama işlecine sahip olmalıdır.

- Bir paralel bölge içinde özel olan veya `reduction` bir yönergenin yan tümcesinde görünen değişkenler, `parallel` `lastprivate` paralel yapıyı bağlayan iş paylaşımı yönergesinin yan tümcesinde belirtilemez.

#### <a name="2724-shared"></a>2.7.2.4 shared

Bu yan tümce, bir takımda bulunan tüm iş parçacıkları arasındaki *değişken listesinde* görünen değişkenleri paylaşır. Bir ekibin içindeki tüm iş parçacıkları, değişkenler için aynı depolama alanına erişir `shared` .

`shared`Yan tümcesinin sözdizimi şöyledir:

```cpp
shared(variable-list)
```

#### <a name="2725-default"></a>2.7.2.5 default

`default`Yan tümcesi, kullanıcının değişkenlerin veri paylaşım özniteliklerini etkilemesini sağlar. `default`Yan tümcesinin sözdizimi şöyledir:

```cpp
default(shared | none)
```

Belirtmek `default(shared)` `shared` , `threadprivate` veya nitelenmediği durumlar dışında, bir yan tümcesindeki her bir görünür değişkeni açıkça listelemek için eşdeğerdir **`const`** . Açık bir yan tümce yokluğunda `default` , varsayılan davranış belirtilmişse ile aynıdır `default(shared)` .

Belirtmek `default(none)` için, paralel yapının sözcük biçiminde bir değişkene her başvuru için aşağıdakilerden en az birinin doğru olması gerekir:

- Değişken, başvuruyu içeren bir yapının veri paylaşımı özniteliği yan tümcesinde açıkça listelenir.

- Değişken, paralel yapı içinde bildirilmiştir.

- Değişkeni `threadprivate` .

- Değişkenin **`const`** nitelenmiş bir türü vardır.

- Değişkeni, `for` bir veya yönergesini hemen izleyen bir döngü için döngü denetim değişkenidir `for` `parallel for` ve değişken başvurusu döngünün içinde görünür.

Bir `firstprivate` `lastprivate` iliştirilmiş yönergesinin,, veya yan tümcesindeki bir değişkeni belirtmek `reduction` kapsayan bağlamdaki değişkene örtülü başvuruya neden olur. Bu tür örtük başvurular, yukarıda listelenen gereksinimlere de tabidir.

Yönergede yalnızca tek bir `default` yan tümce belirtilebilir `parallel` .

Bir değişkenin varsayılan veri paylaşımı özniteliği `private` , `firstprivate` `lastprivate` `reduction` `shared` Aşağıdaki örnekte gösterildiği gibi,,, ve yan tümceleri kullanılarak geçersiz kılınabilir:

```cpp
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```

#### <a name="2726-reduction"></a>2.7.2.6 reduction

Bu yan tümce, işleç *op*ile *değişken listesinde*görünen skaler değişkenlerde bir azalma gerçekleştirir. `reduction`Yan tümcesinin sözdizimi şöyledir:

`reduction(`*op* `:` *değişken listesi*`)`

Aşağıdaki formlardan birine sahip bir ifade için genellikle bir azaltma belirtilir:

- *x* `=` *x* *op* *Expr*
- *x* *binop* `=` *Expr*
- *x* `=` *Expr* *op* *x* (çıkarma hariç)
- *x*`++`
- `++` *x*
- *x*`--`
- `--` *x*

burada:

*x*<br/>
Listede belirtilen azaltma değişkenlerinden biri.

*değişken listesi*<br/>
Skalar azaltma değişkenlerinin virgülle ayrılmış listesi.

*ifadeyi*<br/>
*X*başvurusu olmayan skaler türü olan bir ifade.

*üs*<br/>
Aşırı yüklenmiş bir işleç değil,,,,, `+` `*` `-` `&` `^` `|` , `&&` , veya `||` .

*binop*<br/>
Aşırı yüklenmiş bir operatör değil,,,,, `+` `*` `-` `&` `^` veya `|` .

Aşağıda yan tümcesinin bir örneği verilmiştir `reduction` :

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

Örnekte gösterildiği gibi, bir işleç bir işlev çağrısının içinde gizli olabilir. Kullanıcı, `reduction` yan tümcesinde belirtilen işlecin azaltma işlemiyle eşleştiğinden dikkatli olmalıdır.

İşlecin sağ işleneninde `||` Bu örnekteki yan etkileri olmasa da, bunlara izin verilir, ancak dikkatli olarak kullanılmalıdır. Bu bağlamda, döngünün sıralı yürütmesi sırasında gerçekleşmeyecek olan bir yan etkisi paralel yürütme sırasında gerçekleşebilir. Bu fark, yineleme yürütme sırası belirsiz olduğu için oluşabilir.

İşleci, azaltma için derleyici tarafından kullanılan özel değişkenlerin başlangıç değerini belirlemede ve sonlandırma işlecini belirlemede kullanılır. İşleci açıkça belirtmek, azaltma bildiriminin yapının sözcük dışı olmasını sağlar. Yönergede herhangi bir sayıda `reduction` tümce belirlenebilir, ancak bu yönerge için en fazla bir yan tümce içinde bir değişken görünebilir `reduction` .

*Değişken listesindeki* her değişkenin özel bir kopyası, yan tümcesi kullanılmış gibi her bir iş parçacığı için bir tane oluşturulur `private` . Özel kopya işlecine göre başlatılır (aşağıdaki tabloya bakın).

`reduction`Yan tümcesinin belirtildiği bölgenin sonunda, özgün nesne, özgün değerini, belirtilen işleci kullanarak özel kopyaların her birinin son değeriyle birleştirmenin sonucunu yansıtacak şekilde güncelleştirilir. Azaltma işleçleri tüm ilişkilendirilebilir (çıkarma hariç) ve derleyici son değerin hesaplamasını serbestçe yeniden ilişkilendirebilirsiniz. (Çıkarma azaltmanın kısmi sonuçları, son değeri oluşturmak için eklenir.)

İlk iş parçacığı kapsayan yan tümcesine ulaştığında özgün nesnenin değeri belirsiz hale gelir ve azaltma hesaplaması tamamlanana kadar bu şekilde kalır.  Normalde hesaplama, yapının sonunda tamamlanacaktır; Ancak `reduction` yan tümce de uygulanmış bir yapı üzerinde kullanılıyorsa `nowait` , tüm iş parçacıklarının yan tümcesini tamamladığına emin olmak için bir engel eşitlemesi gerçekleştirilene kadar özgün nesnenin değeri belirsiz olarak kalır `reduction` .

Aşağıdaki tabloda, geçerli olan işleçler ve bunların kurallı başlatma değerleri listelenmektedir. Gerçek başlatma değeri, azaltma değişkeninin veri türüyle tutarlı olacak.

|İşleç|Başlatma|
|--------------|--------------------|
|`+`|0|
|`*`|1|
|`-`|0|
|`&`|~ 0|
|`|`|0|
|`^`|0|
|`&&`|1|
|`||`|0|

Yan tümcesine yönelik kısıtlamalar `reduction` aşağıdaki gibidir:

- `reduction`Yan tümcesindeki değişkenlerin türü azaltma işleci için, işaretçi türleri ve başvuru türleri hiçbir şekilde izin verilmeyen durumlar dışında geçerli olmalıdır.

- Yan tümcesinde belirtilen bir değişken `reduction` **`const`** nitelenmemiş olmalıdır.

- Bir paralel bölge içinde özel olan veya `reduction` bir yönergenin yan tümcesinde görünen değişkenler, `parallel` `reduction` paralel yapıyı bağlayan iş paylaşımı yönergesinin yan tümcesinde belirtilemez.

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

`copyin`Yan tümcesi, `threadprivate` paralel bölgeyi yürüten ekipteki her iş parçacığının değişkenlerine aynı değeri atamak için bir mekanizma sağlar. Bir yan tümcesinde belirtilen her değişken için `copyin` , ekibin ana iş parçacığındaki değişkenin değeri, atama ölçütü olarak paralel bölgenin başlangıcında iş parçacığı özel kopyalara kopyalanır. `copyin`Yan tümcesinin sözdizimi şöyledir:

```cpp

copyin(
variable-list
)
```

Yan tümcesine yönelik kısıtlamalar `copyin` aşağıdaki gibidir:

- Yan tümcesinde belirtilen bir değişken `copyin` , erişilebilir, belirsiz bir kopya atama işlecine sahip olmalıdır.

- Yan tümcesinde belirtilen bir değişken `copyin` bir `threadprivate` değişken olmalıdır.

#### <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

`copyprivate`Yan tümcesi, bir ekibin bir üyesinden diğer üyelere bir değer yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Bu tür paylaşılan bir değişkenin sağlanması zor olur (örneğin, her düzeyde farklı bir değişken gerektiren bir özyineleme). `copyprivate`Yan tümce yalnızca `single` yönergede görünebilir.

`copyprivate`Yan tümcesinin sözdizimi şöyledir:

```cpp

copyprivate(
variable-list
)
```

`copyprivate`Bağımsız tümcesinin değişken listesi içindeki değişkenlerde etkisi, yapısıyla ilişkili yapılandırılmış bloğun yürütülmesi `single` ve ekipteki iş parçacıklarından önce, yapının sonunda engeli kapatmadan önce oluşur. Ardından, tüm diğer iş parçacıklarında, *değişken listesindeki*her bir değişken için, bu değişken yapının yapısal bloğunu yürüten iş parçacığında karşılık gelen değişkenin değeri ile tanımlanır (atama ölçütü olarak).

`copyprivate`Yan tümcesine yönelik kısıtlamalar aşağıdaki gibidir:

- Yan tümcesinde belirtilen bir değişken `copyprivate` `private` `firstprivate` , aynı yönerge için OR yan tümcesinde görünmemelidir `single` .

- `single`Bir `copyprivate` paralel bölgenin dinamik kapsamı içinde yan tümcesine sahip bir yönergeyle karşılaşılırsa, yan tümcesinde belirtilen tüm değişkenler `copyprivate` kapsayan bağlamda özel olmalıdır.

- Yan tümcesinde belirtilen bir değişken, `copyprivate` erişilebilir bir kopya atama işlecine sahip olmalıdır.

## <a name="28-directive-binding"></a>2,8 yönerge bağlama

Yönergelerin dinamik bağlamasının aşağıdaki kurallara uyması gerekir:

- `for`,, `sections` , `single` `master` Ve yönergeleri, `barrier` `parallel` `if` Bu yönergede mevcut olabilecek herhangi bir yan tümcenin değerinden bağımsız olarak, varsa dinamik olarak kapsayan öğesine bağlanır. Şu anda yürütülen bir paralel bölge yoksa, yönergeler yalnızca ana iş parçacığından oluşan bir takım tarafından yürütülür.

- `ordered`Yönergesi, dinamik olarak kapsayan öğesine bağlanır `for` .

- `atomic`Yönergesi `atomic` yalnızca geçerli takımın değil, tüm iş parçacıklarında yer alarak özel erişim uygular.

- `critical`Yönergesi `critical` yalnızca geçerli takımın değil, tüm iş parçacıklarında yer alarak özel erişim uygular.

- Bir yönerge hiçbir şekilde, en yakın dinamik olarak kapsayan herhangi bir yönergeyi hiçbir şekilde bağlanamaz `parallel` .

## <a name="29-directive-nesting"></a>2,9 Yönerge iç içe

Yönergelerin dinamik iç içe geçirilmesi aşağıdaki kurallara uymalıdır:

- Farklı bir şekilde `parallel` başka bir yönerge, `parallel` iç içe paralellik etkin olmadığı müddetçe, yalnızca geçerli iş parçacığından oluşan yeni bir takım oluşturur.

- `for`, `sections` ve `single` aynı şekilde bağlanan yönergelerin birbirini `parallel` iç içe olmasına izin verilmez.

- `critical`aynı ada sahip yönergelerin birbirini iç içe olmasına izin verilmez. Bu kısıtlamanın kilitlenmeyi engellemek için yeterli olmadığını unutmayın.

- `for`, ve yönergeleri,, ve alanları `sections` `single` `critical` `ordered` `master` bölgelere aynı şekilde bağlansa,, ve bölgelerine dinamik kapsam içinde izin verilmez `parallel` .

- `barrier``for` `ordered` `sections` `single` `master` `critical` yönergeler bölgelerle aynı şekilde bağlansa `parallel` ,,,, ve bölgelerinin dinamik kapsamında yönergelere izin verilmez.

- `master``for` `sections` `single` yönergeler, `master` `parallel` iş paylaşımı yönergeleriyle aynı şekilde bağlansa, ve yönergelerinin dinamik kapsamı içinde izin verilmez.

- `ordered``critical`yönergeler bölgelerle aynı şekilde bağlansa bölgelerin dinamik kapsamı içinde yönergelere izin verilmez `parallel` .

- Paralel bir bölgenin içinde dinamik olarak yürütülene izin verilen herhangi bir yönerge, paralel bir bölgenin dışında yürütüldüğünde de izin verilir. Kullanıcı tarafından belirtilen paralel bölgenin dışında dinamik olarak yürütüldüğünde, yönerge yalnızca ana iş parçacığından oluşan bir takım tarafından yürütülür.
