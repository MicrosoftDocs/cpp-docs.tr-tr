---
title: "error_condition sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_condition
- system_error/std::error_condition::value_type
- system_error/std::error_condition::assign
- system_error/std::error_condition::category
- system_error/std::error_condition::clear
- system_error/std::error_condition::message
- system_error/std::error_condition::operator bool
dev_langs: C++
helpviewer_keywords:
- std::error_condition
- std::error_condition::value_type
- std::error_condition::assign
- std::error_condition::category
- std::error_condition::clear
- std::error_condition::message
- 
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c8109db3a6607abd1792485c93a59795d432f824
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="errorcondition-class"></a>error_condition Sınıfı
Kullanıcı tanımlı hata kodları temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class error_condition;
```  
  
## <a name="remarks"></a>Açıklamalar  
 Türünde bir nesne `error_condition` bir hata kodu değeri ve temsil eden bir nesne için bir işaretçi depolayan bir [kategori](../standard-library/error-category-class.md) hata kodları için kullanılan kullanıcı tanımlı hatalar bildirdi.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[error_condition](#error_condition)|Türünde bir nesne oluşturur `error_condition`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[value_type](#value_type)|Saklı hata kodu değerini temsil eden tür.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Ata](#assign)|Bir hata kodu değerini ve kategoriyi bir hata koşuluna atar.|  
|[Kategori](#category)|Hata kategorisi döndürür.|  
|[Temizle](#clear)|Hata kodu değerini ve kategori temizler.|  
|[İleti](#message)|Hata kodu adını döndürür.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator ==](#op_eq_eq)|Testler arasında eşitliği `error_condition` nesneleri.|  
|[operator! =](#op_neq)|Testler arasında eşitsizlik için `error_condition` nesneleri.|  
|[operator <](#op_lt)|Varsa testleri `error_condition` nesne küçük `error_code` nesne geçirilen karşılaştırma için.|  
|[işleç =](#op_eq)|Yeni bir numaralandırma değeri atar `error_condition` nesnesi.|  
|[işleç bool değeri](#op_bool)|Türünde bir değişken bıraktığı `error_condition`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<system_error >  
  
 **Namespace:** std  
  
##  <a name="assign"></a>error_condition::Assign  
 Bir hata kodu değerini ve kategoriyi bir hata koşuluna atar.  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`val`|Hata kodu değeri depolamak için `error_code`.|  
|`_Cat`|Hata kategorisi depolamak üzere `error_code`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi depoları `val` hata kodu değerini gösteren bir işaretçi olarak `_Cat`.  
  
##  <a name="category"></a>error_condition::category  
 Hata kategorisi döndürür.  
  
```
const error_category& category() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru depolanan hata kategorisi  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="clear"></a>error_condition::Clear  
 Hata kodu değerini ve kategori temizler.  
  
```
clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi sıfır hata kodu değeri ve bir işaretçi depolar [generic_category](../standard-library/system-error-functions.md#generic_category) nesnesi.  
  
##  <a name="error_condition"></a>error_condition::error_condition  
 Türünde bir nesne oluşturur `error_condition`.  
  
```
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`val`|Hata kodu değeri depolamak için `error_condition`.|  
|`_Cat`|Hata kategorisi depolamak üzere `error_condition`.|  
|`_Errcode`|Numaralandırma değeri depolamak için `error_condition`.|  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu sıfır hata kodu değeri ve bir işaretçi depolar [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
 İkinci oluşturucu depoları `val` hata kodu değerini gösteren bir işaretçi olarak [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).  
  
 Üçüncü Oluşturucusu depoları `(value_type)_Errcode` hata kodu değerini gösteren bir işaretçi olarak [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="message"></a>error_condition::Message  
 Hata kodu adını döndürür.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `string` hata kodu adını temsil eden.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevinin döndürdüğü `category().message(value())`.  
  
##  <a name="op_eq_eq"></a>error_condition::operator ==  
 Testler arasında eşitliği `error_condition` nesneleri.  
  
```
bool operator==(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|Eşitlik için test ojbect.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** nesneleri eşitse; **false** nesneleri eşit değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci döndürür `category() == right.category() && value == right.value()`.  
  
##  <a name="op_neq"></a>error_condition::operator! =  
 Testler arasında eşitsizlik için `error_condition` nesneleri.  
  
```
bool operator!=(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|Eşitsizlik için test edilebilir nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa `error_condition` nesnesi eşit değil `error_condition` nesnesi geçirildi `right`; Aksi halde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci döndürür `!(*this == right)`.  
  
##  <a name="op_lt"></a>error_condition::operator&lt;  
 Varsa testleri `error_condition` nesne küçük `error_code` nesne geçirilen karşılaştırma için.  
  
```
bool operator<(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|`error_condition` Karşılaştırılacak nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa `error_condition` nesne küçük `error_condition` karşılaştırma için; geçirilen nesnesi Aksi takdirde, **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci döndürür `category() < right.category() || category() == right.category() && value < right.value()`.  
  
##  <a name="op_eq"></a>error_condition::operator =  
 Yeni bir numaralandırma değeri atar `error_condition` nesnesi.  
  
```
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
 operator=(Enum _Errcode);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Errcode`|Numaralandırma değeri atamak için `error_condition` nesnesi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru `error_condition` yeni numaralandırma değeri üye işlevi tarafından atanan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci depoları `(value_type)error` hata kodu değerini gösteren bir işaretçi olarak [generic_category](../standard-library/system-error-functions.md#generic_category). Döndürdüğü `*this`.  
  
##  <a name="op_bool"></a>error_condition::operator bool  
 Türünde bir değişken bıraktığı `error_condition`.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Boole değeri `error_condition` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir değer dönüştürülebilir işleci döndürür `true` yalnızca [değeri](#value) sıfıra eşit değil. Dönüş türü yalnızca dönüştürülebilir `bool`, değil `void *` veya diğer bilinen skaler türler.  
  
##  <a name="value"></a>error_condition::Value  
 Saklı hata kodu değerini döndürür.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türü depolanan hata kodu değeri [value_type](#value_type).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="value_type"></a>error_condition::value_type  
 Saklı hata kodu değerini temsil eden tür.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tür tanımı için eş anlamlı olduğundan `int`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [error_category sınıfı](../standard-library/error-category-class.md)   
 [< system_error >](../standard-library/system-error.md)



