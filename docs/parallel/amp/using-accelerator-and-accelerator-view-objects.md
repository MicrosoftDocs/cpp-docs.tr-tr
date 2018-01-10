---
title: "Hızlandırıcı ve accelerator_view nesnelerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cc676407a88979679a362b3d36f361614524432
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="using-accelerator-and-acceleratorview-objects"></a>Hızlandırıcı ve accelerator_view Nesnelerini Kullanma
Kullanabileceğiniz [hızlandırıcı](../../parallel/amp/reference/accelerator-class.md) ve [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) sınıfları cihaz veya öykünücü C++ AMP kodunuzu çalıştırmak için belirtin. Bir sistem birkaç aygıtları veya bellek, paylaşılan bellek desteğini, hata ayıklama desteği veya çift duyarlıklı destek miktarına göre farklılık Öykünücüler olabilir. C++ hızlandırılmış yoğun paralellik (C++ AMP) kullanılabilir Hızlandırıcıları inceleyin, varsayılan olarak ayarlayın, birden çok çağrılar parallel_for_each için birden çok accelerator_views belirtin ve özel hata ayıklama görevleri gerçekleştirmek için kullanabileceğiniz API'ler sağlar.  
  
## <a name="using-the-default-accelerator"></a>Varsayılan Hızlandırıcı kullanma  
 Belirli bir seçmek için kod yazma sürece C++ AMP çalışma zamanı varsayılan Hızlandırıcı seçer. Çalışma zamanı gibi varsayılan Hızlandırıcı seçti:  
  
1.  Uygulama hata ayıklama modunda çalışıyorsa, Hızlandırıcı, hata ayıklama destekler.  
  
2.  Aksi takdirde, bu ayarlanırsa CPPAMP_DEFAULT_ACCELERATOR ortam değişkeni tarafından belirtilen Hızlandırıcı.  
  
3.  Aksi takdirde benzetilmiş olmayan bir aygıt.  
  
4.  Aksi takdirde, en fazla kullanılabilir bellek miktarına sahip bir aygıt.  
  
5.  Aksi takdirde, görüntüye bağlı olmayan bir aygıt.  
  
 Ayrıca, çalışma zamanı belirten bir `access_type` , `access_type_auto` varsayılan Hızlandırıcı için. Başka bir deyişle, varsayılan Hızlandırıcı desteklenir ve kendi performans özellikleri (bant genişliği ve gecikme) adanmış (paylaşılmayan) bellek ile aynı olduğu bilinen paylaşılan bellek kullanır.  
  
 Varsayılan Hızlandırıcı özelliklerini varsayılan Hızlandırıcı oluşturma ve özelliklerini inceleyerek belirleyebilirsiniz. Aşağıdaki kod örneğinde Hızlandırıcı bellek, paylaşılan bellek desteği, çift duyarlıklı desteği ve varsayılan Hızlandırıcı sınırlı duyarlıklı destek miktarını yolun yazdırır.  
  
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
  
