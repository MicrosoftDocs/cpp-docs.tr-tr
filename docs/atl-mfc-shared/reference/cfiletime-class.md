---
title: "CFileTime sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
dev_langs: C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 23727110219af5ff7a38036b4607e9636d5c9c3f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cfiletime-class"></a>CFileTime sınıfı
Bu sınıf bir dosyayla ilişkili tarih ve saat değerleri yönetme için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CFileTime :  public FILETIME
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileTime::CFileTime](#cfiletime)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](#getcurrenttime)|Almak için bu statik işlev çağrısı bir `CFileTime` geçerli sistem tarihi ve saati temsil eden nesne.|  
|[CFileTime::GetTime](#gettime)|Saati almak için bu yöntemi çağırın `CFileTime` nesnesi.|  
|[CFileTime::LocalToUTC](#localtoutc)|Yerel dosya saati Eşgüdümlü Evrensel Saat (UTC) üzerinde dayalı bir dosyanın dosya saati dönüştürmek için bu yöntemi çağırın.|  
|[CFileTime::SetTime](#settime)|Tarih ve saat tarafından depolanan ayarlamak için bu yöntemi çağırın `CFileTime` nesnesi.|  
|[CFileTime::UTCToLocal](#utctolocal)|Üzerinde Eşgüdümlü Evrensel Saat (UTC) yerel dosya zamana bağlı süre dönüştürmek için bu yöntemi çağırın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileTime::operator-](#operator_-)|Bu işleç çıkarma yapmak için kullanılan bir `CFileTime` veya `CFileTimeSpan` nesnesi.|  
|[CFileTime::operator! =](#operator_neq)|Bu işleç iki karşılaştırır `CFileTime` eşitsizlik nesneleri.|  
|[CFileTime::operator +](#operator_add)|Bu işleç toplama gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesnesi.|  
|[CFileTime::operator +=](#operator_add_eq)|Bu işleç toplama gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesne ve geçerli nesneye sonucu atayın.|  
|[CFileTime::operator&lt;](#operator_lt)|Bu işleç iki karşılaştırır `CFileTime` küçük olanı belirlemek için nesneleri.|  
|[CFileTime::operator&lt;=](#operator_lt_eq)|Bu işleç iki karşılaştırır `CFileTime` eşitlik veya daha düşük belirlemek için nesneleri.|  
|[CFileTime::operator =](#operator_eq)|Atama işleci.|  
|[CFileTime::operator-=](#operator_-_eq)|Bu işleç çıkarma yapmak için kullanılan bir `CFileTimeSpan` nesne ve geçerli nesneye sonucu atayın.|  
|[CFileTime::operator ==](#operator_eq_eq)|Bu işleç iki karşılaştırır `CFileTime` nesneleri eşitlik için.|  
|[CFileTime::operator&gt;](#operator_gt)|Bu işleç iki karşılaştırır `CFileTime` büyük belirlemek için nesneleri.|  
|[CFileTime::operator&gt;=](#operator_gt_eq)|Bu işleç iki karşılaştırır `CFileTime` eşitlik veya büyük belirlemek için nesneleri.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileTime::Day](#day)|Bir gün yapmak 100 nanosaniyelik aralık sayısını depolamak statik veri üyesi.|  
|[CFileTime::Hour](#hour)|Statik veri üyesi 100 nanosaniyelik aralık sayısını depolanması, bir saat olun.|  
|[CFileTime::Millisecond](#millisecond)|Statik veri üyesi 100 nanosaniyelik aralık sayısını depolanması, bir milisaniyelik olun.|  
|[CFileTime::Minute](#minute)|Bir dakika yapmak 100 nanosaniyelik aralık sayısını depolamak statik veri üyesi.|  
|[CFileTime::Second](#second)|Statik veri üyesi 100 nanosaniyelik aralık sayısını depolanması, bir saniye olun.|  
|[CFileTime::Week](#week)|Statik veri üyesi 100 nanosaniyelik aralık sayısını depolanması, bir haftanın olun.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf oluşturma, erişim ve dosyaların değiştirilmesini ilişkili tarih ve saat değerleri yönetme için yöntemleri sağlar. Yöntem ve bu sınıfın verilerin sık ile birlikte kullanılan `CFileTimeSpan` göreli saat değerleri ile ilgili nesneleri.  
  
 Tarih ve saat değeri, 1 Ocak 1601'den bu yana 100 nano saniyelik aralıkların sayısını temsil eden bir 64-bit değeri olarak depolanır. Bu Eşgüdümlü Evrensel Saat (UTC) biçimidir.  
  
 Aşağıdaki statik const üye değişkenleri hesaplamalar basitleştirmek için sağlanır:  
  
|Üye değişkeni|100 nano saniyelik aralıkların sayısı|  
|---------------------|-----------------------------------------|  
|Milisaniye|10,000|  
|Saniye|Mili saniye * 1.000|  
|Dakika|İkinci * 60|  
|Saat|Dakika * 60|  
|Gün|Saat * 24|  
|Hafta|Gün * 7|  
  
 **Not** tüm dosya sistemleri oluşturma kaydedebilir ve son erişim zamanı ve tüm dosya sistemleri kaydı bunları aynı şekilde. Windows NT FAT dosya sistemi üzerinde örnek oluşturmak için 10 milisaniye çözünürlüğü süresi olan, yazma süresi 2 saniyelik bir çözüm, ve erişim süresi 1 gün (erişim tarihi) çözünürlüğü sahiptir. NTFS erişim süresi 1 saatlik bir çözünürlüğü vardır. Ayrıca, FAT disk saatlerinin yerel saatle kaydeder, ancak NTFS disk saatlerinin UTC biçiminde kaydeder. Daha fazla bilgi için bkz: [dosya sürelerinin](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `FILETIME`  
  
 `CFileTime`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltime.h  
  
##  <a name="cfiletime"></a>CFileTime::CFileTime  
 Oluşturucu.  
  
```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ft`  
 A [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) yapısı.  
  
 `nTime`  
 Tarih ve saat bir 64-bit değeri olarak ifade edilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `CFileTime` Nesne bir varolan tarih ve saat kullanılarak oluşturulabilir bir `FILETIME` yapılandırdığınızı ya da bir 64-bit değerinde (yerel veya Eşgüdümlü Evrensel Saat (UTC) saat biçimleri) olarak ifade edilir. Varsayılan Oluşturucu zaman 0 olarak ayarlar.  
  
##  <a name="day"></a>CFileTime::Day  
 Bir gün yapmak 100 nanosaniyelik aralık sayısını depolamak statik veri üyesi.  
  
```
static const ULONGLONG Day = Hour* 24;
```  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFileTime::Millisecond](#millisecond).  
  
##  <a name="getcurrenttime"></a>CFileTime::GetCurrentTime  
 Almak için bu statik işlev çağrısı bir `CFileTime` geçerli sistem tarihi ve saati temsil eden nesne.  
  
```
static CFileTime GetCurrentTime() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli sistem tarihi ve saati Eşgüdümlü Evrensel Saat (UTC) biçiminde döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]  
  
##  <a name="gettime"></a>CFileTime::GetTime  
 Saati almak için bu yöntemi çağırın `CFileTime` nesnesi.  
  
```
ULONGLONG GetTime() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarih ve yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde olabilir 64 bitlik bir sayı olarak saati döndürür.  
  
##  <a name="hour"></a>CFileTime::Hour  
 Statik veri üyesi 100 nanosaniyelik aralık sayısını depolanması, bir saat olun.  
  
```
static const ULONGLONG Hour = Minute* 60;
```  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFileTime::Millisecond](#millisecond).  
  
##  <a name="localtoutc"></a>CFileTime::LocalToUTC  
 Yerel dosya saati Eşgüdümlü Evrensel Saat (UTC) üzerinde dayalı bir dosyanın dosya saati dönüştürmek için bu yöntemi çağırın.  
  
```
CFileTime LocalToUTC() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CFileTime` saati UTC biçiminde içeren nesne.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFileTime::UTCToLocal](#utctolocal).  
  
##  <a name="millisecond"></a>CFileTime::Millisecond  
 Statik veri üyesi 100 nanosaniyelik aralık sayısını depolanması, bir milisaniyelik olun.  
  
```
static const ULONGLONG Millisecond = 10000;
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]  
  
##  <a name="minute"></a>CFileTime::Minute  
 Bir dakika yapmak 100 nanosaniyelik aralık sayısını depolamak statik veri üyesi.  
  
```
static const ULONGLONG Minute = Second* 60;
```  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFileTime::Millisecond](#millisecond).  
  
##  <a name="operator_-"></a>CFileTime::operator-  
 Bu işleç çıkarma yapmak için kullanılan bir `CFileTime` veya `CFileTimeSpan` nesnesi.  
  
```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` nesnesi.  
  
 `ft`  
 A `CFileTime` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CFileTime` nesnesi veya bir `CFileTimeSpan` iki nesne arasındaki zaman farkı sonucunu temsil eden nesne.  
  
##  <a name="operator_neq"></a>CFileTime::operator! =  
 Bu işleç iki karşılaştırır `CFileTime` eşitsizlik nesneleri.  
  
```
bool operator!=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ft`  
 `CFileTime` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırılan öğesi eşit değilse `CFileTime` nesnesi, aksi takdirde **false**.  
  
##  <a name="operator_add"></a>CFileTime::operator +  
 Bu işleç toplama gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesnesi.  
  
```
CFileTime operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CFileTime` özgün saati artı göreli zaman sonucunu temsil eden nesne.  
  
##  <a name="operator_add_eq"></a>CFileTime::operator +=  
 Bu işleç toplama gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesne ve geçerli nesneye sonucu atayın.  
  
```
CFileTime& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CFileTime` özgün saati artı göreli zaman sonucunu temsil eden nesne.  
  
##  <a name="operator_lt"></a>CFileTime::operator&lt;  
 Bu işleç iki karşılaştırır `CFileTime` küçük olanı belirlemek için nesneleri.  
  
```
bool operator<(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ft`  
 `CFileTime` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne (önceki zaman içinde) ikinci küçükse **false** Aksi takdirde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]  
  
##  <a name="operator_lt_eq"></a>CFileTime::operator&lt;=  
 Bu işleç iki karşılaştırır `CFileTime` eşitlik veya daha düşük belirlemek için nesneleri.  
  
```
bool operator<=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ft`  
 `CFileTime` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne ikinci eşit veya değerinden (zaman içinde önceki) Aksi durumda ise **false**.  
  
##  <a name="operator_eq"></a>CFileTime::operator =  
 Atama işleci.  
  
```
CFileTime& operator=(const FILETIME& ft) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ft`  
 A `CFileTime` yeni saat ve tarihi içeren bir nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CFileTime` nesnesi.  
  
##  <a name="operator_-_eq"></a>CFileTime::operator-=  
 Bu işleç çıkarma yapmak için kullanılan bir `CFileTimeSpan` nesne ve geçerli nesneye sonucu atayın.  
  
```
CFileTime& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 A `CFileTimeSpan` çıkarmak için göreli zaman içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CFileTime` nesnesi.  
  
##  <a name="operator_eq_eq"></a>CFileTime::operator ==  
 Bu işleç iki karşılaştırır `CFileTime` nesneleri eşitlik için.  
  
```
bool operator==(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ft`  
 `CFileTime` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** aksi nesneleri eşitse, **false**.  
  
##  <a name="operator_gt"></a>CFileTime::operator&gt;  
 Bu işleç iki karşılaştırır `CFileTime` büyük belirlemek için nesneleri.  
  
```
bool operator>(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ft`  
 `CFileTime` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne (zaman içinde daha sonra) daha büyük olup olmadığını ikinciden, aksi takdirde **false**.  
  
##  <a name="operator_gt_eq"></a>CFileTime::operator&gt;=  
 Bu işleç iki karşılaştırır `CFileTime` eşitlik veya büyük belirlemek için nesneleri.  
  
```
bool operator>=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ft`  
 `CFileTime` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne (ilerleyen bölümlerinde saati) büyük veya ona eşit ikinci, aksi takdirde ise **false**.  
  
##  <a name="second"></a>CFileTime::Second  
 Bir gün yapmak 100 nanosaniyelik aralık sayısını depolamak statik veri üyesi.  
  
```
static const ULONGLONG Second = Millisecond* 1000;
```  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFileTime::Millisecond](#millisecond).  
  
##  <a name="settime"></a>CFileTime::SetTime  
 Tarih ve saat tarafından depolanan ayarlamak için bu yöntemi çağırın `CFileTime` nesnesi.  
  
```
void SetTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nTime`  
 Tarih ve yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde saati temsil eden 64-bit değeri.  
  
##  <a name="utctolocal"></a>CFileTime::UTCToLocal  
 Üzerinde Eşgüdümlü Evrensel Saat (UTC) yerel dosya zamana bağlı süre dönüştürmek için bu yöntemi çağırın.  
  
```
CFileTime UTCToLocal() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CFileTime` yerel dosya saat biçiminde saati içeren bir nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]  
  
##  <a name="week"></a>CFileTime::Week  
 Statik veri üyesi 100 nanosaniyelik aralık sayısını depolanması, bir haftanın olun.  
  
```
static const ULONGLONG Week = Day* 7;
```  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFileTime::Millisecond](#millisecond).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan sınıfı](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)


