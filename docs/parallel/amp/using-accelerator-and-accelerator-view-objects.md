---
title: Hızlandırıcı ve accelerator_view Nesnelerini Kullanma
ms.date: 11/04/2016
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
ms.openlocfilehash: e3fed4dc2a431b751d4ad50484e32b738e786d10
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404183"
---
# <a name="using-accelerator-and-accelerator_view-objects"></a>Hızlandırıcı ve accelerator_view Nesnelerini Kullanma

C++ AMP kodunuzu çalıştırmak için cihazı veya öykünücüyü belirtmek üzere [Hızlandırıcı](../../parallel/amp/reference/accelerator-class.md) ve [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) sınıflarını kullanabilirsiniz. Bir sistem, bellek miktarına, paylaşılan bellek desteğine, hata ayıklama desteğine veya çift duyarlıklı desteğe göre farklılık gösteren çeşitli cihazlara veya öykünücülere sahip olabilir. C++ Accelerated Massive Parallelism (C++ AMP), kullanılabilir Hızlandırıcılar 'ı incelemek için kullanabileceğiniz API 'Ler sağlar, birini varsayılan olarak ayarlayabilir, birden fazla parallel_for_each çağrısı için birden çok accelerator_views belirtebilir ve özel hata ayıklama görevleri gerçekleştirebilirsiniz.

## <a name="using-the-default-accelerator"></a>Varsayılan hızlandırıcıyı kullanma

C++ AMP çalışma zamanı, belirli bir seçim yapmak için kod yazmadığınız takdirde varsayılan bir Hızlandırıcı seçer. Çalışma zamanı varsayılan hızlandırıcıyı aşağıdaki şekilde seçer:

1. Uygulama hata ayıklama modunda çalışıyorsa, hata ayıklamayı destekleyen bir hızlandırıcı.

2. Aksi halde, ayarlandıysa CPPAMP_DEFAULT_ACCELERATOR ortam değişkeni tarafından belirtilen hızlandırıcı.

3. Aksi halde, öykünmemiş bir cihaz.

4. Aksi takdirde, en büyük kullanılabilir bellek miktarına sahip olan cihaz.

5. Aksi halde, görüntüsüne eklenmemiş bir cihaz.

Ayrıca, çalışma zamanı `access_type` varsayılan hızlandırıcı için bir ' ı belirtir `access_type_auto` . Bu, varsayılan hızlandırıcının desteklendiğinde paylaşılan belleği kullandığı ve performans özelliklerinin (bant genişliği ve gecikme süresi) adanmış (paylaşılmayan) bellekle aynı olduğu bilindiğinde olduğu anlamına gelir.

Varsayılan hızlandırıcıyı oluşturarak ve özelliklerini inceleyerek varsayılan hızlandırıcının özelliklerini belirleyebilirsiniz. Aşağıdaki kod örneği, yolu, Hızlandırıcı bellek miktarını, paylaşılan bellek desteğini, çift duyarlıklı desteği ve varsayılan hızlandırıcının sınırlı çift duyarlıklı desteğini yazdırır.

```cpp
void default_properties() {
    accelerator default_acc;
    std::wcout << default_acc.device_path << "\n";
    std::wcout << default_acc.dedicated_memory << "\n";
    std::wcout << (accs[i].supports_cpu_shared_memory ?
        "CPU shared memory: true" : "CPU shared memory: false") << "\n";
    std::wcout << (accs[i].supports_double_precision ?
        "double precision: true" : "double precision: false") << "\n";
    std::wcout << (accs[i].supports_limited_double_precision ?
        "limited double precision: true" : "limited double precision: false") << "\n";
}
```

### <a name="cppamp_default_accelerator-environment-variable"></a>CPPAMP_DEFAULT_ACCELERATOR ortam değişkeni

Varsayılan Hızlandırıcının öğesini belirtmek için CPPAMP_DEFAULT_ACCELERATOR ortam değişkenini ayarlayabilirsiniz `accelerator::device_path` . Yol, donanıma bağımlıdır. Aşağıdaki kod, `accelerator::get_all` kullanılabilir Hızlandırıcılar listesini almak için işlevini kullanır ve ardından her hızlandırıcının yolunu ve özelliklerini görüntüler.

