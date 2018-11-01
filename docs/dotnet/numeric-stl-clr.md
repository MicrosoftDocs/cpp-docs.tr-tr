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
ms.openlocfilehash: 95449937dda62d8ef127d41625553f0e4294cf77
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574258"
---
# <a name="numeric-stlclr"></a>sayısal (STL/CLR)

Sağlanan sayısal işlemeler için algoritmalar gerçekleştiren kapsayıcı şablon işlevini tanımlar.

## <a name="syntax"></a>Sözdizimi

```
#include <cliext/numeric>
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/sayısal >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|İşlev|Açıklama|
|--------------|-----------------|
|[accumulate (STL/CLR)](#accumulate)|Art arda gelen kısmi toplamları tarafından bazı başlangıç değerleri de dahil olmak üzere, belirtilen bir aralıktaki tüm öğelerin toplamını hesaplar veya benzer şekilde bir belirtilen ikili işlem toplamı dışında kullanımından elde edilen art arda gelen kısmi sonuçların sonucunu hesaplar.|
|[adjacent_difference (STL/CLR)](#adjacent_difference)|Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.|
|[inner_product (STL/CLR)](#inner_product)|İki aralığın öğe düzeyinde çarpımının ürün toplamını hesaplar ve belirtilen bir başlangıç değerine ekler veya toplamın ve ürün ikili işlemler başka bir belirtilen ikili işlem tarafından değiştirildiği desene genelleştirilmiş bir yordamının sonucunu hesaplar.|
|[partial_sum (STL/CLR)](#partial_sum)|Bir öğeyi kullanarak ilk öğedeki bir giriş aralığında hesaplar `i`öğedeki ve böyle her bir toplamın sonucunu depolar `i`öğedeki bir hedef aralığına veya genelleştirilmiş bir yordamının sonucunu hesaplar burada toplama işleminin başka bir belirtilen ikili işlem tarafından değiştirilir.|

## <a name="members"></a>Üyeler

## <a name="accumulate"></a> biriktir (STL/CLR)

Art arda gelen kısmi toplamları tarafından bazı başlangıç değerleri de dahil olmak üzere, belirtilen bir aralıktaki tüm öğelerin toplamını hesaplar veya benzer şekilde bir belirtilen ikili işlem toplamı dışında kullanımından elde edilen art arda gelen kısmi sonuçların sonucunu hesaplar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _Ty> inline
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);
template<class _InIt, class _Ty, class _Fn2> inline
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı sayısal işlevi gibi davranır `accumulate`. Daha fazla bilgi için [accumulate](../standard-library/numeric-functions.md#accumulate).

## <a name="adjacent_difference"></a> adjacent_difference (STL/CLR)

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

Bu işlev C++ Standart Kitaplığı sayısal işlevi gibi davranır `adjacent_difference`. Daha fazla bilgi için [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference).

## <a name="inner_product"></a> inner_product (STL/CLR)

İki aralığın öğe düzeyinde çarpımının ürün toplamını hesaplar ve belirtilen bir başlangıç değerine ekler veya toplamın ve ürün ikili işlemler başka bir belirtilen ikili işlem tarafından değiştirildiği desene genelleştirilmiş bir yordamının sonucunu hesaplar.

###<a name="syntax"></a>Sözdizimi

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

Bu işlev C++ Standart Kitaplığı sayısal işlevi gibi davranır `inner_product`. Daha fazla bilgi için [inner_product](../standard-library/numeric-functions.md#inner_product).

## <a name="partial_sum"></a> partial_sum (STL/CLR)

Bir öğeyi kullanarak ilk öğedeki bir giriş aralığında hesaplar `i`öğedeki ve böyle her bir toplamın sonucunu depolar `i`öğedeki bir hedef aralığına veya genelleştirilmiş bir yordamının sonucunu hesaplar burada toplama işleminin başka bir belirtilen ikili işlem tarafından değiştirilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);
template<class _InIt, class _OutIt, class _Fn2> inline
    _OutIt partial_sum(_InIt _First, _InIt _Last,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı sayısal işlevi gibi davranır `partial_sum`. Daha fazla bilgi için [partial_sum](../standard-library/numeric-functions.md#partial_sum).