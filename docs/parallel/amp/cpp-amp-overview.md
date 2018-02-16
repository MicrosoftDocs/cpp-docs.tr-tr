---
title: "C++ AMP'ye genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, requirements
- C++ Accelerated Massive Parallelism, architecture
- C++ AMP
- C++ Accelerated Massive Parallelism, overview
- C++ Accelerated Massive Parallelism
ms.assetid: 9e593b06-6e3c-43e9-8bae-6d89efdd39fc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0ee5b9c04794c531e2fa16cee72d6eee607dfbd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="c-amp-overview"></a>C++ AMP'ye Genel Bakış
C++ hızlandırılmış yoğun paralellik (C++ AMP), bir grafik işlemci birimi (GPU) gibi veri paralel donanım üzerinde ayrı ekran kartı yararlanarak C++ kod yürütmeyi hızlandırır. C++ AMP kullanarak, böylece heterojen donanımda paralellik kullanarak yürütme hızlandırılabilir çok boyutlu veri algoritmaları kodlayabilirsiniz. Çok boyutlu diziler, dizin oluşturma, bellek aktarımı, döşeme ve matematiksel işlev kitaplığının C++ AMP programlama modeli içerir. C++ AMP dil uzantıları, böylece performansı artırabilir nasıl veriler CPU'su tarafından GPU ve geri taşınır denetlemek için kullanabilirsiniz.  
  
## <a name="system-requirements"></a>Sistem Gereksinimleri  
  
- [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/reference/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../../parallel/amp/includes/winsvr08_r2_md.md)], veya [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)]  
  
-   DirectX 11 özelliği düzeyi 11.0 veya üstü donanım  
  
-   Yazılım öykünücüsünde hata ayıklama için [!INCLUDE[win8](../../build/reference/includes/win8_md.md)] veya [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] gereklidir. Donanımda hata ayıklamak için grafik kartınız için sürücüleri yüklemeniz gerekir. Daha fazla bilgi için bkz: [GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code).  
  
## <a name="introduction"></a>Giriş  
 C++ AMP'ın birincil bileşenlerini aşağıdaki iki örnek gösterilmektedir. İki boyutlu diziler karşılık gelen öğelerini eklemek istediğinizi varsayalım. Örneğin, eklemek isteyebilirsiniz `{1, 2, 3, 4, 5}` ve `{6, 7, 8, 9, 10}` almak için `{7, 9, 11, 13, 15}`. C++ AMP kullanmadan, sayıları ve sonuçları görüntülemek için aşağıdaki kodu yazabilirsiniz.  
  
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
  
 Kod önemli kısımlarını aşağıdaki gibidir:  
  
-   Veri: Veriler üç dizi oluşur. Aynı derece (bir) ve uzunluğu (beş) sahip.  
  
-   Yineleme: İlk `for` döngü öğeleri diziler üzerinden yineleme için bir mekanizma sağlar. Toplamları hesaplamak için çalıştırmak istediğiniz kod ilk bulunan `for` bloğu.  
  
-   Dizin: `idx` değişkeni dizi ayrı ayrı öğeler erişir.  
  
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
  
 Aynı temel öğeleri var, ancak C++ AMP yapıları kullanılır:  
  
-   Veri: C++ dizileri üç C++ AMP oluşturmak için kullandığınız [array_view](../../parallel/amp/reference/array-view-class.md) nesneleri. Oluşturmak için dört değerlerini sağlamak bir `array_view` nesnesi: veri değerleri, derecesini, öğe türü ve uzunluğu `array_view` her boyut nesnesi. Rank ve türü türü parametreleri olarak geçirilir. Veri ve uzunluğu Oluşturucusu parametre olarak geçirilir. Bu örnekte, oluşturucuya iletilen C++ tek boyutlu dizidir. Rank ve uzunluğu verileri dikdörtgen şekline oluşturmak için kullanılan `array_view` nesne ve veri değerleri dizisi doldurmak için kullanılır. Çalışma zamanı kitaplığı da içerir [array sınıfı](../../parallel/amp/reference/array-class.md), benzer bir arabirimi olan `array_view` sınıfı ve bu makalenin sonraki bölümlerinde ele alınmıştır.  
  
