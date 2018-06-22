---
title: sayısal (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/numeric>
- cliext::accumulate
- cliext::adjacent_difference
- cliext::inner_product
- cliext::partial_sum
dev_langs:
- C++
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
- accumulate function [STL/CLR]
- adjacent_difference function [STL/CLR]
- inner_product function [STL/CLR]
- partial_sum function [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4313b80a4fa83e5340f678834b64dd5269278a0d
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305520"
---
# <a name="numeric-stlclr"></a>sayısal (STL/CLR)
Sayısal işlemek için sağlanan algoritmalar gerçekleştirmek kapsayıcı şablon işlevleri tanımlar.  
  
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
|[accumulate (STL/CLR)](#accumulate)|Tüm öğelerin toplamı, art arda kısmi toplamlarını bilgi işlem tarafından bazı başlangıç değeri de dahil olmak üzere belirli bir aralık içinde hesaplar veya benzer şekilde toplam dışında belirtilen bir ikili işlem kullanılarak elde edilen art arda kısmi sonuçlar sonucunu hesaplar.|  
|[adjacent_difference (STL/CLR)](#adjacent_difference)|Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.|  
|[inner_product (STL/CLR)](#inner_product)|İki aralıklarının element-wise ürün toplamını hesaplar ve belirtilen ilk değerine ekler veya sum ve ürün ikili işlemleri tarafından belirtilen diğer ikili işlemlerin burada değiştirilir genelleştirilmiş bir yordamın sonuç hesaplar.|  
|[partial_sum (STL/CLR)](#partial_sum)|SUM'ları ilk öğe ile bir giriş aralığında bir dizi hesaplar `i`th öğesi ve her tür toplamda sonucunu depolar `i`th öğesi bir hedef aralığının veya genel bir yordam sonucunu hesaplar burada toplam işlem Belirtilen başka bir ikili işlem tarafından değiştirilir.|  
 
## <a name="functions"></a>İşlevler

## <a name="accumulate"></a> accumulate (STL/CLR)
Tüm öğelerin toplamı, art arda kısmi toplamlarını bilgi işlem tarafından bazı başlangıç değeri de dahil olmak üzere belirli bir aralık içinde hesaplar veya benzer şekilde toplam dışında belirtilen bir ikili işlem kullanılarak elde edilen art arda kısmi sonuçlar sonucunu hesaplar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı sayısal işlevi ile aynı şekilde davranır `accumulate`. Daha fazla bilgi için bkz: [accumulate](../standard-library/numeric-functions.md#accumulate).  

## <a name="adjacent_difference"></a> adjacent_difference (STL/CLR)
Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı sayısal işlevi ile aynı şekilde davranır `adjacent_difference`. Daha fazla bilgi için bkz: [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference).  

## <a name="inner_product"></a> inner_product (STL/CLR)
İki aralıklarının element-wise ürün toplamını hesaplar ve belirtilen ilk değerine ekler veya sum ve ürün ikili işlemleri tarafından belirtilen diğer ikili işlemlerin burada değiştirilir genelleştirilmiş bir yordamın sonuç hesaplar.  
  
###<a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı sayısal işlevi ile aynı şekilde davranır `inner_product`. Daha fazla bilgi için bkz: [inner_product](../standard-library/numeric-functions.md#inner_product).

## <a name="partial_sum"></a> partial_sum (STL/CLR)
SUM'ları ilk öğe ile bir giriş aralığında bir dizi hesaplar `i`th öğesi ve her tür toplamda sonucunu depolar `i`th öğesi bir hedef aralığının veya genel bir yordam sonucunu hesaplar burada toplam işlem Belirtilen başka bir ikili işlem tarafından değiştirilir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı sayısal işlevi ile aynı şekilde davranır `partial_sum`. Daha fazla bilgi için bkz: [partial_sum](../standard-library/numeric-functions.md#partial_sum).  
    