---
title: "CTimeSpan sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cedf05bd8f5af198569891b4d6d59610d5098eb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ctimespan-class"></a>CTimeSpan sınıfı
Bir zaman aralığı saniye sayısı olarak dahili olarak depolanan zaman miktarı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|Yapıları `CTimeSpan` çeşitli şekillerde nesneleri.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|Dönüştüren bir `CTimeSpan` içine biçimlendirilmiş bir dize.|  
|[CTimeSpan::GetDays](#getdays)|Bu tam gün sayısını gösteren bir değer döndürür `CTimeSpan`.|  
|[CTimeSpan::GetHours](#gethours)|Geçerli gün (-23 ile 23) saat sayısını temsil eden bir değer döndürür.|  
|[CTimeSpan::GetMinutes](#getminutes)|Geçerli saat (-59 ile 59) dakika sayısını temsil eden bir değer döndürür.|  
|[CTimeSpan::GetSeconds](#getseconds)|Geçerli (-59 ile 59) dakika içinde saniye sayısını temsil eden bir değer döndürür.|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|Değerini döndürür `CTimeSpan` nesnesi.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|Bu tam saat toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Bu tam dakika toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Bu tam saniye toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.|  
|[CTimeSpan::Serialize64](#serialize64)|Bir arşiv veri serileştirir.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator + -](#operator_add_-)|Ekler ve çıkarır `CTimeSpan` nesneleri.|  
|[operator +=-=](#operator_add_eq_-_eq)|Ekler ve çıkarır bir `CTimeSpan` nesne için ve bu `CTimeSpan`.|  
|[operator == < vs.](#ctimespan_comparison_operators)|İki göreli zaman değerlerini karşılaştırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CTimeSpan`bir taban sınıfı yok.  
  
 `CTimeSpan`İşlevler, gün, saat, dakika çeşitli saniyeye ve saniye dönüştürün.  
  
 `CTimeSpan` Nesne depolanır bir **__time64_t** 8 bayt yapısı.  
  
 Bir yardımcı sınıf [CTime](../../atl-mfc-shared/reference/ctime-class.md), mutlak bir zamanı temsil eder.  
  
 `CTime` Ve `CTimeSpan` sınıfları türetme için tasarlanmamıştır. Hiçbir sanal işlevler, her ikisi de boyutu olduğundan `CTime` ve `CTimeSpan` nesneleri tam olarak 8 bayt durumdadır. Çoğu üye satır içi işlevlerdir.  
  
 Kullanma hakkında daha fazla bilgi için `CTimeSpan`, makalelerine bakın [tarih ve saat](../../atl-mfc-shared/date-and-time.md), ve [zaman Yönetimi](../../c-runtime-library/time-management.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltime.h  
  
##  <a name="ctimespan_comparison_operators"></a>CTimeSpan Karşılaştırma işleçleri  
 Karşılaştırma işleçleri.  
  
```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
  
 Karşılaştırma yapılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işleçlere iki göreli saat değerleri karşılaştırın. Döndürmeleri **true** koşul ise, true, aksi **false**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="ctimespan"></a>CTimeSpan::CTimeSpan  
 Yapıları `CTimeSpan` çeşitli şekillerde nesneleri.  
  
```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(  
 LONG lDays,
 int nHours,
 int nMins,
 int nSecs) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *timeSpanSrc*  
 A `CTimeSpan` zaten var. nesne.  
  
 `time`  
 A **__time64_t** saniye sayısı zaman aralığı içinde saat değeri.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Gün, saat, dakika ve saniye, sırasıyla.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucular yeni bir oluşturma `CTimeSpan` nesnesi ile belirtilen göreli zaman başlatıldı. Her Oluşturucusu aşağıda belirtilmiştir:  
  
- **CTimeSpan ();**  Bir başlatılmamış yapıları `CTimeSpan` nesnesi.  
  
- **CTimeSpan (const CTimeSpan &);**  Oluşturan bir `CTimeSpan` başka bir nesne `CTimeSpan` değeri.  
  
- **CTimeSpan (__time64_t);**  Oluşturan bir `CTimeSpan` nesnesinin bir **__time64_t** türü.  
  
- **CTimeSpan (uzun**, **int, int, int);** Oluşturan bir `CTimeSpan` her bileşenin bileşenleriyle nesnesinden kısıtlı aşağıdaki aralıkları:  
  
    |Bileşen|Aralık|  
    |---------------|-----------|  
    |`lDays`|0-25.000 (yaklaşık)|  
    |`nHours`|0-23|  
    |`nMins`|0-59|  
    |`nSecs`|0-59|  
  
 Hata ayıklama sürümü Microsoft Foundation Class Kitaplığı, bir veya daha fazla zaman günlük bileşenlerinin aralık dışında olup olmadığını onaylar unutmayın. Bu bağımsız değişkenler çağrılmadan önce doğrulamak için sorumluluğundadır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>CTimeSpan::Format  
 Buna karşılık gelen biçimlendirilmiş bir dize oluşturur `CTimeSpan`.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `pFormat`, `pszFormat`  
 Bir biçimlendirme dize benzer `printf` biçimlendirme dizesi. Biçimlendirme bir yüzde öncesinde kodları ( `%`) oturum açın, ilgili tarafından değiştirilir `CTimeSpan` bileşeni. Biçimlendirme dizesi diğer karakterler döndürülen dize değişmeden kopyalanır. Değer ve biçimlendirme kodlarını anlamını **biçimi** aşağıda listelenmiştir:  
  
- **%D** toplam gün bu`CTimeSpan`  
  
- **%H** saat geçerli gün içinde  
  
- **%M** geçerli bir saat içinde dakika  
  
- **%S** geçerli dakikada saniye  
  
- **%%**Yüzde işareti  
  
 `nID`  
 Bu biçim tanımlayan dize kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` biçimlendirilmiş saati içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama sürümü kitaplığının biçimlendirme kodları denetler ve kodu yukarıdaki listede değilse, onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>CTimeSpan::GetDays  
 Bu tam gün sayısını gösteren bir değer döndürür `CTimeSpan`.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zaman aralığı içinde tam 24 saatlik gün sayısını döndürür. Bu değer süresi negatifse negatif olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Günışığından neden Not `GetDays` olası şaşırtıcı sonucu dönün. Örneğin, DST olduğunda uygulamada **GetDays** çünkü Nisan bir günde bir saatlik olarak kısaltılır ve bu nedenle tam bir gün olarak sayılmaz Nisan 1 ve 1 Mayıs arasındaki gün sayısını 29, 30, raporlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>CTimeSpan::GetHours  
 Geçerli gün (-23 ile 23) saat sayısını temsil eden bir değer döndürür.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli gün içinde saat sayısını döndürür. -23 23 aracılığıyla aralıktır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>CTimeSpan::GetMinutes  
 Geçerli saat (-59 ile 59) dakika sayısını temsil eden bir değer döndürür.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli saat içinde dakika sayısını döndürür. İle 59-59 aralıktır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetHours](#gethours).  
  
##  <a name="getseconds"></a>CTimeSpan::GetSeconds  
 Geçerli (-59 ile 59) dakika içinde saniye sayısını temsil eden bir değer döndürür.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli dakikada saniye sayısını döndürür. İle 59-59 aralıktır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetHours](#gethours).  
  
##  <a name="gettimespan"></a>CTimeSpan::GetTimeSpan  
 Değerini döndürür `CTimeSpan` nesnesi.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli değeri döndürür `CTimeSpan` nesnesi.  
  
##  <a name="gettotalhours"></a>CTimeSpan::GetTotalHours  
 Bu tam saat toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tam saat toplam sayısını döndürür `CTimeSpan`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes  
 Bu tam dakika toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tam dakika toplam sayısını döndürür `CTimeSpan`.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetTotalHours](#gettotalhours).  
  
##  <a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds  
 Bu tam saniye toplam sayısını temsil eden bir değer döndürür `CTimeSpan`.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu tam saniye toplam sayısını döndürür `CTimeSpan`.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetTotalHours](#gettotalhours).  
  
##  <a name="operator_add_-"></a>CTimeSpan::operator +, -  
 Ekler ve çıkarır `CTimeSpan` nesneleri.  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 Eklenecek değer `CTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CTimeSpan` işlemin sonucunu temsil eden nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu iki işleç ekleme ve çıkarma izin `CTimeSpan` nesneleri için ve birbirlerinden.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>CTimeSpan::operator +=-=  
 Ekler ve çıkarır bir `CTimeSpan` nesne için ve bu `CTimeSpan`.  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 Eklenecek değer `CTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş `CTimeSpan` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleçlere ekleme ve çıkarma izin bir `CTimeSpan` nesne için ve bu `CTimeSpan`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>CTimeSpan::Serialize64  
  
> [!NOTE]
>  Bu yöntem yalnızca MFC projelerinde kullanılabilir.  
  
 Üye değişkeni için veya bir arşiv ilişkilendirilmiş verileri serileştirir.  
  
```
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 `ar`  
 `CArchive` Güncelleştirmek istediğiniz nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş `CArchive` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [damgasını, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [_time64 _time32, saat](../../c-runtime-library/reference/time-time32-time64.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)


