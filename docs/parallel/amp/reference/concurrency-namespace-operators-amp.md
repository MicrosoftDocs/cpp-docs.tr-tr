---
title: Eşzamanlılık ad alanı işleçleri (AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d3bb77599fc81fa29f2c8155a6fd491ed2d639c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="concurrency-namespace-operators-amp"></a>Eşzamanlılık ad alanı işleçleri (AMP)
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[işleç *](#operator_star)|  
|[operator +](#operator_add)|[operator-](#operator-)|[operator /](#operator_div)|  
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
  

##  <a name="operator_div"></a>  operator /   
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
