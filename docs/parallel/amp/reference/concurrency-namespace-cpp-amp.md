---
title: Eşzamanlılık Ad Alanı (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- AMP/Concurrency
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
ms.openlocfilehash: e0870eb046f1cec091a72d49c94a2fea41484340
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278697"
---
# <a name="concurrency-namespace-c-amp"></a>Eşzamanlılık Ad Alanı (C++ AMP)

Sınıfları ve veri-paralel donanımlarda C++ kodu yürütülmesini hızlandıran işlevleri sağlar. Daha fazla bilgi için [C++ AMP'ye genel bakış](../cpp-amp-overview.md)

## <a name="syntax"></a>Sözdizimi

```
namespace Concurrency;
```

## <a name="members"></a>Üyeler

### <a name="namespaces"></a>Ad Alanları

|Ad|Açıklama|
|----------|-----------------|
|[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)|D3D birlikte çalışabilirlik destekleyen işlevleri sağlar. AMP kodunda hesaplamak için D3D kaynaklarını sorunsuz kullanımını ve gereksiz Ara kopyalar oluşturmadan, AMP D3D kodunda oluşturulan kaynakların kullanımını etkinleştirir. DirectX uygulamalarınızın işlem yoğunluklu bölümlerini kademeli olarak hızlandırmak ve AMP hesaplamalarıyla üretilen verilerde D3D API'sini kullanmak için C++ AMP'ı kullanabilirsiniz.|
|[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)|İçindeki işlevler `fast_math` ad alanı, C99 uyumlu değildir. Her işlevin yalnızca tek duyarlıklı sürümleri sağlanır. Bu işlevler karşılık gelen işlevlerden daha hızlı DirectX iç işlevler kullanan `precise_math` ad alanı ve hızlandırıcıda genişletilmiş çift duyarlıklı destek gerektirmeyen, ancak daha az doğru olur. C99 kodu ile kaynak düzeyinde uyumluluk için her işlevin iki sürümü vardır; Her iki sürümü, alır ve tek duyarlıklı değerler döndürür.|
|[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)|Grafik programlama için türleri ve tasarlanmış işlevleri sağlar.|
|[Concurrency::precise_math Ad Alanı](concurrency-precise-math-namespace.md)|İçindeki işlevler `precise_math` ad alanı olan C99 uyumludur. Her işlevin hem tek duyarlık hem çift duyarlık sürümleri dahil edilir. Bu işlevler — Bu, tek duyarlıklı işlevler içerir — hızlandırıcıda genişletilmiş çift duyarlıklı desteği gerektirir.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[accelerator Sınıfı](accelerator-class.md)|Fiziksel bir DP-optimize hesaplama düğümünün bir soyutlamasını temsil eder.|
|[accelerator_view Sınıfı](accelerator-view-class.md)|C++ AMP paralel Veri Hızlandırıcı üzerinde bir sanal cihaz soyutlamayı temsil eder.|
|[accelerator_view_removed Sınıfı](accelerator-view-removed-class.md)|Windows zaman aşımı-algılama-ve-kurtarma mekanizmasına bağlı temel DirectX çağrısı başarısız olduğunda oluşturulan özel durum.|
|[array Sınıfı](array-class.md)|Bulunan veri bir `accelerator_view` ızgara etki alanında. Grid alanındaki her öğe için değişkenlerden koleksiyonudur. Her değişken bir C++ türüne karşılık gelen bir değer tutar.|
|[array_view Sınıfı](array-view-class.md)|Bir dizi içindeki verinin bir görünümünü temsil eder\<T, N >.|
|[completion_future Sınıfı](completion-future-class.md)|Karşılık gelen bir gelecek bir C++ AMP zaman uyumsuz işlemi temsil eder.|
|[extent Sınıfı](extent-class.md)|Kaynağı 0 olan bir N-boyutlu boşluk uzayın sınırlarını belirten N tam sayı değerler bir vektörü temsil eder. Koordinat vektöründeki değerler en önemliden en az önemliye doğru sıralanır. Örneğin, Kartezyen 3-boyutlu uzayda, kapsam vektörü (7,5,3) z koordinatı 0 ile 7, 0'dan y koordinatı aralığı 5, aralığı ve x koordinatı 0 ile 3 olarak değişen bir alanı temsil eder.|
|[index Sınıfı](index-class.md)|N boyutlu bir dizin noktası tanımlar.|
|[invalid_compute_domain Sınıfı](invalid-compute-domain-class.md)|Çalışma zamanı sırasında belirtilen hesaplama alanını kullanarak bir çekirdeği başlatamadığında oluşturulan özel durum `parallel_for_each` çağrı sitesini.|
|[out_of_memory Sınıfı](out-of-memory-class.md)|Bir yöntem sistem ya da cihaz belleği olmaması nedeniyle başarısız olduğunda oluşturulan özel durum.|
|[runtime_exception Sınıfı](runtime-exception-class.md)|C++ AMP kitaplığında özel durumlar için temel türü.|
|[tile_barrier Sınıfı](tile-barrier-class.md)|Yalnızca sistem tarafından oluşturulabilen ve geçirilen özellik sınıfı döşenmiş `parallel_for_each` parçası olarak lambda `tiled_index` parametresi. Bir yöntem sağlar `wait()`, amacı olan iş parçacığı grubunda (döşeme) çalışan iş parçacıklarının yürütülmesini eşitlemek için.|
|[tiled_extent Sınıfı](tiled-extent-class.md)|A `tiled_extent` nesnesi bir `extent` halidir tek boyutlu, iki boyutlu veya üç boyutlu kesen bir veya üç boyutta nesnesi.|
|[tiled_index Sınıfı](tiled-index-class.md)|Bir dizin sağlar bir `tiled_grid` nesne. Bu sınıf, öğe yerel döşeme kaynağına ve genel kaynağa göre erişmek için özelliklere sahiptir.|
|[uninitialized_object Sınıfı](uninitialized-object-class.md)|Başlatılmamış bir nesne kullanıldığında oluşturulan özel durum.|
|[unsupported_feature Sınıfı](unsupported-feature-class.md)|Desteklenmeyen bir özellik kullanıldığında oluşturulan özel durum.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[access_type numaralandırması](concurrency-namespace-enums-amp.md#access_type)|Veri erişim türünü belirtir.|
|[queuing_mode numaralandırması](concurrency-namespace-enums-amp.md#queuing_mode)|Hızlandırıcı üzerinde desteklenen sıralama modlarını belirtir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|--------------|-----------------|
|[operator == işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Belirtilen veri yapılarının eşit olup olmadığını belirler.|
|[işleç! = işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Belirtilen veri yapılarının eşit olup olmadığını belirler.|
|[operator + işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|Belirtilen bağımsız değişkenlerin bileşen odaklı toplamını hesaplar.|
|[operator-işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|Belirtilen bağımsız değişkenlerin bileşen odaklı farkı hesaplar.|
|[operator * işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|Belirtilen bağımsız değişkenlerin bileşen odaklı çarpımını hesaplar.|
|[operator / işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|Belirtilen bağımsız değişkenlerin bileşen odaklı bölümünü hesaplar.|
|[operator % işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_mod)|İkinci belirtilen bağımsız değişken tarafından belirtilen ilk bağımsız değişken modüllerini hesaplar.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Tüm bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|C++ AMP çalışma zamanının başlamasını iptal eder.|
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Fazla Yüklendi. Belirtilen konumda depolanan değer ilk belirtilen değere eşit karşılaştırırsa, ikinci belirtilen değer bir atomik işlem olarak aynı konumda depolanır.|
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Fazla Yüklendi. Atomik işlem olarak belirtilen değere belirtilen konumda depolanan değeri ayarlar.|
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Fazla Yüklendi. Atomik işlem olarak bu değeri ve belirtilen değeri toplamına belirtilen konumda depolanan değeri ayarlar.|
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Fazla Yüklendi. Bit düzeyinde için belirtilen konumda depolanan değeri ayarlar `and` değeri ve atomik işlem olarak belirtilen değeri.|
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Fazla Yüklendi. Değer belirtilen konumda depolanan ve atomik işlem olarak aynı konumdaki sonucu depolar azaltır.|
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Fazla Yüklendi. Belirtilen konumda depolanan değeri artırır ve atomik işlem olarak aynı konumdaki sonucu depolar.|
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Fazla Yüklendi. Ayarlar büyüğü belirtilen konumda depolanan değeri o değerin ve atomik işlem olarak belirtilen değere.|
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Fazla Yüklendi. Ayarlar daha belirtilen konumda depolanan değeri o değerin ve atomik işlem olarak belirtilen değere.|
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Fazla Yüklendi. Bit düzeyinde için belirtilen konumda depolanan değeri ayarlar `or` değeri ve atomik işlem olarak belirtilen değeri.|
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Fazla Yüklendi. Farkı bu değeri ve belirtilen değeri atomik işlem olarak belirtilen konumda depolanan değeri ayarlar.|
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Fazla Yüklendi. Bit düzeyinde için belirtilen konumda depolanan değeri ayarlar `xor` değeri ve atomik işlem olarak belirtilen değeri.|
|[kopyalama](concurrency-namespace-functions-amp.md#copy)|C++ AMP nesnesi kopyalar. Tüm zaman uyumlu veri aktarımı gereksinimleri karşılanır. Kodu kod hızlandırıcıda çalışıyor olduğunda veriler kopyalanamaz. Bu işlevin genel formu `copy(src, dest)`.|
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|C++ AMP nesnesi kopyalar ve döndürür [completion_future](completion-future-class.md) , beklenen. Kod hızlandırıcıda çalışıyor olduğunda veriler kopyalanamaz. Bu işlevin genel formu `copy(src, dest)`.|
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|Sahip bir işlevin yürütülmesini durdurur `restrict(amp)` kısıtlama yan tümcesi.|
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Visual Studio biçimlendirilmiş bir dize yazdırır **çıkış** penceresine bir [runtime_exception](runtime-exception-class.md) aynı biçime sahip bir özel durum dize.|
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Visual Studio biçimlendirilmiş bir dize yazdırır **çıkış** penceresi. Var olan bir işlevden çağrılır `restrict(amp)` kısıtlama yan tümcesi.|
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Tüm genel bellek kullanımları tamamlanıncaya kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller tamamlanmıştır.|
|[parallel_for_each işlevi (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|Hesaplama alanı genelinde bir işlev çalıştırır.|
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller `tile_static` bellek erişimleri tamamlanana.|

## <a name="constants"></a>Sabitler

|Ad|Açıklama|
|----------|-----------------|
|[HLSL_MAX_NUM_BUFFERS sabiti](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Arabellek DirectX tarafından izin verilen maksimum sayısı.|
|[MODULENAME_MAX_LENGTH sabiti](concurrency-namespace-constants-amp.md#modulename_max_length)|Modül adının en büyük uzunluğunu saklar. Bu değer derleyicide ve çalışma zamanı aynı olmalıdır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp.h

## <a name="see-also"></a>Ayrıca bkz.

[Başvuru (C++ AMP)](reference-cpp-amp.md)
