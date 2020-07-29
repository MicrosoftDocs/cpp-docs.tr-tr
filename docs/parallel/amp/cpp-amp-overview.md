---
title: C++ AMP'ye Genel Bakış
ms.date: 11/19/2018
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, requirements
- C++ Accelerated Massive Parallelism, architecture
- C++ AMP
- C++ Accelerated Massive Parallelism, overview
- C++ Accelerated Massive Parallelism
ms.assetid: 9e593b06-6e3c-43e9-8bae-6d89efdd39fc
ms.openlocfilehash: 249170e1e29d3ca8c488d15be8fa4ccd2b9070c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222764"
---
# <a name="c-amp-overview"></a>C++ AMP'ye Genel Bakış

C++ Accelerated Massive Parallelism (C++ AMP), ayrı bir grafik kartında grafik işleme birimi (GPU) gibi veri paralel donanımlardan yararlanarak C++ kodunun yürütülmesini hızlandırır. C++ AMP kullanarak, çok boyutlu veri algoritmalarının kodlayarak, yürütmenin heterojen donanımda paralellik kullanarak hızlandırmasını sağlayabilirsiniz. C++ AMP programlama modeli çok boyutlu diziler, dizin oluşturma, bellek aktarımı, döşeme ve bir matematiksel işlev kitaplığını içerir. Performansı artırmak için, verilerin CPU 'dan GPU 'ya ve geri nasıl taşındığını denetlemek için C++ AMP dil uzantılarını kullanabilirsiniz.

## <a name="system-requirements"></a>Sistem Gereksinimleri

- Windows 7 veya üzeri

- Windows Server 2008 R2 veya sonraki sürümü

- DirectX 11 Özellik düzeyi 11,0 veya üzeri donanım

- Yazılım öykünücüsünde hata ayıklamak için Windows 8 veya Windows Server 2012 gereklidir. Donanımda hata ayıklama için, grafik kartınızın sürücülerini yüklemelisiniz. Daha fazla bilgi için bkz. [GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code).

- Not: AMP Şu anda ARM64 üzerinde desteklenmiyor.

## <a name="introduction"></a>Giriş

Aşağıdaki iki örnek C++ AMP birincil bileşenlerini gösterir. 2 1 boyutlu dizilerin karşılık gelen öğelerini eklemek istediğinizi varsayın. Örneğin, eklemek `{1, 2, 3, 4, 5}` ve `{6, 7, 8, 9, 10}` almak isteyebilirsiniz `{7, 9, 11, 13, 15}` . C++ AMP kullanmadan, sayıları eklemek ve sonuçları göstermek için aşağıdaki kodu yazabilirsiniz.

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

- Veri: veriler üç dizilerden oluşur. Hepsi aynı dereceye (bir) ve uzunluğa (beş) sahiptir.

- Yineleme: ilk **`for`** döngü, dizideki öğeler arasında yineleme yapmak için bir mekanizma sağlar. Toplamları hesaplamak için yürütmek istediğiniz kod ilk **`for`** blokta bulunur.

- Dizin: `idx` değişken, dizilerin ayrı öğelerine erişir.

C++ AMP kullanarak, bunun yerine aşağıdaki kodu yazabilirsiniz.

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

Aynı temel öğeler mevcuttur, ancak C++ AMP yapılar kullanılır:

- Veri: C++ dizilerini, üç C++ AMP [array_view](../../parallel/amp/reference/array-view-class.md) nesnesi oluşturmak için kullanırsınız. Bir nesne oluşturmak için dört değer sağlarsınız `array_view` : veri değerleri, derece, öğe türü ve `array_view` her boyuttaki nesnenin uzunluğu. Rank ve Type tür parametreleri olarak geçirilir. Veri ve uzunluk, Oluşturucu parametreleri olarak geçirilir. Bu örnekte, oluşturucuya geçirilen C++ dizisi tek boyutlu olur. Derece ve uzunluğu, nesnedeki verilerin dikdörtgen şeklini oluşturmak için kullanılır `array_view` ve veri değerleri diziyi dolduracak şekilde kullanılır. Çalışma zamanı kitaplığı, sınıfa benzeyen ve bu makalenin ilerleyen kısımlarında ele alınan bir arabirime sahip [dizi sınıfını](../../parallel/amp/reference/array-class.md)da içerir `array_view` .

