---
description: 'Daha fazla bilgi edinin: concurrency:: Graphics Namespace işlevleri'
title: Concurrency::graphics ad alanı işlevleri
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::fast_math::copy_async
- amp_graphics/Concurrency::fast_math::copy
ms.assetid: ace01cd5-29d3-4356-930e-c81a61c5f934
ms.openlocfilehash: dab12e4a0d1c767d9422991679ed59152cd89c1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122284"
---
# <a name="concurrencygraphics-namespace-functions"></a>Concurrency::graphics ad alanı işlevleri

[kopya](#copy)\
[copy_async](#copy_async)

## <a name="copy-function-concurrencygraphics-namespace"></a><a name="copy"></a> Copy Işlevi (concurrency:: Graphics ad alanı)

Bir kaynak dokusunu hedef arabelleğe kopyalar veya bir kaynak arabelleğini hedef arabelleğe kopyalar. Bu işlevin genel formu `copy(src, dest)` .

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
Kopyalanacak nesne.

*_Dst_byte_size*<br/>
Hedefteki baytların sayısı.

*_Dst_type*<br/>
Hedef nesnenin türü.

*_Dst_offset*<br/>
Kopyalamanın başlayacağı hedefe olan fark.

*InputIterator*<br/>
Giriş yineleyicisinin türü.

*OutputIterator*<br/>
Çıkış yineleyicisinin türü.

*_Src*<br/>
Kopyalanacak nesneye.

*_Src_byte_size*<br/>
Kaynaktaki bayt sayısı.

*_Src_type*<br/>
Kaynak nesnenin türü.

*_Src_offset*<br/>
Kopyalamanın başlayacağı kaynağa olan Aralık.

*adı*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*soyadına*<br/>
Kaynak kapsayıcıya bir bitiş yineleyicisi.

## <a name="copy_async-function-concurrencygraphics-namespace"></a><a name="copy_async"></a> copy_async Işlevi (concurrency:: Graphics ad alanı)

Zaman uyumsuz olarak bir kaynak dokusunu bir hedef arabelleğe kopyalar veya bir kaynak arabelleği hedef arabelleğe kopyalar ve ardından beklemiş olabilecek bir [completion_future](completion-future-class.md) nesnesi döndürür. Bir hızlandırıcı üzerinde kod çalışırken veri kopyalanamıyor. Bu işlevin genel formu `copy(src, dest)` .

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
Kopyalanacak nesne.

*_Dst_byte_size*<br/>
Hedefteki baytların sayısı.

*_Dst_type*<br/>
Hedef nesnenin türü.

*_Dst_offset*<br/>
Kopyalamanın başlayacağı hedefe olan fark.

*InputIterator*<br/>
Giriş yineleyicisinin türü.

*OutputIterator*<br/>
Çıkış yineleyicisinin türü.

*_Src*<br/>
Kopyalanacak nesneye.

*_Src_byte_size*<br/>
Kaynaktaki bayt sayısı.

*_Src_type*<br/>
Kaynak nesnenin türü.

*_Src_offset*<br/>
Kopyalamanın başlayacağı kaynağa olan Aralık.

*adı*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*soyadına*<br/>
Kaynak kapsayıcıya bir bitiş yineleyicisi.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** Eşzamanlılık:: grafik

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
