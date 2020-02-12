---
title: Eşzamanlılık Ad Alanı (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- AMP/Concurrency
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
ms.openlocfilehash: 34c3c10fa6bec2737ba78a71c282f90f284a28c2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139368"
---
# <a name="concurrency-namespace-c-amp"></a>Eşzamanlılık Ad Alanı (C++ AMP)

Veri paralel donanımındaki C++ kodun yürütülmesini hızlandıran sınıfları ve işlevleri sağlar. Daha fazla bilgi için bkz [ C++ . amp genel bakış](../cpp-amp-overview.md)

## <a name="syntax"></a>Sözdizimi

```cpp
namespace Concurrency;
```

## <a name="members"></a>Üyeler

### <a name="namespaces"></a>Ad Alanları

|Ad|Açıklama|
|----------|-----------------|
|[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)|D3D birlikte çalışabilirliği destekleyen işlevler sağlar. , Ek ara kopyalar oluşturmadan,, AMP kodunda işlem için D3D kaynaklarının ve D3D kodunda AMP 'da oluşturulan kaynakların kullanımı için sorunsuz bir şekilde kullanılmasını mümkün. Amp kullanarak C++ , DirectX uygulamalarınızın yoğun işlem yoğunluğu olan bölümlerini kademeli olarak HıZLANDıRıR ve amp hesaplamalarından ÜRETILEN VERILERDE D3D API 'sini kullanabilirsiniz.|
|[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)|`fast_math` ad alanındaki işlevler C99 uyumlu değildir. Her bir işlevin yalnızca tek duyarlıklı sürümleri sağlanır. Bu işlevler, `precise_math` ad alanındaki karşılık gelen işlevlerden daha hızlı olan DirectX iç işlevlerini kullanır ve hızlandırıcıda genişletilmiş çift duyarlıklı destek gerektirmez, ancak daha az doğru olur. C99 Code ile kaynak düzeyinde uyumluluk için her bir işlevin iki sürümü vardır. Her iki sürüm de tek duyarlıklı değerler alır ve döndürür.|
|[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)|Grafik programlama için tasarlanmış türleri ve işlevleri sağlar.|
|[Concurrency::precise_math Ad Alanı](concurrency-precise-math-namespace.md)|`precise_math` ad alanındaki işlevler C99 uyumludur. Her bir işlevin hem tek duyarlıklı hem de çift duyarlıklı sürümleri dahil edilmiştir. Bu işlevler, tek duyarlıklı işlevleri içerir — hızlandırıcı üzerinde genişletilmiş çift duyarlıklı destek gerektirir.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[accelerator Sınıfı](accelerator-class.md)|Fiziksel bir DP ile iyileştirilmiş işlem düğümünün bir soyutlamasını temsil eder.|
|[accelerator_view Sınıfı](accelerator-view-class.md)|Bir C++ amp veri paralel hızlandırıcısında bir sanal cihaz soyutlamasını temsil eder.|
|[accelerator_view_removed Sınıfı](accelerator-view-removed-class.md)|Windows zaman aşımı algılama ve kurtarma mekanizması nedeniyle temeldeki bir DirectX çağrısı başarısız olduğunda oluşturulan özel durum.|
|[array Sınıfı](array-class.md)|Kılavuz etki alanındaki bir `accelerator_view` veri toplama. Bir kılavuz etki alanındaki her öğe için bir değişken koleksiyonudur. Her değişken, bazı C++ türlerine karşılık gelen bir değer içerir.|
|[array_view Sınıfı](array-view-class.md)|\<T, N > dizisindeki verilerin bir görünümünü temsil eder.|
|[completion_future Sınıfı](completion-future-class.md)|Bir C++ amp zaman uyumsuz işlemine karşılık gelen bir geleceği temsil eder.|
|[extent Sınıfı](extent-class.md)|0 ' ın kaynağına sahip N boyutlu bir alanın sınırlarını belirten N tamsayı değerlerinin bir vektörünü temsil eder. Koordinat Vektördeki değerler en önemli değerden en az önemli olarak sıralanır. Örneğin, 3 boyutlu bir alanda, kapsam vektörü (7, 5, 3), z koordinatı 0 ile 7 arasında, y koordinatı 0 ile 5 arasında aralıklar ve x koordinatı 0 ile 3 arasında değişir.|
|[index Sınıfı](index-class.md)|N boyutlu bir dizin noktasını tanımlar.|
|[invalid_compute_domain Sınıfı](invalid-compute-domain-class.md)|Çalışma zamanı `parallel_for_each` çağrı sitesinde belirtilen işlem etki alanını kullanarak bir çekirdek başlatamadığınızda oluşturulan özel durum.|
|[out_of_memory Sınıfı](out-of-memory-class.md)|Bir yöntem sistem veya cihaz belleği olmaması nedeniyle başarısız olduğunda oluşturulan özel durum.|
|[runtime_exception Sınıfı](runtime-exception-class.md)|C++ Amp kitaplığındaki özel durumların temel türü.|
|[tile_barrier Sınıfı](tile-barrier-class.md)|Yalnızca sistem tarafından oluşturulabilir ve `tiled_index` parametresinin bir parçası olarak döşeli `parallel_for_each` lambda öğesine geçirilir. Bu, amacı iş parçacığı grubunda (kutucukta) çalışan iş parçacıklarının yürütülmesini eşitleyeceğiniz `wait()`bir yöntem sağlar.|
|[tiled_extent Sınıfı](tiled-extent-class.md)|`tiled_extent` nesnesi, bir ile üç boyutun bir `extent` nesnesidir ve bu da kapsamı alt alanı tek boyutlu, iki boyutlu veya üç boyutlu döşemelere böler.|
|[tiled_index Sınıfı](tiled-index-class.md)|`tiled_grid` nesnesine bir dizin sağlar. Bu sınıf, yerel kutucuk kaynağına göre ve genel kaynağa göreli olarak öğeye erişmek için özelliklere sahiptir.|
|[uninitialized_object Sınıfı](uninitialized-object-class.md)|Başlatılmamış bir nesne kullanıldığında oluşturulan özel durum.|
|[unsupported_feature Sınıfı](unsupported-feature-class.md)|Desteklenmeyen bir özellik kullanıldığında oluşturulan özel durum.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[access_type numaralandırması](concurrency-namespace-enums-amp.md#access_type)|Veri erişim türünü belirtir.|
|[queuing_mode numaralandırması](concurrency-namespace-enums-amp.md#queuing_mode)|Hızlandırıcıda desteklenen sıraya alma modlarını belirtir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|--------------|-----------------|
|[operator = = Işleci (C++ amp)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Belirtilen veri yapılarının eşit olup olmadığını belirler.|
|[operator! = Işleci (C++ amp)](concurrency-namespace-operators-amp.md#operator_neq)|Belirtilen veri yapılarının eşit olup olmadığını belirler.|
|[operator + Işleci (C++ amp)](concurrency-namespace-operators-amp.md#operator_add)|Belirtilen bağımsız değişkenlerin bileşen temelinde toplamını hesaplar.|
|[operator-Işleci (C++ amp)](concurrency-namespace-operators-amp.md#operator-)|Belirtilen bağımsız değişkenler arasındaki bileşen temelinde farkı hesaplar.|
|[operator * Işleci (C++ amp)](concurrency-namespace-operators-amp.md#operator_star)|Belirtilen bağımsız değişkenlerin bileşen odaklı ürününü hesaplar.|
|[operator/Işleci (C++ amp)](concurrency-namespace-operators-amp.md#operator_div)|Belirtilen bağımsız değişkenlerin bileşen temelinde bölümünü hesaplar.|
|[operator% Işleci (C++ amp)](concurrency-namespace-operators-amp.md#operator_mod)|Belirtilen ikinci bağımsız değişken tarafından belirtilen ilk bağımsız değişkenin mod sayısını hesaplar.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Tüm bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|C++ Amp çalışma zamanının işaretini kaldır.|
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Fazla Yüklendi. Belirtilen konumda depolanan değer, belirtilen ilk değere eşit olarak karşılaştırırsa, belirtilen ikinci değer bir atomik işlemle aynı konumda depolanır.|
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerin toplamına ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerin bit düzeyinde `and` ve bir atomik işlem olarak belirtilen bir değer olarak ayarlar.|
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Fazla Yüklendi. Belirtilen konumda depolanan değeri azaltır ve sonucu atomik bir işlemle aynı konumda depolar.|
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Fazla Yüklendi. Belirtilen konumda depolanan değeri artırır ve sonucu atomik bir işlemle aynı konumda depolar.|
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerden büyük bir değere ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerden küçük bir değere ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerin bit düzeyinde `or` ve bir atomik işlem olarak belirtilen bir değer olarak ayarlar.|
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Fazla Yüklendi. Belirtilen konumda depolanan değeri, bu değerin farkına ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerin bit düzeyinde `xor` ve bir atomik işlem olarak belirtilen bir değer olarak ayarlar.|
|[kopya](concurrency-namespace-functions-amp.md#copy)|Bir C++ amp nesnesini kopyalar. Tüm zaman uyumlu veri aktarımı gereksinimleri karşılandı. Kod bir hızlandırıcı üzerinde kod çalıştırırken veri kopyalanamıyor. Bu işlevin genel formu `copy(src, dest)`.|
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|Bir C++ amp nesnesini kopyalar ve beklemiş olabilecek [completion_future](completion-future-class.md) döndürür. Bir hızlandırıcı üzerinde kod çalışırken veri kopyalanamıyor. Bu işlevin genel formu `copy(src, dest)`.|
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|`restrict(amp)` kısıtlama yan tümcesine sahip bir işlevin yürütülmesini iptal eder.|
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Visual Studio **çıktı** penceresine biçimlendirilmiş bir dize yazdırır ve aynı biçimlendirme dizesine sahip [runtime_exception](runtime-exception-class.md) bir özel durum başlatır.|
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Visual Studio **çıktı** penceresine biçimli bir dize yazdırır. `restrict(amp)` kısıtlama yan tümcesine sahip olan bir işlevden çağırılır.|
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Tüm genel bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[parallel_for_each Işlevi (C++ amp)](concurrency-namespace-functions-amp.md#parallel_for_each)|İşlem etki alanı genelinde bir işlev çalıştırır.|
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|`tile_static` bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|

## <a name="constants"></a>Sabitler

|Ad|Açıklama|
|----------|-----------------|
|[HLSL_MAX_NUM_BUFFERS sabiti](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|DirectX tarafından izin verilen en fazla arabellek sayısı.|
|[MODULENAME_MAX_LENGTH sabiti](concurrency-namespace-constants-amp.md#modulename_max_length)|Modül adının maksimum uzunluğunu depolar. Bu değer, derleyicide ve çalışma zamanında aynı olmalıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

## <a name="see-also"></a>Ayrıca bkz.

[Başvuru (C++ AMP)](reference-cpp-amp.md)
