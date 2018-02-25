---
title: "Eşzamanlılık ad alanı işleçleri (AMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 308c09af9989aa998a7e1f7d748f52a2d8dca391
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-operators-amp"></a>Eşzamanlılık ad alanı işleçleri (AMP)
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[operator*](#operator_star)|  
|[operator+](#operator_add)|[operator-](#operator-)|[operator /](#operator_div)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_eq_eq"></a>  operator ==   
 Belirtilen bağımsız değişkenler eşit olup olmadığını belirler.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Tuple bağımsız değişkenleri derecesini.  
  
 `_Lhs`  
 Karşılaştırılacak başlıklar biri.  
  
 `_Rhs`  
 Karşılaştırılacak başlıklar biri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` diziler eşitse; Aksi takdirde `false`.  
  
##  <a name="operator_neq"></a>  operator! =   
 Belirtilen bağımsız değişkenler eşit olup olmadığını belirler.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Tuple bağımsız değişkenleri derecesini.  
  
 `_Lhs`  
 Karşılaştırılacak başlıklar biri.  
  
 `_Rhs`  
 Karşılaştırılacak başlıklar biri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` diziler eşit değilse; Aksi takdirde `false`.  
  
##  <a name="operator_add"></a>  operator +   

 Belirtilen bağımsız değişkenler component-wise toplamını hesaplar.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Tuple bağımsız değişkenleri derecesini.  
  
 `_Lhs`  
 Eklemek için bağımsız değişkenlerden biri.  
  
 `_Rhs`  
 Eklemek için bağımsız değişkenlerden biri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bağımsız değişkenler component-wise toplamı.  
  
##  <a name="operator-"></a>  operator-   

 Belirtilen bağımsız değişkenler arasındaki component-wise farkı hesaplar.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Tuple bağımsız değişkenleri derecesini.  
  
 `_Lhs`  
 Çıkartma yapılacak için bağımsız değişken.  
  
 `_Rhs`  
 Çıkarmak için bağımsız değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bağımsız değişkenler arasındaki component-wise fark.  
  
##  <a name="operator_star"></a>  işleç *   

 Belirtilen bağımsız değişkenler component-wise çarpımını hesaplar.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Tuple bağımsız değişkenleri derecesini.  
  
 `_Lhs`  
 Bir başlık çarpın.  
  
 `_Rhs`  
 Bir başlık çarpın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bağımsız değişkenler component-wise ürün.  
  

##  <a name="operator_div">operator /</a>   
 Belirtilen bağımsız değişkenler component-wise sayının hesaplar.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Tuple bağımsız değişkenleri derecesini.  
  
 `_Lhs`  
 Bölünür tanımlama.  
  
 `_Rhs`  
 Tarafından bölmek için tanımlama grubu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bağımsız değişkenler component-wise bölüm.  
  
##  <a name="operator_mod"></a>  operator %   

 Modulus ilk belirtilen bağımsız değişkenin ikinci belirtilen bağımsız değişken olarak hesaplar.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Tuple bağımsız değişkenleri derecesini.  
  
 `_Lhs`  
 Tuple içinden modulo hesaplanır.  
  
 `_Rhs`  
 Tanımlama grubu için modül tarafından.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk belirtilen bağımsız değişken modulus ikinci belirtilen bağımsız değişken sonucu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace ](concurrency-namespace-cpp-amp.md)
