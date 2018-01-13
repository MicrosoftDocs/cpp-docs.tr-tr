---
title: "error_category sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
dev_langs: C++
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 927711e5ad87be2a8c4683cb960cc02015de2316
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="errorcategory-class"></a>error_category Sınıfı
Nesneler için hata kodları kategorisini tanımlayan soyut, ortak tabanı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class error_category;
```  
  
## <a name="remarks"></a>Açıklamalar  
 Önceden tanımlanmış iki nesne uygulamak `error_category`: [generic_category](../standard-library/system-error-functions.md#generic_category) ve [system_category](../standard-library/system-error-functions.md#system_category).  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[value_type](#value_type)|Saklı hata kodu değerini temsil eden tür.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[default_error_condition](#default_error_condition)|Bir hata koşulu nesne için hata kodu değerini depolar.|  
|[eşdeğer](#equivalent)|Hata nesneleri eşdeğer olup olmadığını belirten bir değer döndürür.|  
|[message](#message)|Belirtilen hata kodu adını döndürür.|  
|[adı](#name)|Kategorinin adını döndürür.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator ==](#op_eq_eq)|Testler arasında eşitliği `error_category` nesneleri.|  
|[operator!=](#op_neq)|Testler arasında eşitsizlik için `error_category` nesneleri.|  
|[operator <](#op_lt)|Varsa testleri [error_category](../standard-library/error-category-class.md) nesne küçük `error_category` nesne geçirilen karşılaştırma için.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<system_error >  
  
 **Namespace:** std  
  
##  <a name="default_error_condition"></a>error_category::default_error_condition  
 Bir hata koşulu nesne için hata kodu değerini depolar.  
  
```
virtual error_condition default_error_condition(int _Errval) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Errval`|Hata kodu değeri depolamak için [error_condition](../standard-library/error-condition-class.md).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `error_condition(_Errval, *this)`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="equivalent"></a>error_category::equivalent  
 Hata nesneleri eşdeğer olup olmadığını belirten bir değer döndürür.  
  
```
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Errval`|Hata kodu Karşılaştırılacak değer.|  
|`_Cond`|[Error_condition](../standard-library/error-condition-class.md) Karşılaştırılacak nesne.|  
|`_Code`|[Error_code](../standard-library/error-code-class.md) Karşılaştırılacak nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Kategori ve değer eşitse; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevinin döndürdüğü `*this == _Cond.category() && _Cond.value() == _Errval`.  
  
 İkinci üye işlevinin döndürdüğü `*this == _Code.category() && _Code.value() == _Errval`.  
  
##  <a name="message"></a>error_category::Message  
 Belirtilen hata kodu adını döndürür.  
  
```
virtual string message(error_code::value_type val) const = 0;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`val`|Hata kodu açıklamak için değer.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata kodu açıklayıcı adını döndürür `val` kategori için.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="name"></a>error_category::Name  
 Kategorinin adını döndürür.  
  
```
virtual const char *name() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kategori adı null ile sonlandırılmış bayt dize olarak döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="op_eq_eq"></a>error_category::operator ==  
 Testler arasında eşitliği `error_category` nesneleri.  
  
```
bool operator==(const error_category& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|Eşitlik için test edilebilir nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** nesneleri eşitse; **false** nesneleri eşit değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işleci döndürür `this == &right`.  
  
##  <a name="op_neq"></a>error_category::operator! =  
 Testler arasında eşitsizlik için `error_category` nesneleri.  
  
```
bool operator!=(const error_category& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|Eşitsizlik için test edilebilir nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa `error_category` nesnesi eşit değil `error_category` nesnesi geçirildi `right`; Aksi halde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci döndürür `(!*this == right)`.  
  
##  <a name="op_lt"></a>error_category::operator&lt;  
 Varsa testleri [error_category](../standard-library/error-category-class.md) nesne küçük `error_category` nesne geçirilen karşılaştırma için.  
  
```
bool operator<(const error_category& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|`error_category` Karşılaştırılacak nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa `error_category` nesne küçük `error_category` karşılaştırma için; geçirilen nesnesi Aksi takdirde, **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci döndürür `this < &right`.  
  
##  <a name="value_type"></a>error_category::value_type  
 Saklı hata kodu değerini temsil eden tür.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tür tanımı için eş anlamlı olduğundan `int`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<system_error>](../standard-library/system-error.md)