### <a name="cppampdefaultaccelerator-environment-variable"></a>CPPAMP_DEFAULT_ACCELERATOR ortam değişkeni  
 Belirtmek için CPPAMP_DEFAULT_ACCELERATOR ortam değişkeni ayarlayabilirsiniz `accelerator::device_path` varsayılan Hızlandırıcı. Yolun donanım bağımlıdır. Aşağıdaki kod `accelerator::get_all` kullanılabilir Hızlandırıcıları listesini almak için çalışır ve her Hızlandırıcı özelliklerini ve yolunu görüntüler.  
  
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
 Hızlandırıcı seçmek için kullanın `accelerator::get_all` kullanılabilir Hızlandırıcıları listesini almak ve bir seçmek için yöntemine temel özelliklerini üzerinde. Bu örnek, çoğu belleği Hızlandırıcı çekme gösterilmektedir:  
  
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
>  Tarafından döndürülen Hızlandırıcıları birini `accelerator::get_all` CPU hızlandırıcısıdır. Kod CPU Hızlandırıcı yürütülemiyor. CPU accelerator filtrelemek için değerini karşılaştırın [device_path](reference/accelerator-class.md#device_path) tarafından döndürülen Hızlandırıcı özelliğinin `accelerator::get_all` değeriyle [accelerator::cpu_accelerator](reference/accelerator-class.md#cpu_accelerator). Daha fazla bilgi için bu makaledeki "Özel Hızlandırıcıları" bölümüne bakın.  
  
## <a name="shared-memory"></a>Paylaşılan bellek  
 Paylaşılan bellek hem CPU hem de Hızlandırıcı tarafından erişilebilen bellektir. Paylaşılan bellek kullanımını ortadan kaldırır veya CPU ve Hızlandırıcı arasında veri kopyalama yükünü önemli ölçüde azaltır. Bellek paylaşılmasına karşın, hem CPU hem de Hızlandırıcı tarafından eşzamanlı olarak erişilemez ve bunun nedenle tanımsız davranışlara neden olur. Hızlandırıcı özelliği [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) döndürür `true` Hızlandırıcı paylaşılan bellek destekliyorsa ve [default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) özelliğini alır varsayılan[access_type](reference/concurrency-namespace-enums-amp.md#access_type) üzerinde ayrılan bellek `accelerator`— Örneğin, `array`ilişkili s `accelerator`, veya `array_view` üzerinde erişilen nesneler `accelerator`. 
  
 C++ AMP çalışma zamanı en iyi varsayılan otomatik olarak seçer `access_type` her `accelerator`, ancak paylaşılan bellek performans özellikleri (bant genişliği ve gecikme) okunurken olanlar adanmış (paylaşılmayan) Hızlandırıcı bellek kötü olabilir CPU veya her ikisi de yazma İşlemcisinden. Paylaşılan bellek, okuma ve yazma CPU için ayrılmış bellek yanı sıra gerçekleştirirse, çalışma zamanı varsayılan olarak `access_type_read_write`; Aksi halde çalışma zamanı daha pasif varsayılan seçer `access_type`ve uygulamanın bellek erişirseniz onu geçersiz kılmanıza izin verir Hesaplama tekrar desenlerini farklı bir fayda `access_type`.  
  
 Aşağıdaki kod örneği, varsayılan Hızlandırıcı paylaşılan bellek destekler ve daha sonra varsayılan erişim türü için geçersiz kılar ve oluşturur olup olmadığını belirlemek gösterilmiştir bir `accelerator_view` almaktır.  
  
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
  
 Bir `accelerator_view` her zaman yansıtır `default_cpu_access_type` , `accelerator` geçersiz kılma veya değiştirmek için arabirim sağlar ve ilişkili olduğu kendi `access_type`.  
  
## <a name="changing-the-default-accelerator"></a>Varsayılan Hızlandırıcı değiştirme  
 Varsayılan Hızlandırıcı çağırarak değiştirebileceğiniz `accelerator::set_default` yöntemi. Herhangi bir kod üzerinde GPU yürütülmeden önce yalnızca uygulama yürütme ve değiştirmelisiniz sonra varsayılan Hızlandırıcı değiştirebilirsiniz. Hızlandırıcı değiştirmek için tüm sonraki işlev çağrılarını dönmek `false`. Çağrıda farklı Hızlandırıcı kullanmak isteyip istemediğinizi `parallel_for_each`, bu makalede "Birden çok Hızlandırıcıları kullanma" bölümüne bakın. Aşağıdaki kod örneğinde varsayılan Hızlandırıcı değil benzetilmiş, bir görüntüye bağlı değil ve çift duyarlıklı destekleyen bir ayarlar.  
  
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
  
## <a name="using-multiple-accelerators"></a>Birden çok Hızlandırıcıları  
 Birden çok Hızlandırıcıları uygulamanızda kullanmanın iki yolu vardır:  

-   Geçirebilirsiniz `accelerator_view` çağrıları nesnelere [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) yöntemi.  
  
-   Oluşturabileceğiniz bir `array` kullanarak belirli bir nesne `accelerator_view` nesne. C + AMP çalışma zamanı alacağı `accelerator_view` yakalanan nesnesinden `array` lambda ifadesi nesne.  
  
## <a name="special-accelerators"></a>Özel Hızlandırıcıları  
 Üç özel Hızlandırıcıları aygıt yollarını özellikleri olarak kullanılabilir `accelerator` sınıfı:  
  
- [Accelerator::direct3d_ref veri üyesi](reference/accelerator-class.md#direct3d_ref): Bu tek iş parçacıklı Hızlandırıcı yazılım genel grafik kartı benzetmek için CPU kullanır. Varsayılan olarak hata ayıklama için kullanılır, ancak donanım Hızlandırıcıları yavaş olduğundan, üretimde kullanışlı değildir. Ayrıca, yalnızca DirectX SDK ve Windows SDK'sı kullanılabilir ve müşterilerinizin bilgisayarlarda yüklü olması beklenmez. Daha fazla bilgi için bkz: [GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code).  
  
- [Accelerator::direct3d_warp veri üyesi](reference/accelerator-class.md#direct3d_warp): Bu Hızlandırıcı Streaming SIMD Uzantıları (SSE) kullanan çok çekirdekli CPU C++ AMP kod yürütmek için bir geri dönüş çözümü sağlar.  
  
- [Accelerator::cpu_accelerator veri üyesi](reference/accelerator-class.md#cpu_accelerator): diziler hazırlama yukarı ayarlamak için bu Hızlandırıcı kullanabilirsiniz. C++ AMP kod yürütülemiyor. Daha fazla bilgi için bkz: [C++ AMP hazırlama dizilerde](http://go.microsoft.com/fwlink/p/?linkId=248485) sonrası paralel programlama yerel kod günlüğündeki.  
  
## <a name="interoperability"></a>Birlikte Çalışabilirlik  
 C++ AMP çalışma zamanı arasında birlikte çalışabilirlik destekleyen `accelerator_view` sınıfı ve Direct3D [ID3D11Device arabirimi](http://go.microsoft.com/fwlink/p/?linkId=248488). [Create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view) metodu bir `IUnknown` arabirimi ve döndürür bir `accelerator_view` nesnesi. [Get_device](http://msdn.microsoft.com/en-us/8194125e-8396-4d62-aa8a-65831dea8439) metodu bir `accelerator_view` nesne ve döndürür bir `IUknown` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ AMP (C++ hızlandırılmış yoğun paralellik)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [GPU kodunda hata ayıklama](/visualstudio/debugger/debugging-gpu-code)   
 [accelerator_view Sınıfı](../../parallel/amp/reference/accelerator-view-class.md)
