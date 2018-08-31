---
title: Hızlandırıcı ve accelerator_view nesnelerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ebbb33a4f17f5b4d458c4add4d59040d698dd4b8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222200"
---
# <a name="using-accelerator-and-acceleratorview-objects"></a>Hızlandırıcı ve accelerator_view Nesnelerini Kullanma
Kullanabileceğiniz [hızlandırıcı](../../parallel/amp/reference/accelerator-class.md) ve [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) cihazda veya öykünücüde C++ AMP kodunuzu çalıştırmak için belirtmek için sınıflar. Bir sistem, birkaç cihaz ya da bellek, paylaşılan bellek desteği, hata ayıklama desteği veya çifte duyarlılık desteği miktarına göre farklılık gösteren öykünücüleri olabilir. C++ Accelerated Massive Parallelism (C++ AMP) uygun Hızlandırıcıları incelemek, birini varsayılan olarak ayarlamak, çoklu çağrı görünümlerinin belirtin ve özel hata ayıklama görevlerini gerçekleştirmek için kullanabileceğiniz API'ler sağlar.  
  
## <a name="using-the-default-accelerator"></a>Varsayılan hızlandırıcıyı kullanma  
 
Belirli bir kod yazmadığınız sürece, C++ AMP çalışma zamanı varsayılan hızlandırıcıyı seçer. Çalışma zamanı varsayılan hızlandırıcıyı aşağıdaki gibi seçer:  
  
1. Uygulamayı hata ayıklama modunda çalışıyorsa, Hızlandırıcı hata ayıklamayı destekler.  
  
2. Aksi takdirde, bu ayarlanırsa, CPPAMP_DEFAULT_ACCELERATOR ortam değişkeni tarafından belirtilen Hızlandırıcı.  
  
3. Aksi durumda, benzetilmemiş cihaz.  
  
4. Aksi takdirde, kullanılabilir bellek miktarı en yüksek olan cihaz.  
  
5. Aksi takdirde, görüntüye bağlı olmayan bir cihaz.  
  
Ayrıca, çalışma zamanı belirtir bir `access_type` , `access_type_auto` varsayılan Hızlandırıcı için. Başka bir deyişle, destekleniyorsa ve performans özelliklerinin (bant genişliği ve gecikme) adanmış (paylaştırılmamış) bellek ile aynı olduğu bilinen varsayılan hızlandırıcının paylaşılan belleği kullanır.  
  
Varsayılan hızlandırıcıyı oluşturarak ve özelliklerini araştırarak özelliklerini varsayılan hızlandırıcının belirleyebilirsiniz. Aşağıdaki kod örneği, yolu, Hızlandırıcı bellek, paylaşılan bellek desteğini, çift duyarlıklı desteği ve varsayılan hızlandırıcının sınırlı çift duyarlıklı destek miktarı yazdırır.  
  
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
  
### <a name="cppampdefaultaccelerator-environment-variable"></a>CPPAMP_DEFAULT_ACCELERATOR çevre değişkeni  
Belirlemek için CPPAMP_DEFAULT_ACCELERATOR çevre değişkenini ayarlayabilirsiniz `accelerator::device_path` varsayılan hızlandırıcının. Yol donanıma bağımlıdır. Aşağıdaki kod `accelerator::get_all` işlevini Hızlandırıcıların listesini almak için ve her hızlandırıcının özelliklerini ve yolunu görüntüler.  
  
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
 
