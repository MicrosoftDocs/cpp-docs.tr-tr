---
description: 'Daha fazla bilgi edinin: eşzamanlılık ad alanı (C++ AMP)'
title: Eşzamanlılık Ad Alanı (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- AMP/Concurrency
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
ms.openlocfilehash: 9334634dc3d332b24f067c04f00e82feea5a6001
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342588"
---
# <a name="concurrency-namespace-c-amp"></a>Eşzamanlılık Ad Alanı (C++ AMP)

Veri paralel donanımlarda C++ kodu yürütmeyi hızlandıran sınıfları ve işlevleri sağlar. Daha fazla bilgi için bkz. [C++ amp genel bakış](../cpp-amp-overview.md)

## <a name="syntax"></a>Syntax

```cpp
namespace Concurrency;
```

## <a name="members"></a>Üyeler

### <a name="namespaces"></a>Ad alanları

|Ad|Açıklama|
|----------|-----------------|
|[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)|D3D birlikte çalışabilirliği destekleyen işlevler sağlar. , Ek ara kopyalar oluşturmadan,, AMP kodunda işlem için D3D kaynaklarının ve D3D kodunda AMP 'da oluşturulan kaynakların kullanımı için sorunsuz bir şekilde kullanılmasını mümkün. DirectX uygulamalarınızın yoğun işlem yoğunluklu bölümlerini artımlı olarak hızlandırmak ve AMP hesaplamalarından üretilen verilerde D3D API 'sini kullanmak için C++ AMP kullanabilirsiniz.|
|[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)|`fast_math`Ad alanındaki Işlevler C99 uyumlu değildir. Her bir işlevin yalnızca tek duyarlıklı sürümleri sağlanır. Bu işlevler, ad alanındaki karşılık gelen işlevlerden daha hızlı olan DirectX iç işlevlerini kullanır `precise_math` ve hızlandırıcıda genişletilmiş çift duyarlıklı destek gerektirmez, ancak daha az doğru olur. C99 Code ile kaynak düzeyinde uyumluluk için her bir işlevin iki sürümü vardır. Her iki sürüm de tek duyarlıklı değerler alır ve döndürür.|
|[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)|Grafik programlama için tasarlanmış türleri ve işlevleri sağlar.|
|[Eşzamanlılık::p recise_math ad alanı](concurrency-precise-math-namespace.md)|`precise_math`Ad alanındaki Işlevler C99 uyumludur. Her bir işlevin hem tek duyarlıklı hem de çift duyarlıklı sürümleri dahil edilmiştir. Bu işlevler, tek duyarlıklı işlevleri içerir — hızlandırıcı üzerinde genişletilmiş çift duyarlıklı destek gerektirir.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[Hızlandırıcı sınıfı](accelerator-class.md)|Fiziksel bir DP ile iyileştirilmiş işlem düğümünün bir soyutlamasını temsil eder.|
|[accelerator_view sınıfı](accelerator-view-class.md)|C++ AMP veri paralel hızlandırıcıda sanal cihaz soyutlamasını temsil eder.|
|[accelerator_view_removed sınıfı](accelerator-view-removed-class.md)|Windows zaman aşımı algılama ve kurtarma mekanizması nedeniyle temeldeki bir DirectX çağrısı başarısız olduğunda oluşturulan özel durum.|
|[Array sınıfı](array-class.md)|`accelerator_view`Kılavuz etki alanındaki bir veri toplama. Bir kılavuz etki alanındaki her öğe için bir değişken koleksiyonudur. Her değişken, bazı C++ türlerine karşılık gelen bir değer içerir.|
|[array_view sınıfı](array-view-class.md)|Dizideki verilerin bir görünümünü temsil eder \<T,N> .|
|[completion_future sınıfı](completion-future-class.md)|C++ AMP zaman uyumsuz bir işleme karşılık gelen bir ileride temsil eder.|
|[kapsam sınıfı](extent-class.md)|0 ' ın kaynağına sahip N boyutlu bir alanın sınırlarını belirten N tamsayı değerlerinin bir vektörünü temsil eder. Koordinat Vektördeki değerler en önemli değerden en az önemli olarak sıralanır. Örneğin, 3 boyutlu bir alanda, kapsam vektörü (7, 5, 3), z koordinatı 0 ile 7 arasında, y koordinatı 0 ile 5 arasında aralıklar ve x koordinatı 0 ile 3 arasında değişir.|
|[Dizin sınıfı](index-class.md)|N boyutlu bir dizin noktasını tanımlar.|
|[invalid_compute_domain sınıfı](invalid-compute-domain-class.md)|Çalışma zamanı, çağrı sitesinde belirtilen işlem etki alanını kullanarak bir çekirdek başlatamadığınızda oluşturulan özel durum `parallel_for_each` .|
|[out_of_memory sınıfı](out-of-memory-class.md)|Bir yöntem sistem veya cihaz belleği olmaması nedeniyle başarısız olduğunda oluşturulan özel durum.|
|[runtime_exception sınıfı](runtime-exception-class.md)|C++ AMP kitaplığındaki özel durumların temel türü.|
|[tile_barrier sınıfı](tile-barrier-class.md)|Yalnızca sistem tarafından oluşturulabilir ve parametresinin bir parçası olarak döşeli bir lambda 'e geçirilir `parallel_for_each` `tiled_index` . Bu, `wait()` amacı iş parçacığı grubunda (kutucukta) çalışan iş parçacıklarının yürütülmesini eşitleyeceğiniz bir yöntem sağlar.|
|[tiled_extent sınıfı](tiled-extent-class.md)|Bir `tiled_extent` nesne, `extent` bir-üç boyutun bir nesnesidir ve bu, kapsamı alt alanı tek boyutlu, iki boyutlu veya üç boyutlu döşemelere böler.|
|[tiled_index sınıfı](tiled-index-class.md)|Nesnesine bir dizin sağlar `tiled_grid` . Bu sınıf, yerel kutucuk kaynağına göre ve genel kaynağa göreli olarak öğeye erişmek için özelliklere sahiptir.|
|[uninitialized_object sınıfı](uninitialized-object-class.md)|Başlatılmamış bir nesne kullanıldığında oluşturulan özel durum.|
|[unsupported_feature sınıfı](unsupported-feature-class.md)|Desteklenmeyen bir özellik kullanıldığında oluşturulan özel durum.|

### <a name="enumerations"></a>Listelemeler

|Ad|Açıklama|
|----------|-----------------|
|[access_type numaralandırması](concurrency-namespace-enums-amp.md#access_type)|Veri erişim türünü belirtir.|
|[queuing_mode numaralandırması](concurrency-namespace-enums-amp.md#queuing_mode)|Hızlandırıcıda desteklenen sıraya alma modlarını belirtir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|--------------|-----------------|
|[operator = = Işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Belirtilen veri yapılarının eşit olup olmadığını belirler.|
|[operator! = Işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Belirtilen veri yapılarının eşit olup olmadığını belirler.|
|[operator + Işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|Belirtilen bağımsız değişkenlerin bileşen temelinde toplamını hesaplar.|
|[operator-Işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|Belirtilen bağımsız değişkenler arasındaki bileşen temelinde farkı hesaplar.|
|[operator * Işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|Belirtilen bağımsız değişkenlerin bileşen odaklı ürününü hesaplar.|
|[operator/Işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|Belirtilen bağımsız değişkenlerin bileşen temelinde bölümünü hesaplar.|
|[operator% Işleci (C++ AMP)](concurrency-namespace-operators-amp.md#operator_mod)|Belirtilen ikinci bağımsız değişken tarafından belirtilen ilk bağımsız değişkenin mod sayısını hesaplar.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Tüm bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|C++ AMP çalışma zamanının kaydını geri alır.|
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Fazla Yüklendi. Belirtilen konumda depolanan değer, belirtilen ilk değere eşit olarak karşılaştırırsa, belirtilen ikinci değer bir atomik işlemle aynı konumda depolanır.|
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerin toplamına ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Fazla Yüklendi. Belirtilen konumda depolanan değeri `and` Bu değerin bit seviyesinde ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Fazla Yüklendi. Belirtilen konumda depolanan değeri azaltır ve sonucu atomik bir işlemle aynı konumda depolar.|
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Fazla Yüklendi. Belirtilen konumda depolanan değeri artırır ve sonucu atomik bir işlemle aynı konumda depolar.|
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerden büyük bir değere ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Fazla Yüklendi. Belirtilen konumda depolanan değeri bu değerden küçük bir değere ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Fazla Yüklendi. Belirtilen konumda depolanan değeri `or` Bu değerin bit seviyesinde ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Fazla Yüklendi. Belirtilen konumda depolanan değeri, bu değerin farkına ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Fazla Yüklendi. Belirtilen konumda depolanan değeri `xor` Bu değerin bit seviyesinde ve bir atomik işlem olarak belirtilen değere ayarlar.|
|[kopya](concurrency-namespace-functions-amp.md#copy)|C++ AMP nesnesini kopyalar. Tüm zaman uyumlu veri aktarımı gereksinimleri karşılandı. Kod bir hızlandırıcı üzerinde kod çalıştırırken veri kopyalanamıyor. Bu işlevin genel formu `copy(src, dest)` .|
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|C++ AMP nesnesini kopyalar ve beklemiş olabilecek [completion_future](completion-future-class.md) döndürür. Bir hızlandırıcı üzerinde kod çalışırken veri kopyalanamıyor. Bu işlevin genel formu `copy(src, dest)` .|
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|Kısıtlama yan tümcesine sahip bir işlevin yürütülmesini iptal eder `restrict(amp)` .|
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Visual Studio **çıktı** penceresine biçimlendirilmiş bir dize yazdırır ve aynı biçimlendirme dizesine sahip [runtime_exception](runtime-exception-class.md) bir özel durum başlatır.|
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Visual Studio **çıktı** penceresine biçimli bir dize yazdırır. Kısıtlama yan tümcesine sahip olan bir işlevden çağırılır `restrict(amp)` .|
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Tüm genel bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[parallel_for_each Işlevi (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|İşlem etki alanı genelinde bir işlev çalıştırır.|
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller `tile_static` .|

## <a name="constants"></a>Sabitler

|Ad|Açıklama|
|----------|-----------------|
|[HLSL_MAX_NUM_BUFFERS sabiti](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|DirectX tarafından izin verilen en fazla arabellek sayısı.|
|[MODULENAME_MAX_LENGTH sabiti](concurrency-namespace-constants-amp.md#modulename_max_length)|Modül adının maksimum uzunluğunu depolar. Bu değer, derleyicide ve çalışma zamanında aynı olmalıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

## <a name="see-also"></a>Ayrıca bkz.

[Başvuru (C++ AMP)](reference-cpp-amp.md)
