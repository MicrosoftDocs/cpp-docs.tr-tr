---
title: C++ AMP'ye Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, requirements
- C++ Accelerated Massive Parallelism, architecture
- C++ AMP
- C++ Accelerated Massive Parallelism, overview
- C++ Accelerated Massive Parallelism
ms.assetid: 9e593b06-6e3c-43e9-8bae-6d89efdd39fc
ms.openlocfilehash: 070f0885f11f29413aca3028d4f747e0edfd2413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663794"
---
# <a name="c-amp-overview"></a>C++ AMP'ye Genel Bakış

C++ Accelerated Massive Parallelism (C++ AMP) ayrı ekran kartı üzerindeki grafik işlemci birimi (GPU) gibi veri-paralel donanımlardan yararlanarak C++ kod yürütülmesini hızlandırır. C++ AMP kullanarak çok boyutlu veri algoritmaları kodlayabilirsiniz, böylece türdeş olmayan donanımda paralellik kullanarak yürütme hızlandırılabilir. C++ AMP programlama modeli çok boyutlu diziler, dizin oluşturma, bellek aktarımı, döşeme ve bir matematiksel işlev kitaplığını içerir. C++ AMP dil uzantılarını performansı artırabilirsiniz, böylece nasıl verilerin CPU'dan GPU'ya ve geri taşındığını kontrol etmek için kullanabilirsiniz.

## <a name="system-requirements"></a>Sistem Gereksinimleri

- Windows 7, Windows 8, Windows Server 2008 R2 veya Windows Server 2012

- DirectX 11 özelliği düzey 11.0 veya daha sonraki bir donanım

- Yazılım benzetmesi üzerinde hata ayıklama için Windows 8 veya Windows Server 2012 gereklidir. Donanım üzerinde hata ayıklamak için ekran kartınızın sürücülerini yüklemeniz gerekir. Daha fazla bilgi için [GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code).

## <a name="introduction"></a>Giriş

Aşağıdaki iki örnek C++ AMP birincil bileşenlerini göstermektedir. Karşılık gelen öğelerle iki tek boyutlu diziler eklemek istediğinizi varsayalım. Örneğin, eklemek isteyebilirsiniz `{1, 2, 3, 4, 5}` ve `{6, 7, 8, 9, 10}` edinme `{7, 9, 11, 13, 15}`. C++ AMP kullanmadan sayıları toplamak ve sonuçları görüntülemek için aşağıdaki kodu yazabilirsiniz.

```cpp
#include <iostream>

void StandardMethod() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    for (int idx = 0; idx < 5; idx++)
    {
        sumCPP[idx] = aCPP[idx] + bCPP[idx];
    }

    for (int idx = 0; idx < 5; idx++)
    {
        std::cout << sumCPP[idx] << "\n";
    }
}
```

Kodun önemli bölümleri aşağıdaki gibidir:

- Veri: Veri üç diziden oluşur. Tümü aynı boyut sayısına (bir) ve uzunluğa (beş) sahiptir.

- Yineleme: İlk `for` döngüsü dizilerde öğelerin arasında dolaşmak için bir mekanizma sağlar. Toplamları hesaplamak için yürütmek istediğiniz kod ilk bulunan `for` blok.

- Dizin: `idx` değişkeni dizilerin tek tek öğelerine erişir.

C++ AMP kullanarak, aşağıdaki kodu yerine yazabilirsiniz.

```cpp
#include <amp.h>
#include <iostream>
using namespace concurrency;

const int size = 5;

void CppAmpMethod() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[size];

    // Create C++ AMP objects.
    array_view<const int, 1> a(size, aCPP);
    array_view<const int, 1> b(size, bCPP);
    array_view<int, 1> sum(size, sumCPP);
    sum.discard_data();

    parallel_for_each(
        // Define the compute domain, which is the set of threads that are created.
        sum.extent,
        // Define the code to run on each thread on the accelerator.
        [=](index<1> idx) restrict(amp) {
            sum[idx] = a[idx] + b[idx];
        }
    );

    // Print the results. The expected output is "7, 9, 11, 13, 15".
    for (int i = 0; i < size; i++) {
        std::cout << sum[i] << "\n";
    }
}
```

