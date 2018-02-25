---
title: "&lt;system_error&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
dev_langs:
- C++
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 84cac348fcc2c9577b3a0e1f72ac56a4bbabf90f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt; işleçleri
||||  
|-|-|-|  
|[operator!=](#op_neq)|[işleci&lt;](#op_lt)|[operator==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a>  operator ==  
 Nesne işlecinin sol tarafındaki sağ tarafında nesnesine eşitse testleri.  
  
```
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Eşitlik için test edilebilir nesne.|  
|`right`|Eşitlik için test edilebilir nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** nesneleri eşitse; **false** nesneleri eşit değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, döndürür `left.category() == right.category() && left.value() == right.value()`.  
  
##  <a name="op_neq"></a>  operator! =  
 Testleri işlecinin sol tarafındaki nesnesi sağ tarafında nesnede eşit değil.  
  
```
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Eşitsizlik için test edilebilir nesne.|  
|`right`|Eşitsizlik için test edilebilir nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** nesne içinde aktarılırsa `left` geçirilen nesnesine eşit değil `right`; Aksi halde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, döndürür `!(left == right)`.  
  
##  <a name="op_lt">işleci</a>&lt;  
 Bir nesnenin karşılaştırma için içeri geçirilen nesneden küçük olup olmadığını sınar.  
  
```
template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Karşılaştırılacak nesne.|  
|`right`|Karşılaştırılacak nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** nesne içinde aktarılırsa `left` daha az nesne geçirilen `right`; Aksi takdirde, **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev hata sıralamasını sınar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<system_error>](../standard-library/system-error.md)



