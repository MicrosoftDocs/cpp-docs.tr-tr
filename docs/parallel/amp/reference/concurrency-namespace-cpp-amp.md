---
title: Eşzamanlılık Namespace (C++ AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- AMP/Concurrency
dev_langs:
- C++
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 127c1b63693b128e9cdf23813bbfe8e0ec251f9d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693383"
---
# <a name="concurrency-namespace-c-amp"></a>Eşzamanlılık Ad Alanı (C++ AMP)
Sınıfları ve verileri paralel donanımda C++ kod yürütmeyi hızlandırmak işlevleri sağlar. Daha fazla bilgi için bkz: [C++ AMP'ye genel bakış](../cpp-amp-overview.md)  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="namespaces"></a>Ad Alanları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)|D3D birlikte çalışabilirlik desteği işlevleri sağlar. İşlem AMP kodda D3D kaynaklarının sorunsuz kullanımını ve Ara yedek kopya oluşturmak zorunda kalmadan D3D kodda AMP içinde oluşturulan kaynaklarının kullanımını etkinleştirir. Artımlı olarak DirectX uygulamalarınızı işlem yoğunluklu bölümlerini hızlandırmak ve AMP hesaplamalar üretilen veriler üzerinde D3D API kullanmak için C++ AMP kullanabilirsiniz.|  
|[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)|İşlevlerini `fast_math` ad alanı C99 uyumlu değildir. Yalnızca tek duyarlıklı sürümleri her işlev sağlanır. Bu işlevler karşılık gelen işlevlerde daha hızlıdır DirectX iç işlevleri kullanmak `precise_math` ad alanı ve Hızlandırıcı genişletilmiş çift duyarlıklı desteği gerektirmez, ancak daha az kesin. Her işlev C99 koduyla kaynak düzeyi uyumluluk için iki sürümü vardır; Her iki sürümünü alın ve tek duyarlıklı değerleri döndürür.|  
|[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)|Türler ve tasarlanmış işlevler için grafik programlamaya sağlar.|  
|[Concurrency::precise_math Ad Alanı](concurrency-precise-math-namespace.md)|İşlevlerini `precise_math` ad alanı olan C99 uyumlu. Her işlevi tek duyarlıklı ve çift duyarlıklı sürümleri dahil edilir. Bu işlevler — bu tek duyarlıklı işlevler içerir — Hızlandırıcı genişletilmiş çift duyarlıklı desteğini gerektirir.|  
  
### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accelerator Sınıfı](accelerator-class.md)|Bir fiziksel DP iyileştirilmiş işlem düğümünde bir soyutlamasını temsil eder.|  
|[accelerator_view Sınıfı](accelerator-view-class.md)|C++ AMP verileri paralel Hızlandırıcı üzerinde bir sanal cihaz soyutlama temsil eder.|  
|[accelerator_view_removed Sınıfı](accelerator-view-removed-class.md)|Windows zaman aşımı-algılama-ve-kurtarma mekanizması nedeniyle bir temel alınan DirectX araması başarısız olmadığında oluşan özel durum.|  
|[array Sınıfı](array-class.md)|Veri toplama üzerinde bir `accelerator_view` kılavuz etki alanındaki. Değişkenleri, bir kılavuz etki alanındaki her öğe için bir tane koleksiyonudur. Her bir değişken bazı C++ türüne karşılık gelen bir değer içerir.|  
|[array_view Sınıfı](array-view-class.md)|Bir dizi verileri görünüme temsil eden\<T, N >.|  
|[completion_future Sınıfı](completion-future-class.md)|Karşılık gelen bir gelecekteki bir C++ AMP zaman uyumsuz işlemi temsil eder.|  
|[extent Sınıfı](extent-class.md)|Vektör 0 olan bir kaynağı olan bir N boyutlu alanı sınırları belirtin N tamsayı değerleri temsil eder. Koordinat vektör değerleri en önemli için en az önemli sıralanır. Örneğin, Kartezyen 3 boyutlu alanında ölçüde vektör (7,5,3) 7, 0'dan y koordinat aralıkları 5, 0'dan z koordinatı aralıkları ve 0 ile 3 x koordinatını değişen bir alanı temsil eder.|  
|[index Sınıfı](index-class.md)|N boyutlu bir dizin noktası tanımlar.|  
|[invalid_compute_domain Sınıfı](invalid-compute-domain-class.md)|Çalışma zamanı sırasında belirtilen işlem etki alanı kullanarak bir çekirdek başlatılamıyor olmadığında oluşan özel durum `parallel_for_each` çağrısı site.|  
|[out_of_memory Sınıfı](out-of-memory-class.md)|Bir yöntem sistem ya da aygıt bellek yetersizliği nedeniyle başarısız olmadığında oluşan özel durum.|  
|[runtime_exception Sınıfı](runtime-exception-class.md)|C++ AMP Kitaplığı'nda özel durumlar için temel türü.|  
|[tile_barrier Sınıfı](tile-barrier-class.md)|Yalnızca sistem tarafından creatable ve geçirilir bir yetenek sınıfı bir döşeli `parallel_for_each` parçası olarak lambda `tiled_index` parametresi. Bir yöntem sağlar `wait()`, amacı olan iş parçacığı grubu (döşeme) çalışan iş parçacıklarının yürütülmesine eşitlenecek.|  
|[tiled_extent Sınıfı](tiled-extent-class.md)|A `tiled_extent` nesne bir `extent` tek boyutlu, iki boyutlu ya da üç boyutlu döşemesine ölçüde alanı subdivides nesne bir ile üç boyut.|  
|[tiled_index Sınıfı](tiled-index-class.md)|Bir dizine sağlayan bir `tiled_grid` nesnesi. Bu sınıf öğesine yerel bölmesi kaynağa göreli ve genel kaynağa göreli erişmek için özellikler vardır.|  
|[uninitialized_object Sınıfı](uninitialized-object-class.md)|Başlatılmamış bir nesneye kullanıldığında oluşan özel durum.|  
|[unsupported_feature Sınıfı](unsupported-feature-class.md)|Desteklenmeyen bir özellik kullanıldığında oluşan özel durum.|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[access_type numaralandırması](concurrency-namespace-enums-amp.md#access_type)|Veri erişim türünü belirtir.|  
|[queuing_mode numaralandırması](concurrency-namespace-enums-amp.md#queuing_mode)|Hızlandırıcı üzerinde desteklenen sıralama modları belirtir.|  
  
### <a name="operators"></a>İşleçler  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[operator == işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Belirtilen veri yapılarını eşit olup olmadığını belirler.|  
|[operator! = işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Belirtilen veri yapılarını eşit olup olmadığını belirler.|  
|[operator + işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|Belirtilen bağımsız değişkenler component-wise toplamını hesaplar.|  
|[operator-işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|Belirtilen bağımsız değişkenler arasındaki component-wise farkı hesaplar.|  
|[operator * işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|Belirtilen bağımsız değişkenler component-wise çarpımını hesaplar.|  
|[operator / işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|Belirtilen bağımsız değişkenler component-wise sayının hesaplar.|  
|[operator % işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_mod)|Modulus ilk belirtilen bağımsız değişkenin ikinci belirtilen bağımsız değişken olarak hesaplar.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Tüm iş parçacıklarının tüm bellek erişimler tamamlanana kadar döşemesinin yürütülmesini engeller.|  
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|C++ AMP çalışma zamanı uninitializes.|  
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Fazla Yüklendi. Belirtilen konumda saklanan değeri ilk belirtilen değere eşit karşılaştırır, ikinci belirtilen değere atomik bir işlem ile aynı konumda depolanır.|  
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Fazla Yüklendi. Belirtilen değer için belirtilen konumda atomik bir işlem olarak depolanan değeri ayarlar.|  
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Fazla Yüklendi. Bu değer ve belirli bir değeri toplamı için belirtilen konumda atomik bir işlem olarak depolanan değeri ayarlar.|  
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Fazla Yüklendi. Bitsel belirtilen konumda saklanan değeri ayarlar `and` bu değeri ve atomik bir işlem olarak belirtilen değeri.|  
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Fazla Yüklendi. Değeri belirtilen konumda depolanır ve sonucu atomik bir işlem ile aynı konumda depolar azaltır.|  
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Fazla Yüklendi. Belirtilen konumda saklanan değeri artırır ve sonucu atomik bir işlem ile aynı konumda depolar.|  
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Fazla Yüklendi. Büyük için belirtilen konumda saklanan değeri ayarlar bu değeri ve atomik bir işlem olarak belirtilen değeri.|  
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Fazla Yüklendi. Küçük için belirtilen konumda saklanan değeri ayarlar bu değeri ve atomik bir işlem olarak belirtilen değeri.|  
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Fazla Yüklendi. Bitsel belirtilen konumda saklanan değeri ayarlar `or` bu değeri ve atomik bir işlem olarak belirtilen değeri.|  
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Fazla Yüklendi. Bu değer ve belirtilen değeri fark atomik bir işlem olarak için belirtilen konumda saklanan değeri ayarlar.|  
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Fazla Yüklendi. Bitsel belirtilen konumda saklanan değeri ayarlar `xor` bu değeri ve atomik bir işlem olarak belirtilen değeri.|  
|[Kopyalama](concurrency-namespace-functions-amp.md#copy)|C++ AMP nesnesini kopyalar. Tüm zaman uyumlu veri aktarımı gereksinimleri karşılıyor. Kod üzerinde Hızlandırıcı kod çalıştırırken veriler kopyalanamaz. Bu işlevin genel form `copy(src, dest)`.|  
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|C++ AMP nesnesini kopyalar ve döndürür [completion_future](completion-future-class.md) , beklenen. Kod Hızlandırıcı üzerinde çalışırken, veriler kopyalanamaz. Bu işlevin genel form `copy(src, dest)`.|  
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|Olan bir işlev yürütülmesini durdurur `restrict(amp)` kısıtlama yan tümcesi.|  
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Visual Studio biçimlendirilmiş bir dize yazdırır **çıkış** penceresini açın ve başlatır bir [runtime_exception](runtime-exception-class.md) aynı biçime sahip özel durum dize.|  
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Visual Studio biçimlendirilmiş bir dize yazdırır **çıkış** penceresi. Olan bir işlev adlı `restrict(amp)` kısıtlama yan tümcesi.|  
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Tüm iş parçacıklarının tüm genel bellek erişen kadar döşemesinin blokları yürütülmesi tamamlandı.|  
|[parallel_for_each işlevi (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|Bir işlev işlem etki alanı arasında çalışır.|  
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Engeller döşemesinin kadar tüm iş parçacıklarının yürütülmesine `tile_static` bellek erişimleri tamamlandı.|  
  
## <a name="constants"></a>Sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HLSL_MAX_NUM_BUFFERS sabiti](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Arabellek DirectX tarafından izin verilen maksimum sayısı.|  
|[MODULENAME_MAX_LENGTH sabiti](concurrency-namespace-constants-amp.md#modulename_max_length)|Modül adının uzunluğu en fazla depolar. Bu değer, derleyici ve çalışma zamanı aynı olmalıdır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (C++ AMP)](reference-cpp-amp.md)