Aynı temel öğeler vardır, ancak C++ AMP yapıları kullanılır:

- Veri: C++ dizilerini üç C++ AMP oluşturmak için kullandığınız [array_view](../../parallel/amp/reference/array-view-class.md) nesneleri. Oluşturmak için 4 değer sağlarsınız bir `array_view` nesne: veri değerleri, boyut, öğe türü ve uzunluğunu `array_view` her boyutundaki nesne. Boyut sayısı ve türü, tür parametreleri geçirilir. Veri ve uzunluk Oluşturucu parametreler olarak geçirilir. Bu örnekte, oluşturucuya iletilen C++ dizisi tek boyutlu. Boyut sayısı ve uzunluğu dikdörtgen şeklindeki verileri oluşturmak için kullanılan `array_view` nesnesi ve veri değerleri diziyi doldurmak için kullanılır. Ayrıca çalışma zamanı kitaplığı içeren [array sınıfı](../../parallel/amp/reference/array-class.md), benzer bir arabirim olduğu `array_view` sınıfı ve bu makalenin sonraki bölümlerinde ele alınmıştır.

- Yineleme: [parallel_for_each işlevi (C++ AMP)](reference/concurrency-namespace-functions-amp.md#parallel_for_each) veri öğeleri boyunca yineleme için bir mekanizma sağlar veya *hesaplama alanı*. Bu örnekte, hesaplama alanı tarafından belirtilen `sum.extent`. Yürütmek istediğiniz kod bir lambda ifadesinde bulunan veya *çekirdek işlevi*. `restrict(amp)` Yalnızca C++ AMP'nin hızlandırabileceği C++ dilinin alt kullanıldığını gösterir.

- Dizin: [index sınıfı](../../parallel/amp/reference/index-class.md) değişken `idx`, bir boyut sayısı eşleştirilecek derecesi ile bildirilen `array_view` nesne. Dizini kullanarak, tek tek öğelerine erişebilirsiniz `array_view` nesneleri.

## <a name="shaping-and-indexing-data-index-and-extent"></a>Veri şekillendirme ve dizinleme: dizin ve kapsam

Veri değerlerini tanımlamalı ve verinin şeklini çekirdek kodu çalıştırmadan önce bildirme gerekir. Tüm verileri bir dizi olarak (dikdörtgen) olacak şekilde tanımlandı ve herhangi bir boyut (boyut sayısı) için bir dizi tanımlayabilirsiniz. Veriler, herhangi bir boyutta herhangi bir büyüklükte olabilir.

### <a name="index-class"></a>index Sınıfı

[İndex sınıfı](../../parallel/amp/reference/index-class.md) bir konumu belirtir `array` veya `array_view` her boyuttaki başlangıca olan uzaklığı tek bir nesneye Kapsüllenen nesne. Dizideki bir konuma eriştiğinizde, geçirdiğiniz bir `index` nesne dizinleme işlecine `[]`, bir tamsayı dizin listesi yerine. Kullanarak, her boyuttaki öğelere erişebilirsiniz [array:: operator() işleci](reference/array-class.md#operator_call) veya [array_view:: operator() işleci](reference/array-view-class.md#operator_call).

Aşağıdaki örnek, bir tek boyutlu üçüncü öğeyi belirten bir tek boyutlu bir dizin oluşturur. `array_view` nesne. Dizin üçüncü öğeyi yazdırmak için kullanılan `array_view` nesne. Çıktı 3'tür.

```cpp
int aCPP[] = {1, 2, 3, 4, 5};
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout << a[idx] << "\n";
// Output: 3
```

Aşağıdaki örnek, olan öğeyi belirten bir iki boyutlu bir dizin oluşturur. burada satır = 1 ve sütun 2'de bir iki boyutlu = `array_view` nesne. İlk parametre `index` oluşturucudur satır bileşeni ve ikinci parametre de sütun bileşenidir. Çıkış 6'dır.

```cpp
int aCPP[] = {1, 2, 3, 4, 5, 6};
array_view<int, 2> a(2, 3, aCPP);

index<2> idx(1, 2);

std::cout <<a[idx] << "\n";
// Output: 6
```

Aşağıdaki örnek, olan öğeyi belirten bir üç boyutlu bir dizin oluşturur. burada derinliği 0, satır = 1 ve sütun 3'te bir üç boyutlu = `array_view` nesne. İlk parametrenin derinlik bileşeni olduğundan, ikinci parametre satır bileşeni olduğu ve üçüncü parametre de sütun bileşenidir dikkat edin. Çıkış 8'dir.

```cpp
int aCPP[] = {
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};

array_view<int, 3> a(2, 3, 4, aCPP);

// Specifies the element at 3, 1, 0.
index<3> idx(0, 1, 3);

std::cout << a[idx] << "\n";
// Output: 8
```

### <a name="extent-class"></a>extent Sınıfı

[Extent sınıfı](../../parallel/amp/reference/extent-class.md) her boyutundaki verinin uzunluğunu belirtir `array` veya `array_view` nesne. Bir uzantı oluşturma ve oluşturmak için kullanmak bir `array` veya `array_view` nesne. Ayrıca, varolan bir ölçüde alabilirsiniz `array` veya `array_view` nesne. Aşağıdaki örnek her boyutunun kapsam uzunluğunu yazdırır bir `array_view` nesne.

```cpp
int aCPP[] = {
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};
// There are 3 rows and 4 columns, and the depth is two.
array_view<int, 3> a(2, 3, 4, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";
std::cout << "The number of rows is " << a.extent[1] << "\n";
std::cout << "The depth is " << a.extent[0] << "\n";
std::cout << "Length in most significant dimension is " << a.extent[0] << "\n";
```

Aşağıdaki örnek, oluşturur bir `array_view` aynı nesne boyutlarını önceki örnekte, ancak bu örnek nesne olarak kullandığı bir `extent` içinde belirli parametreler yerine nesne `array_view` Oluşturucusu.

```cpp
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";
std::cout << "The number of rows is " << a.extent[1] << "\n";
std::cout << "The depth is " << a.extent[0] << "\n";
```

## <a name="moving-data-to-the-accelerator-array-and-arrayview"></a>Veri hızlandırıcıya taşıma: array ve array_view

Veri hızlandırıcıya taşımakta kullanılan iki veri kapsayıcı çalışma zamanı kitaplığında tanımlanır. Bunlar [array sınıfı](../../parallel/amp/reference/array-class.md) ve [array_view sınıfı](../../parallel/amp/reference/array-view-class.md). `array` Nesne oluşturulduğunda verinin derin kopya oluşturan bir kapsayıcı sınıfı. `array_view` Veriyi çekirdek işlevi veriye eriştiğinde kopyalayan sarmalayıcı sınıfı. Veri kaynağı cihazda gerektiğinde veri geri kopyalanır.

### <a name="array-class"></a>array Sınıfı

Olduğunda bir `array` nesnesi oluşturulduğunda, veri kümesi için bir işaretçi içeren bir oluşturucu kullanırsanız, verileri bir derin kopyası Hızlandırıcı üzerinde yaratılır. Çekirdek işlevi Hızlandırıcı üzerindeki kopyada değişiklik yapar. Çekirdek işlevinin yürütülmesi tamamlandığında, veriyi kaynak veri yapısına geri kopyalamanız gerekir. Aşağıdaki örnek, bir vektör içindeki her öğeyi 10 ile çarpar. Çekirdek işlevi tamamlandıktan sonra `vector conversion operator` veriyi vektör nesnesine geri kopyalamak için kullanılır.

```cpp
std::vector<int> data(5);

for (int count = 0; count <5; count++)
{
    data[count] = count;
}

array<int, 1> a(5, data.begin(), data.end());

parallel_for_each(
    a.extent,
    [=, &a](index<1> idx) restrict(amp) {
        a[idx] = a[idx]* 10;
    });

data = a;
for (int i = 0; i < 5; i++)
{
    std::cout << data[i] << "\n";
}
```

### <a name="arrayview-class"></a>array_view Sınıfı

`array_view` Hemen hemen aynı üyelere sahiptir `array` sınıfı, ancak arka plandaki davranışı aynı değildir. Aktarılan veriler `array_view` Oluşturucusu çoğaltılmaz GPU üzerinde sahip olduğu gibi bir `array` Oluşturucusu. Bunun yerine, veri çekirdek işlev çalıştırıldığında hızlandırıcıya kopyalanır. Bu nedenle, iki oluşturursanız `array_view` aynı verileri kullanan nesneler her ikisi de `array_view` nesneleri aynı bellek alanına bakın. Bunu yaptığınızda, herhangi bir çok iş parçacıklı erişimi eşitlemeniz gerekir. Kullanmanın ana avantajı `array_view` sınıfı, yalnızca gerekli olduğunda veri taşınır.

### <a name="comparison-of-array-and-arrayview"></a>Array ve array_view karşılaştırması

Aşağıdaki tabloda benzerlikler özetler ve arasındaki farklar `array` ve `array_view` sınıfları.

|Açıklama|array sınıfı|array_view sınıfı|
|-----------------|-----------------|-----------------------|
|Boyut sayısı belirlendiğinde|Derleme zamanında.|Derleme zamanında.|
|Kapsam belirlendiğinde|Çalışma zamanında.|Çalışma zamanında.|
|Şekil|Dikdörtgen.|Dikdörtgen.|
|Veri depolama|Bir veri kapsayıcıdır.|Bir veri sarmalayıcıdır.|
|Kopyala|Tanım anında açık ve derin kopya.|Çekirdek işlevi kullanılarak erişildiğinde örtülü kopya.|
|Veri alma|Dizin verisini CPU iş parçacığında bir nesneye geri kopyalayarak.|Doğrudan erişerek `array_view` nesne veya çağırarak [array_view::synchronize metodu](reference/array-view-class.md#synchronize) orijinal kapsayıcıdan veri erişmeye devam etmek için.|

### <a name="shared-memory-with-array-and-arrayview"></a>Array ve array_view ile paylaşılan bellek

Paylaşılan bellek, CPU ve Hızlandırıcı tarafından erişilebilen bellektir. Paylaşılan bellek kullanımı ortadan kaldırır veya CPU ve Hızlandırıcı arasında veri kopyalama yükünü önemli ölçüde azaltır. Belleğin paylaşılmasına rağmen CPU ve Hızlandırıcı tarafından aynı anda erişilemez ve bunu yaparsanız, bu nedenle tanımsız davranışa neden olur.

`array` nesneleri paylaşılan belleğin kullanımı üzerinde ayrıntılı denetim ilgili Hızlandırıcı desteklerse belirtmek için kullanılabilir. Bir Hızlandırıcı paylaşılan belleği destekleyip desteklemediğini hızlandırıcının belirlenir [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) döndüren özellik **true** paylaşılan bellek destekliyorsa. Paylaşılan bellek destekleniyorsa, varsayılan [access_type numaralandırması](reference/concurrency-namespace-enums-amp.md#access_type) bellek ayırmaları hızlandırıcıda göre belirlenir `default_cpu_access_type` özelliği. Varsayılan olarak, `array` ve `array_view` nesneler aynı devralır `access_type` ilişkili birincil olarak `accelerator`.

Ayarlayarak [array::cpu_access_type veri üyesi](reference/array-class.md#cpu_access_type) özelliği bir `array` açıkça, böylece uygulamanın donanımının performans için en iyi duruma getirebilirsiniz alıştırma ayrıntılı nasıl paylaşılan bellek kullanılır, denetleyebilirsiniz Hesaplama çekirdeklerinin bellek erişim düzenlerini esas alarak özellikleri. Bir `array_view` aynı `cpu_access_type` olarak `array` ; ile ilişkili veya array_view veri kaynağı olmadan oluşturulursa, `access_type` öncelikle depoyu dağıtmaya neden olan ortamı etkiler. Bu ilk (CPU) ana bilgisayar tarafından erişilirse, CPU veri kaynağı ve paylaşımları üzerinde oluşturulmuş gibi diğer bir deyişle, ardından davranır `access_type` , `accelerator_view` yakalamayla ilişkilendirilen; ancak ilk olarak ancak tarafından erişilen bir `accelerator_view`, sanki olarak davranır üzerinde oluşturulan bir `array` üzerinde oluşturulan `accelerator_view` ve paylaşımları `array`'s `access_type`.

Aşağıdaki kod örneği, varsayılan hızlandırıcının paylaşılan belleği destekleyen ve ardından farklı cpu_access_type yapılandırmalarına sahip çeşitli diziler oluşturur olup olmadığını belirlemek gösterilmektedir.

```cpp
#include <amp.h>
#include <iostream>

using namespace Concurrency;

int main()
{
    accelerator acc = accelerator(accelerator::default_accelerator);

    // Early out if the default accelerator doesn’t support shared memory.
    if (!acc.supports_cpu_shared_memory)
    {
        std::cout << "The default accelerator does not support shared memory" << std::endl;
        return 1;
    }

    // Override the default CPU access type.
    acc.default_cpu_access_type = access_type_read_write

    // Create an accelerator_view from the default accelerator. The
    // accelerator_view inherits its default_cpu_access_type from acc.
    accelerator_view acc_v = acc.default_view;

    // Create an extent object to size the arrays.
    extent<1> ex(10);

    // Input array that can be written on the CPU.
    array<int, 1> arr_w(ex, acc_v, access_type_write);

    // Output array that can be read on the CPU.
    array<int, 1> arr_r(ex, acc_v, access_type_read);

    // Read-write array that can be both written to and read from on the CPU.
    array<int, 1> arr_rw(ex, acc_v, access_type_read_write);
}
```

## <a name="executing-code-over-data-parallelforeach"></a>Veriye göre kod yürütme: parallel_for_each

[Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) işlevi veriye karşı Hızlandırıcı üzerinde çalıştırmak istediğiniz kodu tanımlar `array` veya `array_view` nesne. Aşağıdaki kod bu konunun girişindeki göz önünde bulundurun.

```cpp
#include <amp.h>
#include <iostream>
using namespace concurrency;

void AddArrays() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5] = {0, 0, 0, 0, 0};

    array_view<int, 1> a(5, aCPP);
    array_view<int, 1> b(5, bCPP);
    array_view<int, 1> sum(5, sumCPP);

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
            sum[idx] = a[idx] + b[idx];
        }
    );

    for (int i = 0; i < 5; i++) {
        std::cout << sum[i] << "\n";
    }
}
```

`parallel_for_each` Yöntemi iki bağımsız değişken, bir hesaplama alanı ve bir lambda ifadesi alır.

*Hesaplama alanı* olduğu bir `extent` nesnesi veya bir `tiled_extent` paralel yürütmek için Yaratılacak iş parçacıkları kümesini tanımlayan nesne. Hesaplama etki alanındaki her öğe için bir iş parçacığı oluşturulur. Bu durumda, `extent` nesnesi tek boyutludur ve beş öğeye sahiptir. Bu nedenle, beş iş parçacığı başlatılır.

*Lambda ifadesi* her iş parçacığı üzerinde çalıştırılacak kodu tanımlar. Yakalama yan tümcesi `[=]`, lambda ifadesinin gövdesi, bu durumda olan değere göre yakalanan tüm değişkenlere erişimi olduğunu belirtir `a`, `b`, ve `sum`. Bu örnekte, tek boyutlu bir parametre listesi oluşturur `index` adlı değişken `idx`. Değerini `idx[0]` ilk iş parçacığında 0'dır ve sonraki her iş parçacığında bir artırılır. `restrict(amp)` Yalnızca C++ AMP'nin hızlandırabileceği C++ dilinin alt kullanıldığını gösterir.  Kısıtlama değiştiricisine sahip işlevlerin kısıtlamaları açıklanan [sınırla (C++ AMP)](../../cpp/restrict-cpp-amp.md). Daha fazla bilgi için bkz: [Lambda ifadesi söz dizimi](../../cpp/lambda-expression-syntax.md).

Lambda ifadesi yürütülecek kodu içerebilir veya ayrı bir çekirdek işlevi çağırabilir. Çekirdek işlevi içermelidir `restrict(amp)` değiştiricisi. Aşağıdaki örnek önceki örnekle eşdeğerdir ancak ayrı bir çekirdek işlevi çağırır.

```cpp
#include <amp.h>
#include <iostream>
using namespace concurrency;

void AddElements(
    index<1> idx,
    array_view<int, 1> sum,
    array_view<int, 1> a,
    array_view<int, 1> b) restrict(amp) {
    sum[idx] = a[idx] + b[idx];
}

void AddArraysWithFunction() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5] = {0, 0, 0, 0, 0};

    array_view<int, 1> a(5, aCPP);
    array_view<int, 1> b(5, bCPP);
    array_view<int, 1> sum(5, sumCPP);

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp) {
            AddElements(idx, sum, a, b);
        }
    );

    for (int i = 0; i < 5; i++) {
        std::cout << sum[i] << "\n";
    }
}
```

## <a name="accelerating-code-tiles-and-barriers"></a>Kodu hızlandırma: Döşeme ve Bariyerler

Döşeme kullanarak ek hızlandırma elde edebilirsiniz. Döşeme iş parçacıklarını eşit dikdörtgen altkümelere, böler veya *kutucukları*. Size uygun döşeme boyutunu veri kümenize ve Kodladığınız algoritması göre belirleyin. Her iş parçacığı için erişiminiz *genel* bir veri öğesi tam göreli konumunu `array` veya `array_view` erişim *yerel* göreceli dizinine ve döşemeye konumu. Dizin değerlerini Genelden yerele çevirmek için kod yazmanız gerekmez çünkü yerel dizin değerlerini kullanmak kodunuzu basitleştirir. Döşemeyi kullanmak için çağrı [extent::tile yöntemi](reference/extent-class.md#tile) hesaplama alanında `parallel_for_each` yöntemi ve kullanım bir [tiled_index](../../parallel/amp/reference/tiled-index-class.md) lambda ifadesindeki nesne.

Tipik uygulamalarda, başka bir yolla ilgili bir döşeme içindeki öğeler ve erişmek ve değerleri döşeme içindeki izlemek kod vardır. Kullanım [tile_static anahtar sözcüğü](../../cpp/tile-static-keyword.md) anahtar sözcüğü ve [tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait) bunu sağlamak için. Sahip bir değişken **tile_static** anahtar sözcüğü bir kapsamı bütün bir döşemedir sahiptir ve her döşeme için değişkenin bir örneği oluşturulur. Değişkene döşeme iş parçacığı erişimi eşitlenmesini işlemesi gerekir. [Tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait) döşemedeki tüm iş parçacıkları çağrıya ulaşıncaya kadar geçerli iş parçacığının yürütülmesini durdurur `tile_barrier::wait`. Döşeme içindeki değerleri kullanarak toplayabilirsiniz şekilde **tile_static** değişkenleri. Ardından tüm değerleri erişmesi gereken tüm hesaplamaları sonlandırabilirsiniz.

Aşağıdaki diyagram döşemeler şeklinde düzenlenmiş veri örnekleme, iki boyutlu bir dizi temsil eder.

![Döşenmiş kapsamın değerleri dizin](../../parallel/amp/media/camptiledgridexample.png "camptiledgridexample")

Aşağıdaki kod örneği önceki diyagramdaki örnekleme verisini kullanır. Kod her değeri döşemenin değerlerinin ortalaması ile değiştirir.

```cpp
// Sample data:
int sampledata[] = {
    2, 2, 9, 7, 1, 4,
    4, 4, 8, 8, 3, 4,
    1, 5, 1, 2, 5, 2,
    6, 8, 3, 2, 7, 2};

// The tiles:
// 2 2    9 7    1 4
// 4 4    8 8    3 4
//
// 1 5    1 2    5 2
// 6 8    3 2    7 2

// Averages:
int averagedata[] = {
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
};

array_view<int, 2> sample(4, 6, sampledata);

array_view<int, 2> average(4, 6, averagedata);

parallel_for_each(
    // Create threads for sample.extent and divide the extent into 2 x 2 tiles.
    sample.extent.tile<2,2>(),
        [=](tiled_index<2,2> idx) restrict(amp) {
        // Create a 2 x 2 array to hold the values in this tile.
        tile_static int nums[2][2];

        // Copy the values for the tile into the 2 x 2 array.
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];

        // When all the threads have executed and the 2 x 2 array is complete, find the average.
        idx.barrier.wait();
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];

        // Copy the average into the array_view.
        average[idx.global] = sum / 4;
    });

for (int i = 0; i <4; i++) {
    for (int j = 0; j <6; j++) {
        std::cout << average(i,j) << " ";
    }
    std::cout << "\n";
}

// Output:
// 3 3 8 8 3 3
// 3 3 8 8 3 3
// 5 5 2 2 4 4
// 5 5 2 2 4 4
```

## <a name="math-libraries"></a>Matematik kitaplıkları

C++ AMP, iki matematik kitaplığı içerir. Çift duyarlık Kitaplığı'nda [Concurrency::precise_math Namespace](../../parallel/amp/reference/concurrency-precise-math-namespace.md) çift duyarlıklı işlevler için destek sağlar. Donanımda çift duyarlık desteği yine de gereklidir tek duyarlıklı işlevler için de destek sağlar. İle uyumlu [C99 belirtimi (ISO/IEC 9899)](http://go.microsoft.com/fwlink/p/?linkid=225887). Hızlandırıcı tam çift duyarlık desteği sağlamalıdır. Değerini kontrol ederek mevcut olup olmadığını belirlemek [accelerator::supports_double_precision veri üyesi](reference/accelerator-class.md#supports_double_precision). Hızlı matematik kitaplığı, [Concurrency::fast_math Namespace](../../parallel/amp/reference/concurrency-fast-math-namespace.md), başka bir matematiksel işlevler kümesi içerir. Bu işlevler yalnızca Destek `float` işlenenler, daha çabuk yürütülürler ancak kitaplığındakiler kadar çift duyarlık matematik Kitaplığı'nda değildir. İşlevleri içerdiği \<amp_math.h > üstbilgi dosyasını ve tüm ile bildirilir `restrict(amp)`. İşlevler \<cmath > Üstbilgi dosyası her ikisini de kopyalayıp aktarılır `fast_math` ve `precise_math` ad alanları. **Kısıtlama** ayırt etmek için kullanılan anahtar sözcüğü \<cmath > sürümü ile C++ AMP sürüm. Aşağıdaki kodu kullanarak hızlı yöntemi hesaplama etki alanındaki her değerin 10 tabanında logaritmasını hesaplar.

```cpp
#include <amp.h>
#include <amp_math.h>
#include <iostream>
using namespace concurrency;

void MathExample() {

    double numbers[] = { 1.0, 10.0, 60.0, 100.0, 600.0, 1000.0 };
    array_view<double, 1> logs(6, numbers);

    parallel_for_each(
        logs.extent,
        [=] (index<1> idx) restrict(amp) {
            logs[idx] = concurrency::fast_math::log10(logs[idx]);
        }
    );

    for (int i = 0; i < 6; i++) {
        std::cout << logs[i] << "\n";
    }
}
```

## <a name="graphics-library"></a>Grafik kitaplığı

C++ AMP hızlandırılmış grafik programlama için tasarlanmış bir grafik kitaplığı içerir. Bu kitaplık sadece doğal grafik işlevselliği destekleyen cihazlarda kullanılır. Yöntemler [Concurrency::graphics Namespace](../../parallel/amp/reference/concurrency-graphics-namespace.md) ve içerdiği \<amp_graphics.h > üst bilgi dosyası. Grafik kitaplığı anahtar bileşenleri şunlardır:

- [texture sınıfı](../../parallel/amp/reference/texture-class.md): doku sınıfını kullanarak bellekten ya da bir dosyadan doku oluşturmak için kullanabilirsiniz. Dokular veri içerdikleri ve bunların atama ve kopya oluşumuna göre C++ Standart Kitaplığı kapsayıcıları benzer çünkü dizilerine benzer. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../../standard-library/stl-containers.md). Şablon parametreleri için `texture` öğe türü ve boyut sınıfı bulunur. Boyut sayısı 1, 2 veya 3 olabilir. Öğe türü, bu makalenin sonraki bölümlerinde açıklanan kısa vektör türlerinden biri olabilir.

- [writeonly_texture_view sınıfı](../../parallel/amp/reference/writeonly-texture-view-class.md): herhangi bir dokuya salt yazılır erişim sağlar.

- Kısa vektör kitaplığı: uzunluğu 2, 3 ve 4 temel alan kısa vektör türleri kümesi tanımlar **int**, `uint`, **float**, **çift**, [norm ](../../parallel/amp/reference/norm-class.md), veya [unorm](../../parallel/amp/reference/unorm-class.md).

## <a name="universal-windows-platform-uwp-apps"></a>Evrensel Windows Platformu (UWP) uygulamaları

Diğer C++ kitaplıkları gibi UWP uygulamalarında C++ AMP kullanabilirsiniz. Bu makaleler, C++, C#, Visual Basic veya JavaScript kullanılarak oluşturulan C++ AMP kodunu uygulamaları nasıl ekleyeceğinizi açıklar:

- [UWP Uygulamalarında C++ AMP Kullanma](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)

- [İzlenecek yol: C++ ve JavaScript çağırma temel bir Windows çalışma zamanı bileşeni oluşturma](http://go.microsoft.com/fwlink/p/?linkid=249077)

- [Bing Haritalar seyahat iyileştirici, JavaScript ve C++'ta bir pencere Store uygulaması](http://go.microsoft.com/fwlink/p/?linkid=249078)

- [C# kullanarak Windows çalışma zamanı C++ AMP kullanma](http://go.microsoft.com/fwlink/p/?linkid=249080)

- [C#, C++ AMP kullanma](http://go.microsoft.com/fwlink/p/?linkid=249081)

- [Yönetilen Koddan Yerel İşlevleri Çağırma](../../dotnet/calling-native-functions-from-managed-code.md)

## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP ve eşzamanlılık görselleştiricisi

Eşzamanlılık görselleştiricisi C++ AMP kod performansını çözümlemek için destek içerir. Bu makaleler, bu özellikleri açıklar:

- [GPU Etkinlik Grafiği](/visualstudio/profiling/gpu-activity-graph)

- [GPU Etkinliği (Disk Belleği)](/visualstudio/profiling/gpu-activity-paging)

- [GPU Etkinliği (Bu İşlem)](/visualstudio/profiling/gpu-activity-this-process)

- [GPU Etkinliği (Diğer İşlemler)](/visualstudio/profiling/gpu-activity-other-processes)

- [Kanallar (İş Parçacıkları Görünümü)](/visualstudio/profiling/channels-threads-view)

- [Eşzamanlılık görselleştiricisi ile C++ AMP kodunu analiz etme](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)

## <a name="performance-recommendations"></a>Performans önerileri

İşaretsiz tamsayılar sayılarda işaretli tam sayılarda önemli ölçüde daha iyi performansa sahip. Mümkün olduğunda, işaretsiz tamsayılar kullanmanızı öneririz.

## <a name="see-also"></a>Ayrıca Bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Lambda İfadesi Söz Dizimi](../../cpp/lambda-expression-syntax.md)<br/>
[Başvuru (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[Yerel kod Blog içinde paralel programlama](http://go.microsoft.com/fwlink/p/?linkid=238472)