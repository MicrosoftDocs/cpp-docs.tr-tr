---
title: CONCURRENCY::Graphics ad alanı işlevleri
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::fast_math::copy_async
- amp_graphics/Concurrency::fast_math::copy
ms.assetid: ace01cd5-29d3-4356-930e-c81a61c5f934
ms.openlocfilehash: 30503ffa7e5c3845af6c9f61f4e8fc2f64b74e5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467138"
---
# <a name="concurrencygraphics-namespace-functions"></a>CONCURRENCY::Graphics ad alanı işlevleri

|||
|-|-|
|[kopyalama](#copy)|[copy_async](#copy_async)|

##  <a name="copy"></a>  copy işlevi (Concurrency::graphics Namespace)

Bir kaynak dokuyu hedef arabellek içine kopyalar veya kaynak arabelleği hedef arabellek içine kopyalar. Bu işlevin genel formu `copy(src, dest)`.

```
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
Kopyalanacak doku bölümü faturalandırılırsınız.

*_Dst*<br/>
Üstüne kopyalanacak nesne.

*_Dst_byte_size*<br/>
Hedefteki bayt sayısı.

*_Dst_type*<br/>
Hedef nesne türü.

*_Dst_offset*<br/>
Kopyalamanın başlayacağı hedefe olan uzaklık.

*Inputıterator*<br/>
Giriş yineleyicisinin türü.

*Outputıterator*<br/>
Çıkış yineleyici türü.

*_Src*<br/>
Kopyalanacak nesneye için.

*_Src_byte_size*<br/>
Kaynaktaki bayt sayısı.

*_Src_type*<br/>
Kaynak nesne türü.

*_Src_offset*<br/>
Kopyalamanın başlayacağı kaynağa olan uzaklık.

*ilk*<br/>
Kaynak kapsayıcı içine bir başlangıç yineleyicisi.

*Son*<br/>
Kaynak kapsayıcı içine bir bitiş yineleyicisi.

##  <a name="copy_async"></a>  copy_async işlevi (Concurrency::graphics Namespace)

Zaman uyumsuz olarak kaynak dokuyu hedef arabellek içine kopyalar veya kaynak arabelleği hedef arabellek içine kopyalar ve ardından döndürür bir [completion_future](completion-future-class.md) üzerinde beklenen nesne. Kod hızlandırıcıda çalışıyor olduğunda veriler kopyalanamaz. Bu işlevin genel formu `copy(src, dest)`.

```
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
Kopyalanacak doku bölümü faturalandırılırsınız.

*_Dst*<br/>
Üstüne kopyalanacak nesne.

*_Dst_byte_size*<br/>
Hedefteki bayt sayısı.

*_Dst_type*<br/>
Hedef nesne türü.

*_Dst_offset*<br/>
Kopyalamanın başlayacağı hedefe olan uzaklık.

*Inputıterator*<br/>
Giriş yineleyicisinin türü.

*Outputıterator*<br/>
Çıkış yineleyici türü.

*_Src*<br/>
Kopyalanacak nesneye için.

*_Src_byte_size*<br/>
Kaynaktaki bayt sayısı.

*_Src_type*<br/>
Kaynak nesne türü.

*_Src_offset*<br/>
Kopyalamanın başlayacağı kaynağa olan uzaklık.

*ilk*<br/>
Kaynak kapsayıcı içine bir başlangıç yineleyicisi.

*Son*<br/>
Kaynak kapsayıcı içine bir bitiş yineleyicisi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_graphics.h

**Namespace:** Concurrency::graphics

## <a name="see-also"></a>Ayrıca Bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
