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
ms.openlocfilehash: b03a6189d2205dff62d94f07bc597ca2e1013a28
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840212"
---
# <a name="concurrency-namespace-functions-amp"></a>Eşzamanlılık ad alanı işlevleri (AMP)

:::row:::
   :::column span="":::
      [`all_memory_fence`](#all_memory_fence)\
      [`amp_uninitialize`](#amp_uninitialize)\
      [`atomic_compare_exchange`](#atomic_compare_exchange)\
      [`atomic_exchange`](#atomic_exchange)\
      [`atomic_fetch_add`](#atomic_fetch_add)\
      [`atomic_fetch_and`](#atomic_fetch_and)
   :::column-end:::
   :::column span="":::
      [`atomic_fetch_dec`](#atomic_fetch_dec)\
      [`atomic_fetch_inc`](#atomic_fetch_inc)\
      [`atomic_fetch_max`](#atomic_fetch_max)\
      [`atomic_fetch_min`](#atomic_fetch_min)\
      [`atomic_fetch_or`](#atomic_fetch_or)
   :::column-end:::
   :::column span="":::
      [`atomic_fetch_sub`](#atomic_fetch_sub)\
      [`atomic_fetch_xor`](#atomic_fetch_xor)\
      [`copy`](#copy)\
      [`copy_async`](#copy_async)\
      [`direct3d_abort`](#direct3d_abort)
   :::column-end:::
   :::column span="":::
      [`direct3d_errorf`](#direct3d_errorf)\
      [`direct3d_printf`](#direct3d_printf)\
      [`global_memory_fence`](#global_memory_fence)\
      [`parallel_for_each`](#parallel_for_each)\
      [`tile_static_memory_fence`](#tile_static_memory_fence)
   :::column-end:::
:::row-end:::

## <a name="all_memory_fence"></a><a name="all_memory_fence"></a> all_memory_fence

Tüm bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görülebilir olmasını sağlar ve Program sırasıyla yürütülür.

```cpp
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
Bir `tile_barrier` nesnesi.

## <a name="amp_uninitialize"></a><a name="amp_uninitialize"></a> amp_uninitialize

C++ AMP çalışma zamanının kaydını geri alır. Bu işlevi bir uygulama ömrü boyunca birden çok kez çağırmak geçerlidir. Bu işlevi çağırdıktan sonra herhangi bir C++ AMP API çağrısı C++ AMP çalışma zamanını yeniden başlatılır. Bu işleve yapılan çağrılar genelinde C++ AMP nesnelerinin kullanılması geçersizdir ve bunu yapmak tanımsız davranışa neden olur. Ayrıca, bu işlevi ve diğer tüm AMP API 'Leri aynı anda çağırmak geçersizdir ve tanımsız davranışa neden olur.

```cpp
void __cdecl amp_uninitialize();
```

## <a name="atomic_compare_exchange"></a><a name="atomic_compare_exchange"></a> atomic_compare_exchange

, İlk bağımsız değişkende belirtilen bellek konumunda depolanan değeri ikinci belirtilen bağımsız değişkenin değeriyle eşit olarak karşılaştırır ve değerler aynıysa, bellek konumundaki değer üçüncü belirtilen bağımsız değişkenin değeriyle değiştirilir.

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

*_Dest*<br/>
Karşılaştırılacak değerlerden birinin okunduğu ve yeni değerin (varsa) depolanacağı konum, burada.

*_Expected_value*<br/>
İkinci değerin karşılaştırılacağı konum okundu.

*deeri*<br/>
Öğesine eşitse, tarafından belirtilen bellek konumuna depolanacak değer `_Dest` `_Dest` `_Expected_value` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlem başarılı olursa, Aksi takdirde, **`false`** .

## <a name="atomic_exchange-function-c-amp"></a><a name="atomic_exchange"></a> atomic_exchange Işlevi (C++ AMP)

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

*_Dest*<br/>
Hedef konuma yönelik işaretçi.

*deeri*<br/>
Yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Hedef konumun özgün değeri.

## <a name="atomic_fetch_add-function-c-amp"></a><a name="atomic_fetch_add"></a> atomic_fetch_add Işlevi (C++ AMP)

Bir bellek konumunun değerine bir değer ekler.

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

*_Dest*<br/>
Bellek konumu işaretçisi.

*deeri*<br/>
Eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="atomic_fetch_and-function-c-amp"></a><a name="atomic_fetch_and"></a> atomic_fetch_and Işlevi (C++ AMP)

, Bir değer ve bir bellek konumunun değeri için bir bit düzeyinde ve çalışır.

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

*_Dest*<br/>
Bellek konumu işaretçisi.

*deeri*<br/>
Bit düzeyinde AND hesaplamasında kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="atomic_fetch_dec"></a><a name="atomic_fetch_dec"></a> atomic_fetch_dec

, Belirtilen bellek konumunda depolanan değeri bir ölçüde azaltır.

```cpp
inline int atomic_fetch_dec(_Inout_ int* _Dest
    ) restrict(amp)

inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Azaltılangirecek değerin bellekteki konumu.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunda depolanan özgün değer.

## <a name="atomic_fetch_inc"></a><a name="atomic_fetch_inc"></a> atomic_fetch_inc

Belirtilen bellek konumunda depolanan değeri otomatik olarak artırır.

```cpp
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Artılacak değerin bellekteki konumu.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunda depolanan özgün değer.

## <a name="atomic_fetch_max"></a><a name="atomic_fetch_max"></a> atomic_fetch_max

, İlk bağımsız değişkende belirtilen bellek konumunda depolanan değer ve ikinci bağımsız değişkende belirtilen değer arasındaki maksimum değeri otomatik olarak hesaplar ve aynı bellek konumunda depolar.

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

*_Dest*<br/>
Karşılaştırılacağı değerlerden birinin okunduğu ve iki değerin en fazla depolanacağı konum, bu değerin saklanacağı konumdur.

*deeri*<br/>
Belirtilen konumdaki değerle karşılaştırılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konum konumunda depolanan özgün değer.

## <a name="atomic_fetch_min"></a><a name="atomic_fetch_min"></a> atomic_fetch_min

, İlk bağımsız değişkende belirtilen bellek konumunda depolanan değer ve ikinci bağımsız değişkende belirtilen değer arasındaki minimum değeri otomatik olarak hesaplar ve aynı bellek konumunda depolar.

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

*_Dest*<br/>
Karşılaştırılacak değerlerden birinin okunduğu ve iki değerin en az bir şekilde depolanacağı konum burada.

*deeri*<br/>
Belirtilen konumdaki değerle karşılaştırılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konum konumunda depolanan özgün değer.

## <a name="atomic_fetch_or-function-c-amp"></a><a name="atomic_fetch_or"></a> atomic_fetch_or Işlevi (C++ AMP)

, Bir değer ve bir bellek konumunun değeri ile bir bit düzeyinde veya işlem gerçekleştirir.

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

*_Dest*<br/>
Bellek konumu işaretçisi.

*deeri*<br/>
Bit düzeyinde veya hesaplamada kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="atomic_fetch_sub-function-c-amp"></a><a name="atomic_fetch_sub"></a> atomic_fetch_sub Işlevi (C++ AMP)

Bir bellek konumundan bir değeri atomicbir şekilde çıkarır.

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

*_Dest*<br/>
Hedef konuma yönelik işaretçi.

*deeri*<br/>
Çıkarılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="atomic_fetch_xor-function-c-amp"></a><a name="atomic_fetch_xor"></a> atomic_fetch_xor Işlevi (C++ AMP)

, Bir değerin ve bir bellek konumunun bit düzeyinde XOR işlemi uygular.

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

*_Dest*<br/>
Bellek konumu işaretçisi.

*deeri*<br/>
XOR hesaplamasında kullanılacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bellek konumunun özgün değeri.

## <a name="copy"></a><a name="copy"></a> kopya

C++ AMP nesnesini kopyalar. Tüm zaman uyumlu veri aktarımı gereksinimleri karşılandı. Hızlandırıcı üzerinde kod çalıştırırken veri kopyalayamazsınız. Bu işlevin genel formu `copy(src, dest)` .

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

*_Dest*<br/>
Kopyalanacak nesne.

*_DestIter*<br/>
Hedefteki başlangıç konumuna bir çıkış yineleyicisi.

*InputIterator*<br/>
Giriş yineleyicisinin türü.

*OutputIterator*<br/>
Çıkış yineleyicisinin türü.

*_Rank*<br/>
Kopyalanacak nesnenin veya Kopyalanacak nesnenin derecesi.

*_Src*<br/>
Kopyalanacak nesneye.

*_SrcFirst*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*_SrcLast*<br/>
Kaynak kapsayıcıya bir bitiş yineleyicisi.

*value_type*<br/>
Kopyalanmış öğelerin veri türü.

## <a name="copy_async"></a><a name="copy_async"></a> copy_async

C++ AMP nesnesini kopyalar ve beklemiş olabilecek bir [completion_future](completion-future-class.md) nesnesi döndürür. Hızlandırıcı üzerinde kod çalıştırırken veri kopyalayamazsınız.  Bu işlevin genel formu `copy(src, dest)` .

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

*_Dest*<br/>
Kopyalanacak nesne.

*_DestIter*<br/>
Hedefteki başlangıç konumuna bir çıkış yineleyicisi.

*InputIterator*<br/>
Giriş yineleyicisinin türü.

*OutputIterator*<br/>
Çıkış yineleyicisinin türü.

*_Rank*<br/>
Kopyalanacak nesnenin veya Kopyalanacak nesnenin derecesi.

*_Src*<br/>
Kopyalanacak nesneye.

*_SrcFirst*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*_SrcLast*<br/>
Kaynak kapsayıcıya bir bitiş yineleyicisi.

*value_type*<br/>
Kopyalanmış öğelerin veri türü.

### <a name="return-value"></a>Dönüş Değeri

`future<void>`Bu, beklemiş olabilecek bir.

## <a name="direct3d_abort"></a><a name="direct3d_abort"></a> direct3d_abort

Kısıtlama yan tümcesiyle bir işlevin yürütülmesini iptal eder `restrict(amp)` . AMP çalışma zamanı çağrıyı algıladığında, "Başvuru tarayıcısı: gölgelendirici iptal yönergesi isabet" hata iletisiyle [runtime_exception](runtime-exception-class.md) bir özel durum oluşturur.

```cpp
void direct3d_abort() restrict(amp);
```

## <a name="direct3d_errorf"></a><a name="direct3d_errorf"></a> direct3d_errorf

Visual Studio çıktı penceresine biçimli bir dize yazdırır. Kısıtlama yan tümcesine sahip bir işlevden çağrılır `restrict(amp)` . AMP çalışma zamanı çağrıyı algıladığında, aynı biçimlendirme dizesiyle [runtime_exception](runtime-exception-class.md) bir özel durum başlatır.

```cpp
void direct3d_errorf(
    const char *,
...) restrict(amp);
```

## <a name="direct3d_printf"></a><a name="direct3d_printf"></a> direct3d_printf

Visual Studio çıktı penceresine biçimli bir dize yazdırır. Kısıtlama yan tümcesine sahip bir işlevden çağrılır `restrict(amp)` .

```cpp
void direct3d_printf(
    const char *,
...) restrict(amp);
```

## <a name="global_memory_fence"></a><a name="global_memory_fence"></a> global_memory_fence

Tüm genel bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, genel bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görülebilir olmasını sağlar ve Program sırasıyla yürütülür.

```cpp
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
Tile_barrier nesnesi

## <a name="parallel_for_each-function-c-amp"></a><a name="parallel_for_each"></a> parallel_for_each Işlevi (C++ AMP)

İşlem etki alanı genelinde bir işlev çalıştırır. Daha fazla bilgi için bkz. [C++ amp genel bakış](../../../parallel/amp/cpp-amp-overview.md).

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
`accelerator_view`Paralel hesaplamanın çalıştırılacağı nesne.

*_Compute_domain*<br/>
`extent`Hesaplama için verileri içeren bir nesne.

*_Dim0*<br/>
`tiled_extent`Nesnenin boyutu.

*_Dim1*<br/>
`tiled_extent`Nesnenin boyutu.

*_Dim2*<br/>
`tiled_extent`Nesnenin boyutu.

*_Kernel*<br/>
"İndex" türünde bir bağımsız değişken alan \<_Rank> ve paralel hesaplamayı gerçekleştiren bir lambda veya işlev nesnesi.

*_Kernel_type*<br/>
Lambda veya functor.

*_Rank*<br/>
Kapsamın derecesi.

## <a name="tile_static_memory_fence"></a><a name="tile_static_memory_fence"></a> tile_static_memory_fence

Tüm bekleyen bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller `tile_static` . Bu `tile_static` , bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görülebilir olmasını ve erişimin Program sırasıyla çalıştırılmasını sağlar.

```cpp
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Barrier*<br/>
Tile_barrier nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
