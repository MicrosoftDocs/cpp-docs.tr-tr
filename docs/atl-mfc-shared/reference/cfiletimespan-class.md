---
title: "CFileTimeSpan sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
dev_langs: C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da47f0113ec2e36f6df4afa32f6aff84d5ee6dfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan sınıfı
Bu sınıf, göreli bir tarih ve saat değerleri bir dosyayla ilişkili yönetme için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Zaman aralık almak için bu yöntemi çağırın `CFileTimeSpan` nesnesi.|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Zaman aralığını ayarlamak için bu yöntemi çağırın `CFileTimeSpan` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|Çıkarma gerçekleştiren bir `CFileTimeSpan` nesnesi.|  
|[CFileTimeSpan::operator! =](#operator_neq)|İki karşılaştırır `CFileTimeSpan` eşitsizlik nesneleri.|  
|[CFileTimeSpan::operator +](#operator_add)|Toplama gerçekleştiren bir `CFileTimeSpan` nesnesi.|  
|[CFileTimeSpan::operator +=](#operator_add_eq)|Toplama gerçekleştiren bir `CFileTimeSpan` nesne ve geçerli nesneye sonucu atayın.|  
|[CFileTimeSpan::operator&lt;](#operator_lt)|İki karşılaştırır `CFileTimeSpan` küçük olanı belirlemek için nesneleri.|  
|[CFileTimeSpan::operator&lt;=](#operator_lt_eq)|İki karşılaştırır `CFileTimeSpan` eşitlik veya daha düşük belirlemek için nesneleri.|  
|[CFileTimeSpan::operator =](#operator_eq)|Atama işleci.|  
|[CFileTimeSpan::operator-=](#operator_-_eq)|Çıkarma gerçekleştiren bir `CFileTimeSpan` nesne ve geçerli nesneye sonucu atayın.|  
|[CFileTimeSpan::operator ==](#operator_eq_eq)|İki karşılaştırır `CFileTimeSpan` nesneleri eşitlik için.|  
|[CFileTimeSpan::operator&gt;](#operator_gt)|İki karşılaştırır `CFileTimeSpan` büyük belirlemek için nesneleri.|  
|[CFileTimeSpan::operator&gt;=](#operator_gt_eq)|İki karşılaştırır `CFileTimeSpan` eşitlik veya büyük belirlemek için nesneleri.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın sağladığı yöntemlerle göreli nokta yönetmek için ne zaman ilgili işlemleri gerçekleştirirken sık karşılaşılan süresini bir dosyanın oluşturulduğu, en son erişilen veya son değiştirilme tarihi. Bu sınıf yöntemlerini sık ile birlikte kullanılan [CFileTime sınıfı](../../atl-mfc-shared/reference/cfiletime-class.md) nesneleri.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltime.h  
  
##  <a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan  
 Oluşturucu.  
  
```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 Varolan bir `CFileTimeSpan` nesnesi.  
  
 `nSpan`  
 Sürenin milisaniye cinsinden süre.  
  
### <a name="remarks"></a>Açıklamalar  
 `CFileTimeSpan` Nesne var olan kullanılarak oluşturulabilir `CFileTimeSpan` nesne ya da bir 64-bit değeri olarak ifade edilir. Varsayılan Oluşturucu süresi 0 olarak ayarlar.  
  
##  <a name="gettimespan"></a>CFileTimeSpan::GetTimeSpan  
 Zaman aralık almak için bu yöntemi çağırın `CFileTimeSpan` nesnesi.  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zaman aralığını milisaniye cinsinden döndürür.  
  
##  <a name="operator_-"></a>CFileTimeSpan::operator-  
 Çıkarma gerçekleştiren bir **CFileTimeSpan** nesnesi.  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CFileTimeSpan` iki zaman aralıkları arasındaki farkı sonucunu temsil eden nesne.  
  
##  <a name="operator_neq"></a>CFileTimeSpan::operator! =  
 İki karşılaştırır `CFileTimeSpan` eşitsizlik nesneleri.  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 `CFileTimeSpan` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırılan öğesi eşit değilse `CFileTimeSpan` nesne; Aksi halde **false**.  
  
##  <a name="operator_add"></a>CFileTimeSpan::operator +  
 Toplama gerçekleştiren bir `CFileTimeSpan` nesnesi.  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CFileTimeSpan` iki saat toplamını içeren kapsayan nesne.  
  
##  <a name="operator_add_eq"></a>CFileTimeSpan::operator +=  
 Toplama gerçekleştiren bir `CFileTimeSpan` nesne ve geçerli nesneye sonucu atar.  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CFileTimeSpan` iki saat toplamını içeren kapsayan nesne.  
  
##  <a name="operator_lt"></a>CFileTimeSpan::operator&lt;  
 İki karşılaştırır `CFileTimeSpan` küçük olanı belirlemek için nesneleri.  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 `CFileTimeSpan` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne düşükse (diğer bir deyişle, daha kısa bir süre gösterir) ikinciden, aksi takdirde **false**.  
  
##  <a name="operator_lt_eq"></a>CFileTimeSpan::operator&lt;=  
 İki karşılaştırır `CFileTimeSpan` eşitlik veya daha düşük belirlemek için nesneleri.  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 `CFileTimeSpan` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne küçükse (diğer bir deyişle, daha kısa bir süre gösterir) veya ikinci, aksi takdirde eşit **false**.  
  
##  <a name="operator_eq"></a>CFileTimeSpan::operator =  
 Atama işleci.  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CFileTimeSpan` nesnesi.  
  
##  <a name="operator_-_eq"></a>CFileTimeSpan::operator-=  
 Çıkarma gerçekleştiren bir `CFileTimeSpan` nesne ve geçerli nesneye sonucu atar.  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CFileTimeSpan` nesnesi.  
  
##  <a name="operator_eq_eq"></a>CFileTimeSpan::operator ==  
 İki karşılaştırır `CFileTimeSpan` nesneleri eşitlik için.  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 `CFileTimeSpan` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** aksi nesneleri eşitse, **false**.  
  
##  <a name="operator_gt"></a>CFileTimeSpan::operator&gt;  
 İki karşılaştırır `CFileTimeSpan` büyük belirlemek için nesneleri.  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 `CFileTimeSpan` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne büyükse (diğer bir deyişle, daha uzun bir süre gösterir) ikinciden, aksi takdirde **false**.  
  
##  <a name="operator_gt_eq"></a>CFileTimeSpan::operator&gt;=  
 İki karşılaştırır `CFileTimeSpan` eşitlik veya büyük belirlemek için nesneleri.  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 `CFileTimeSpan` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne büyükse (diğer bir deyişle, daha uzun bir süre gösterir) veya ikinci, aksi takdirde eşit **false**.  
  
##  <a name="settimespan"></a>CFileTimeSpan::SetTimeSpan  
 Zaman aralığını ayarlamak için bu yöntemi çağırın `CFileTimeSpan` nesnesi.  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nSpan`  
 Milisaniye cinsinden zaman aralığı için yeni değer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime sınıfı](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)