- Yineleme: [parallel_for_each işlevi (C++ amp)](reference/concurrency-namespace-functions-amp.md#parallel_for_each) , veri öğeleri veya *işlem etki alanı*arasında yineleme için bir mekanizma sağlar. Bu örnekte, işlem etki alanı tarafından belirtilir `sum.extent` . Çalıştırmak istediğiniz kod bir lambda ifadesinde veya *çekirdek işlevinde*bulunur. `restrict(amp)`Yalnızca C++ amp hızlandırabilecek C++ dilinin alt kümesinin kullanıldığını gösterir.

- Dizin: [Dizin sınıfı](../../parallel/amp/reference/index-class.md) değişkeni, `idx` nesnesinin derecesine uyacak şekilde bir ile birlikte bildirilmiştir `array_view` . Dizinini kullanarak, nesnelerin ayrı öğelerine erişebilirsiniz `array_view` .

## <a name="shaping-and-indexing-data-index-and-extent"></a>Verileri şekillendirme ve dizin oluşturma: Dizin ve kapsam

Çekirdek kodunu çalıştırmadan önce veri değerlerini tanımlamanız ve verilerin şeklini bildirmeniz gerekir. Tüm veriler bir dizi (dikdörtgen) olarak tanımlanır ve diziyi herhangi bir dereceye (boyut sayısı) sahip olacak şekilde tanımlayabilirsiniz. Veriler, boyutların herhangi birinde herhangi bir boyutta olabilir.

### <a name="index-class"></a>index Sınıfı

[Index sınıfı](../../parallel/amp/reference/index-class.md) , `array` `array_view` her boyuttaki kaynaktan gelen sapmayı tek bir nesnede kapsülleyerek veya nesnesinde bir konum belirtir. Dizideki bir konuma eriştiğinizde, bir `index` nesneyi `[]` tamsayı dizinleri listesi yerine dizin oluşturma işlecine geçitirsiniz. Her boyuttaki öğelere [Array:: operator () işlecini](reference/array-class.md#operator_call) veya [array_view:: operator () işlecini](reference/array-view-class.md#operator_call)kullanarak erişebilirsiniz.

Aşağıdaki örnek, tek boyutlu bir nesnede üçüncü öğeyi belirten tek boyutlu bir dizin oluşturur `array_view` . Dizin, nesnedeki üçüncü öğeyi yazdırmak için kullanılır `array_view` . Çıktı 3 ' dir.

```cpp
int aCPP[] = {1, 2, 3, 4, 5};
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout << a[idx] << "\n";
// Output: 3
```

Aşağıdaki örnek, iki boyutlu bir nesnede satır = 1 ve sütun = 2 olan öğeyi belirten iki boyutlu bir dizin oluşturur `array_view` . `index`Oluşturucudaki ilk parametre satır bileşenidir ve ikinci parametre sütun bileşenidir. Çıktı 6 ' dır.

```cpp
int aCPP[] = {1, 2, 3, 4, 5, 6};
array_view<int, 2> a(2, 3, aCPP);

index<2> idx(1, 2);

std::cout <<a[idx] << "\n";
// Output: 6
```

Aşağıdaki örnek, derinlik = 0, satır = 1 ve üç boyutlu bir nesnede sütun = 3 olan öğeyi belirten üç boyutlu bir dizin oluşturur `array_view` . İlk parametrenin derinlik bileşeni olduğuna, ikinci parametrenin ise satır bileşeni olduğuna ve üçüncü parametrenin ise sütun bileşeninden olduğuna dikkat edin. Çıktı 8 ' dir.

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

[Kapsam sınıfı](../../parallel/amp/reference/extent-class.md) , veya nesnesinin her boyutundaki verilerin uzunluğunu belirtir `array` `array_view` . Bir kapsam oluşturabilir ve bunu bir veya nesnesi oluşturmak için kullanabilirsiniz `array` `array_view` . Ayrıca, varolan bir veya nesnesinin kapsamını da alabilirsiniz `array` `array_view` . Aşağıdaki örnek, bir nesnenin her boyutunda kapsamın uzunluğunu yazdırır `array_view` .

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

Aşağıdaki örnek `array_view` , önceki örnekteki nesneyle aynı boyutlara sahip bir nesne oluşturur, ancak bu örnek `extent` oluşturucuda açık Parametreler kullanmak yerine bir nesne kullanır `array_view` .

```cpp
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";
std::cout << "The number of rows is " << a.extent[1] << "\n";
std::cout << "The depth is " << a.extent[0] << "\n";
```

## <a name="moving-data-to-the-accelerator-array-and-array_view"></a>Verileri Hızlandırıcı: dizi ve array_view taşıma

Hızlandırıcıya veri taşımak için kullanılan iki veri kapsayıcısı, çalışma zamanı kitaplığı 'nda tanımlanmıştır. Bunlar [dizi sınıfıdır](../../parallel/amp/reference/array-class.md) ve [array_view sınıfıdır](../../parallel/amp/reference/array-view-class.md). `array`Sınıfı, nesne oluşturulduğunda verilerin derin bir kopyasını oluşturan bir kapsayıcı sınıfıdır. `array_view`Sınıfı, çekirdek işlevi verilere eriştiğinde verileri kopyalayan bir sarmalayıcı sınıftır. Kaynak cihazda veri gerektiğinde veriler geri kopyalanır.

### <a name="array-class"></a>array Sınıfı

Bir `array` nesne oluşturulduğunda, veri kümesine yönelik bir işaretçi içeren bir Oluşturucu kullanırsanız, hızlandırıcının derin bir kopyası oluşturulur. Çekirdek işlevi, hızlandırıcının kopyasını değiştirir. Çekirdek işlevinin yürütülmesi bittiğinde, verileri kaynak veri yapısına geri kopyalamanız gerekir. Aşağıdaki örnek, vektör içindeki her öğeyi 10 ile çarpar. Çekirdek işlevi bittikten sonra, `vector conversion operator` verileri vektör nesnesine geri kopyalamak için kullanılır.

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

### <a name="array_view-class"></a>array_view Sınıfı

, `array_view` Sınıfıyla neredeyse aynı üyelere sahiptir `array` , ancak temeldeki davranış aynı değildir. Oluşturucuya geçirilen veriler, `array_view` bir Oluşturucu ile olduğu IÇIN GPU üzerinde çoğaltılmaz `array` . Bunun yerine, çekirdek işlevi yürütüldüğünde veriler hızlandırıcıya kopyalanır. Bu nedenle, `array_view` aynı verileri kullanan iki nesne oluşturursanız, her iki nesne de `array_view` aynı bellek alanına başvurur. Bunu yaptığınızda, çok iş parçacıklı erişimi eşitlemeniz gerekir. Sınıfını kullanmanın ana avantajı, `array_view` verilerin yalnızca gerekli olması halinde taşınabilme amaçlıdır.

### <a name="comparison-of-array-and-array_view"></a>Dizi ve array_view karşılaştırması

Aşağıdaki tabloda ve sınıfları arasındaki benzerlikler ve farklar özetlenmektedir `array` `array_view` .

|Açıklama|array sınıfı|array_view sınıfı|
|-----------------|-----------------|-----------------------|
|Derece saptandığı zaman|Derleme zamanında.|Derleme zamanında.|
|Kapsam belirlendiğinde|Çalışma zamanında.|Çalışma zamanında.|
|Şekil|L.|L.|
|Veri depolama|Bir veri kapsayıcısıdır.|Bir veri sarmalayıcısıdır.|
|Kopyala|Tanımda açık ve derin kopya.|Çekirdek işlevi tarafından erişildiğinde örtülü kopya.|
|Veri alımı|Dizi verilerini, CPU iş parçacığındaki bir nesneye geri kopyalayarak.|Nesnenin doğrudan erişimine `array_view` veya [array_view:: Synchronize metodunu](reference/array-view-class.md#synchronize) çağırarak özgün kapsayıcıdaki verilere erişmeye devam edin.|

### <a name="shared-memory-with-array-and-array_view"></a>Dizi ve array_view paylaşılan bellek

Paylaşılan bellek, hem CPU hem de hızlandırıcı tarafından erişilebilen bellektir. Paylaşılan bellek kullanımı, CPU ve Hızlandırıcı arasında veri kopyalama yükünü ortadan kaldırır veya önemli ölçüde azaltır. Bellek paylaşılsa da, hem CPU hem de hızlandırıcı tarafından aynı anda erişilemez ve bunun yapılması tanımsız davranışlara neden olur.

`array`ilişkili Hızlandırıcı destekliyorsa, paylaşılan belleğin kullanımı üzerinde ayrıntılı denetim belirtmek için nesneler kullanılabilir. Hızlandırıcının paylaşılan belleği destekleyip desteklemediğini, [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) **`true`** paylaşılan bellek desteklendiğinde döndüren hızlandırıcının supports_cpu_shared_memory özelliği tarafından belirlenir. Paylaşılan bellek destekleniyorsa, hızlandırıcının bellek ayırmaları için varsayılan [Access_type numaralandırması](reference/concurrency-namespace-enums-amp.md#access_type) özelliği tarafından belirlenir `default_cpu_access_type` . Varsayılan olarak, `array` ve `array_view` nesneleri ilişkili birincil ile aynı `access_type` şekilde sürer `accelerator` .

Açık bir şekilde [Array:: Cpu_access_type Data member](reference/array-class.md#cpu_access_type) özelliğini ayarlayarak `array` , paylaşılan belleğin nasıl kullanıldığı hakkında ayrıntılı denetim uygulayabilirsiniz. böylece, uygulamanın performans özelliklerine göre uygulamayı en iyi hale getirerek, hesaplama kerklerinin bellek erişimi düzenlerine göre uygulamayı iyileştirebilmenizi sağlayabilirsiniz. `array_view`, `cpu_access_type` İle ilişkili olduğu ile aynı şekilde yansıtır `array` ; veya array_view bir veri kaynağı olmadan oluşturulursa, `access_type` Bu, öncelikle depolama alanı ayırmasına neden olan ortamı yansıtır. Diğer bir deyişle, ana bilgisayar (CPU) tarafından ilk kez erişildiğinde, bir CPU veri kaynağı üzerinde oluşturulmuş gibi davranır ve `access_type` `accelerator_view` yakalama ile ilişkili ' ı paylaşır; ancak, bir tarafından ilk kez erişilirse `accelerator_view` , bu, üzerinde oluşturulmuş bir üzerinde oluşturulmuş gibi davranır ve ' ı `array` `accelerator_view` paylaşır `array` `access_type` .

Aşağıdaki kod örneği, varsayılan hızlandırıcının paylaşılan belleği destekleyip desteklemediğini nasıl belirleyeceğini gösterir ve ardından farklı cpu_access_type yapılandırmalarına sahip olan birkaç dizi oluşturur.

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

## <a name="executing-code-over-data-parallel_for_each"></a>Veriler üzerinde kod yürütme: parallel_for_each

[Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) işlevi, hızlandırıcı üzerinde veya nesnesindeki verilere karşı çalıştırmak istediğiniz kodu tanımlar `array` `array_view` . Bu konunun sunumundan aşağıdaki kodu göz önünde bulundurun.

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

`parallel_for_each`Yöntemi iki bağımsız değişken alır, bir işlem etki alanı ve bir lambda ifadesi.

*İşlem etki alanı* , `extent` `tiled_extent` paralel yürütme için oluşturulacak iş parçacığı kümesini tanımlayan bir nesnedir. İşlem etki alanındaki her öğe için bir iş parçacığı oluşturulur. Bu durumda, `extent` nesne tek boyutlu olur ve beş öğesi vardır. Bu nedenle, beş iş parçacığı başlatılır.

*Lambda ifadesi* her bir iş parçacığında çalıştırılacak kodu tanımlar. Yakalama yan tümcesi, `[=]` lambda ifadesinin gövdesinin değere göre yakalanan tüm değişkenlere eriştiğini belirtir; bu durumda, `a` `b` ve olur `sum` . Bu örnekte, parametre listesi adlı tek boyutlu bir `index` değişken oluşturur `idx` . Öğesinin değeri `idx[0]` ilk iş parçacığında 0 ' dır ve sonraki her iş parçacığında bir artış artar. `restrict(amp)`Yalnızca C++ amp hızlandırabilecek C++ dilinin alt kümesinin kullanıldığını gösterir.  Restrict değiştiricisine sahip işlevlerle ilgili sınırlamalar [restrict (C++ amp)](../../cpp/restrict-cpp-amp.md)bölümünde açıklanmaktadır. Daha fazla bilgi için bkz. [lambda Ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md).

Lambda ifadesi yürütülecek kodu içerebilir veya ayrı bir çekirdek işlevi çağırabilir. Çekirdek işlevi `restrict(amp)` değiştiricisini içermelidir. Aşağıdaki örnek, önceki örneğe eşdeğerdir, ancak ayrı bir çekirdek işlevi çağırır.

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

## <a name="accelerating-code-tiles-and-barriers"></a>Kodu hızlandırma: kutucuklar ve engelleri

Döşeme kullanarak ek hızlandırma elde edebilirsiniz. Döşeme, iş parçacıklarını eşit dikdörtgen alt kümelerine veya *döşemelere*böler. Veri kümesine ve kodlarınızın kodlanmasını yaptığınız algoritmaya göre uygun kutucuk boyutunu belirlersiniz. Her iş parçacığı için, bir veri öğesinin *genel* konumuna `array` veya `array_view` kutucuğa göre *Yerel* konuma erişim sahibi olursunuz. Yerel Dizin değerinin kullanılması kodunuzu basitleştirir çünkü dizin değerlerini Global 'ten yerel olarak çevirecek kodu yazmanız gerekmez. Döşeme kullanmak için, yöntemindeki işlem etki alanında [kapsam:: Tile yöntemini](reference/extent-class.md#tile) çağırın `parallel_for_each` ve lambda ifadesinde [tiled_index](../../parallel/amp/reference/tiled-index-class.md) nesnesini kullanın.

Tipik uygulamalarda, bir kutucukta bulunan öğeler bir şekilde ilişkilendirilir ve kodun, kutucuk genelinde değerleri uygulamasına erişmesi ve takip etmesini sağlamak gerekir. Bunu gerçekleştirmek için [Tile_static anahtar sözcüğünü](../../cpp/tile-static-keyword.md) ve [tile_barrier:: wait yöntemini](reference/tile-barrier-class.md#wait) kullanın. **Tile_static** anahtar sözcüğüne sahip bir değişken bir kutucuğun tamamında kapsam içerir ve her kutucuk için değişkenin bir örneği oluşturulur. Değişkene kutucuk iş parçacığı erişiminin eşitlemesini işlemeniz gerekir. [Tile_barrier:: wait yöntemi](reference/tile-barrier-class.md#wait) , kutucuktaki tüm iş parçacıkları öğesine yapılan çağrıya ulaşıncaya kadar geçerli iş parçacığının yürütülmesini durduruyor `tile_barrier::wait` . Bu nedenle, **tile_static** değişkenleri kullanarak kutucuk genelinde değer birikmesini sağlayabilirsiniz. Daha sonra tüm değerlere erişmesi gereken tüm hesaplamaları tamamlayabilmeniz gerekir.

Aşağıdaki diyagram, kutucuklar halinde düzenlenmiş bir örnekleme verisi dizisini temsil eder.

![Döşeli bir kapsam içindeki dizin değerleri](../../parallel/amp/media/camptiledgridexample.png "Döşeli bir kapsam içindeki dizin değerleri")

Aşağıdaki kod örneği, önceki diyagramdan örnekleme verilerini kullanır. Kod, kutucuktaki her değeri kutucuktaki değerlerin ortalaması ile değiştirir.

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

C++ AMP iki matematik kitaplığı içerir. [Eşzamanlılık::p Recise_math ad alanındaki](../../parallel/amp/reference/concurrency-precise-math-namespace.md) çift duyarlıklı kitaplık, çift duyarlıklı işlevler için destek sağlar. Ayrıca tek duyarlıklı işlevler için destek sağlar, ancak donanımda çift duyarlıklı destek hala gereklidir. [C99 belirtimine uyar (ISO/ıec 9899)](https://go.microsoft.com/fwlink/p/?linkid=225887). Hızlandırıcı tam çift duyarlık desteği sağlamalıdır. [Hızlandırıcı:: Supports_double_precision veri üyesinin](reference/accelerator-class.md#supports_double_precision)değerini denetleyerek olup olmadığını belirleyebilirsiniz. [Concurrency:: Fast_math ad alanındaki](../../parallel/amp/reference/concurrency-fast-math-namespace.md)hızlı matematik kitaplığı, başka matematik işlevleri kümesini içerir. Yalnızca işlenenleri destekleyen bu işlevler, **`float`** daha çabuk yürütülür ancak çift duyarlıklı matematik kitaplığındaki kesin değildir. İşlevler, \<amp_math.h> üstbilgi dosyasında bulunur ve tümü ile birlikte gösterilir `restrict(amp)` . \<cmath>Üstbilgi dosyasındaki işlevler hem hem de `fast_math` `precise_math` ad alanlarına aktarılır. **`restrict`** Anahtar sözcüğü, \<cmath> sürümü ve C++ amp sürümünü ayırt etmek için kullanılır. Aşağıdaki kod, işlem etki alanındaki her bir değerin hızlı yöntemi kullanılarak 10 tabanında logaritmasını hesaplar.

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
            logs[idx] = concurrency::fast_math::log10(numbers[idx]);
        }
    );

    for (int i = 0; i < 6; i++) {
        std::cout << logs[i] << "\n";
    }
}
```

## <a name="graphics-library"></a>Grafik kitaplığı

C++ AMP, hızlandırılmış grafik programlama için tasarlanan bir grafik kitaplığı içerir. Bu kitaplık yalnızca yerel grafik işlevlerini destekleyen cihazlarda kullanılır. Yöntemler [concurrency:: Graphics ad](../../parallel/amp/reference/concurrency-graphics-namespace.md) alanında bulunur ve \<amp_graphics.h> üstbilgi dosyasında bulunur. Grafik kitaplığının temel bileşenleri şunlardır:

- [doku sınıfı](../../parallel/amp/reference/texture-class.md): bir dosyadan veya bir dosyadan dokular oluşturmak için doku sınıfını kullanabilirsiniz. Dokular, veri içerdikleri için dizilere benzer ve atama ve kopya oluşturmaya göre C++ standart kitaplığındaki kapsayıcılara benzer. Daha fazla bilgi için bkz. [C++ standart kitaplık kapsayıcıları](../../standard-library/stl-containers.md). Sınıf için şablon parametreleri `texture` öğe türü ve rüttür. Sıra 1, 2 veya 3 olabilir. Öğe türü, bu makalenin ilerleyen kısımlarında açıklanan kısa vektör türlerinden biri olabilir.

- [Writeonly_texture_view sınıfı](../../parallel/amp/reference/writeonly-texture-view-class.md): herhangi bir dokuya salt yazılır erişim sağlar.

- Kısa vektör kitaplığı:,,,, **`int`** `uint` **`float`** **`double`** [norm](../../parallel/amp/reference/norm-class.md)veya [unorm](../../parallel/amp/reference/unorm-class.md)'yi temel alan, 2, 3 ve 4 uzunluğunda bir kısa vektör türleri kümesi tanımlar.

## <a name="universal-windows-platform-uwp-apps"></a>Evrensel Windows Platformu (UWP) uygulamaları

Diğer C++ kitaplıkları gibi UWP uygulamalarınızda C++ AMP de kullanabilirsiniz. Bu makalelerde, C++, C#, Visual Basic veya JavaScript kullanılarak oluşturulan uygulamalarda C++ AMP kodunun nasıl dahil olduğu açıklanır:

- [UWP uygulamalarında C++ AMP kullanma](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)

- [İzlenecek yol: C++ ' da temel bir Windows Çalışma Zamanı bileşeni oluşturma ve JavaScript 'ten çağırma](https://go.microsoft.com/fwlink/p/?linkid=249077)

- [JavaScript ve C++ içindeki bir pencere Mağazası uygulaması olan Bing Haritalar seyahat Iyileştirici](https://go.microsoft.com/fwlink/p/?linkid=249078)

- [Windows Çalışma Zamanı kullanarak C# ' den C++ AMP kullanma](https://devblogs.microsoft.com/pfxteam/how-to-use-c-amp-from-c-using-winrt/)

- [C 'den C++ AMP kullanma #](https://devblogs.microsoft.com/pfxteam/how-to-use-c-amp-from-c/)

- [Yönetilen koddan yerel Işlevleri çağırma](../../dotnet/calling-native-functions-from-managed-code.md)

## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP ve eşzamanlılık görselleştiricisi

Eşzamanlılık görselleştiricisi C++ AMP kodun performansını çözümlemek için destek içerir. Bu makaleler şu özellikleri anlatmaktadır:

- [GPU Etkinlik Grafiği](/visualstudio/profiling/gpu-activity-graph)

- [GPU Etkinliği (Disk Belleği)](/visualstudio/profiling/gpu-activity-paging)

- [GPU Etkinliği (Bu İşlem)](/visualstudio/profiling/gpu-activity-this-process)

- [GPU Etkinliği (Diğer İşlemler)](/visualstudio/profiling/gpu-activity-other-processes)

- [Kanallar (İş Parçacıkları Görünümü)](/visualstudio/profiling/channels-threads-view)

- [Eşzamanlılık görselleştiricisi ile C++ AMP kodu analiz etme](/archive/blogs/nativeconcurrency/analyzing-c-amp-code-with-the-concurrency-visualizer)

## <a name="performance-recommendations"></a>Performans Önerileri

İşaretsiz tamsayıların mod ve bölme işareti, işaretli tamsayıların ve bölenden önemli ölçüde daha iyi performansa sahiptir. Mümkün olduğunda işaretsiz tamsayılar kullanmanızı öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Lambda Ifadesi söz dizimi](../../cpp/lambda-expression-syntax.md)<br/>
[Başvuru (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[Yerel kod blogu 'nda paralel programlama](https://go.microsoft.com/fwlink/p/?linkid=238472)
