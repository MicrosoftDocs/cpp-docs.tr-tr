---
title: "CAdapt sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs: C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 37ce02b9493c47a2c93d9e54e14f73b5c980317d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cadapt-class"></a>CAdapt sınıfı
Bu şablon, nesnenin adresi dışında bir öğe döndürmek üzere address-of işlecini yeniden tanımlayan sınıfları sarmalamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class CAdapt
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Uyarlanmış tür.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|Oluşturucu.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAdapt::operator const T &](#operator_const_t_amp)|Döndürür bir `const` başvuru `m_T`.|  
|[CAdapt::operator T &](#operator_t_amp)|Bir başvuru döndürür `m_T`.|  
|[CAdapt::operator <](#operator_lt)|Uyarlanmış türünde bir nesneyi karşılaştırır `m_T`.|  
|[CAdapt::operator =](#operator_eq)|İçin uyarlanmış türünde bir nesne atar `m_T`.|  
|[CAdapt::operator ==](#operator_eq_eq)|Uyarlanmış türünde bir nesneyi karşılaştırır `m_T`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|Uyarlanan veri.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAdapt`address-of işleci yeniden tanımlamanız sınıfları sarmalamak için kullanılan basit bir şablonu ( `operator &`) nesnenin adresi dışında bir şey döndürülecek. Bu tür sınıflar örneklerindendir ATL'ın `CComBSTR`, `CComPtr`, ve `CComQIPtr` sınıfları ve derleyici COM destek sınıfı `_com_ptr_t`. Tüm bu sınıfların yeniden tanımlamanız dönüş adresi veri üyeleri birinin address-of işleci (bir `BSTR` durumunda `CComBSTR`ve bir arabirim işaretçisi diğer sınıfların söz konusu olduğunda).  
  
 `CAdapt`kullanıcının birincil rolüdür sınıf tarafından tanımlanan address-of işleci gizlemek için `T`, henüz hala uyarlanmış sınıf özelliklerini korur. `CAdapt`Bu rol bir ortak üye tutarak fulfils [m_T](#m_t), türü `T`ve dönüştürme işleçleri, Karşılaştırma işleçleri ve kopya Oluşturucu özelleştirmeleri, izin vermek için tanımlayarak `CAdapt` olmaları durumunda olarak kabul edilmesi için Nesne türü `T`.  
  
 Bağdaştırıcı sınıfı `CAdapt` address-of işleci kullanılarak içerdikleri nesneler adreslerini elde edebilmek bazı kapsayıcı Stil sınıfları beklediğiniz için yararlıdır. İşlecin adresinin yeniden tanımlanması, genellikle derleme hatalarına neden olacak ve bunun "çalışmasını" bekleyen sınıfların uyarlanmamış türünün kullanımını önleyecek şekilde bu gereksinimi bozabilir. `CAdapt`Bu sorunların geçici bir yol sağlar.  
  
 Genellikle, kullanacağınız `CAdapt` depolamak istediğiniz zaman `CComBSTR`, `CComPtr`, `CComQIPtr`, veya `_com_ptr_t` bir kapsayıcı stili sınıfındaki nesneler. C++ Standart Kitaplığı kapsayıcıları öncesi C ++ 11 için standart desteklemek için gerekli en yaygın olarak, bu, ancak C ++ 11 standart kitaplığı kapsayıcıları otomatik olarak aşırı türleriyle çalışma `operator&()`. Standart kitaplığı bu dahili olarak kullanarak erişir [std::addressof](../../standard-library/memory-functions.md#addressof) nesneleri true adreslerini almak için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcomcli.h  
  
##  <a name="cadapt"></a>CAdapt::CAdapt  
 Oluşturucular oluşturulan, uyarlanmış türünde bir nesne kopyalanan veya başka bir bağdaştırıcı nesnesinden kopyalanan varsayılan olarak kullanılacak bağdaştırıcı nesneyi izin verin.  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parametreler  
 `rSrc`  
 Yeni oluşturulan bağdaştırıcısı nesnesine kopyalanacak uyarlanan türünde bir değişken.  
  
 *rSrCA*  
 İçerdiği verileri kopyalanamaz (yeni oluşturulan bağdaştırıcısı nesnesine veya taşınamaz) bir bağdaştırıcı nesne.  
  
##  <a name="m_t"></a>CAdapt::m_T  
 Uyarlanan verileri tutar.  
  
```
T m_T;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu **ortak** veri üyesi erişilebilir doğrudan veya dolaylı olarak ile [işleci const T &](#operator_const_t_amp) ve [işleci T &](#operator_t_amp).  
  
##  <a name="operator_const_t_amp"></a>CAdapt::operator const T&amp;  
 Döndürür bir **const** başvuru [m_T](#m_t) bağdaştırıcısı nesnesini bir nesne türü değilmiş gibi kabul edilmesi izin verme üye `T`.  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **const** başvuru `m_T`.  
  
##  <a name="operator_t_amp"></a>CAdapt::operator T&amp;  
 Bir başvuru döndürür [m_T](#m_t) bağdaştırıcısı nesnesini bir nesne türü değilmiş gibi kabul edilmesi izin verme üye `T`.  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru `m_T`.  
  
##  <a name="operator_lt"></a>CAdapt::operator&lt;  
 Uyarlanmış türünde bir nesneyi karşılaştırır [m_T](#m_t).  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `rSrc`  
 Karşılaştırılacak nesne başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karşılaştırması sonucunu `m_T` ve `rSrc`.  
  
##  <a name="operator_eq"></a>CAdapt::operator =  
 Bağımsız değişken atama işleci atar `rSrc`, veri üyesi için [m_T](#m_t) ve geçerli bağdaştırıcısı nesnesini döndürür.  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parametreler  
 `rSrc`  
 Kopyalanacak uyarlanmış türünde bir nesneye başvuru. 

 `rSrCA`Taşınacak bir nesneye başvuru. 
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli nesneye başvuru.  
  
##  <a name="operator_eq_eq"></a>CAdapt::operator ==  
 Uyarlanmış türünde bir nesneyi karşılaştırır [m_T](#m_t).  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `rSrc`  
 Karşılaştırılacak nesne başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karşılaştırması sonucunu `m_T` ve `rSrc`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