```cpp
void list_all_accelerators()
{
    std::vector<accelerator> accs = accelerator::get_all();

    for (int i = 0; i <accs.size(); i++) {
        std::wcout << accs[i].device_path << "\n";
        std::wcout << accs[i].dedicated_memory << "\n";
        std::wcout << (accs[i].supports_cpu_shared_memory ?
            "CPU shared memory: true" : "CPU shared memory: false") << "\n";
        std::wcout << (accs[i].supports_double_precision ?
            "double precision: true" : "double precision: false") << "\n";
        std::wcout << (accs[i].supports_limited_double_precision ?
            "limited double precision: true" : "limited double precision: false") << "\n";
    }
}
```

## <a name="selecting-an-accelerator"></a>Hızlandırıcı seçme

Bir Hızlandırıcı seçmek için, `accelerator::get_all` kullanılabilir Hızlandırıcılar listesini almak üzere yöntemini kullanın ve sonra özelliklerine göre birini seçin. Bu örnek, en çok belleğe sahip olan hızlandırıcının nasıl kullanılacağını gösterir:

```cpp
void pick_with_most_memory()
{
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator acc_chosen = accs[0];

    for (int i = 0; i <accs.size(); i++) {
        if (accs[i].dedicated_memory> acc_chosen.dedicated_memory) {
            acc_chosen = accs[i];
        }
    }

    std::wcout << "The accelerator with the most memory is "
        << acc_chosen.device_path << "\n"
        << acc_chosen.dedicated_memory << ".\n";
}
```

