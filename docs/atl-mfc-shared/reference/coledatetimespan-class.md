---
title: "COleDateTimeSpan sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
dev_langs: C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 173ae35f49379bcccf552a105b5615378e7a42cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan sınıfı
Göreli zaman, bir zaman aralığı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class COleDateTimeSpan
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Oluşturan bir `COleDateTimeSpan` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](#format)|Biçimlendirilmiş dize gösterimini oluşturur bir `COleDateTimeSpan` nesnesi.|  
|[COleDateTimeSpan::GetDays](#getdays)|Bu aralık gün kısmını döndürür `COleDateTimeSpan` nesne temsil eder.|  
|[COleDateTimeSpan::GetHours](#gethours)|Bu aralık saat bölümünü döndürür `COleDateTimeSpan` nesne temsil eder.|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|Bu aralık dakika kısmını döndürür `COleDateTimeSpan` nesne temsil eder.|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|Bu aralık ikinci bölümünü döndürür `COleDateTimeSpan` nesne temsil eder.|  
|[COleDateTimeSpan::GetStatus](#getstatus)|Bu durum (geçerlilik) alır `COleDateTimeSpan` nesnesi.|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Bu gün sayısını döndürür `COleDateTimeSpan` nesne temsil eder.|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Saat sayısı bu döndürür `COleDateTimeSpan` nesne temsil eder.|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Bu dakika sayısını döndürür `COleDateTimeSpan` nesne temsil eder.|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Bu saniye sayısını döndürür `COleDateTimeSpan` nesne temsil eder.|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Bu değeri ayarlar `COleDateTimeSpan` nesnesi.|  
|[COleDateTimeSpan::SetStatus](#setstatus)|Durumunu (geçerlilik) Bu ayarlar `COleDateTimeSpan` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|||  
|-|-|  
|[operator +, -](#operator_add_-)|Ekleme, çıkarın ve oturum değiştirme `COleDateTimeSpan` değerleri.|  
|[operator +=-=](#operator_add_eq_-_eq)|Ekleme ve bir `COleDateTimeSpan` bu değerden `COleDateTimeSpan` değeri.|  
|[işleç =](#operator_eq)|Kopya bir `COleDateTimeSpan` değeri.|  
|[operator ==, <, < =](#coledatetimespan_relational_operators)|İki karşılaştırmak `COleDateTimeSpan` değerleri.|  
|[double işleci](#operator_double)|Bu dönüştürür `COleDateTimeSpan` değeri bir **çift**.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|Arka plandaki içeren **çift** bu `COleDateTimeSpan` nesnesi.|  
|[COleDateTimeSpan::m_status](#m_status)|Bu durumu içeren `COleDateTimeSpan` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleDateTimeSpan`bir taban sınıfı yok.  
  
 A `COleDateTimeSpan` zaman gün içinde tutar.  
  
 `COleDateTimeSpan`kendi yardımcı sınıf ile kullanılan [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime`yalıtan **tarih** OLE Otomasyon veri türü. `COleDateTime`mutlak saat değerlerini temsil eder. Tüm `COleDateTime` hesaplamaları içeren `COleDateTimeSpan` değerleri. Bu sınıflar arasındaki ilişki arasında bir paraleldir [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Daha fazla bilgi için `COleDateTime` ve `COleDateTimeSpan` sınıfları, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ATLComTime.h  
  
##  <a name="coledatetimespan_relational_operators"></a>COleDateTimeSpan ilişkisel işleçler  
 Karşılaştırma işleçleri.  
  
```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *dateSpan*  
 `COleDateTimeSpan` Karşılaştırmak için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işleçlere iki tarih/zaman aralığı değerleri karşılaştırır ve dönüş **true** koşul ise, true, aksi **false**.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Her iki işlenen geçersiz ise bir ATLASSERT meydana gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="coledatetimespan"></a>COleDateTimeSpan::COleDateTimeSpan  
 Oluşturan bir `COleDateTimeSpan` nesnesi.  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dblSpanSrc`  
 Yeni içine kopyalanacak gün sayısını `COleDateTimeSpan` nesnesi.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Yeni içine kopyalanacak gün ve saat değerleri gösterir `COleDateTimeSpan` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm bu oluşturucular Yeni Oluştur `COleDateTimeSpan` nesneleri belirtilen değerle başlatılır. Bu oluşturucu her kısa bir açıklamasını aşağıdaki gibidir:  
  
- **COleDateTimeSpan ()** oluşturan bir `COleDateTimeSpan` nesne 0 olarak başlatılır.  
  
- **COleDateTimeSpan (** `dblSpanSrc` **)** oluşturan bir `COleDateTimeSpan` bir kayan nokta değer nesnesi.  
  
- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)**  Oluşturan bir `COleDateTimeSpan` nesne belirtilen sayısal değerleri başlatıldı.  
  
 Yeni durumunu `COleDateTimeSpan` nesnesi için geçerli ayarlanır.  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="format"></a>COleDateTimeSpan::Format  
 Biçimlendirilmiş dize gösterimini oluşturur bir `COleDateTimeSpan` nesnesi.  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `pFormat`  
 Bir biçimlendirme dize benzer `printf` biçimlendirme dizesi. Biçimlendirme bir yüzde öncesinde kodları ( `%`) oturum açın, ilgili tarafından değiştirilir `COleDateTimeSpan` bileşeni. Biçimlendirme dizesi diğer karakterler döndürülen dize değişmeden kopyalanır. Değer ve biçimlendirme kodlarını anlamını **biçimi** aşağıda listelenmiştir:  
  
- **%H** saat geçerli gün içinde  
  
- **%M** geçerli bir saat içinde dakika  
  
- **%S** geçerli dakikada saniye  
  
- **%%**Yüzde işareti  
  
 Yukarıda listelenen dört biçim kodları biçimi kabul edecek yalnızca kodlarıdır.  
  
-  
  
 `nID`  
 Denetim Biçimlendir dize kaynak kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` biçimlendirilen tarih/zaman aralığı değeri içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Arama zaman aralığı değeri biçimlendirilmiş bir temsilini oluşturmak için bu işlevleri. Varsa bu durumu `COleDateTimeSpan` nesnesi null, boş bir dize dönüş değeri değil. Geçersiz durumundaysa, dönüş dizesi dize kaynak tarafından belirtilen **IDS_INVALID_DATETIMESPAN**.  
  
 Bu işlev için formları kısa bir açıklamasını aşağıdaki gibidir:  
  
 **Biçim (** `pFormat` **)**  
 Bu form bir yüzde işaretiyle (%) öncesinde özel biçimlendirme kodlar içerir biçim dizesini kullanarak değeri olarak biçimleri `printf`. Biçimlendirme dizesi işlevi için parametre olarak geçirilir.  
  
 **Biçim (** `nID` **)**  
 Bu form bir yüzde işaretiyle (%) öncesinde özel biçimlendirme kodlar içerir biçim dizesini kullanarak değeri olarak biçimleri `printf`. Biçimlendirme dizesi bir kaynaktır. Bu dize kaynağı kimliği, parametre olarak geçirilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="getdays"></a>COleDateTimeSpan::GetDays  
 Bu tarih/zaman aralığı değeri gün kısmını alır.  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tarih/zaman aralığı değerinin gün bölümü.  
  
### <a name="remarks"></a>Açıklamalar  
 Yaklaşık - değerleri bu işlevi aralığından dönüş 3,615,000 ve 3,615,000.  
  
 Değerini sorgulamak diğer işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="gethours"></a>COleDateTimeSpan::GetHours  
 Bu tarih/zaman aralığı değerinin saat bölümünü alır.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tarih/zaman aralığı değerinin saat bölümü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev aralığı - 23 ve 23 arasında dönüş değerleri.  
  
 Değerini sorgulamak diğer işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="getminutes"></a>COleDateTimeSpan::GetMinutes  
 Bu tarih/zaman aralığı değeri dakika kısmını alır.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tarih/zaman aralığı değeri dakika kısmı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev aralığı - 59 ile 59 arasında dönüş değerleri.  
  
 Değerini sorgulamak diğer işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="getseconds"></a>COleDateTimeSpan::GetSeconds  
 Bu tarih/zaman aralığı değeri ikinci kısmını alır.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tarih/zaman aralığı değeri saniye kısmı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev aralığı - 59 ile 59 arasında dönüş değerleri.  
  
 Değerini sorgulamak diğer işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="getstatus"></a>COleDateTimeSpan::GetStatus  
 Bu durum (geçerlilik) alır `COleDateTimeSpan` nesnesi.  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu durumu `COleDateTimeSpan` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri tarafından tanımlanan **DateTimeSpanStatus** numaralandırılmış içinde tanımlanan türü `COleDateTimeSpan` sınıfı.  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
};  
```  
  
 Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:  
  
- **COleDateTimeSpan::valid** belirtir bu `COleDateTimeSpan` nesne geçerlidir.  
  
- **COleDateTimeSpan::invalid** belirtir bu `COleDateTimeSpan` nesnesi geçersiz; diğer bir deyişle, değeri yanlış olabilir.  
  
- **COleDateTimeSpan::null** belirtir bu `COleDateTimeSpan` nesnesi null, diğer bir deyişle, bu nesne için herhangi bir değer belirtildi. (Bu bir "herhangi bir değer aksine C++ kullanılmasının" veritabanı algılama "null" **NULL**.)  
  
 Durumunu bir `COleDateTimeSpan` nesnesi aşağıdaki durumlarda geçersiz:  
  
-   Bu nesne bir taşması veya underflow aritmetik atama işlemi sırasında yani, karşılaştı, `+=` veya `-=`.  
  
-   Bu nesne için geçersiz bir değer atanmışsa.  
  
-   Kullanarak geçersiz bu nesnenin durumu açıkça ayarlanmış olmadığını `SetStatus`.  
  
 Durum için geçersiz ayarlama işlemleri hakkında daha fazla bilgi için bkz: [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) ve [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="gettotaldays"></a>COleDateTimeSpan::GetTotalDays  
 Gün olarak ifade bu tarih/zaman aralığı değeri alır.  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gün olarak ifade bu tarih/zaman aralığı değeri. Bu işlev bir double döndürülecek örneklenmiş olsa da, her zaman bir tamsayı değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev aralığında yaklaşık - 3.65e6 ve 3.65e6 dönüş değerleri.  
  
 Değerini sorgulamak diğer işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="gettotalhours"></a>COleDateTimeSpan::GetTotalHours  
 Saat cinsinden ifade edilen bu tarih/zaman aralığı değeri alır.  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saat cinsinden ifade edilen bu tarih/zaman aralığı değeri. Bu işlev bir double döndürülecek örneklenmiş olsa da, her zaman bir tamsayı değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev aralığında yaklaşık - 8.77e7 ve 8.77e7 dönüş değerleri.  
  
 Değerini sorgulamak diğer işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetTotalDays](#gettotaldays).  
  
##  <a name="gettotalminutes"></a>COleDateTimeSpan::GetTotalMinutes  
 Dakika cinsinden ifade edilen bu tarih/zaman aralığı değeri alır.  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tarih/zaman aralığı dakika cinsinden ifade edilen değer. Bu işlev bir double döndürülecek örneklenmiş olsa da, her zaman bir tamsayı değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev aralığında yaklaşık - 5.26e9 ve 5.26e9 dönüş değerleri.  
  
 Değerini sorgulamak diğer işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetTotalDays](#gettotaldays).  
  
##  <a name="gettotalseconds"></a>COleDateTimeSpan::GetTotalSeconds  
 Saniye cinsinden ifade edilen bu tarih/zaman aralığı değeri alır.  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tarih/zaman aralığı saniye cinsinden ifade edilen değer. Bu işlev bir double döndürülecek örneklenmiş olsa da, her zaman bir tamsayı değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi dönüş değerleri arasındaki aralığı yaklaşık - 3.16e11 için 3.16e11.  
  
 Değerini sorgulamak diğer işlevleri için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetTotalDays](#gettotaldays).  
  
##  <a name="m_span"></a>COleDateTimeSpan::m_span  
 Arka plandaki **çift** bu değeri `COleDateTime` nesnesi.  
  
```
double m_span;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer, tarih/zaman aralığı gün cinsinden ifade eder.  
  
> [!CAUTION]
>  Değer değiştirme **çift** veri üyesi, bu değeri değiştirir `COleDateTimeSpan` nesnesi. Bu durumu değiştirmez `COleDateTimeSpan` nesnesi.  
  
##  <a name="m_status"></a>COleDateTimeSpan::m_status  
 Bu veri üyesi türü numaralandırılmış türüdür **DateTimeSpanStatus**, içinde tanımlanan `COleDateTimeSpan` sınıfı.  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:  
  
- **COleDateTimeSpan::valid** belirtir bu `COleDateTimeSpan` nesne geçerlidir.  
  
- **COleDateTimeSpan::invalid** belirtir bu `COleDateTimeSpan` nesnesi geçersiz; diğer bir deyişle, değeri yanlış olabilir.  
  
- **COleDateTimeSpan::null** belirtir bu `COleDateTimeSpan` nesnesi null, diğer bir deyişle, bu nesne için herhangi bir değer belirtildi. (Bu bir "herhangi bir değer aksine C++ kullanılmasının" veritabanı algılama "null" **NULL**.)  
  
 Durumunu bir `COleDateTimeSpan` nesnesi aşağıdaki durumlarda geçersiz:  
  
-   Bu nesne bir taşması veya underflow aritmetik atama işlemi sırasında yani, karşılaştı, `+=` veya `-=`.  
  
-   Bu nesne için geçersiz bir değer atanmışsa.  
  
-   Kullanarak geçersiz bu nesnenin durumu açıkça ayarlanmış olmadığını [SetStatus](#setstatus).  
  
 Durum için geçersiz ayarlama işlemleri hakkında daha fazla bilgi için bkz: [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) ve [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
> [!CAUTION]
>  Gelişmiş programlama durumlar için bu veri üyesidir. Satır içi üye işlevleri kullanması gereken [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bkz: `SetStatus` açıkça bu veri üyesi ayarlama ile ilgili daha fazla uyarılar için.  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTimeSpan` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_eq"></a>COleDateTimeSpan::operator =  
 Kopya bir `COleDateTimeSpan` değeri.  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aşırı yüklenmiş atama işleci kaynak tarih/zaman aralığı değeri bu kopyalar `COleDateTimeSpan` nesnesi.  
  
##  <a name="operator_add_-"></a>COleDateTimeSpan::operator +, -  
 Ekleme, çıkarın ve oturum değiştirme `COleDateTimeSpan` değerleri.  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İlk iki işleç ekleyin ve tarih/saat-aralık değerleri çıkarma olanak tanır. Üçüncü bir tarih/zaman aralığı değerinin oturum değiştirmenize olanak verir.  
  
 İşlenen birini ise null, elde edilen durumunu `COleDateTimeSpan` değeri NULL'dur.  
  
 İşlenen birini geçersiz ve diğer null değilse, elde edilen durumunu `COleDateTimeSpan` değeri geçersiz.  
  
 Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz: [m_status](#m_status) üye değişkeni.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::operator +=-=  
 Ekleme ve bir `COleDateTimeSpan` bu değerden `COleDateTimeSpan` değeri.  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleçlere ekleme ve bu tarih/saat-aralık değerleri sağlayan `COleDateTimeSpan` nesnesi. İşlenen birini ise null, elde edilen durumunu `COleDateTimeSpan` değeri NULL'dur.  
  
 İşlenen birini geçersiz ve diğer null değilse, elde edilen durumunu `COleDateTimeSpan` değeri geçersiz.  
  
 Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz: [m_status](#m_status) üye değişkeni.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="operator_double"></a>COleDateTimeSpan::operator çift  
 Bu dönüştürür `COleDateTimeSpan` değeri bir **çift**.  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç bu değerini döndürür `COleDateTimeSpan` değeri olarak bir kayan nokta gün sayısı.  
  
##  <a name="setdatetimespan"></a>COleDateTimeSpan::SetDateTimeSpan  
 Bu tarih/zaman aralığı değerini ayarlar.  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Bu kopyalanacak tarih aralığı ve zaman aralığını değerler `COleDateTimeSpan` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Değerini sorgulamak işlevler için bir `COleDateTimeSpan` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="setstatus"></a>COleDateTimeSpan::SetStatus  
 Durumunu (geçerlilik) Bu ayarlar `COleDateTimeSpan` nesnesi.  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *durumu*  
 Bu yeni durum değeri `COleDateTimeSpan` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 *Durum* tarafından tanımlanan parametre değeri **DateTimeSpanStatus** numaralandırılmış içinde tanımlanan türü `COleDateTimeSpan` sınıfı.  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:  
  
- **COleDateTimeSpan::valid** belirtir bu `COleDateTimeSpan` nesne geçerlidir.  
  
- **COleDateTimeSpan::invalid** belirtir bu `COleDateTimeSpan` nesnesi geçersiz; diğer bir deyişle, değeri yanlış olabilir.  
  
- **COleDateTimeSpan::null** belirtir bu `COleDateTimeSpan` nesnesi null, diğer bir deyişle, bu nesne için herhangi bir değer belirtildi. (Bu bir "herhangi bir değer aksine C++ kullanılmasının" veritabanı algılama "null" **NULL**.)  
  
    > [!CAUTION]
    >  Bu işlev, Gelişmiş programlama durumlar için kullanılır. Bu işlev, bu nesne verileri değiştirmez. Durum ayarlamak için çoğunlukla kullanılacak `null` veya **geçersiz**. Unutmayın atama işleci ( [işleç =](#eq)) ve [SetDateTimeSpan](#setdatetimespan) kaynak değerler dayalı bir nesnenin durumu ayarlayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleDateTime sınıfı](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime sınıfı](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)


