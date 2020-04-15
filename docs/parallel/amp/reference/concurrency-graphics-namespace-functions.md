---
title: Concurrency::graphics ad alanı işlevleri
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::fast_math::copy_async
- amp_graphics/Concurrency::fast_math::copy
ms.assetid: ace01cd5-29d3-4356-930e-c81a61c5f934
ms.openlocfilehash: 776f715f72d2e3b6b3841856323a52953e9c5344
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376336"
---
# <a name="concurrencygraphics-namespace-functions"></a>Concurrency::graphics ad alanı işlevleri

|||
|-|-|
|[Kopya](#copy)|[copy_async](#copy_async)|

## <a name="copy-function-concurrencygraphics-namespace"></a><a name="copy"></a>kopyalama Fonksiyonu (Eşzamanlılık::grafik Namespace)

Kaynak dokusunu hedef arabelleğe kopyalar veya kaynak arabelleği hedef arabelleği olarak kopyalar. Bu fonksiyonun genel `copy(src, dest)`biçimi .

```cpp
template <
    typename _Src_type,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type>
>
void copy (
    const _Src_type& _Src,
    _Out_ void* _Dst,
    unsigned int _Dst_byte_size);

template <
    typename _Src_type,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type
>
void copy(
    const _Src_type& _Src,
    const index<_Src_type::rank>& _Src_offset,
    const extent<_Src_type::rank>& _Copy_extent,
    _Out_ void* _Dst,
    unsigned int _Dst_byte_size);

template <
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type
>
void copy(
    const void* _Src,
    unsigned int _Src_byte_size, _Dst_type& _Dst);

template <
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type
>
void copy(
    const void* _Src,
    unsigned int _Src_byte_size,
    _Dst_type& _Dst,
    const index<_Dst_type::rank>& _Dst_offset,
    const extent<_Dst_type::rank>& _Copy_extent);

template <
    typename InputIterator,
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type
>
void copy(InputIterator first, InputIterator last, _Dst_type& _Dst);

template <
    typename InputIterator,
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type
>void copy(InputIterator first, InputIterator last, _Dst_type& _Dst,
    const index<_Dst_type::rank>& _Dst_offset,
    const extent<_Dst_type::rank>& _Copy_extent);

template <
    typename _Src_type,
    typename OutputIterator,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type
>
void copy(
    const _Src_type& _Src, OutputIterator _Dst);

template <
    typename _Src_type,
    typename OutputIterator,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type
>
void copy (
    const _Src_type& _Src,
    const index<_Src_type::rank>& _Src_offset,
    const extent<_Src_type::rank>& _Copy_extent, OutputIterator _Dst);

template <
    typename _Src_type,
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type
>
void copy (
    const _Src_type& _Src, _Dst_type& _Dst);

template <
    typename _Src_type,
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture,
    void>::type
>
void copy (
    const _Src_type& _Src,
    const index<_Src_type::rank>& _Src_offset, _Dst_type& _Dst,
    const index<_Dst_type::rank>& _Dst_offset,
    const extent<_Src_type::rank>& _Copy_extent);
```

### <a name="parameters"></a>Parametreler

*_Copy_extent*<br/>
Kopyalanacak doku bölümünün kapsamı.

*_Dst*<br/>
Kopyalanması gereken nesne.

*_Dst_byte_size*<br/>
Hedefteki bayt sayısı.

*_Dst_type*<br/>
Hedef nesnenin türü.

*_Dst_offset*<br/>
Kopyalamaya başlanacak hedefe mahsup.

*GirişIterator*<br/>
Giriş yineleyicisinin türü.

*OutputIterator*<br/>
Çıktı yineleyicisinin türü.

*_Src*<br/>
Kopyalamaya itiraz etmek için.

*_Src_byte_size*<br/>
Kaynaktaki bayt sayısı.

*_Src_type*<br/>
Kaynak nesnenin türü.

*_Src_offset*<br/>
Kopyalamaya başlamak için kaynak içine ofset.

*Ilk*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*Son*<br/>
Kaynak kapsayıcıya sonlandırıcı bir yineleyici.

## <a name="copy_async-function-concurrencygraphics-namespace"></a><a name="copy_async"></a>copy_async Fonksiyonu (Eşzamanlılık::grafik Namespace)

Bir kaynak dokusunu bir hedef arabelleğe kopyalar veya kaynak arabelleği bir hedef arabelleğe kopyalar ve sonra üzerinde beklenebilecek [completion_future](completion-future-class.md) bir nesne döndürür. Kod hızlandırıcı üzerinde çalışırken veriler kopyalanamıyor. Bu fonksiyonun genel `copy(src, dest)`biçimi .

```cpp
template<
    typename _Src_type,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type
>
concurrency::completion_future copy_async(
    const _Src_type& _Src,
    _Out_ void* _Dst,
    unsigned int _Dst_byte_size);

template<
    typename _Src_type,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type
>
concurrency::completion_future copy_async(
    const _Src_type& _Src,
    const index<_Src_type::rank>& _Src_offset,
    const extent<_Src_type::rank>& _Copy_extent,
    _Out_ void* _Dst,
    unsigned int _Dst_byte_size);

template <
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type
>
concurrency::completion_future copy_async(
    const void* _Src,
    unsigned int _Src_byte_size, _Dst_type& _Dst);

template <
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type
>
concurrency::completion_future copy_async(
    const void* _Src,
    unsigned int _Src_byte_size, _Dst_type& _Dst,
    const index<_Dst_type::rank>& _Dst_offset,
    const extent<_Dst_type::rank>& _Copy_extent);

template <
    typename InputIterator,
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type
>
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst);

template <
    typename InputIterator,
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type
>
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst,
    const index<_Dst_type::rank>& _Dst_offset,
    const extent<_Dst_type::rank>& _Copy_extent);

template <
    typename _Src_type,
    typename OutputIterator,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type
>
concurrency::completion_future copy_async(_Src_type& _Src, OutputIterator _Dst);

template <
    typename _Src_type,
    typename OutputIterator,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type
>
concurrency::completion_future copy_async(_Src_type& _Src,
    const index<_Src_type::rank>& _Src_offset,
    const extent<_Src_type::rank>& _Copy_extent,
    OutputIterator _Dst);

template <
    typename _Src_type,
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type
>
concurrency::completion_future copy_async(_Src_type& _Src, _Dst_type& _Dst);

template <
    typename _Src_type,
    typename _Dst_type,
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type
>
concurrency::completion_future copy_async(_Src_type& _Src,
    const index<_Src_type::rank>& _Src_offset, _Dst_type &_Dst,
    const index<_Dst_type::rank>& _Dst_offset,
    const extent<_Src_type::rank>& _Copy_extent);
```

### <a name="parameters"></a>Parametreler

*_Copy_extent*<br/>
Kopyalanacak doku bölümünün kapsamı.

*_Dst*<br/>
Kopyalanması gereken nesne.

*_Dst_byte_size*<br/>
Hedefteki bayt sayısı.

*_Dst_type*<br/>
Hedef nesnenin türü.

*_Dst_offset*<br/>
Kopyalamaya başlanacak hedefe mahsup.

*GirişIterator*<br/>
Giriş yineleyicisinin türü.

*OutputIterator*<br/>
Çıktı yineleyicisinin türü.

*_Src*<br/>
Kopyalamaya itiraz etmek için.

*_Src_byte_size*<br/>
Kaynaktaki bayt sayısı.

*_Src_type*<br/>
Kaynak nesnenin türü.

*_Src_offset*<br/>
Kopyalamaya başlamak için kaynak içine ofset.

*Ilk*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*Son*<br/>
Kaynak kapsayıcıya sonlandırıcı bir yineleyici.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp_graphics.h

**Ad alanı:** Eşzamanlılık::grafikler

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
