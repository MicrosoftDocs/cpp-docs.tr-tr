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
ms.openlocfilehash: 1187b745a6d8c903c22958185be8d98a6e3d0204
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376346"
---
# <a name="concurrency-namespace-functions-amp"></a>Eşzamanlılık ad alanı işlevleri (AMP)

||||
|-|-|-|
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|
|[atomic_exchange Fonksiyonu (C++ AMP)](#atomic_exchange)|[atomic_fetch_add Fonksiyonu (C++ AMP)](#atomic_fetch_add)|[atomic_fetch_and Fonksiyonu (C++ AMP)](#atomic_fetch_and)|
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|
|[atomic_fetch_min](#atomic_fetch_min)|[atomic_fetch_or Fonksiyonu (C++ AMP)](#atomic_fetch_or)|[atomic_fetch_sub Fonksiyonu (C++ AMP)](#atomic_fetch_sub)|
|[atomic_fetch_xor Fonksiyonu (C++ AMP)](#atomic_fetch_xor)|[Kopya](#copy)|[copy_async](#copy_async)|
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|
|[global_memory_fence](#global_memory_fence)|[parallel_for_each Fonksiyonu (C++ AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|

## <a name="all_memory_fence"></a><a name="all_memory_fence"></a>all_memory_fence

Tüm bellek erişimleri tamamlanana kadar bir döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görünür olmasını ve program sırasına göre yürütülmesini sağlar.

```cpp
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
Bir `tile_barrier` nesnesi.

## <a name="amp_uninitialize"></a><a name="amp_uninitialize"></a>amp_uninitialize

C++ AMP çalışma süresini başlatmaz. Bu işlevi bir uygulama ömrü boyunca birden çok kez çağırmak yasaldır. Bu işlevi aradıktan sonra herhangi bir C++ AMP API'yi çağırmak C++ AMP çalışma süresini yeniden başlatmaz. C++ AMP nesnelerinin bu işleve yapılan çağrılarda kullanılmasının yasa dışı olduğunu ve bunu yapmanın tanımlanmamış davranışlara yol açacağını unutmayın. Ayrıca, aynı anda bu işlevi ve diğer AMP API'leri çağıran yasadışı ve tanımlanmamış davranışneden olur.

```cpp
void __cdecl amp_uninitialize();
```

## <a name="atomic_compare_exchange"></a><a name="atomic_compare_exchange"></a>atomic_compare_exchange

Atomik olarak, eşitlik için ilk bağımsız değişkende belirtilen bir bellek konumunda depolanan değeri ikinci belirtilen bağımsız değişkenin değeriyle karşılaştırır ve değerler aynıysa, bellek konumundaki değer üçüncü belirtilen bağımsız değişkenle değiştirilir.

```cpp
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

*_dest*<br/>
Karşılaştırılacak değerlerden birinin okunduğu ve varsa yeni değerin depolanabilmek için bulunduğu konum.

*_Expected_value*<br/>
Karşılaştırılacak ikinci değerin bulunduğu konum okunur.

*Değer*<br/>
`_Dest` Eğer' `_Dest` e eşitse, bellek konumuna depolanacak `_Expected_value`değer.

### <a name="return-value"></a>Dönüş Değeri

işlem başarılı olursa **doğrudur;** aksi takdirde, **yanlış**.

## <a name="atomic_exchange-function-c-amp"></a><a name="atomic_exchange"></a>atomic_exchange Fonksiyonu (C++ AMP)

Hedef konumun değerini atomik bir işlem olarak ayarlar.

```cpp
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

*_dest*<br/>
Hedef konuma işaretçi.

*Değer*<br/>
Yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Hedef konumun özgün değeri.

## <a name="atomic_fetch_add-function-c-amp"></a><a name="atomic_fetch_add"></a>atomic_fetch_add Fonksiyonu (C++ AMP)

Atomik olarak bellek konumunun değerine bir değer ekleyin.

```cpp
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

*_dest*<br/>
Bellek konumuna işaretçi.

*Değer*<br/>
Eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="atomic_fetch_and-function-c-amp"></a><a name="atomic_fetch_and"></a>atomic_fetch_and Fonksiyonu (C++ AMP)

Atomik olarak bir değer ve bir bellek konumunun değeri bir bitwise VE çalışma gerçekleştirir.

```cpp
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

*_dest*<br/>
Bellek konumuna işaretçi.

*Değer*<br/>
Bitwise AND hesaplamasında kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="atomic_fetch_dec"></a><a name="atomic_fetch_dec"></a>atomic_fetch_dec

Atomik olarak belirtilen bellek konumunda depolanan değeri belirtir.

```cpp
inline int atomic_fetch_dec(_Inout_ int* _Dest
    ) restrict(amp)

inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_dest*<br/>
Verilecek değerin bellekteki konumu.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunda depolanan özgün değer.

## <a name="atomic_fetch_inc"></a><a name="atomic_fetch_inc"></a>atomic_fetch_inc

Atomik olarak belirtilen bellek konumunda depolanan değeri arttır.

```cpp
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_dest*<br/>
Artımlı değerin bellekteki konumu.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunda depolanan özgün değer.

## <a name="atomic_fetch_max"></a><a name="atomic_fetch_max"></a>atomic_fetch_max

Atomik olarak, ilk bağımsız değişkende belirtilen bellek konumunda depolanan değer ile ikinci bağımsız değişkende belirtilen değer arasındaki en büyük değeri hesaplar ve aynı bellek konumunda saklar.

```cpp
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

*_dest*<br/>
Karşılaştırılacak değerlerden birinin okunduğu ve iki değerden en fazlabirinin depolanabilmek için bulunduğu konum.

*Değer*<br/>
Belirtilen konumdaki değerle karşılaştırılması gereken değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konum konumunda depolanan özgün değer.

## <a name="atomic_fetch_min"></a><a name="atomic_fetch_min"></a>atomic_fetch_min

Atomik olarak, ilk bağımsız değişkende belirtilen bellek konumunda depolanan değer ile ikinci bağımsız değişkende belirtilen değer arasındaki minimum değeri hesaplar ve aynı bellek konumunda saklar.

```cpp
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

*_dest*<br/>
Karşılaştırılacak değerlerden birinin okunduğu ve iki değerin en azının depolanabilmek için hangi konum okunur.

*Değer*<br/>
Belirtilen konumdaki değerle karşılaştırılması gereken değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konum konumunda depolanan özgün değer.

## <a name="atomic_fetch_or-function-c-amp"></a><a name="atomic_fetch_or"></a>atomic_fetch_or Fonksiyonu (C++ AMP)

Atomik bir değer ve bir bellek konumu değeri ile bitwise VEYA işlemi gerçekleştirir.

```cpp
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

*_dest*<br/>
Bellek konumuna işaretçi.

*Değer*<br/>
Bitwise OR hesaplamasında kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="atomic_fetch_sub-function-c-amp"></a><a name="atomic_fetch_sub"></a>atomic_fetch_sub Fonksiyonu (C++ AMP)

Atomik olarak bir bellek konumundan bir değer çıkarır.

```cpp
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

*_dest*<br/>
Hedef konuma işaretçi.

*Değer*<br/>
Çıkarılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="atomic_fetch_xor-function-c-amp"></a><a name="atomic_fetch_xor"></a>atomic_fetch_xor Fonksiyonu (C++ AMP)

Atomik olarak bir değer ve bellek konumu bitwise XOR işlemi gerçekleştirir.

```cpp
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

*_dest*<br/>
Bellek konumuna işaretçi.

*Değer*<br/>
XOR hesaplamasında kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="copy"></a><a name="copy"></a>Kopya

C++ AMP nesnesi kopyalar. Tüm eşzamanlı veri aktarım gereksinimleri karşılanır. Bir hızlandırıcıda kod çalıştırırken verileri kopyalayamaz. Bu fonksiyonun genel `copy(src, dest)`biçimi .

```cpp
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

*_dest*<br/>
Kopyalanması gereken nesne.

*_DestIter*<br/>
Hedefteki başlangıç konumuna bir çıkış yineleyicisi.

*GirişIterator*<br/>
Giriş yineleyicisinin türü.

*OutputIterator*<br/>
Çıktı yineleyicisinin türü.

*_Rank*<br/>
Kopyalanması gereken nesnenin veya kopyalanması gereken nesnenin sıralaması.

*_Src*<br/>
Kopyalamaya itiraz etmek için.

*_SrcFirst*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*_SrcLast*<br/>
Kaynak kapsayıcıya sonlandırıcı bir yineleyici.

*value_type*<br/>
Kopyalanan öğelerin veri türü.

## <a name="copy_async"></a><a name="copy_async"></a>copy_async

C++ AMP nesnesi kopyalar ve üzerinde beklenebilecek [completion_future](completion-future-class.md) bir nesne döndürür. Bir hızlandırıcıda kod çalıştırırken verileri kopyalayamaz.  Bu fonksiyonun genel `copy(src, dest)`biçimi .

```cpp
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

*_dest*<br/>
Kopyalanması gereken nesne.

*_DestIter*<br/>
Hedefteki başlangıç konumuna bir çıkış yineleyicisi.

*GirişIterator*<br/>
Giriş yineleyicisinin türü.

*OutputIterator*<br/>
Çıktı yineleyicisinin türü.

*_Rank*<br/>
Kopyalanması gereken nesnenin veya kopyalanması gereken nesnenin sıralaması.

*_Src*<br/>
Kopyalamaya itiraz etmek için.

*_SrcFirst*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*_SrcLast*<br/>
Kaynak kapsayıcıya sonlandırıcı bir yineleyici.

*value_type*<br/>
Kopyalanan öğelerin veri türü.

### <a name="return-value"></a>Dönüş Değeri

Beklenebilecek bir şey. `future<void>`

## <a name="direct3d_abort"></a><a name="direct3d_abort"></a>direct3d_abort

Kısıtlama yan tümcesi ile `restrict(amp)` bir işlevin yürütülmesini iptal eder. AMP çalışma zamanı aramayı algıladığında, "Reference Rasterizer: Shader iptal talimatı isabeti" hata iletisiyle [runtime_exception](runtime-exception-class.md) bir özel durum oluşturur.

```cpp
void direct3d_abort() restrict(amp);
```

## <a name="direct3d_errorf"></a><a name="direct3d_errorf"></a>direct3d_errorf

Visual Studio çıkış penceresine biçimlendirilmiş bir dize yazdırır. Kısıtlama yan tümcesi `restrict(amp)` olan bir işlevden çağrılır. AMP çalışma zamanı aramayı algıladığında, aynı biçimlendirme dizesiyle [runtime_exception](runtime-exception-class.md) bir özel durum ortaya çıkarır.

```cpp
void direct3d_errorf(
    const char *,
...) restrict(amp);
```

## <a name="direct3d_printf"></a><a name="direct3d_printf"></a>direct3d_printf

Visual Studio çıkış penceresine biçimlendirilmiş bir dize yazdırır. Kısıtlama yan tümcesi `restrict(amp)` olan bir işlevden çağrılır.

```cpp
void direct3d_printf(
    const char *,
...) restrict(amp);
```

## <a name="global_memory_fence"></a><a name="global_memory_fence"></a>global_memory_fence

Tüm genel bellek erişimleri tamamlanana kadar bir döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, genel bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görünür olmasını ve program sırasına göre yürütülmesini sağlar.

```cpp
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
tile_barrier nesnesi

## <a name="parallel_for_each-function-c-amp"></a><a name="parallel_for_each"></a>parallel_for_each Fonksiyonu (C++ AMP)

İşlem etki alanında bir işlev çalıştırın. Daha fazla bilgi için [Bkz. C++ AMP Genel Bakış.](../../../parallel/amp/cpp-amp-overview.md)

```cpp
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
Paralel `accelerator_view` hesaplamayı çalıştıracak nesne.

*_Compute_domain*<br/>
Hesaplama `extent` için veri içeren bir nesne.

*_Dim0*<br/>
Nesnenin `tiled_extent` boyutu.

*_Dim1*<br/>
Nesnenin `tiled_extent` boyutu.

*_Dim2*<br/>
Nesnenin `tiled_extent` boyutu.

*_Kernel*<br/>
"Dizin\<_Rank>" türünden bir bağımsız değişken alan ve paralel hesaplamayı gerçekleştiren bir lambda veya işlev nesnesi.

*_Kernel_type*<br/>
Bir lambda ya da funktör.

*_Rank*<br/>
Ölçüde rütbe.

## <a name="tile_static_memory_fence"></a><a name="tile_static_memory_fence"></a>tile_static_memory_fence

Tüm bekleyen `tile_static` bellek erişimleri tamamlanana kadar bir döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, `tile_static` bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görünür olmasını ve erişimlerin program sırasına göre yürütülmesini sağlar.

```cpp
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
tile_barrier bir nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
