---
title: CTime sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTime
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec195c7733255487b08f8b48379abe58e305f61
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366555"
---
# <a name="ctime-class"></a>CTime sınıfı
Bir mutlak saatini ve tarihini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTime  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTime::CTime](#ctime)|Yapıları `CTime` çeşitli şekillerde nesneleri.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTime::Format](#format)|Dönüştüren bir `CTime` biçimlendirilmiş bir dize nesnesine — yerel saat dilimini temel alan.|  
|[CTime::FormatGmt](#formatgmt)|Dönüştüren bir `CTime` biçimlendirilmiş bir dize nesnesine — üzerinde UTC'ye göre.|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Depolanan saat bilgisi dönüştürür `CTime` Win32 uyumlu DBTIMESTAMP yapısına nesne.|  
|[CTime::GetAsSystemTime](#getassystemtime)|Depolanan saat bilgisi dönüştürür `CTime` Win32 uyumlu nesnesine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) yapısı.|  
|[CTime::GetCurrentTime](#getcurrenttime)|Oluşturur bir `CTime` geçerli saati (statik üye fonksiyonu) temsil eden nesne.|  
|[CTime::GetDay](#getday)|Günü temsil tarafından döndürür `CTime` nesnesi.|  
|[CTime::GetDayOfWeek](#getdayofweek)|Tarafından temsil edilen haftanın gününü verir `CTime` nesnesi.|  
|[CTime::GetGmtTm](#getgmttm)|Böler bir `CTime` bileşenleri nesnesine — üzerinde UTC'ye göre.|  
|[CTime::GetHour](#gethour)|Tarafından temsil edilen saati döndürür `CTime` nesnesi.|  
|[CTime::GetLocalTm](#getlocaltm)|Böler bir `CTime` bileşenleri nesnesine — yerel saat dilimini temel alan.|  
|[CTime::GetMinute](#getminute)|Tarafından temsil edilen dakikayı döndürür `CTime` nesnesi.|  
|[CTime::GetMonth](#getmonth)|Tarafından temsil edilen ayı verir `CTime` nesnesi.|  
|[CTime::GetSecond](#getsecond)|Tarafından temsil edilen ikinci döndürür `CTime` nesnesi.|  
|[CTime::GetTime](#gettime)|Döndürür bir **__time64_t** değerini verilen `CTime` nesnesi.|  
|[CTime::GetYear](#getyear)|Tarafından temsil edilen yıl döndürür `CTime` nesnesi.|  
|[CTime::Serialize64](#serialize64)|Bir arşiv veri serileştirir.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator + -](#operator_add_-)|Bu işleçlere ekleme ve çıkarma `CTimeSpan` ve `CTime` nesneleri.|  
|[operator +=-=](#operator_add_eq_-_eq)|Bu işleçlere ekleme ve bir `CTimeSpan` nesne için ve bu `CTime` nesnesi.|  
|[işleç =](#operator_eq)|Atama işleci.|  
|[operator ==, <, vb..](#ctime_comparison_operators)|Karşılaştırma işleçleri.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CTime` bir taban sınıfı yok.  
  
 `CTime` değerler Eşgüdümlü Evrensel Saat (UTC) Eşgüdümlü Evrensel Saat (Greenwich saati, GMT) eşdeğerdir temel alır. Bkz: [zaman Yönetimi](../../c-runtime-library/time-management.md) saat dilimi belirleme hakkında bilgi.  
  
 Oluştururken bir `CTime` nesne, ayarlamak `nDST` parametresi Standart Saati yürürlükte ya da göstermek için 0'dan büyük bir değere o gün ışığından yararlanma saati yürürlükte olduğunu göstermek için 0 veya bir değer sıfırdan C çalışma zamanı kitaplığı kodu bilgi sağlamak için e Standart Saati gün ışığından yararlanma saati etkin olup. `tm_isdst` gerekli bir alandır. Ayarlı değil, kendi değeri tanımsız ise ve dönüş değerini [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) tahmin edilemez. Varsa `timeptr` önceki bir çağrı tarafından döndürülen tm yapısı işaret [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), veya [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` alan içerir doğru değeri.  
  
 Bir yardımcı sınıf [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), bir zaman aralığı temsil eder.  
  
 `CTime` Ve `CTimeSpan` sınıfları türetme için tasarlanmamıştır. Hiçbir sanal işlevleri boyutu olduğundan `CTime` ve `CTimeSpan` nesneleri tam olarak 8 bayt durumdadır. Çoğu üye satır içi işlevlerdir.  
  
> [!NOTE]
>  Üst tarih sınırı 31/12/3000'dir. Alt sınır 1/1/1970 12:00:00 GMT.  
  
 Kullanma hakkında daha fazla bilgi için `CTime`, makalelerine bakın [tarih ve saat](../../atl-mfc-shared/date-and-time.md), ve [zaman Yönetimi](../../c-runtime-library/time-management.md) çalışma zamanı kitaplığı başvurusu.  
  
> [!NOTE]
>  `CTime` Yapısı MFC 8.0 MFC 7.1 değiştirilmiş. Seri hale varsa bir `CTime` kullanarak yapısı `operator <<` MFC 8.0 veya sonraki bir sürümünü altında sonuçta elde edilen dosyasını MFC eski sürümleri okunamaz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltime.h  
  
##  <a name="ctime_comparison_operators"></a>  CTime Karşılaştırma işleçleri  
 Karşılaştırma işleçleri.  
  
```  
bool operator==(CTime time) const throw(); 
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `time`  
 `CTime` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işleçlere mutlak iki kez karşılaştırır ve dönüş **true** koşul ise, true, aksi **false**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="ctime"></a>  CTime::CTime  
 Yeni bir `CTime` nesnesi ile belirtilen süre başlatıldı.  
  
```  
CTime() throw(); 
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts,int nDST = -1) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `timeSrc`  
 Gösteren bir `CTime` zaten var. nesne.  
  
 `time`  
 A **__time64_t** zaman değeri, 1 Ocak 1970 UTC saniye sayısıdır. Bu, yerel saat olarak ayarlanacağını unutmayın. Örneğin, New York'taki olan ve oluşturursanız bir `CTime` parametresi 0, geçirerek nesne [CTime::GetMonth](#getmonth) 12 döndürür.  

  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Yeni içine kopyalanacak tarih ve saat değerlerini gösteren `CTime` nesnesi.  
  
 `nDST`  
 Günışığından etkin olup olmadığını gösterir. Üç değerlerden biri olabilir:  
  
- `nDST` 0Standard zaman kümesine etkili olur.  
  
- `nDST` saati etkindir 0Daylight büyük bir değere ayarlayın.  
  
- `nDST` 0The varsayılan değerinden daha düşük bir değere ayarlayın. Standart Saati günışığından etkin olup otomatik olarak hesaplar.  
  
 `wDosDate`, `wDosTime`  
 Bir tarih/saat değerine dönüştürülen ve yeni içine kopyalanan MS-DOS tarih ve saat değerlerini `CTime` nesne.  
  
 `st`  
 A [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us) bir tarih/saat değerine dönüştürülen ve yeni içine kopyalanan yapısı `CTime` nesnesi.  
  
 `ft`  
 A [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us) bir tarih/saat değerine dönüştürülen ve yeni içine kopyalanan yapısı `CTime` nesnesi.  
  
 dbts  
 Geçerli yerel saat içeren bir DBTIMESTAMP yapısı referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Her Oluşturucusu aşağıda belirtilmiştir:  
  
- **CTime();**  Bir başlatılmamış yapıları `CTime` nesnesi. Bu oluşturucu tanımlamanıza olanak verir `CTime` nesne dizileri. Bu tür diziler kullanmadan önce geçerli sürelerine sahip başlatması gerekir.  
  
- **CTime (const CTime &);**  Oluşturan bir `CTime` başka bir nesne `CTime` değeri.  
  
- **CTime (__time64_t);**  Oluşturan bir `CTime` nesnesinin bir **__time64_t** türü. Bu oluşturucu UTC saati bekler ve sonucu sonucu depolamadan önce bir yerel saate dönüştürür.  
  
- **CTime (int, int,...);**  Oluşturan bir `CTime` her bileşeni ile yerel saat bileşenleri nesnesinden kısıtlı aşağıdaki aralıkları:  
  
    |Bileşen|Aralık|  
    |---------------|-----------|  
    |`nYear`|1970-3000|  
    |`nMonth`|1-12|  
    |`nDay`|1-31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     Bu oluşturucu UTC uygun dönüştürme yapar. Microsoft Foundation Class Kitaplığı hata ayıklama sürümü varsa onaylar veya daha zamanı bileşenleri aralık dışında. Bağımsız değişkenler çağırmadan önce doğrulamanız gerekir. Bu oluşturucu yerel saat bekliyor.  
  
- **CTime (WORD, sözcük);**  Oluşturan bir `CTime` belirtilen MS-DOS tarih ve saat değerleri bir nesneden. Bu oluşturucu yerel saat bekliyor.  
  
- **CTime (const SYSTEMTIME &);**  Oluşturan bir `CTime` nesnesinin bir `SYSTEMTIME` yapısı. Bu oluşturucu yerel saat bekliyor.  
  
- **CTime (const FILETIME &);**  Oluşturan bir `CTime` nesnesinin bir `FILETIME` yapısı. Büyük olasılıkla kullanmaz `CTime FILETIME` doğrudan başlatma. Kullanırsanız, bir `CFile` bir dosyayı değiştirmek için nesne `CFile::GetStatus` size için dosya zaman damgasını alır bir `CTime` nesne başlatılmış olan bir `FILETIME` yapısı. Bu oluşturucu UTC üzerinde temel bir saat varsayar ve otomatik olarak sonucu depolamak önce değeri yerel saate dönüştürür.  
  
    > [!NOTE]
    >  Oluşturucu kullanılarak **DBTIMESTAMP** parametresi kullanılabilir yalnızca biçim dahil edildiğinde.  
  
 Daha fazla bilgi için bkz: [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) ve [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Windows SDK'sındaki yapısı. Ayrıca bkz. [MS-DOS tarih ve saat](http://msdn.microsoft.com/library/windows/desktop/ms724503) Windows SDK'sı giriş.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="format"></a>  CTime::Format  
 Tarih saat değeri biçimlendirilmiş bir temsilini oluşturmak için bu üye işlevini çağırın.  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `pszFormat`  
 Bir biçimlendirme dize benzer `printf` biçimlendirme dizesi. Biçimlendirme bir yüzde öncesinde kodları ( `%`) oturum açın, ilgili tarafından değiştirilir `CTime` bileşeni. Biçimlendirme dizesi diğer karakterler döndürülen dize değişmeden kopyalanır. Çalışma zamanı işlevi görmek [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) biçimlendirme kodları listesi için.  
  
 `nFormatID`  
 Bu biçim tanımlayan dize kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) biçimlendirilmiş saati içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bu durumu `CTime` nesnesi null, boş bir dize dönüş değeri değil.  
  
 Bu yöntem biçimlendirmek için tarih-saat değeri, 1 Ocak 1970'ten 31 Aralık 3000 aracılığıyla yarısı çeşitli olmayan bir özel durum döndürürse Evrensel Eşgüdümlü saate (UTC).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="formatgmt"></a>  CTime::FormatGmt  
 Buna karşılık gelen biçimlendirilmiş bir dize oluşturur `CTime` nesnesi.  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `pszFormat`  
 Benzer şekilde bir biçimlendirme dizesini belirtir `printf` biçimlendirme dizesi. Çalışma zamanı işlevi görmek [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Ayrıntılar için.  
  
 `nFormatID`  
 Bu biçim tanımlayan dize kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) biçimlendirilmiş saati içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Saat değeri değil dönüştürülür ve bu nedenle UTC yansıtır.  
  
 Bu yöntem biçimlendirmek için tarih-saat değeri, 1 Ocak 1970'ten 31 Aralık 3000 aracılığıyla yarısı çeşitli olmayan bir özel durum döndürürse Evrensel Eşgüdümlü saate (UTC).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CTime::Format](#format).  
  
##  <a name="getasdbtimestamp"></a>  CTime::GetAsDBTIMESTAMP  
 Depolanan saat bilgisi dönüştürmek için bu üye işlevini çağırın `CTime` Win32 uyumlu DBTIMESTAMP yapısına nesne.  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dbts`  
 Geçerli yerel saat içeren bir DBTIMESTAMP yapısı referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuçta elde edilen zaman başvurulan depolar `dbts` yapısı. **DBTIMESTAMP** bu işlev tarafından başlatılan veri yapısı olacaktır, **kesir** üye sıfır olarak ayarlayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="getassystemtime"></a>  CTime::GetAsSystemTime  
 Depolanan saat bilgisi dönüştürmek için bu üye işlevini çağırın `CTime` Win32 uyumlu nesnesine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) yapısı.  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *timeDest*  
 Bir başvuru bir [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) dönüştürülmüş tarih/saat değeri tutacak yapısı `CTime` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi takdirde false.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetAsSystemTime` Sonuçta elde edilen zaman başvurulan depolar *timeDest* yapısı. `SYSTEMTIME` Bu işlev tarafından başlatılan veri yapısı olacaktır, **wMilliseconds** üye sıfır olarak ayarlayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="getcurrenttime"></a>  CTime::GetCurrentTime  
 Döndürür bir `CTime` geçerli saati temsil eden nesne.  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli sistem tarihi ve saati Eşgüdümlü Evrensel Saat (UTC) döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="getday"></a>  CTime::GetDay  
 Günü temsil tarafından döndürür `CTime` nesnesi.  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 1 ile 31 Aralık içinde yerel saate göre ayın günü döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını `GetLocalTm`, bir iç, statik olarak ayrılan arabellek kullanır. Diğer çağrılar nedeniyle bu arabelleği veri üzerine `CTime` üye işlevleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="getdayofweek"></a>  CTime::GetDayOfWeek  
 Tarafından temsil edilen haftanın gününü verir `CTime` nesnesi.  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerel zamana dayalı haftanın gününü verir; 1 = Pazar, 2 = Pazartesi =, 7 = Cumartesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını `GetLocalTm`, ayrılan arabellek bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleği veri üzerine `CTime` üye işlevleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="getgmttm"></a>  CTime::GetGmtTm  
 Alır bir **yapısı tm** ayrıştırma bu konuda yer alan süreyi içeren `CTime` nesnesi.  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `ptm`  
 Saat veri alacak arabellek noktalarına. Bu işaretçi ise **NULL**, bir özel durum.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir içi doldurulmuş **yapısı tm** içerme dosyası zaman tanımlanan. H. Bkz: [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) yapısı düzeni için.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetGmtTm` UTC biçiminde döndürür.  
  
 `ptm` olamaz `NULL`. Eski davranışı geri dönmek istiyorsanız `ptm` olabilir `NULL` bir iç, statik olarak ayrılan arabellek kullanılması gerektiğini belirtmek için ardından tanımsız `_SECURE_ATL`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="gethour"></a>  CTime::GetHour  
 Tarafından temsil edilen saati döndürür `CTime` nesnesi.  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 0 ile 23 aralığında yerel saate göre saati döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını `GetLocalTm`, ayrılan arabellek bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleği veri üzerine `CTime` üye işlevleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="getlocaltm"></a>  CTime::GetLocalTm  
 Alır bir **yapısı tm** ayrıştırma bu konuda yer alan süreyi içeren `CTime` nesnesi.  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `ptm`  
 Saat veri alacak arabellek noktalarına. Bu işaretçi ise **NULL**, bir özel durum.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir içi doldurulmuş **yapısı tm** içerme dosyası zaman tanımlanan. H. Bkz: [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) yapısı düzeni için.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetLocalTm` yerel saat döndürür.  
  
 `ptm` olamaz `NULL`. Eski davranışı geri dönmek istiyorsanız `ptm` olabilir `NULL` bir iç, statik olarak ayrılan arabellek kullanılması gerektiğini belirtmek için ardından tanımsız `_SECURE_ATL`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="getminute"></a>  CTime::GetMinute  
 Tarafından temsil edilen dakikayı döndürür `CTime` nesnesi.  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 0 ile 59 aralığında yerel saate göre dakikayı döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını `GetLocalTm`, ayrılan arabellek bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleği veri üzerine `CTime` üye işlevleri.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetHour](#gethour).  
  
##  <a name="getmonth"></a>  CTime::GetMonth  
 Tarafından temsil edilen ayı verir `CTime` nesnesi.  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 1 ile 12 arasında aralıktaki yerel saate göre ayı verir (1 Ocak =).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını `GetLocalTm`, ayrılan arabellek bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleği veri üzerine `CTime` üye işlevleri.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetDay](#getday).  
  
##  <a name="getsecond"></a>  CTime::GetSecond  
 Tarafından temsil edilen ikinci döndürür `CTime` nesnesi.  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İkinci döndürür 0 ile 59 aralığında yerel saate göre.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını `GetLocalTm`, ayrılan arabellek bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleği veri üzerine `CTime` üye işlevleri.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetHour](#gethour).  
  
##  <a name="gettime"></a>  CTime::GetTime  
 Döndürür bir **__time64_t** değerini verilen `CTime` nesnesi.  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **GetTime** geçerli saniye sayısını döndürür `CTime` nesne ve 1 Ocak 1970'ten.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="getyear"></a>  CTime::GetYear  
 Tarafından temsil edilen yıl döndürür `CTime` nesnesi.  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ocak aralıktaki yerel saate göre yıl döndürür Ocak 18 2038 (dahil) için 1,1970.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını `GetLocalTm`, ayrılan arabellek bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleği veri üzerine `CTime` üye işlevleri.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetDay](#getday).  
  
##  <a name="operator_eq"></a>  CTime::operator =  
 Atama işleci.  
  
```  
CTime& operator=(__time64_t time) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `time`  
 Yeni tarih/saat değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş `CTime` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aşırı yüklenmiş atama işleci kaynak zaman bu kopyalar `CTime` nesnesi. İç saat depolama alanında bir `CTime` nesnesidir saat dilimini bağımsız. Saat dilimi dönüştürmesi atama sırasında gerekli değildir.  
  
##  <a name="operator_add_-"></a>  CTime::operator +, -  
 Bu işleçlere ekleme ve çıkarma `CTimeSpan` ve `CTime` nesneleri.  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 *TimeSpan*  
 `CTimeSpan` Nesnesinin eklenir veya çıkarılır.  
  
 `time`  
 `CTime` Çıkarılır için nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CTime` veya `CTimeSpan` işlemin sonucunu temsil eden nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `CTime` nesneleri temsil mutlak zaman `CTimeSpan` nesneleri göreli zaman temsil eder. İlk iki işleç ekleme ve çıkarma izin `CTimeSpan` ve ondan nesneleri `CTime` nesneleri. Üçüncü işleci bir çıkarma sayesinde `CTime` elde etmek üzere başka bir nesneden bir `CTimeSpan` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  CTime::operator +=-=  
 Bu işleçlere ekleme ve bir `CTimeSpan` nesne için ve bu `CTime` nesnesi.  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `span`  
 `CTimeSpan` Nesnesinin eklenir veya çıkarılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş `CTime` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleçlere ekleme ve çıkarma izin bir `CTimeSpan` nesne için ve bu `CTime` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="serialize64"></a>  CTime::Serialize64  
  
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
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [_time64 _time32, saat](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)


