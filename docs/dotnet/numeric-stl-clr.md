---
title: sayısal (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/numeric>
- cliext::accumulate
- cliext::adjacent_difference
- cliext::inner_product
- cliext::partial_sum
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
- accumulate function [STL/CLR]
- adjacent_difference function [STL/CLR]
- inner_product function [STL/CLR]
- partial_sum function [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
ms.openlocfilehash: 1939a6dd9b6d8186eb278623f3b0a5a3d851f4d3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208487"
---
# <a name="numeric-stlclr"></a>sayısal (STL/CLR)

Sayısal işleme için belirtilen algoritmaları gerçekleştiren kapsayıcı şablonu işlevlerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```
#include <cliext/numeric>
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<clienext/numeric >

**Ad alanı:** cliext

## <a name="declarations"></a>Bildirimler

|İşlev|Açıklama|
|--------------|-----------------|
|[accumulate (STL/CLR)](#accumulate)|Ardışık kısmi toplamları hesaplayarak, belirli bir aralıktaki tüm öğelerin toplamını, bazı başlangıç değerleri de dahil olmak üzere, belirli bir ikili işlemi, toplamın dışında bir şekilde kullanarak hesaplar.|
|[adjacent_difference (STL/CLR)](#adjacent_difference)|Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.|
|[inner_product (STL/CLR)](#inner_product)|İki aralıktaki öğe odaklı ürünün toplamını hesaplar ve belirtilen bir başlangıç değerine ekler ya da Sum ve ürün ikili işlemlerinin diğer belirtilen ikili işlemlerle değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.|
|[partial_sum (STL/CLR)](#partial_sum)|İlk öğeden `i`th öğesi aracılığıyla bir giriş aralığındaki bir dizi toplamı hesaplar ve bu her bir toplamın sonucunu bir hedef aralığın `i`bir şekilde depolar ya da toplam işlemin belirtilen başka bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.|

## <a name="members"></a>Üyeler

## <a name="accumulate-stlclr"></a><a name="accumulate"></a>topla (STL/CLR)

Ardışık kısmi toplamları hesaplayarak, belirli bir aralıktaki tüm öğelerin toplamını, bazı başlangıç değerleri de dahil olmak üzere, belirli bir ikili işlemi, toplamın dışında bir şekilde kullanarak hesaplar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _Ty> inline
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);
template<class _InIt, class _Ty, class _Fn2> inline
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, `accumulate`C++ standart kitaplık sayısal işleviyle aynı şekilde davranır. Daha fazla bilgi için bkz. [birikme](../standard-library/numeric-functions.md#accumulate).

## <a name="adjacent_difference-stlclr"></a><a name="adjacent_difference"></a>adjacent_difference (STL/CLR)

Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,
        _OutIt _Dest);
template<class _InIt, class _OutIt, class _Fn2> inline
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, `adjacent_difference`C++ standart kitaplık sayısal işleviyle aynı şekilde davranır. Daha fazla bilgi için bkz. [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference).

## <a name="inner_product-stlclr"></a><a name="inner_product"></a>inner_product (STL/CLR)

İki aralıktaki öğe odaklı ürünün toplamını hesaplar ve belirtilen bir başlangıç değerine ekler ya da Sum ve ürün ikili işlemlerinin diğer belirtilen ikili işlemlerle değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2, class _Ty> inline
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _Ty _Val);
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,
       class _Fn22> inline
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, `inner_product`C++ standart kitaplık sayısal işleviyle aynı şekilde davranır. Daha fazla bilgi için bkz. [inner_product](../standard-library/numeric-functions.md#inner_product).

## <a name="partial_sum-stlclr"></a><a name="partial_sum"></a>partial_sum (STL/CLR)

İlk öğeden `i`th öğesi aracılığıyla bir giriş aralığındaki bir dizi toplamı hesaplar ve bu her bir toplamın sonucunu bir hedef aralığın `i`bir şekilde depolar ya da toplam işlemin belirtilen başka bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);
template<class _InIt, class _OutIt, class _Fn2> inline
    _OutIt partial_sum(_InIt _First, _InIt _Last,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, `partial_sum`C++ standart kitaplık sayısal işleviyle aynı şekilde davranır. Daha fazla bilgi için bkz. [partial_sum](../standard-library/numeric-functions.md#partial_sum).