> [!NOTE]
> Tarafından döndürülen hızlandırıcılardan biri `accelerator::get_all` CPU hızlandırıcısıdır. CPU hızlandırıcısında kod yürütemezsiniz. CPU hızlandırıcıyı filtrelemek için Hızlandırıcı [device_path](reference/accelerator-class.md#device_path) `accelerator::get_all` [:: cpu_accelerator](reference/accelerator-class.md#cpu_accelerator)değeri ile döndürülen hızlandırıcının device_path özelliğinin değerini karşılaştırın. Daha fazla bilgi için bu makaledeki "özel Hızlandırıcılar" bölümüne bakın.

## <a name="shared-memory"></a>Paylaşılan bellek

Paylaşılan bellek, hem CPU hem de hızlandırıcı tarafından erişilebilen bellektir. Paylaşılan bellek kullanımı, CPU ve Hızlandırıcı arasında veri kopyalama yükünü ortadan kaldırır veya önemli ölçüde azaltır. Bellek paylaşılsa da, hem CPU hem de hızlandırıcı tarafından aynı anda erişilemez ve bunun yapılması tanımsız davranışlara neden olur. Hızlandırıcı özelliği [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) , hızlandırıcı paylaşılan belleği destekliyorsa **true** değerini döndürür ve [default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) özelliği, üzerinde ayrılan bellek için varsayılan [access_type](reference/concurrency-namespace-enums-amp.md#access_type) alır `accelerator` (örneğin, ile ilişkili **dizi** `accelerator` veya `array_view` üzerinde erişilen nesneler) `accelerator` .

C++ AMP Runtime her biri için en iyi varsayılan değerleri otomatik olarak seçer `access_type` `accelerator` , ancak paylaşılan belleğin performans özellikleri (bant genişliği ve gecikme), CPU 'dan okurken, CPU 'dan yazarken veya her ikisinde de ayrılmış (paylaşılmayan) Hızlandırıcı belleklerinden daha kötüden olabilir. Paylaşılan bellek, CPU 'dan okuma ve yazma için ayrılmış bellek ve diğer bir deyişle, çalışma zamanı varsayılan olarak olur `access_type_read_write` ; Aksi takdirde, çalışma zamanı daha koruyucu bir varsayılan seçer `access_type` ve hesaplama için bellek erişimi desenleri farklı bir şekilde avantaj veriyorsa uygulamanın bunu geçersiz kılmasına izin verir `access_type` .

Aşağıdaki kod örneği, varsayılan hızlandırıcının paylaşılan belleği destekleyip desteklemediğini nasıl belirleyeceğini gösterir ve ardından varsayılan erişim türünü geçersiz kılar ve öğesinden bir oluşturur `accelerator_view` .

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
    acc.set_default_cpu_access_type(access_type_read_write);

    // Create an accelerator_view from the default accelerator. The
    // accelerator_view reflects the default_cpu_access_type of the
    // accelerator it’s associated with.
    accelerator_view acc_v = acc.default_view;
}
```

`accelerator_view`Her zaman `default_cpu_access_type` `accelerator` ile ilişkili olduğunu yansıtır ve geçersiz kılmak ya da değiştirmek için arabirim sağlamaz `access_type` .

## <a name="changing-the-default-accelerator"></a>Varsayılan hızlandırıcıyı değiştirme

Yöntemini çağırarak Varsayılan hızlandırıcıyı değiştirebilirsiniz `accelerator::set_default` . Varsayılan hızlandırıcıyı uygulama yürütmesi başına yalnızca bir kez değiştirebilir ve GPU üzerinde herhangi bir kod yürütülmeden önce bunu değiştirmeniz gerekir. Hızlandırıcıyı değiştirmek için sonraki işlev çağrıları **false**döndürür. Bir çağrısında farklı bir Hızlandırıcı kullanmak istiyorsanız `parallel_for_each` , bu makaledeki "çoklu Hızlandırıcılar kullanma" bölümünü okuyun. Aşağıdaki kod örneği, Varsayılan hızlandırıcıyı benzetilmemiş, bir görüntülemeye bağlı olmayan bir şekilde ayarlar ve çift duyarlığı destekler.

```cpp
bool pick_accelerator()
{
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator chosen_one;

    auto result = std::find_if(accs.begin(), accs.end(),
        [] (const accelerator& acc) {
            return !acc.is_emulated &&
                acc.supports_double_precision &&
                !acc.has_display;
        });

    if (result != accs.end()) {
        chosen_one = *(result);
    }

    std::wcout <<chosen_one.description <<std::endl;
    bool success = accelerator::set_default(chosen_one.device_path);
    return success;
}
```

## <a name="using-multiple-accelerators"></a>Birden çok Hızlandırıcı kullanma

Uygulamanızda birden çok Hızlandırıcı kullanmanın iki yolu vardır:

- `accelerator_view` [Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) metoduna yapılan çağrılara nesneleri geçirebilirsiniz.

- Belirli bir nesneyi kullanarak bir **dizi** nesnesi oluşturabilirsiniz `accelerator_view` . C + AMP çalışma zamanı, `accelerator_view` lambda ifadesinde yakalanan **dizi** nesnesinden nesneyi seçer.

## <a name="special-accelerators"></a>Özel Hızlandırıcılar

Üç özel Hızlandırıcıların cihaz yolları, sınıfının özellikleri olarak kullanılabilir `accelerator` :

- [Hızlandırıcı::d Irect3d_ref veri üyesi](reference/accelerator-class.md#direct3d_ref): Bu tek iş parçacıklı hızlandırıcı, bir genel grafik kartına ÖYKÜNMEK için CPU üzerinde yazılım kullanır. Hata ayıklama için varsayılan olarak kullanılır, ancak donanım hızlandırıcılardan yavaş olduğundan üretimde yararlı değildir. Ayrıca, bu, yalnızca DirectX SDK ve Windows SDK kullanılabilir ve müşterilerinizin bilgisayarlarına yüklenmesi olası değildir. Daha fazla bilgi için bkz. [GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code).

- [Hızlandırıcı::d Irect3d_warp veri üyesi](reference/accelerator-class.md#direct3d_warp): Bu hızlandırıcı, STREAMING SIMD EXTENSIONS (SSE) kullanan çok çekirdekli cpu 'larda C++ amp kodu yürütmek için bir geri dönüş çözümü sağlar.

- [Accelerator:: Cpu_accelerator veri üyesi](reference/accelerator-class.md#cpu_accelerator): Bu hızlandırıcıyı, hazırlama dizilerini ayarlamak için kullanabilirsiniz. C++ AMP kodu yürütemiyor. Daha fazla bilgi için yerel kod blogundan paralel programlama [C++ amp postadaki hazırlama dizileri](/archive/blogs/nativeconcurrency/staging-arrays-in-c-amp) ' ne bakın.

## <a name="interoperability"></a>Birlikte Çalışabilirlik

C++ AMP çalışma zamanı, `accelerator_view` sınıf Ile Direct3D [ID3D11Device arabirimi](/windows/win32/api/d3d11/nn-d3d11-id3d11device)arasında birlikte çalışabilirliği destekler. [Create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view) yöntemi bir arabirim alır `IUnknown` ve bir nesne döndürür `accelerator_view` . [Get_device](reference/concurrency-direct3d-namespace-functions-amp.md#get_device) yöntemi bir nesnesi alır `accelerator_view` ve bir arabirim döndürür `IUnknown` .

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[GPU Kodunda Hata Ayıklama](/visualstudio/debugger/debugging-gpu-code)<br/>
[accelerator_view sınıfı](../../parallel/amp/reference/accelerator-view-class.md)
