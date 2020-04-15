---
title: short_vector_traits Yapısı
ms.date: 11/04/2016
f1_keywords:
- short_vector_traits
- AMP_SHORT_VECTORS/short_vector_traits
- AMP_SHORT_VECTORS/Concurrency::graphics::short_vector_traits::short_vector_traits
- AMP_SHORT_VECTORS/Concurrency::graphics::short_vector_traits::size Constant
ms.assetid: cd9492da-9e02-4a6e-9d50-b61252cdb460
ms.openlocfilehash: d743f74deaea5cb31cd609ece90891c8cfe2258f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374739"
---
# <a name="short_vector_traits-structure"></a>short_vector_traits Yapısı

short_vector_traits, altta yatan vektör uzunluğunun ve kısa vektör tipinin veya skaler türünün skaler türünün alınmasını sağlar

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    typename T
>
struct short_vector_traits;
template<>
struct short_vector_traits<unsigned int>;
template<>
struct short_vector_traits<uint_2>;
template<>
struct short_vector_traits<uint_3>;
template<>
struct short_vector_traits<uint_4>;
template<>
struct short_vector_traits<int>;
template<>
struct short_vector_traits<int_2>;
template<>
struct short_vector_traits<int_3>;
template<>
struct short_vector_traits<int_4>;
template<>
struct short_vector_traits<float>;
template<>
struct short_vector_traits<float_2>;
template<>
struct short_vector_traits<float_3>;
template<>
struct short_vector_traits<float_4>;
template<>
struct short_vector_traits<unorm>;
template<>
struct short_vector_traits<unorm_2>;
template<>
struct short_vector_traits<unorm_3>;
template<>
struct short_vector_traits<unorm_4>;
template<>
struct short_vector_traits<norm>;
template<>
struct short_vector_traits<norm_2>;
template<>
struct short_vector_traits<norm_3>;
template<>
struct short_vector_traits<norm_4>;
template<>
struct short_vector_traits<double>;
template<>
struct short_vector_traits<double_2>;
template<>
struct short_vector_traits<double_3>;
template<>
struct short_vector_traits<double_4>;
```

### <a name="parameters"></a>Parametreler

`T`

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[short_vector_traits::short_vector_traits Yapıcı](#ctor)||

### <a name="public-constants"></a>Genel Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[short_vector_traits::boyut Sabiti](#size)||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`short_vector_traits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp_short_vectors.h

**Ad alanı:** Eşzamanlılık::grafikler

## <a name="short_vector_traitsshort_vector_traits-constructor"></a><a name="ctor"></a>short_vector_traits::short_vector_traits Yapıcı

```cpp
short_vector_traits();
```

## <a name="short_vector_traitssize-constant"></a><a name="size"></a>short_vector_traits::boyut Sabiti

```cpp
static int const size = 1;
```

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
