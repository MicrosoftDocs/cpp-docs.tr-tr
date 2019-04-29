---
title: short_vector Yapısı
ms.date: 11/04/2016
f1_keywords:
- short_vector
- AMP_SHORT_VECTORS/short_vector
- AMP_SHORT_VECTORS/Concurrency::graphics::short_vector::short_vector Constructor
ms.assetid: e4f50b8f-1150-437d-b58c-79c5fb883708
ms.openlocfilehash: 012a70ae628a896c8202e46a5624f37f58b0781b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351553"
---
# <a name="shortvector-structure"></a>short_vector Yapısı

short_vector kısa vektörleri genel programlama için yararlı olan azaltılarak tanımları sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<
    typename _Scalar_type,
    int _Size
>
struct short_vector;
template<>
struct short_vector<unsigned int, 1>;
template<>
struct short_vector<unsigned int, 2>;
template<>
struct short_vector<unsigned int, 3>;
template<>
struct short_vector<unsigned int, 4>;
template<>
struct short_vector<int, 1>;
template<>
struct short_vector<int, 2>;
template<>
struct short_vector<int, 3>;
template<>
struct short_vector<int, 4>;
template<>
struct short_vector<float, 1>;
template<>
struct short_vector<float, 2>;
template<>
struct short_vector<float, 3>;
template<>
struct short_vector<float, 4>;
template<>
struct short_vector<unorm, 1>;
template<>
struct short_vector<unorm, 2>;
template<>
struct short_vector<unorm, 3>;
template<>
struct short_vector<unorm, 4>;
template<>
struct short_vector<norm, 1>;
template<>
struct short_vector<norm, 2>;
template<>
struct short_vector<norm, 3>;
template<>
struct short_vector<norm, 4>;
template<>
struct short_vector<double, 1>;
template<>
struct short_vector<double, 2>;
template<>
struct short_vector<double, 3>;
template<>
struct short_vector<double, 4>;
```

#### <a name="parameters"></a>Parametreler

*_Scalar_type*<br/>

*_Boyut*<br/>

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`type`||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[short_vector::short_vector Oluşturucusu](#ctor)||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`short_vector`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_short_vectors.h

**Namespace:** CONCURRENCY::Graphics

##  <a name="ctor"></a>  short_vector::short_vector Oluşturucusu

```
short_vector();
```

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