Bir Hızlandırıcı seçmek için kullanın `accelerator::get_all` birini seçin ve Hızlandırıcıların listesini almak için yöntem tabanlı özelliklerine göre. Bu örnek, en fazla belleği olan hızlandırıcının nasıl seçileceğini gösterir:  
  
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
> Tarafından döndürülen hızlandırıcılardan biri `accelerator::get_all` CPU hızlandırıcısıdır. Kodu CPU Hızlandırıcısı üzerinde yürütülemiyor. CPU hızlandırıcılarını süzmek için değeri ile karşılaştırmak [device_path](reference/accelerator-class.md#device_path) tarafından döndürülen hızlandırıcının özellik `accelerator::get_all` değeriyle [accelerator::cpu_accelerator](reference/accelerator-class.md#cpu_accelerator). Daha fazla bilgi için bu makaledeki "Özel Hızlandırıcılar" bölümüne bakın.  
  
## <a name="shared-memory"></a>Paylaşılan bellek  
 
Paylaşılan bellek, CPU ve Hızlandırıcı tarafından erişilebilen bellektir. Paylaşılan bellek kullanımı ortadan kaldırır veya CPU ve Hızlandırıcı arasında veri kopyalama yükünü önemli ölçüde azaltır. Belleğin paylaşılmasına rağmen CPU ve Hızlandırıcı tarafından aynı anda erişilemez ve bunu yaparsanız, bu nedenle tanımsız davranışa neden olur. Hızlandırıcı özelliği [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) döndürür **true** Hızlandırıcı paylaşılan bellek destekliyorsa ve [default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) özellik alımları Varsayılan [access_type](reference/concurrency-namespace-enums-amp.md#access_type) üzerinde ayrılmış bellek `accelerator`— Örneğin, **dizi**s ile ilişkili `accelerator`, veya `array_view` üzerinden erişilen nesneler `accelerator`. 
  
C++ AMP çalışma zamanı en iyi varsayılan otomatik olarak seçer `access_type` her `accelerator`, ancak paylaşılan belleğin performans özellikleri (bant genişliği ve gecikme) okurken belleğinkinden ayrılmış (paylaşılmayan) Hızlandırıcı bellek olabilir CPU veya hem de yazma CPU'dan. Paylaşılan bellek, okuma ve yazma CPU'dan için ayrılmış bellek gerçekleştiriyorsa, çalışma zamanı için varsayılan olarak `access_type_read_write`; Aksi takdirde çalışma zamanı daha pasif bir varsayılan seçer `access_type`ve bellek erişim bunu geçersiz kılmasına izin verir Hesaplama çekirdeklerinin desenleri farklı bir avantaj `access_type`.  
  
Aşağıdaki kod örneği, varsayılan hızlandırıcının paylaşılan belleği destekleyip ve ardından varsayılan erişim türünü geçersiz kılar ve oluşturur olup olmadığını belirlemek gösterilmiştir bir `accelerator_view` almaktır.  
  
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
  
Bir `accelerator_view` her zaman yansıtır `default_cpu_access_type` , `accelerator` ilişkili olduğu ve geçersiz kılmak veya değiştirmek için herhangi bir arabirim sağlar, `access_type`.  
  
## <a name="changing-the-default-accelerator"></a>Varsayılan hızlandırıcıyı değiştirme  
 
Çağırarak varsayılan hızlandırıcıyı değiştirebilirsiniz `accelerator::set_default` yöntemi. Herhangi bir kod GPU üzerinde yürütülmeden önce yalnızca uygulama yürütme ve bu defa varsayılan hızlandırıcıyı değiştirebilirsiniz. Hızlandırıcıyı değiştirmek için bir sonraki işlev çağrılarının dönüş **false**. Bir çağrıda farklı bir Hızlandırıcı kullanmak istiyorsanız `parallel_for_each`, bu makaledeki "Çoklu Hızlandırıcılar'ı kullanma" bölümüne bakın. Aşağıdaki kod örneği varsayılan hızlandırıcıyı benzetilmemiş, bir görüntüye bağlı olmayan ve çift-duyarlı destekli bir ayarlar.  
  
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
  
## <a name="using-multiple-accelerators"></a>Çoklu Hızlandırıcı kullanma  
 
Uygulamanızda çoklu Hızlandırıcı kullanmak için iki yolu vardır:  

- Geçirebilirsiniz `accelerator_view` çağrıları nesnelere [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) yöntemi.  
  
- Oluşturulabilir bir **dizi** nesnesi `accelerator_view` nesne. C + AMP çalışma zamanı alacağı `accelerator_view` yakalanan nesneden **dizi** lambda ifadesindeki nesne.  
  
## <a name="special-accelerators"></a>Özel Hızlandırıcılar  
 
Üç özel hızlandırıcının cihaz yolları özellikleri olarak kullanılabilir `accelerator` sınıfı:  
  
- [Accelerator::direct3d_ref veri üyesi](reference/accelerator-class.md#direct3d_ref): bir genel grafik kartını benzetmede CPU üzerinde bu tek iş parçacıklı Hızlandırıcı yazılım kullanır. Hata ayıklama için varsayılan olarak kullanılır, ancak donanım hızlandırıcılardan yavaş olduğundan üretimde kullanışlı olduğu değil. Ayrıca, yalnızca DirectX SDK ve Windows SDK'sı bulunur ve müşterilerinizin bilgisayarlarında yüklü beklenmez. Daha fazla bilgi için [GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code).  
  
- [Accelerator::direct3d_warp veri üyesi](reference/accelerator-class.md#direct3d_warp): Bu Hızlandırıcı, Streaming SIMD uzantılarını (SSE) kullanan çok çekirdekli CPU üzerinde C++ AMP kodunu yürütmek için bir geri dönüş çözümü sağlar.  
  
- [Accelerator::cpu_accelerator veri üyesi](reference/accelerator-class.md#cpu_accelerator): Bu Hızlandırıcı diziler hazırlık ayarlamak için kullanabilirsiniz. Bu, C++ AMP kod yürütemez. Daha fazla bilgi için [dizileri C++ amp'de](http://go.microsoft.com/fwlink/p/?linkId=248485) paralel programlama yerel kod blog içinde gönderin.  
  
## <a name="interoperability"></a>Birlikte Çalışabilirlik  
 
C++ AMP çalışma zamanı çalıştırılabilirliği Desteler `accelerator_view` sınıfı ile Direct3D [ıd3d11device arabirimi](http://go.microsoft.com/fwlink/p/?linkId=248488). [Create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view) yöntemi bir `IUnknown` arabirimi ve döndürür bir `accelerator_view` nesne. [Get_device](https://msdn.microsoft.com/8194125e-8396-4d62-aa8a-65831dea8439) yöntemi bir `accelerator_view` nesne ve döndürür bir `IUknown` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[C++ AMP (C++ hızlandırılmış yoğun paralellik)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
[GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code)   
[accelerator_view Sınıfı](../../parallel/amp/reference/accelerator-view-class.md)