-   Yineleme: [parallel_for_each işlevi (C++ AMP)](reference/concurrency-namespace-functions-amp.md#parallel_for_each) veri öğeleri yineleme için bir mekanizma sağlar veya *etki alanı işlem*. Bu örnekte, işlem etki alanı tarafından belirtilen `sum.extent`. Çalıştırmak istediğiniz kod lambda ifadesinde bulunan veya *çekirdek işlevi*. `restrict(amp)` Yalnızca C++ AMP hızlandırabilir C++ dili alt kullanıldığını belirtir.  
  
-   Dizin: [index sınıfı](../../parallel/amp/reference/index-class.md) değişkeni `idx`, bir derecesini eşleşecek şekilde bir derece bildirilmiş `array_view` nesnesi. Dizini kullanarak, ayrı ayrı öğeler erişebilirsiniz `array_view` nesneleri.  
  
## <a name="shaping-and-indexing-data-index-and-extent"></a>Şekillendirme ve dizin oluşturma verileri: dizin ve kapsamı  
 Veri değerleri tanımlayın ve çekirdek kod çalıştırmadan önce veri şekli bildirin. Tüm verileri bir dizi (dikdörtgen) olarak tanımlanır ve tüm dereceye (dimensions sayısı) için dizi tanımlayabilirsiniz. Veri boyutları hiçbirinde herhangi bir boyutta olabilir.  
  
### <a name="index-class"></a>index Sınıfı  
 [İndex sınıfı](../../parallel/amp/reference/index-class.md) bir konumda belirtir `array` veya `array_view` her boyutundaki başlangıç uzaklığı bir nesnesine Kapsüllenen nesne. Bir dizi konumda eriştiğinizde, geçirdiğiniz bir `index` dizin oluşturma işleci nesnesine `[]`, tamsayı dizinler listesi yerine. Her boyut öğeleri kullanarak erişebilirsiniz [array:: operator() işleci](reference/array-class.md#operator_call) veya [array_view:: operator() işleci](reference/array-view-class.md#operator_call).  
  
 Aşağıdaki örnek, üçüncü öğe içinde tek boyutlu belirtir tek boyutlu bir dizin oluşturur `array_view` nesnesi. Dizin üçüncü öğesinde yazdırmak için kullanılan `array_view` nesnesi. Çıktı 3'tür.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5};  
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout << a[idx] << "\n";    
// Output: 3  
```  
  
 Aşağıdaki örnek, öğe belirtir iki boyutlu bir dizin oluşturur. burada satır = 1 ve sütun 2'de iki boyutlu bir = `array_view` nesnesi. İlk parametreyi `index` Oluşturucusu satır bileşenidir ve ikinci parametre sütun bileşendir. Çıktı 6'dır.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5, 6};  
array_view<int, 2> a(2, 3, aCPP);  
  
index<2> idx(1, 2);  
  
std::cout <<a[idx] << "\n";    
// Output: 6  
```  
  
 Aşağıdaki örnek, öğe belirtir üç boyutlu bir dizin oluşturur. burada derinliği = 0, satır = 1 ve sütun 3'te bir üç boyutlu = `array_view` nesnesi. İlk parametre derinliği bileşenidir, ikinci parametre satır bileşenidir ve üçüncü parametre sütun bileşendir dikkat edin. Çıktı 8'dir.  
  
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
 [Extent sınıfı](../../parallel/amp/reference/extent-class.md) veriler her boyut belirtir `array` veya `array_view` nesnesi. Bir kapsam oluşturabilir ve oluşturmak için kullanın bir `array` veya `array_view` nesnesi. Varolan ölçüde de alabilirsiniz `array` veya `array_view` nesnesi. Aşağıdaki örnekte her boyut içindeki kapsamı uzunluğu yazdırır bir `array_view` nesnesi.  
  
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
  
 Aşağıdaki örnekte bir `array_view` aynı olan nesneyi boyutları önceki örnekte, ancak bu örnek nesne olarak kullandığı bir `extent` açık parametrelerinde kullanmak yerine nesne `array_view` Oluşturucusu.  
  
```cpp  
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};  
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";  
std::cout << "The number of rows is " << a.extent[1] << "\n";  
std::cout << "The depth is " << a.extent[0] << "\n";  
```  
  
## <a name="moving-data-to-the-accelerator-array-and-arrayview"></a>Hızlandırıcı veri taşıma: dizi ve array_view  
 Hızlandırıcı veri taşımak için kullanılan iki veri kapsayıcı Çalışma Zamanı Kitaplığı'nda tanımlanır. Bunlar [array sınıfı](../../parallel/amp/reference/array-class.md) ve [array_view sınıfı](../../parallel/amp/reference/array-view-class.md). `array` Sınıftır nesnesi oluşturulduğunda, veri derin bir kopyasını oluşturan bir kapsayıcı. `array_view` Çekirdek işlevi veri eriştiğinde, verileri kopyalayan bir sarmalayıcı sınıfı bir sınıftır. Veri kaynağı cihazda verileri gerektiğinde geri kopyalanır.  
  
### <a name="array-class"></a>array Sınıfı  
 Zaman bir `array` nesne yapılandırılmıştır, veri kümesi için bir işaretçi içeren bir oluşturucu kullanırsanız, verilerin derin bir kopyasını Hızlandırıcı üzerinde oluşturulur. Çekirdek işlevi Hızlandırıcı kopyasında değişiklik yapar. Çekirdek işlevi yürütme tamamlandığında, veri kaynağı veri yapısı geri kopyalamanız gerekir. Aşağıdaki örnekte bir vektör her bir öğe tarafından 10 çarpar. Çekirdek işlevi tamamlandıktan sonra `vector conversion operator` vektör nesnesine verileri kopyalamak için kullanılır.  
  
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
 `array_view` Neredeyse aynı üyelere sahip `array` sınıfı, temel alınan davranış değildir ancak aynı. Veri geçirilen `array_view` Oluşturucusu çoğaltılmaz GPU üzerinde sahip olduğu gibi bir `array` Oluşturucusu. Bunun yerine, çekirdek işlevi çalıştırıldığında verileri Hızlandırıcı kopyalanır. Bu nedenle, iki oluşturursanız `array_view` aynı veri kullanan nesnelerinin her ikisi de `array_view` nesneleri aynı bellek alanına bakın. Bunu yaptığınızda, herhangi bir birden çok iş parçacıklı erişim eşitlemesi gerekir. Kullanmanın ana avantajı `array_view` sınıfı, yalnızca gerekli olduğunda veri taşınır.  
  
### <a name="comparison-of-array-and-arrayview"></a>Dizi ve array_view karşılaştırması  
 Aşağıdaki tabloda benzerlikleri özetler ve arasındaki farklar `array` ve `array_view` sınıfları.  
  
|Açıklama|array sınıfı|array_view sınıfı|  
|-----------------|-----------------|-----------------------|  
|Rank zaman belirlenir|Derleme zamanında.|Derleme zamanında.|  
|Ölçüde zaman belirlenir|Çalışma zamanında.|Çalışma zamanında.|  
|Şekil|Dikdörtgen.|Dikdörtgen.|  
|Veri depolama|Bir veri kapsayıcıdır.|Bir veri sarmalayıcı olur.|  
|Kopyala|Tanımı açık ve derin kopya.|Çekirdek işlevi tarafından erişildiğinde örtük kopyalayın.|  
|Veri alma|Dizi veri kopyalamak için bir nesne CPU iş parçacığı üzerinde yedekleyin.|Doğrudan erişimi tarafından `array_view` nesne veya göre çağırma [array_view::synchronize yöntemi](reference/array-view-class.md#synchronize) özgün kapsayıcı verileri erişmeye devam etmek için.|  
  
### <a name="shared-memory-with-array-and-arrayview"></a>Dizi ve array_view içeren paylaşılan bellek  
 Paylaşılan bellek hem CPU hem de Hızlandırıcı tarafından erişilebilen bellektir. Paylaşılan bellek kullanımını ortadan kaldırır veya CPU ve Hızlandırıcı arasında veri kopyalama yükünü önemli ölçüde azaltır. Bellek paylaşılmasına karşın, hem CPU hem de Hızlandırıcı tarafından eşzamanlı olarak erişilemez ve bunun nedenle tanımsız davranışlara neden olur.  
  
 `array` nesneleri ilişkili Hızlandırıcı destekliyorsa, paylaşılan bellek kullanımı üzerinde ayrıntılı denetim belirtmek için kullanılabilir. Hızlandırıcı paylaşılan bellek destekleyip desteklemediğini Hızlandırıcı tarafından 's belirlenir [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) döndürür özelliği `true` paylaşılan bellek olduğunda desteklenir. Paylaşılan bellek destekleniyorsa, varsayılan [access_type numaralandırması](reference/concurrency-namespace-enums-amp.md#access_type) için bellek ayırma Hızlandırıcı üzerinde tarafından belirlenir `default_cpu_access_type` özelliği. Varsayılan olarak, `array` ve `array_view` nesneleri almak için aynı `access_type` ilişkili birincil olarak `accelerator`.  
  
 Ayarlayarak [array::cpu_access_type veri üyesi](reference/array-class.md#cpu_access_type) özelliği bir `array` açıkça, böylece uygulama donanım performansı için en iyi duruma getirebilirsiniz alıştırma hassas nasıl paylaşılan bellek kullanılır, kontrol edebilirsiniz Hesaplama tekrar bellek erişim düzenlerini esas alarak özellikleri. Bir `array_view` aynı yansıtır `cpu_access_type` olarak `array` ; ile ilişkili veya array_view bir veri kaynağı oluşturulursa, `access_type` ilk depolama alanı ayırmak neden ortamı yansıtır. İlk (CPU) ana bilgisayar tarafından erişilen, CPU veri kaynağı ve paylaşımlar oluşturulan gibi diğer bir deyişle, sonra da davranır `access_type` , `accelerator_view` ilk varsa ancak tarafından erişilen; yakalama ile ilişkili bir `accelerator_view`, onu değilmiş gibi davranır sonra üzerinde oluşturulan bir `array` üzerinde oluşturulan `accelerator_view` ve paylaşımları `array`'s `access_type`.  
  
 Aşağıdaki kod örneği, varsayılan Hızlandırıcı paylaşılan bellek destekler ve farklı cpu_access_type yapılandırmalarının birkaç diziler oluşturur olup olmadığını belirlemek gösterilmiştir.  
  
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
  
## <a name="executing-code-over-data-parallelforeach"></a>Kod veri yürütme: parallel_for_each  
 [Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) işlevi tanımlayan Hızlandırıcı verileri karşı çalıştırmak istediğiniz kod `array` veya `array_view` nesnesi. Giriş, bu konunun aşağıdaki kodu göz önünde bulundurun.  
  
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
  
 `parallel_for_each` Yöntemi iki bağımsız değişken, bir işlem etki alanı ve bir lambda ifadesi alır.  
  
 *Etki alanı işlem* olan bir `extent` nesnesi veya bir `tiled_extent` Paralel yürütme için oluşturmak için iş parçacığı kümesini tanımlayan nesne. Hesaplama etki alanındaki her öğe için bir iş parçacığı oluşturulur. Bu durumda, `extent` nesnesi tek boyutlu ve beş öğesine sahip. Bu nedenle, beş iş parçacığı başlatılır.  
  
 *Lambda ifadesi* her iş parçacığı üzerinde çalıştırmak için kod tanımlar. Yakalama yan tümcesi `[=]`, lambda ifadesi gövdesi, bu durumda olan değer ile tüm yakalanan değişkenleri erişen belirtir `a`, `b`, ve `sum`. Bu örnekte, parametre listesi bir tek boyutlu oluşturur `index` adlı değişken `idx`. Değeri `idx[0]` ilk iş parçacığında 0'dır ve bir sonraki her iş parçacığı tarafından artırır. `restrict(amp)` Yalnızca C++ AMP hızlandırabilir C++ dili alt kullanıldığını belirtir.  Kısıtlama değiştiricisi olan işlevler sınırlamalar açıklanan [sınırla (C++ AMP)](../../cpp/restrict-cpp-amp.md). Daha fazla bilgi için bkz: [Lambda ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md).  
  
 Lambda ifadesi yürütmek için kodu içerebilir veya ayrı çekirdek işlevi çağırabilirsiniz. Çekirdek işlevini içermelidir `restrict(amp)` değiştiricisi. Aşağıdaki örnek önceki örneğe eşdeğerdir ancak ayrı çekirdek işlevi çağırır.  
  
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
  
## <a name="accelerating-code-tiles-and-barriers"></a>Hızlandırma kodu: Döşeme ve engelleri  

 Döşeme kullanarak ek hızlandırma elde edebilirsiniz. Döşeme böler iş parçacıklarının eşit dikdörtgen alt kümeler veya *kutucukları*. Veri kümenizi ve kodlama algoritma göre uygun döşeme boyutunu belirler. Her iş parçacığı için erişiminiz *genel* bir veri öğesi tüm göreli konumunu `array` veya `array_view` erişim *yerel* döşemeye göre konumu. Dizin değerlerinden genel yerel çevirmek için kod yazmanız gerekmez çünkü yerel dizin değerini kullanarak kodunuzu basitleştirir. Döşeme kullanmak için arama [extent::tile yöntemi](reference/extent-class.md#tile) işlem etki alanında bulunan `parallel_for_each` yöntemi ve kullanım bir [tiled_index](../../parallel/amp/reference/tiled-index-class.md) lambda ifadesi nesne.  
  
 Tipik uygulamalarda kutucuk öğeleri herhangi bir yolla ilişkili olan ve erişmek ve değerleri arasında döşeme izlemek koduna sahip. Kullanım [tile_static anahtar sözcüğü](../../cpp/tile-static-keyword.md) anahtar sözcüğü ve [tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait) bunu gerçekleştirmek için. Sahip bir değişken `tile_static` anahtar sözcüğü bir kapsam tüm bir kutucuğu varsa ve her bölme için değişken bir örneği oluşturulur. Değişkene döşeme iş parçacığı erişimi eşitlenmesi işlemelidir. [Tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait) döşemesinin tüm iş parçacıklarının çağrısı ulaştınız kadar geçerli iş parçacığının çalışmayı durdurur `tile_barrier::wait`. Kullanarak değerleri arasında döşeme birikebilir şekilde `tile_static` değişkenleri. Ardından tüm değerleri erişim gerektiren tüm hesaplamalar bitirebilirsiniz.  

  
 Aşağıdaki diyagramda döşemeleri düzenlenmiş veri örnekleme, iki boyutlu bir dizi temsil eder.  
  
 ![Dizin döşeli ölçüde değerleri](../../parallel/amp/media/camptiledgridexample.png "camptiledgridexample")  
  
 Aşağıdaki kod örneği, önceki diyagramda örnekleme verileri kullanır. Kod döşemesinin değerlerin ortalamasını tarafından döşeme yer alan her değerin yerini alır.  
  
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
 C++ AMP iki matematik kitaplıklarını içerir. Çift duyarlıklı Kitaplığı'nda [Concurrency::precise_math Namespace](../../parallel/amp/reference/concurrency-precise-math-namespace.md) çift duyarlıklı işlevleri için destek sağlar. Çift duyarlıklı destek donanımda hala gerekli olmasına rağmen tek duyarlıklı işlevleri için de destek sağlar. İle uyumlu [C99 belirtimi (ISO/IEC 9899)](http://go.microsoft.com/fwlink/p/?linkid=225887). Hızlandırıcı tam çift duyarlıklı desteklemesi gerekir. Değerini kontrol ederek mevcut olup olmadığını belirlemek [accelerator::supports_double_precision veri üyesi](reference/accelerator-class.md#supports_double_precision). Hızlı math Kitaplığı'ndaki [Concurrency::fast_math Namespace](../../parallel/amp/reference/concurrency-fast-math-namespace.md), matematik işlevleri başka bir kümesini içerir. Bu işlevler yalnızca Destek `float` işlenenler, daha hızlı yürütme ancak çift duyarlıklı math kitaplığı de olarak kesin değildir. İşlevler bulunan \<amp_math.h > üst bilgi dosyasını ve tüm ile bildirildiğinde `restrict(amp)`. İşlevlerde \<cmath > Üstbilgi dosyası içine aktarılır `fast_math` ve `precise_math` ad alanları. `restrict` Ayırt etmek için kullanılan anahtar sözcüğü \<cmath > sürümü ve C++ AMP sürümü. Aşağıdaki kod hızlı yöntemini işlem etki alanındaki her bir değerin 10 tabanında logaritmasını hesaplar.  

  
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
 C++ AMP hızlandırılmış grafik programlama için tasarlanmış bir grafik kitaplık içerir. Bu kitaplık yerel grafik işlevlerini destekleyen cihazlarda kullanılır. Yöntemleri [Concurrency::graphics Namespace](../../parallel/amp/reference/concurrency-graphics-namespace.md) ve içerdiği \<amp_graphics.h > Üstbilgi dosyası. Grafik kitaplığının anahtar bileşenleri şunlardır:  
  
- [texture sınıfı](../../parallel/amp/reference/texture-class.md): bellek veya bir dosyadan doku oluşturmak için doku sınıfını kullanabilirsiniz. Dokular diziler veri içerir ve atama ve kopyalama yapım göre C++ Standart Kitaplığı kapsayıcılarında benzer olduğundan benzer. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../../standard-library/stl-containers.md). Şablon parametrelerini `texture` öğe türü ve derecesini sınıfı bulunur. Derece 1, 2 veya 3 olabilir. Öğe türü bu makalenin sonraki bölümlerinde açıklanan kısa vektör türlerden biri olabilir.  
  
- [writeonly_texture_view sınıfı](../../parallel/amp/reference/writeonly-texture-view-class.md): tüm doku yalnızca yazma erişimi sağlar.  
  
- [Kısa vektör Kitaplığı](http://msdn.microsoft.com/en-us/4c4f5bed-c396-493b-a238-c347563f645f): uzunluğu 2, 3 ve temel alan 4 kısa vektör türleri kümesini tanımlayan `int`, `uint`, `float`, `double`, [norm](../../parallel/amp/reference/norm-class.md), veya [unorm](../../parallel/amp/reference/unorm-class.md).  
  
## <a name="universal-windows-platform-uwp-apps"></a>Evrensel Windows Platformu (UWP) uygulamaları  
 Diğer C++ kitaplıkları gibi UWP uygulamalarında C++ AMP kullanabilirsiniz. Bu makaleler C++, C#, Visual Basic veya JavaScript kullanılarak oluşturulan C++ AMP kodunu uygulamalarında nasıl ekleneceğini açıklar:  
  
- [UWP Uygulamalarında C++ AMP Kullanma](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)  
  
- [İzlenecek yol: C++ ve JavaScript'ten çağırma temel Windows çalışma zamanı bileşeni oluşturma](http://go.microsoft.com/fwlink/p/?linkid=249077)  
  
- [Bing Haritalar seyahat iyileştirici, bir Windows mağazası uygulaması JavaScript ve C++](http://go.microsoft.com/fwlink/p/?linkid=249078)  
  
- [C# Windows çalışma zamanı kullanarak üzerinden C++ AMP kullanma](http://go.microsoft.com/fwlink/p/?linkid=249080)  
  
- [C# üzerinden C++ AMP kullanma](http://go.microsoft.com/fwlink/p/?linkid=249081)  
  
- [Yönetilen Koddan Yerel İşlevleri Çağırma](../../dotnet/calling-native-functions-from-managed-code.md)  
  
## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP ve eşzamanlılık görselleştiricisi  
 Eşzamanlılık görselleştiricisi C++ AMP kodunun performansını çözümlemek için destek içerir. Bu makaleler, bu özellikleri açıklar:  
  
- [GPU Etkinlik Grafiği](/visualstudio/profiling/gpu-activity-graph)  
  
- [GPU Etkinliği (Disk Belleği)](/visualstudio/profiling/gpu-activity-paging)  
  
- [GPU Etkinliği (Bu İşlem)](/visualstudio/profiling/gpu-activity-this-process)  
  
- [GPU Etkinliği (Diğer İşlemler)](/visualstudio/profiling/gpu-activity-other-processes)  
  
- [Kanallar (İş Parçacıkları Görünümü)](/visualstudio/profiling/channels-threads-view)  
  
- [Eşzamanlılık görselleştiricisi ile C++ AMP kodunu analiz etme](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)  
  
## <a name="performance-recommendations"></a>Performans önerileri  
 Modulus ve imzasız tamsayılar bölme mod ve imzalı tamsayılar bölümünün daha önemli ölçüde daha iyi performans sahiptir. Mümkün olduğunda imzasız tamsayılar kullanmanızı öneririz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ AMP (C++ hızlandırılmış yoğun paralellik)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Lambda ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md)   
 [Başvuru (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)   
 [Yerel kod günlüğündeki paralel programlama](http://go.microsoft.com/fwlink/p/?linkid=238472)
