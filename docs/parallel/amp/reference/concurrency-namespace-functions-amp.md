---
title: Eşzamanlılık ad alanı işlevleri (AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- amp/Concurrency::all_memory_fence
- amp/Concurrency::atomic_compare_exchange
- amp/Concurrency::atomic_fetch_dec
- amp/Concurrency::atomic_fetch_max
- amp/Concurrency::atomic_fetch_min
- amp/Concurrency::copy
- amp/Concurrency::direct3d_abort
- amp/Concurrency::direct3d_printf
- amp/Concurrency::global_memory_fence
- amp/Concurrency::tile_static_memory_fence
dev_langs:
- C++
ms.assetid: 2bef0985-cb90-4ece-90b9-66529aec73c9
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 360c253860931f00e65575250d3944b05dc9c4a9
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="concurrency-namespace-functions-amp"></a>Eşzamanlılık ad alanı işlevleri (AMP)
||||  
|-|-|-|  
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|  
|[atomic_exchange işlevi (C++ AMP)](#atomic_exchange)|[atomic_fetch_add işlevi (C++ AMP)](#atomic_fetch_add)|[atomic_fetch_and işlevi (C++ AMP)](#atomic_fetch_and)|  
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|  
|[atomic_fetch_min](#atomic_fetch_min)|[atomic_fetch_or işlevi (C++ AMP)](#atomic_fetch_or)|[atomic_fetch_sub Function (C++ AMP)](#atomic_fetch_sub)|  
|[atomic_fetch_xor işlevi (C++ AMP)](#atomic_fetch_xor)|[Kopyalama](#copy)|[copy_async](#copy_async)|  
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|  
|[global_memory_fence](#global_memory_fence)|[parallel_for_each işlevi (C++ AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|  
  
##  <a name="all_memory_fence"></a>  all_memory_fence  
 Tüm iş parçacıklarının tüm bellek erişimler tamamlanana kadar döşemesinin yürütülmesini engeller. Bu, tüm bellek erişimler iş parçacığı döşemesinin başka bir iş parçacığı görünür ve program sırada çalıştırılan sağlar.  
  
```  
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Barrier`  
 A `tile_barrier` nesnesi.  
  
##  <a name="amp_uninitialize"></a>  amp_uninitialize  
 C++ AMP çalışma zamanı uninitializes. Birden çok kez bir uygulamaları ömrü boyunca bu işlevi çağırmak için uygundur. Bu işlev çağırma tüm C++ AMP API afer çağırma C++ AMP çalışma zamanı yeniden başlatır. Bu işlev çağrıları arasında C++ AMP nesneleri kullanmak için geçersiz olduğunu ve bunun nedenle tanımsız davranışlara neden unutmayın. Ayrıca, aynı anda bu işlev ve diğer AMP API'leri çağırmak geçersiz ve tanımsız davranışlara neden.  
  
```  
void __cdecl amp_uninitialize();
```  
  
##  <a name="atomic_compare_exchange"></a>  atomic_compare_exchange  
 Otomatik olarak karşılaştırır bellek konumda ikinci belirtilen bağımsız değişkenin değeri ile eşitlik için ilk bağımsız değişkeninde belirtilen değer ve değerleri aynıysa bellek konumuna değerinde üçüncü bağımsız değişkeni belirtilen değiştirilir.  
  
```  
inline bool atomic_compare_exchange(
    _Inout_ int* _Dest,  
    _Inout_ int* _Expected_value,  
    int value  
    ) restrict(amp)

 
inline bool atomic_compare_exchange(
    _Inout_ unsigned int* _Dest,  
    _Inout_ unsigned int* _Expected_value,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Hangi Karşılaştırılacak değerlerden biri konumdan okuma ve yeni değer varsa, depolanması için sahip olduğu.  
  
 `_Expected_value`  
 Karşılaştırılacak ikinci değer okuma konumu.  
  
 `value`  
 Tarafından belirtilen bellek konumuna depolanması için değeri `_Dest` varsa `_Dest` eşittir `_Expected_value`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` İşlem başarılı olursa; Aksi takdirde `false`.  
  

##  <a name="atomic_exchange"></a>  atomic_exchange işlevi (C++ AMP)  
 Hedef konum değerini atomik bir işlem olarak ayarlar.  
  
```  
inline int atomic_exchange(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_exchange(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)

 
inline float atomic_exchange(
    _Inout_ float* _Dest,  
    float value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Destionation konuma işaretçi.  
  
 `value`  
 Yeni değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hedef konumu özgün değeri.  
  

##  <a name="atomic_fetch_add"></a>  atomic_fetch_add işlevi (C++ AMP)  
 Otomatik olarak bir bellek konumunu değer için bir değer ekleyin.  
  
```  
inline int atomic_fetch_add(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_add(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Bellek konumuna yönelik işaretçi.  
  
 `value`  
 Eklenecek değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek konumuna özgün değeri.  
  
##  <a name="atomic_fetch_and"></a>  atomic_fetch_and işlevi (C++ AMP)  
 Otomatik olarak bir değer ve bir bellek konumunu değerini bit tabanlı ve işlemi gerçekleştirir.  
  
```  
inline int atomic_fetch_and(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_and(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Bellek konumuna yönelik işaretçi.  
  
 `value`  
 Bit düzeyinde AND hesaplamada kullanmak için değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek konumuna özgün değeri.  
  
##  <a name="atomic_fetch_dec"></a>  atomic_fetch_dec  
 Otomatik olarak azaltır değeri belirtilen bellek konumda depolanır.  
  
```  
inline int atomic_fetch_dec(_Inout_ int* _Dest  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Değerin azaltılır bellekte konumdur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek konumunda depolanan özgün değer.  
  
##  <a name="atomic_fetch_inc"></a>  atomic_fetch_inc  
 Belirtilen bellek konumunda depolanan değeri otomatik olarak yükseltir.  
  
```  
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

 
inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Bellek değerinin artırılması konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek konumunda depolanan özgün değer.  
  
##  <a name="atomic_fetch_max"></a>  atomic_fetch_max  
 Otomatik olarak ilk bağımsız değişken ve ikinci bağımsız değişkeni belirtilen değeri belirtilen bellek konumunda depolanan değer arasında bir maksimum değer hesaplar ve aynı bellek konumda depolar.  
  
```  
inline int atomic_fetch_max(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_max(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Hangi Karşılaştırılacak değerlerden biri konumdan okuma ve en fazla iki değerin depolanması olduğu.  
  
 `value`  
 Belirtilen konumda değerine Karşılaştırılacak değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen konum konumunda depolanan özgün değer.  
  
##  <a name="atomic_fetch_min"></a>  atomic_fetch_min  
 Otomatik olarak ilk bağımsız değişken ve ikinci bağımsız değişkeni belirtilen değeri belirtilen bellek konumda saklanan değeri arasında en düşük değer hesaplar ve aynı bellek konumda depolar.  
  
```  
inline int atomic_fetch_min(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_min(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Hangi Karşılaştırılacak değerlerden biri konumdan okuyun ve en az iki değerin depolanması olduğu.  
  
 `value`  
 Belirtilen konumda değerine Karşılaştırılacak değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen konum konumunda depolanan özgün değer.  
  
##  <a name="atomic_fetch_or"></a>  atomic_fetch_or işlevi (C++ AMP)  
 Otomatik olarak bir değer ve bir bellek konumunu değeri ile bit tabanlı veya işlemi gerçekleştirir.  
  
```  
inline int atomic_fetch_or(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_or(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Bellek konumuna yönelik işaretçi.  
  
 `value`  
 Bit düzeyinde OR hesaplanmasında kullanılacak değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek konumuna özgün değeri.  
  
##  <a name="atomic_fetch_sub"></a>  atomic_fetch_sub işlevi (C++ AMP)  
 Otomatik olarak bir bellek konumundan bir değeri çıkarır.  
  
```  
inline int atomic_fetch_sub(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_sub(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Destionation konuma işaretçi.  
  
 `value`  
 Çıkarılsın değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek konumuna özgün değeri.  
  
##  <a name="atomic_fetch_xor"></a>  atomic_fetch_xor işlevi (C++ AMP)  
 Otomatik olarak peforms bir değer ve bir bellek konumunu bit düzeyinde XOR işlemini.  
  
```  
inline int atomic_fetch_xor(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_xor(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Bellek konumuna yönelik işaretçi.  
  
 `value`  
 XOR hesaplanmasında kullanılacak değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek konumuna özgün değeri.  
  
##  <a name="copy"></a>  Kopyalama  
 C++ AMP nesnesini kopyalar. Tüm zaman uyumlu veri aktarımı gereksinimleri karşılıyor. Veri kodu Hızlandırıcı üzerinde çalışırken kopyalanamıyor. Bu işlevin genel form `copy(src, dest)`.  
  
```  
template <typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,
    InputIterator _SrcLast,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,  
    array<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,
     OutputIterator _DestIter);

 
template <typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<const value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<const value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst, 
    InputIterator _SrcLast,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,
    OutputIterator _DestIter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Kopyalamak için nesne.  
  
 `_DestIter`  
 Çıktı yineleyici hedef başına konumunda için.  
  
 `InputIterator`  
 Giriş interator türü.  
  
 `OutputIterator`  
 Çıktı yineleyici türü.  
  
 `_Rank`  
 Kopyalanacak veya kopyalamak için nesneyi derecesini.  
  
 `_Src`  
 Kopyalamak için nesne için.  
  
 `_SrcFirst`  
 Başlangıç yineleyici kaynak kapsayıcı içine.  
  
 `_SrcLast`  
 Bitiş yineleyici kaynak kapsayıcı içine.  
  
 `value_type`  
 Kopyalanan öğelerin veri türü.  
  
##  <a name="copy_async"></a>  copy_async  
 C++ AMP nesnesini kopyalar ve döndüren bir [completion_future](completion-future-class.md) üzerinde beklenen nesnesi. Veri kodu Hızlandırıcı üzerinde çalışırken kopyalanamıyor.  Bu işlevin genel form `copy(src, dest)`.  
  
```  
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst,  
    array<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src, OutputIterator _DestIter);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src, OutputIterator _DestIter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Kopyalamak için nesne.  
  
 `_DestIter`  
 Çıktı yineleyici hedef başına konumunda için.  
  
 `InputIterator`  
 Giriş interator türü.  
  
 `OutputIterator`  
 Çıktı yineleyici türü.  
  
 `_Rank`  
 Kopyalanacak veya kopyalamak için nesneyi derecesini.  
  
 `_Src`  
 Kopyalamak için nesne için.  
  
 `_SrcFirst`  
 Başlangıç yineleyici kaynak kapsayıcı içine.  
  
 `_SrcLast`  
 Bitiş yineleyici kaynak kapsayıcı içine.  
  
 `value_type`  
 Kopyalanan öğelerin veri türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `future<void>` , beklenen.  
  
##  <a name="direct3d_abort"></a>  direct3d_abort  
 Bir işlev yürütülmesini durdurur `restrict(amp)` kısıtlama yan tümcesi. AMP çalışma zamanının çağrı algıladığında, yayınlar bir [runtime_exception](runtime-exception-class.md) özel durum hata iletisiyle "görüntüleyiciye: Gölgelendirici abort yönerge isabet".  
  
```  
void direct3d_abort() restrict(amp);
```  
  
##  <a name="direct3d_errorf"></a>  direct3d_errorf  
 Biçimlendirilmiş bir dize Visual Studio çıkış penceresine yazdırır. İle bir işlevden adlı `restrict(amp)` kısıtlama yan tümcesi. AMP çalışma zamanının çağrı algıladığında, yayınlar bir [runtime_exception](runtime-exception-class.md) aynı biçimlendirme dizesi ile özel durum.  
  
```  
void direct3d_errorf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="direct3d_printf"></a>  direct3d_printf  
 Biçimlendirilmiş bir dize Visual Studio çıkış penceresine yazdırır. İle bir işlevden adlı `restrict(amp)` kısıtlama yan tümcesi.  
  
```  
void direct3d_printf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="global_memory_fence"></a>  global_memory_fence  
 Tüm iş parçacıklarının tüm genel bellek erişen kadar döşemesinin blokları yürütülmesi tamamlandı. Bu genel bellek erişimleri iş parçacığı döşemesinin başka bir iş parçacığı görünür ve program sırada çalıştırılan sağlar.  
  
```  
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Barrier`  
 Tile_barrier nesnesi  
  
##  <a name="parallel_for_each"></a>  parallel_for_each işlevi (C++ AMP)  
 Bir işlev işlem etki alanı arasında çalışır. Daha fazla bilgi için bkz: [C++ AMP'ye genel bakış](../../../parallel/amp/cpp-amp-overview.md).  
  
```  
template <int _Rank, typename _Kernel_type>  
void parallel_for_each(
    const extent<_Rank>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,
     const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,
    const _Kernel_type& _Kernel);

 
template <int _Dim0, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Rank, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const extent<_Rank>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0>& _Compute_domain,  
    const _Kernel_type& _Kernel);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Accl_view`  
 `accelerator_view` Paralel hesaplama çalıştırılacak nesne.  
  
 `_Compute_domain`  
 Bir `extent` hesaplama verilerini içeren nesne.  
  
 `_Dim0`  
 Boyutunun `tiled_extent` nesnesi.  
  
 `_Dim1`  
 Boyutunun `tiled_extent` nesnesi.  
  
 `_Dim2`  
 Boyutunun `tiled_extent` nesnesi.  
  
 `_Kernel`  
 Türünde bir bağımsız değişken bir lambda veya işlev nesnesi "dizini\<_Rank >" ve Paralel hesaplama gerçekleştirir.  
  
 `_Kernel_type`  
 Lambda veya functor.  
  
 `_Rank`  
 Uzantı derecesini.  
  
##  <a name="tile_static_memory_fence"></a>  tile_static_memory_fence  
 Engelleyen bir kutucukta tüm iş parçacıklarının yürütülmesine kadar tüm bekleyen `tile_static` bellek erişimleri tamamlandı. Bu sağlar `tile_static` bellek erişimleri iş parçacığı döşemesinin başka bir iş parçacığı için görünür ve erişimleri program sırada yürütülür.  
  
```  
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Barrier`  
 Tile_barrier nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
