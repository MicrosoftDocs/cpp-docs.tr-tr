---
title: Eşzamanlılık ad alanı işlevleri (AMP)
ms.date: 11/04/2016
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
ms.assetid: 2bef0985-cb90-4ece-90b9-66529aec73c9
ms.openlocfilehash: 7baae51480c273ca023856253af7963ac83d7c92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180394"
---
# <a name="concurrency-namespace-functions-amp"></a>Eşzamanlılık ad alanı işlevleri (AMP)

||||
|-|-|-|
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|
|[atomic_exchange işlevi (C++ AMP)](#atomic_exchange)|[atomic_fetch_add işlevi (C++ AMP)](#atomic_fetch_add)|[atomic_fetch_and işlevi (C++ AMP)](#atomic_fetch_and)|
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|
|[atomic_fetch_min](#atomic_fetch_min)|[atomic_fetch_or Function (C++ AMP)](#atomic_fetch_or)|[atomic_fetch_sub işlevi (C++ AMP)](#atomic_fetch_sub)|
|[atomic_fetch_xor işlevi (C++ AMP)](#atomic_fetch_xor)|[kopyalama](#copy)|[copy_async](#copy_async)|
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|
|[global_memory_fence](#global_memory_fence)|[parallel_for_each işlevi (C++ AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|

##  <a name="all_memory_fence"></a>  all_memory_fence

Tüm bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından ve program sırasıyla yürütülen sağlar.

```
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
A `tile_barrier` nesne.

##  <a name="amp_uninitialize"></a>  amp_uninitialize

C++ AMP çalışma zamanının başlamasını iptal eder. Birden çok kez uygulama ömrü boyunca bu işlevi çağırmak için uygundur. Bu fonksiyonu çağıran tüm C++ AMP API çağrıldığında C++ AMP çalışma zamanı yeniden başlatılır. Bu işleve çağrılar üzerinden C++ AMP nesneleri kullanmanın geçersiz ve bunun yapılması, bu nedenle tanımsız davranışlara neden unutmayın. Ayrıca, bu işleve ve diğer tüm AMP API'lerinin aynı anda çağırmak geçersizdir ve tanımsız davranışla sonuçlanır.

```
void __cdecl amp_uninitialize();
```

##  <a name="atomic_compare_exchange"></a>  atomic_compare_exchange

Atomik olarak bellek konumunda depolanan değeri eşitlik bakımından ikinci belirtilen bağımsız değişkenin değeri ilk bağımsız değişkende belirtilen karşılaştırır ve değerler aynıysa bellek konumundaki değer üçüncü belirtilen bağımsız değiştirilir.

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

*_Dest*<br/>
Konum Karşılaştırılacak değerlerden birinin okunduğu ve yeni bir değer varsa depolanacak olduğu.

*_Expected_value*<br/>
Karşılaştırılacak ikinci değer okuması konumu.

*value*<br/>
Tarafından belirtilen bellek konumuna depolanacak değer `_Dest` varsa `_Dest` eşittir `_Expected_value`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlemi başarılı olursa Aksi takdirde **false**.

##  <a name="atomic_exchange"></a>  atomic_exchange işlevi (C++ AMP)

Hedef konum değeri atomik işlem ayarlar.

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

*_Dest*<br/>
Hedef konuma yönelik işaretçi.

*value*<br/>
Yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Hedef konumu özgün değeri.

##  <a name="atomic_fetch_add"></a>  atomic_fetch_add işlevi (C++ AMP)

Atomik olarak bir bellek konumuna değeri için bir değer ekleyin.

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

*_Dest*<br/>
Bellek konumuna yönelik işaretçi.

*value*<br/>
Eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumu özgün değeri.

##  <a name="atomic_fetch_and"></a>  atomic_fetch_and işlevi (C++ AMP)

Bit düzeyinde bir AND işlemi bir değer ve bir bellek konumuna değeri atomik olarak gerçekleştirir.

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

*_Dest*<br/>
Bellek konumuna yönelik işaretçi.

*value*<br/>
Bit düzeyinde AND hesaplanmasında kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumu özgün değeri.

##  <a name="atomic_fetch_dec"></a>  atomic_fetch_dec

Atomik olarak azaltır değeri belirtilen bellek konumunda depolanır.

```
inline int atomic_fetch_dec(_Inout_ int* _Dest
    ) restrict(amp)

inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Azaltılacak değerin bellekteki konumu.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunda depolanan özgün değer.

##  <a name="atomic_fetch_inc"></a>  atomic_fetch_inc

Belirtilen bellek konumunda depolanan değeri atomik olarak artırır.

```
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Arttırılacak değerin bellekteki konumu.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunda depolanan özgün değer.

##  <a name="atomic_fetch_max"></a>  atomic_fetch_max

Atomik olarak ilk bağımsız değişken ikinci bağımsız değişkende belirtilen değerden belirtilen bellek konumunda depolanan değer maksimum değeri hesaplar ve aynı bellek konumunda depolar.

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

*_Dest*<br/>
Konum Karşılaştırılacak değerlerden birinin okunduğu ve iki değerden en fazla depolanacak olduğu.

*value*<br/>
Belirtilen konumdaki değerle karşılaştırılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konum yerinde depolanan özgün değer.

##  <a name="atomic_fetch_min"></a>  atomic_fetch_min

Atomik olarak ilk bağımsız değişken ikinci bağımsız değişkende belirtilen değerden belirtilen bellek konumunda depolanan değer minimum değeri hesaplar ve aynı bellek konumunda depolar.

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

*_Dest*<br/>
Konum Karşılaştırılacak değerlerden birinin okunduğu ve iki değerden en düşük depolanacak olduğu.

*value*<br/>
Belirtilen konumdaki değerle karşılaştırılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konum yerinde depolanan özgün değer.

##  <a name="atomic_fetch_or"></a>  atomic_fetch_or işlevi (C++ AMP)

Atomik olarak bir değer ve bir bellek konumuna değeri ile bit tabanlı veya işlemi gerçekleştirir.

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

*_Dest*<br/>
Bellek konumuna yönelik işaretçi.

*value*<br/>
Bit düzeyinde OR hesaplanmasında kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumu özgün değeri.

##  <a name="atomic_fetch_sub"></a>  atomic_fetch_sub işlevi (C++ AMP)

Atomik bir bellek konumuna bir değeri çıkarır.

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

*_Dest*<br/>
Hedef konuma yönelik işaretçi.

*value*<br/>
Çıkarılan için değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumu özgün değeri.

##  <a name="atomic_fetch_xor"></a>  atomic_fetch_xor işlevi (C++ AMP)

Atomik olarak peforms bir değer ve bir bellek konumuna bir bit düzeyinde XOR işlem.

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

*_Dest*<br/>
Bellek konumuna yönelik işaretçi.

*value*<br/>
XOR hesaplanmasında kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumu özgün değeri.

##  <a name="copy"></a>  kopyalama

C++ AMP nesnesi kopyalar. Tüm zaman uyumlu veri aktarımı gereksinimleri karşılanır. Kod hızlandırıcıda çalışıyor olduğunda veri kopyalanamıyor. Bu işlevin genel formu `copy(src, dest)`.

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

*_Dest*<br/>
Üstüne kopyalanacak nesne.

*_DestIter*<br/>
Hedef başlangıç konumuna bir çıktı yineleyici.

*Inputıterator*<br/>
Giriş yineleyicisinin türü.

*Outputıterator*<br/>
Çıkış yineleyici türü.

*_Dizin*<br/>
Kopyalanacak nesnenin ya da üstüne Kopyalanacak nesnenin boyut.

*_Src*<br/>
Kopyalanacak nesneye için.

*_SrcFirst*<br/>
Kaynak kapsayıcı içine bir başlangıç yineleyicisi.

*_SrcLast*<br/>
Kaynak kapsayıcı içine bir bitiş yineleyicisi.

*value_type*<br/>
Kopyalanan öğelerin veri türü.

##  <a name="copy_async"></a>  copy_async

Kopya bir C++ AMP nesnesi ve döndürür bir [completion_future](completion-future-class.md) üzerinde beklenen nesne. Kod hızlandırıcıda çalışıyor olduğunda veri kopyalanamıyor.  Bu işlevin genel formu `copy(src, dest)`.

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

*_Dest*<br/>
Üstüne kopyalanacak nesne.

*_DestIter*<br/>
Hedef başlangıç konumuna bir çıktı yineleyici.

*Inputıterator*<br/>
Giriş yineleyicisinin türü.

*Outputıterator*<br/>
Çıkış yineleyici türü.

*_Dizin*<br/>
Kopyalanacak nesnenin ya da üstüne Kopyalanacak nesnenin boyut.

*_Src*<br/>
Kopyalanacak nesneye için.

*_SrcFirst*<br/>
Kaynak kapsayıcı içine bir başlangıç yineleyicisi.

*_SrcLast*<br/>
Kaynak kapsayıcı içine bir bitiş yineleyicisi.

*value_type*<br/>
Kopyalanan öğelerin veri türü.

### <a name="return-value"></a>Dönüş Değeri

A `future<void>` , beklenen.

##  <a name="direct3d_abort"></a>  direct3d_abort

İle bir işlevin yürütülmesini durdurur `restrict(amp)` kısıtlama yan tümcesi. AMP çalışma zamanı çağrıyı algıladığında bilmemektedir bir [runtime_exception](runtime-exception-class.md) özel durum hata iletisiyle "görüntüleyiciye: Gölgelendirici iptal yönergesi isabet".

```
void direct3d_abort() restrict(amp);
```

##  <a name="direct3d_errorf"></a>  direct3d_errorf

Visual Studio çıktı penceresine biçimlendirilmiş bir dize yazdırır. İle bir işlevden çağırılır `restrict(amp)` kısıtlama yan tümcesi. AMP çalışma zamanı çağrıyı algıladığında bilmemektedir bir [runtime_exception](runtime-exception-class.md) özel durumla aynı biçimlendirme dizesi.

```
void direct3d_errorf(
    const char *,
...) restrict(amp);
```

##  <a name="direct3d_printf"></a>  direct3d_printf

Visual Studio çıktı penceresine biçimlendirilmiş bir dize yazdırır. İle bir işlevden çağırılır `restrict(amp)` kısıtlama yan tümcesi.

```
void direct3d_printf(
    const char *,
...) restrict(amp);
```

##  <a name="global_memory_fence"></a>  global_memory_fence

Tüm genel bellek kullanımları tamamlanıncaya kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller tamamlanmıştır. Bu genel bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından ve program sırasıyla yürütülen sağlar.

```
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
Bir tile_barrier nesnesi

##  <a name="parallel_for_each"></a>  parallel_for_each işlevi (C++ AMP)

Hesaplama alanı genelinde bir işlev çalıştırır. Daha fazla bilgi için [C++ AMP'ye genel bakış](../../../parallel/amp/cpp-amp-overview.md).

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

*_Accl_view*<br/>
`accelerator_view` Paralel hesaplama yapabilmek için nesne.

*_Compute_domain*<br/>
Bir `extent` hesaplama için veri içeren nesne.

*_Dim0*<br/>
Boyutu `tiled_extent` nesne.

*_Dim1*<br/>
Boyutu `tiled_extent` nesne.

*_Dim2*<br/>
Boyutu `tiled_extent` nesne.

*_Kernel*<br/>
Türünde bir bağımsız değişken bir lambda veya işlev nesnesi "dizin\<_dizin >" ve Paralel hesaplama gerçekleştirir.

*_Kernel_type*<br/>
Bir lambda veya izleç.

*_Dizin*<br/>
Kapsamın boyut sayısı.

##  <a name="tile_static_memory_fence"></a>  tile_static_memory_fence

Tüm kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller bekleyen `tile_static` bellek erişimleri tamamlanana. Bu, sağlar `tile_static` bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından ve program sırasıyla yürütülen erişir.

```
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
Bir tile_barrier nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
