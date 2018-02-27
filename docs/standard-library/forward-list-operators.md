---
title: "&lt;forward_list&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
dev_langs:
- C++
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: 2c56b8ccbba914b59d1a813c39db2dcc3350e822
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt; işleçleri
||||  
|-|-|-|  
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|  
|[işleci&lt;](#op_lt)|[işleci&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a>  operator ==  
 İletme liste nesnesi işlecinin sol tarafındaki sağ tarafında iletme listesi nesnesine eşitse testleri.  
  
```
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Türünde bir nesne `forward_list`.|  
|`right`|Türünde bir nesne `forward_list`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon işlevi overloads `operator==` iki nesne şablonu sınıfının Karşılaştırılacak `forward_list`. İşlevi döndürür `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`.  
  
##  <a name="op_neq"></a>  operator! =  
 Testleri işlecinin sol tarafındaki iletme liste nesnesi sağ tarafında iletme listesi nesnesine eşit değil.  
  
```
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Türünde bir nesne `forward_list`.|  
|`right`|Türünde bir nesne `forward_list`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** listeler eşit; değilse **false** listeler eşit olması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon işlevi döndürür `!(left == right)`.  
  
##  <a name="op_lt"></a>  işleci&lt;  
 İleriye doğru liste nesnesi işlecinin sol tarafındaki sağ tarafında iletme liste nesnesi küçükse testleri.  
  
```
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Türünde bir nesne `forward_list`.|  
|`right`|Türünde bir nesne `forward_list`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Liste işlecinin sol tarafındaki listenin işlecinin sağ tarafında eşit değildir ancak daha az ise; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon işlevi overloads `operator<` iki nesne şablonu sınıfının Karşılaştırılacak `forward_list`. İşlevi döndürür `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`.  
  
##  <a name="op_lt_eq"></a>  işleci&lt;=  
 İleriye doğru listesi işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ taraftaki iletme listesi nesnesine eşit veya daha az olur.  
  
```
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Türünde bir nesne `forward_list`.|  
|`right`|Türünde bir nesne `forward_list`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Liste işlecinin sol tarafındaki listenin işlecinin sağ tarafında eşit veya daha az ise; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon işlevi döndürür `!(right < left)`.  
  
##  <a name="op_gt"></a>  işleci&gt;  
 Testleri işlecinin sol tarafındaki iletme liste nesnesi sağ tarafında iletme liste nesnesi değerinden daha büyük.  
  
```
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Türünde bir nesne `forward_list`.|  
|`right`|Türünde bir nesne `forward_list`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Listenin işlecinin sol tarafındaki listenin işlecinin sağ tarafında büyükse; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon işlevi döndürür `right < left`.  
  
##  <a name="op_gt_eq"></a>  işleci&gt;=  
 Testleri iletme listesi işlecinin sol tarafındaki büyük veya ona eşit iletme listesi nesnesine sağ tarafında nesnesidir.  
  
```
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Türünde bir nesne `forward_list`.|  
|`right`|Türünde bir nesne `forward_list`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` ileriye doğru liste işlecinin sol tarafındaki büyük veya ona eşit işlecinin sağ tarafında iletme listesine ise; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlevi döndürür `!(left < right)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<forward_list>](../standard-library/forward-list.md)



