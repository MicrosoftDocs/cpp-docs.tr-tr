---
title: "COleDateTime sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
dev_langs:
- C++
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dbe0e831a644dfc09c6b4afb3c54f23b220850d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coledatetime-class"></a>COleDateTime sınıfı
Yalıtan `DATE` OLE Otomasyon kullanılan veri türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class COleDateTime
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|Oluşturan bir `COleDateTime` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDateTime::Format](#format)|Biçimlendirilmiş dize gösterimini oluşturur bir `COleDateTime` nesnesi.|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Zaman içinde elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir **DBTIMESTAMP** veri yapısı.|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Zaman içinde elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) veri yapısı.|  
|[COleDateTime::GetAsUDATE](#getasudate)|Zaman içinde elde etmek için bu yöntemi çağırın `COleDateTime` olarak bir **UDATE** veri yapısı.|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Oluşturur bir `COleDateTime` geçerli saati (statik üye fonksiyonu) temsil eden nesne.|  
|[COleDateTime::GetDay](#getday)|Bu günlük döndürür `COleDateTime` nesnesi (1-31) temsil eder.|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Bu haftanın gününü verir `COleDateTime` nesne (Pazar = 1) temsil eder.|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|Bu yılın gününü verir `COleDateTime` nesne (Oca 1 = 1) temsil eder.|  
|[COleDateTime::GetHour](#gethour)|Bu saati döndürür `COleDateTime` nesne temsil eder (0 - 23).|  
|[COleDateTime::GetMinute](#getminute)|Bu dakikayı döndürür `COleDateTime` nesne temsil eder (0 - 59).|  
|[COleDateTime::GetMonth](#getmonth)|Bu ayın döndürür `COleDateTime` nesnesi (1-12) temsil eder.|  
|[COleDateTime::GetSecond](#getsecond)|Bu ikinci döndürür `COleDateTime` nesne temsil eder (0 - 59).|  
|[COleDateTime::GetStatus](#getstatus)|Bu durum (geçerlilik) alır `COleDateTime` nesnesi.|  
|[COleDateTime::GetYear](#getyear)|Bu yılın döndürür `COleDateTime` nesne temsil eder.|  
|[COleDateTime::ParseDateTime](#parsedatetime)|Bir dizeden tarih/saat değeri okuyan ve değerini ayarlar `COleDateTime`.|  
|[COleDateTime::SetDate](#setdate)|Bu değeri ayarlar `COleDateTime` belirtilen salt değer nesnesi.|  
|[COleDateTime::SetDateTime](#setdatetime)|Bu değeri ayarlar `COleDateTime` nesne belirtilen tarih/saat değeri.|  
|[COleDateTime::SetStatus](#setstatus)|Durumunu (geçerlilik) Bu ayarlar `COleDateTime` nesnesi.|  
|[COleDateTime::SetTime](#settime)|Bu değeri ayarlar `COleDateTime` belirtilen yalnızca zaman değerine nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  

|Ad|Açıklama|  
|----------|-----------------|  
|[COleDateTime::operator ==, COleDateTime::operator < vb.](#coledatetime_relational_operators)|İki karşılaştırmak `COleDateTime` değerleri.|  
|[COleDateTime::operator +, COleDateTime::operator-](#operator_add_-)|Ekleme ve çıkarma `COleDateTime` değerleri.|  
|[COleDateTime::operator +=, COleDateTime::operator-=](#operator_add_eq_-_eq)|Ekleme ve bir `COleDateTime` bu değerden `COleDateTime` nesnesi.|  
|[COleDateTime::operator =](#operator_eq)|Kopya bir `COleDateTime` değeri.|  
|[Tarih, COleDateTime::operator COleDateTime::operator tarih *](#operator_date)|Dönüştüren bir `COleDateTime` içine değeri bir `DATE` veya `DATE*`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|Arka plandaki içeren **tarih** bu `COleDateTime` nesnesi.|  
|[COleDateTime::m_status](#m_status)|Bu durumu içeren `COleDateTime` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleDateTime`bir taban sınıfı yok.  
  
 Olası türlerinde biridir [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) OLE Otomasyon veri türü. A `COleDateTime` bir mutlak tarih ve saat değeri değerini temsil eder.  
  
 `DATE` Türü bir kayan nokta değeri olarak uygulanır. Gün 30 Aralık 1899 gece yarısı ölçülür. Aşağıdaki tabloda bazı tarihlerde ve ilişkili değerleri gösterir:  
  
|Tarih|Değer|  
|----------|-----------|  
|29 Aralık 1899 gece yarısı|-1.0|  
|29 Aralık 1899'den itibaren 6 saatlerinde|-1.25|  
|30 Aralık 1899 gece yarısı|0.0|  
|31 Aralık 1899 gece yarısı|1.0|  
|1 Ocak 1900'den itibaren 6'da|2.25|  
  
> [!CAUTION]
>  Yukarıdaki tabloda gün değerleri, 30 Aralık 1899 gece yarısı önce negatif olur ancak gün saat değerleri sağlamadığı olduğunu unutmayın. Örneğin, 6: 00'da her zaman gününü temsil eden tamsayıyı (sonra 30 Aralık 1899) olumlu veya olumsuz (önce 30 Aralık 1899) olmasına bakılmaksızın bir kesir değerini 0,25 temsil edilir. Bu basit bir kayan nokta karşılaştırma yanlışlıkla sıralamanız gerekir anlamına gelir. bir `COleDateTime` 6: 00'te 29/12/1899 temsil eden **daha sonra** 7: 00'da aynı günde birden temsil eden.  
  
 `COleDateTime` Sınıfı tarih 1 Ocak 100-31 Aralık 9999 işler. `COleDateTime` Sınıfı Gregoryen takvim kullanır; Jülyen tarihleri desteklemez. `COleDateTime`Yaz Saati yok sayar. (Bkz [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).)  
  
> [!NOTE]
>  Kullanabileceğiniz `%y` 1900 başlangıç tarihler için iki rakamlı yıl almak için biçimi. Kullanırsanız `%y` kodu 1900, önceki bir tarih biçimine ASSERT hatası oluşturur.  
  
 Bu tür yalnızca tarih veya yalnızca saat değerlerini temsil etmek için de kullanılır. Kural tarafından yalnızca zaman değerleri için kullanılan 0 (30 Aralık 1899) tarih ve saat 00:00 (gece yarısı) yalnızca tarih değerleri için kullanılır.  
  
 Oluşturursanız, bir `COleDateTime` bir tarih kullanarak nesne 100'den az, kabul edilen, ancak sonraki çağrılar tarihidir `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, ve `GetSecond` başarısız ve -1 döndürür. Daha önce iki basamaklı tarihleri kullanabilirsiniz, ancak tarihleri 100 veya MFC 4.2 büyük ve daha sonra olmalıdır.  
  
 Sorunları önlemek için dört basamaklı tarih belirtin. Örneğin:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 Temel aritmetik işlemler için `COleDateTime` değerleri kullanmak yardımcı sınıf [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan`değerleri bir zaman aralığı tanımlayın. Bu sınıflar arasındaki ilişkiyi arasında bir benzer [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Hakkında daha fazla bilgi için `COleDateTime` ve `COleDateTimeSpan` sınıfları, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ATLComTime.h  
  
##  <a name="coledatetime_relational_operators"></a>COleDateTime ilişkisel işleçler  
 Karşılaştırma işleçleri.  
  
```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `date`  
 **COleDateTime** Karşılaştırılacak nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bir ATLASSERT iki işlenen biri geçersiz olduğunda meydana gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>Örnek  
 İşleçler  **>=** ,  **\< =** ,  **>** , ve  **<** , varsa onay `COleDateTime` nesne ayarlanmış null.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]  
  
##  <a name="coledatetime"></a>COleDateTime::COleDateTime  
 Oluşturan bir `COleDateTime` nesnesi.  
  
```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& dbts) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dateSrc`  
 Var olan `COleDateTime` yeni içine kopyalanacak nesne `COleDateTime` nesne.  
  
 *varSrc*  
 Var olan **değişken** veri yapısı (büyük olasılıkla bir `COleVariant` nesnesi) bir tarih/saat değerine dönüştürülecek ( `VT_DATE`) ve yeni içine kopyalanan `COleDateTime` nesnesi.  
  
 `dtSrc`  
 Bir tarih/saat ( **tarih**) yeni içine Kopyalanacak değer `COleDateTime` nesnesi.  
  
 `timeSrc`  
 A `time_t` veya **__time64_t** bir tarih/saat değerine dönüştürülen ve yeni içine kopyaladığınız değeri `COleDateTime` nesnesi.  
  
 *systimeSrc*  
 A `SYSTEMTIME` bir tarih/saat değerine dönüştürülen ve yeni içine kopyalanan yapısı `COleDateTime` nesnesi.  
  
 `filetimeSrc`  
 A `FILETIME` bir tarih/saat değerine dönüştürülen ve yeni içine kopyalanan yapısı `COleDateTime` nesnesi. Unutmayın `FILETIME` Evrensel Eşgüdümlü saate (UTC) kullanan yapısında bir yerel saat geçirirseniz, sonuçlarınızı yanlış olur. Bkz: [dosya sürelerinin](http://msdn.microsoft.com/library/windows/desktop/ms724290) daha fazla bilgi için Windows SDK'sındaki.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Yeni içine kopyalanacak tarih ve saat değerlerini göstermek `COleDateTime` nesnesi.  
  
 `wDosDate`, `wDosTime`  
 Bir tarih/saat değerine dönüştürülen ve yeni içine kopyalanan MS-DOS tarih ve saat değerlerini `COleDateTime` nesne.  
  
 `dbts`  
 Bir başvuru bir [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) geçerli yerel saat içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu Yeni Oluştur `COleDateTime` nesneleri belirtilen değerle başlatılır. Aşağıdaki tabloda her bir tarih ve saat bileşeni için geçerli aralıklar gösterilmektedir:  
  
|Tarih/Saat bileşeni|Geçerli aralık|  
|--------------------------|-----------------|  
|Yıl|100 - 9999|  
|Ay|0 - 12|  
|günü|0 - 31|  
|saat|0 - 23|  
|Dakika|0 - 59|  
|İkinci|0 - 59|  
  
 Gerçek bir üst sınır gün bileşenini için değişir Not ay ve yıl bileşenlerini temel. Ayrıntılar için bkz **SetDate** veya `SetDateTime` üye işlevleri.  
  
 Her Oluşturucusu kısa bir açıklaması verilmiştir:  
  
- `COleDateTime(`**)** Oluşturan bir `COleDateTime` nesne 0 (gece yarısı, 30 Aralık 1899) başlatıldı.  
  
- `COleDateTime(``dateSrc` **)** Oluşturan bir `COleDateTime` varolan bir nesne `COleDateTime` nesne.  
  
- `COleDateTime(`*varSrc* **)** oluşturan bir `COleDateTime` nesnesi. Dönüştürmeye çalışır bir `VARIANT` yapısı veya [COleVariant](../../mfc/reference/colevariant-class.md) bir tarih/saat nesnesine ( `VT_DATE`) değeri. Bu dönüştürme başarılı olursa, dönüştürülen değer yeni içine kopyalanır `COleDateTime` nesnesi. Değeri, değilse `COleDateTime` nesne ayarlanmış 0 (gece yarısı, 30 Aralık 1899) ve onun durumu geçersiz.  
  
- `COleDateTime(``dtSrc` **)** Oluşturan bir `COleDateTime` nesnesinin bir **tarih** değeri.  
  
- `COleDateTime(``timeSrc` **)** Oluşturan bir `COleDateTime` nesnesinin bir `time_t` değeri.  
  
- `COleDateTime(`*systimeSrc* **)** oluşturan bir `COleDateTime` nesnesinin bir `SYSTEMTIME` değeri.  
  
- `COleDateTime(``filetimeSrc` **)** Oluşturan bir `COleDateTime` nesnesinin bir `FILETIME` değeri. biçimindeki telefon numarasıdır. Unutmayın `FILETIME` Evrensel Eşgüdümlü saate (UTC) kullanan yapısında bir yerel saat geçirirseniz, sonuçlarınızı yanlış olur. Bkz: [dosya sürelerinin](http://msdn.microsoft.com/library/windows/desktop/ms724290) daha fazla bilgi için Windows SDK'sındaki.  
  
- `COleDateTime(``nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** Oluşturan bir `COleDateTime` belirtilen sayısal değerleri nesnesinden.  
  
- `COleDateTime(``wDosDate`, `wDosTime` **)** Oluşturan bir `COleDateTime` belirtilen MS-DOS tarih ve saat değerleri bir nesneden.  
  
 Daha fazla bilgi için `time_t` veri türü, bkz: [zaman](../../c-runtime-library/reference/time-time32-time64.md) işlevi *çalışma zamanı kitaplığı başvurusu*.  
  
 Daha fazla bilgi için bkz: [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) ve [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Windows SDK'sı yapılarda.  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
> [!NOTE]
>  Oluşturucu kullanılarak **DBTIMESTAMP** parametresi kullanılabilir yalnızca biçim dahil edildiğinde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]  
  
##  <a name="format"></a>COleDateTime::Format  
 Tarih/saat değeri biçimlendirilmiş bir gösterimini oluşturur.  
  
```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 Aşağıdaki yerel ayar bayrakları birini gösterir:  
  
- `LOCALE_NOUSEROVERRIDE`Sistem varsayılan yerel ayarları yerine özel kullanıcı ayarları kullanın.  
  
- `VAR_TIMEVALUEONLY`Ayrıştırma sırasında tarih bölümü yoksay.  
  
- `VAR_DATEVALUEONLY`Ayrıştırma sırasında saat bölümü yoksay.  
  
 `lcid`  
 Dönüştürme işlemi için kullanılacak yerel ayar Kimliğini gösterir. Dil tanımlayıcıları hakkında daha fazla bilgi için bkz: [Dil tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/dd318691).  
  
 `lpszFormat`  
 Bir biçimlendirme dize benzer `printf` biçimlendirme dizesi. Her bir yüzde öncesinde kod biçimlendirme ( `%`) oturum açın, ilgili tarafından değiştirilir `COleDateTime` bileşeni. Biçimlendirme dizesi diğer karakterler döndürülen dize değişmeden kopyalanır. Çalışma zamanı işlevi görmek [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) daha fazla bilgi için. Değer ve biçimlendirme kodlarını anlamını `Format` şunlardır:  
  
- `%H`Saat geçerli gün içinde  
  
- `%M`Geçerli bir saat içinde dakika  
  
- `%S`Saniye cinsinden geçerli dakikada  
  
- `%%`Yüzde işareti  
  
 `nFormatID`  
 Denetim Biçimlendir dize kaynak kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` biçimlendirilmiş tarih/saat değeri içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bu durumu `COleDateTime` nesnesi null, boş bir dize dönüş değeri değil. Geçersiz durumundaysa, dönüş dizesi dize kaynak tarafından belirtilen `ATL_IDS_DATETIME_INVALID`.  
  
 Bu işlev için üç formları kısa bir açıklamasını aşağıdaki gibidir:  
  
 `Format`( `dwFlags`, `lcid`)  
 Bu form değeri dil belirtimleri (yerel ayar kimlikleri) kullanarak tarih ve saat için biçimlendirir. Varsayılan parametreleri kullanarak, bu formu tarih ve saat saat bölümü 0 (gece yarısı) olduğundan, durumda yalnızca tarih yazdırılacağı veya tarih bölümü 0 (30 Aralık 1899) sürece; bu durumda yalnızca zaman yazdırılacağı içinde yazdırır. Tarih/saat değeri 0 (30 Aralık 1899, gece yarısı) ise, bu form varsayılan parametreleri ile gece yazdırır.  
  
 `Format`( `lpszFormat`)  
 Bu form değeri yüzde işaretiyle (%) öncesinde özel biçimlendirme kodları içeren biçim dizesini kullanarak olarak biçimleri `printf`. Biçimlendirme dizesi işlevi için parametre olarak geçirilir. Biçimlendirme kodları hakkında daha fazla bilgi için bkz: [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) çalışma zamanı kitaplığı başvurusu.  
  
 `Format`( `nFormatID`)  
 Bu form değeri yüzde işaretiyle (%) öncesinde özel biçimlendirme kodları içeren biçim dizesini kullanarak olarak biçimleri `printf`. Biçimlendirme dizesi bir kaynaktır. Bu dize kaynağı kimliği, parametre olarak geçirilir. Biçimlendirme kodları hakkında daha fazla bilgi için bkz: [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="getasdbtimestamp"></a>COleDateTime::GetAsDBTIMESTAMP  
 Zaman içinde elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir **DBTIMESTAMP** veri yapısı.  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dbts`  
 Bir başvuru bir [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuçta elde edilen zaman başvurulan depolar `dbts` yapısı. **DBTIMESTAMP** bu işlev tarafından başlatılan veri yapısı olacaktır, **kesir** üye sıfır olarak ayarlayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="getassystemtime"></a>COleDateTime::GetAsSystemTime  
 Zaman içinde elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir `SYSTEMTIME` veri yapısı.  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *sysTime*  
 Bir başvuru bir [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) dönüştürülmüş tarih/saat değerinden almaya yapısı `COleDateTime` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** başarılıysa; **false** dönüştürme başarısız olursa veya `COleDateTime` nesne **NULL** veya geçersiz.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetAsSystemTime`Sonuçta elde edilen zaman başvurulan depolar *sysTime* nesnesi. `SYSTEMTIME` Bu işlev tarafından başlatılan veri yapısı olacaktır, **wMilliseconds** üye sıfır olarak ayarlayın.  
  
 Bkz: [GetStatus](#getstatus) içinde tutulan durum bilgileri hakkında daha fazla bilgi için bir `COleDateTime` nesnesi.  
  
##  <a name="getasudate"></a>COleDateTime::GetAsUDATE  
 Zaman içinde elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir **UDATE** veri yapısı.  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `udate`  
 Bir başvuru bir **UDATE** dönüştürülmüş tarih/saat değerinden almaya yapısı `COleDateTime` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** başarılıysa; **false** dönüştürme başarısız olursa veya `COleDateTime` nesne **NULL** veya geçersiz.  
  
### <a name="remarks"></a>Açıklamalar  
 A **UDATE** yapısı "paketten çıkarılan" tarihini temsil eder.  
  
##  <a name="getcurrenttime"></a>COleDateTime::GetCurrentTime  
 Geçerli tarih/saat değeri döndürmek için bu statik üye işlevini çağırın.  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="getday"></a>COleDateTime::GetDay  
 Bu tarih/saat değeri tarafından temsil edilen ayın günü alır.  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu değeri tarafından temsil edilen ayın günü `COleDateTime` nesne veya `COleDateTime::error` gün alınamadığından durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 1 ile 31 arasında geçerli dönüş değerleri aralığı.  
  
 Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]  
  
##  <a name="getdayofweek"></a>COleDateTime::GetDayOfWeek  
 Bu tarih/saat değeri tarafından temsil edilen ayın günü alır.  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu değeri tarafından temsil edilen haftanın gününü `COleDateTime` nesne veya `COleDateTime::error` haftanın günü alınamadığından durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli dönüş değerleri 1 ile 7 arasındaki bir aralıkta 1 burada = Pazar, 2 Pazartesi vb.  
  
 Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]  
  
##  <a name="getdayofyear"></a>COleDateTime::GetDayOfYear  
 Bu tarih/saat değeri tarafından temsil edilen yılın günü alır.  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu değeri tarafından temsil edilen yılın günü `COleDateTime` nesne veya `COleDateTime::error` yılın günü alınamadığından durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli dönüş değerleri aralığı 1 ile 366 arasında burada 1 Ocak = 1.  
  
 Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]  
  
##  <a name="gethour"></a>COleDateTime::GetHour  
 Bu tarih/saat değeri tarafından temsil edilen saati alır.  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu değeri tarafından temsil edilen saat `COleDateTime` nesne veya `COleDateTime::error` saat alınamadığından durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 0 ile 23 arasında geçerli dönüş değerleri aralığı.  
  
 Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]  
  
##  <a name="getminute"></a>COleDateTime::GetMinute  
 Bu tarih/saat değeri tarafından temsil edilen dakika alır.  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu değeri tarafından temsil edilen dakika `COleDateTime` nesne veya `COleDateTime::error` minute alınamadığından.  
  
### <a name="remarks"></a>Açıklamalar  
 0 ile 59 arasında geçerli dönüş değerleri aralığı.  
  
 Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetHour](#gethour).  
  
##  <a name="getmonth"></a>COleDateTime::GetMonth  
 Bu tarih/saat değeri tarafından temsil edilen ay alır.  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu değeri tarafından temsil edilen ay `COleDateTime` nesne veya `COleDateTime::error` ay alınamadığından durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 1 ile 12 arasında geçerli dönüş değerleri aralığı.  
  
 Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetDay](#getday).  
  
##  <a name="getsecond"></a>COleDateTime::GetSecond  
 Bu tarih/saat değeri tarafından temsil edilen ikinci alır.  
  
```
int GetSecond() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu değeri tarafından temsil edilen ikinci `COleDateTime` nesne veya `COleDateTime::error` ikinci alınamadığından durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 0 ile 59 arasında geçerli dönüş değerleri aralığı.  
  
> [!NOTE]
>  `COleDateTime` Sınıf artık saniye desteklemez.  
  
 Uygulamasını hakkında daha fazla bilgi için `COleDateTime`, makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetHour](#gethour).  
  
##  <a name="getstatus"></a>COleDateTime::GetStatus  
 (Geçerlilik) durumunu alır bir verilen `COleDateTime` nesnesi.  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu durumu döndürür `COleDateTime` değeri. Çağırırsanız **GetStatus** üzerinde bir `COleDateTime` oluşturulan varsayılan nesne, geçerli döndürür. Çağırırsanız **GetStatus** üzerinde bir `COleDateTime` Oluşturucusu ayarlanan null ile başlatılmış nesne **GetStatus** null döndürür. Bkz: **açıklamalar** daha fazla bilgi için.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri tarafından tanımlanan **DateTimeStatus** numaralandırılmış içinde tanımlanan türü `COleDateTime` sınıfı.  
  
```  
enum DateTimeStatus  
{  
   error = -1,  
   valid = 0,  
   invalid = 1,    // Invalid date (out of range, etc.)  
   null = 2,       // Literally has no value  
};  
```  
  
 Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:  
  
- `COleDateTime::error`Tarih/saat değeri parçası alınmaya çalışılırken bir hata oluştuğunu gösterir.  
  
- **COleDateTime::valid** belirtir bu `COleDateTime` nesne geçerlidir.  
  
- **COleDateTime::invalid** belirtir bu `COleDateTime` nesnesi geçersiz; diğer bir deyişle, değeri yanlış olabilir.  
  
- **COleDateTime::null** belirtir bu `COleDateTime` nesnesi null, diğer bir deyişle, bu nesne için herhangi bir değer belirtildi. (Bu bir "herhangi bir değer aksine C++ kullanılmasının" veritabanı algılama "null" **NULL**.)  
  
 Durumunu bir `COleDateTime` nesnesi aşağıdaki durumlarda geçersiz:  
  
-   Gelen değerini ayarlarsanız bir **değişken** veya `COleVariant` bir tarih/saat değerine dönüştürülemedi değeri.  
  
-   Gelen değerini ayarlarsanız bir `time_t`, `SYSTEMTIME`, veya `FILETIME` geçerli tarih/saat değerine dönüştürülemedi değeri.  
  
-   Kendi değer ayarlanırsa `SetDateTime` geçersiz parametre değerleri ile.  
  
-   Bu nesne bir taşması veya underflow aritmetik atama işlemi sırasında yani, karşılaştı, `+=` veya `-=`.  
  
-   Bu nesne için geçersiz bir değer atanmışsa.  
  
-   Kullanarak geçersiz bu nesnenin durumu açıkça ayarlanmış olmadığını `SetStatus`.  
  
 İşlemleri hakkında daha fazla bilgi için aşağıdaki üye işlevlerini geçersiz bkz durumu ayarlayabilir:  
  
- [COleDateTime](#coledatetime)  
  
- [SetDateTime](#setdatetime)  
  
- [operator +, -](#operator_add_-)  
  
- [operator +=-=](#operator_add_eq_-_eq)  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="getyear"></a>COleDateTime::GetYear  
 Bu tarih/saat değeri tarafından temsil edilen yıl alır.  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu değeri tarafından temsil edilen yıl `COleDateTime` nesne veya `COleDateTime::error` yıl alınamadığından durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Century içerir geçerli dönüş değerleri aralığı 100 ile 9999 arasında.  
  
 Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetDay](#getday).  
  
##  <a name="m_dt"></a>COleDateTime::m_dt  
 Arka plandaki **tarih** yapısı bu `COleDateTime` nesnesi.  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  Değer değiştirme **tarih** bu işlev tarafından döndürülen işaretçi tarafından erişilen nesne bu değerini değiştirin `COleDateTime` nesnesi. Bu durumu değiştirmez `COleDateTime` nesnesi.  
  
 Uygulaması hakkında daha fazla bilgi için **tarih** nesne, makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="m_status"></a>COleDateTime::m_status  
 Bu durumu içeren `COleDateTime` nesnesi.  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu veri üyesi türü numaralandırılmış türüdür **DateTimeStatus**, içinde tanımlanan `COleDateTime` sınıfı. Bkz: [COleDateTime::GetStatus](#getstatus) Ayrıntılar için.  
  
> [!CAUTION]
>  Gelişmiş programlama durumlar için bu veri üyesidir. Satır içi üye işlevleri kullanması gereken [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bkz: `SetStatus` açıkça bu veri üyesi ayarlama ile ilgili daha fazla uyarılar için.  
  
##  <a name="operator_eq"></a>COleDateTime::operator =  
 Kopya bir `COleDateTime` değeri.  
  
```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& udate) throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aşırı yüklenmiş atama işleçleri kaynak tarih/saat değeri bu kopyalamak `COleDateTime` nesnesi. Her bu kısa bir açıklamasını atama işleçleri aşağıdaki aşırı:  
  
- **işleç = (** `dateSrc` **)** işleneni durumunu ve değeri bu kopyalanır `COleDateTime` nesnesi.  
  
- **işleç = (** *varSrc* **)** varsa dönüştürülmesi [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) değeri (veya [COleVariant](../../mfc/reference/colevariant-class.md) nesnesi) için bir tarih/saat ( `VT_DATE`) olan başarılı dönüştürülen değer bu kopyalanır `COleDateTime` nesne ve durumu ayarlanmış için geçerli. Dönüştürme başarılı olmazsa, bu nesnenin değeri sıfır (30 Aralık 1899 için gece yarısı) ayarlanır ve durumu geçersiz.  
  
- **işleç = (** `dtSrc` **)** **tarih** değeri bu kopyalanır `COleDateTime` nesne ve durumu ayarlanmış için geçerli.  
  
- **işleç = (** `timeSrc` **)** `time_t` veya **__time64_t** değeri dönüştürülür ve bu kopyalanan `COleDateTime` nesnesi. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli ayarlanır; başarısız, ayarlanmış olup olmadığını geçersiz.  
  
- **işleç = (** *systimeSrc* **)** [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) değeri dönüştürülür ve bu kopyalanan `COleDateTime` nesnesi. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli ayarlanır; başarısız, ayarlanmış olup olmadığını geçersiz.  
  
- **işleç = (** `udate` **)** **UDATE** değeri dönüştürülür ve bu kopyalanan `COleDateTime` nesnesi. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli ayarlanır; başarısız, ayarlanmış olup olmadığını geçersiz. A **UDATE** yapısı "paketten çıkarılan" tarihini temsil eder. İşlev bkz [VarDateFromUdate](http://msdn.microsoft.com/en-us/1c924ac5-b896-49e1-9ccf-825ac7a030c8) daha fazla ayrıntı için.  
  
- **işleç = (** `filetimeSrc` **)** [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) değeri dönüştürülür ve bu kopyalanan `COleDateTime` nesnesi. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli ayarlanır; Aksi takdirde ayarlamak için geçersiz. `FILETIME`UTC saati yapısında geçirirseniz, sonuçlarınızı UTC saati yerel saate dönüştürülür ve değişken zaman olarak depolanan Evrensel Eşgüdümlü saate (UTC) kullanır. Bu davranış Visual C++ 6.0 ve Visual C++ .NET 2003 SP2 için de aynıdır. Bkz: [dosya sürelerinin](http://msdn.microsoft.com/library/windows/desktop/ms724290) daha fazla bilgi için Windows SDK'sındaki.  
  
 Daha fazla bilgi için bkz: [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Windows SDK'sı giriş.  
  
 Daha fazla bilgi için `time_t` veri türü, bkz: [zaman](../../c-runtime-library/reference/time-time32-time64.md) işlevi *çalışma zamanı kitaplığı başvurusu*.  
  
 Daha fazla bilgi için bkz: [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) ve [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Windows SDK'sı yapılarda.  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_add_-"></a>COleDateTime::operator +, -  
 Ekleme ve çıkarma **ColeDateTime** değerleri.  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `COleDateTime`nesneleri mutlak kez temsil eder. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) nesneleri göreli kez temsil eder. İlk iki işleç ekleyin ve çıkarma olanak tanıyan bir `COleDateTimeSpan` değeri bir `COleDateTime` değeri. Üçüncü işleci bir çıkarma sayesinde `COleDateTime` elde etmek üzere başka bir değerden bir `COleDateTimeSpan` değeri.  
  
 İşlenen birini ise null, elde edilen durumunu `COleDateTime` değeri NULL'dur.  
  
 Elde edilen `COleDateTime` değeri kabul edilebilir değerler, durumu, sınırların dışında kalan sınırları `COleDateTime` değeri geçersiz.  
  
 İşlenen birini geçersiz ve diğer null değilse, elde edilen durumunu `COleDateTime` değeri geçersiz.  
  
  **+**  Ve  **-**  işleçleri assert, `COleDateTime` nesne ayarlanmış null. Bkz: [COleDateTime ilişkisel işleçleri](#coledatetime_relational_operators) bir örnek.  
  
 Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz: [m_status](#m_status) üye değişkeni.  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>COleDateTime::operator +=-=  
 Ekleme ve bir **ColeDateTime** bu değerden `COleDateTime` nesnesi.  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleçlere ekleme ve çıkarma izin bir `COleDateTimeSpan` için ve bu değer `COleDateTime`. İşlenen birini ise null, elde edilen durumunu `COleDateTime` değeri NULL'dur.  
  
 Elde edilen `COleDateTime` değeri kabul edilebilir değerler, bu durumu sınırların dışında kalan sınırları `COleDateTime` değeri ayarı geçersiz.  
  
 İşlenen birini geçersiz ve diğer null değilse, elde edilen durumunu `COleDateTime` değeri geçersiz.  
  
 Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz: [m_status](#m_status) üye değişkeni.  
  
  **+=**  Ve  **-=**  işleçleri assert, `COleDateTime` nesne ayarlanmış null. Bkz: [COleDateTime ilişkisel işleçleri](#coledatetime_relational_operators) bir örnek.  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_date"></a>COleDateTime::operator tarihi  
 Dönüştüren bir **ColeDateTime** içine değeri bir **tarih**.  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç döndürür bir **tarih** değeri öğesinden kopyalanır nesne `COleDateTime` nesne. Uygulaması hakkında daha fazla bilgi için **tarih** nesne, makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 **Tarih** işleci assert, `COleDateTime` nesne ayarlanmış null. Bkz: [COleDateTime ilişkisel işleçleri](#coledatetime_relational_operators) bir örnek.  
  
##  <a name="parsedatetime"></a>COleDateTime::ParseDateTime  
 Bir tarih/saat değeri okumak için bir dize ayrıştırır.  
  
```
bool ParseDateTime(  
 LPCTSTR lpszDate,
 DWORD dwFlags = 0,
 LCID lcid = LANG_USER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszDate`  
 Ayrıştırılacak olan null ile sonlandırılmış dize için bir işaretçi. Açıklamalar Ayrıntılar için bkz.  
  
 `dwFlags`  
 Yerel ayarlar ve ayrıştırma bayrakları belirtir. Bir veya daha fazla aşağıdaki bayraklar:  
  
- **LOCALE_NOUSEROVERRIDE** özel kullanıcı ayarları yerine sistem varsayılan yerel ayarları kullanın.  
  
- **VAR_TIMEVALUEONLY** Ayrıştırma sırasında tarih bölümü yoksay.  
  
- **VAR_DATEVALUEONLY** Ayrıştırma sırasında saat bölümü yoksay.  
  
 `lcid`  
 Dönüştürme işlemi için kullanılacak yerel ayar Kimliğini gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** dize başarıyla bir tarih/saat değerine aksi dönüştürüldü varsa **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Dize için bir tarih/saat başarıyla dönüştürüldü değeri, bu değeri `COleDateTime` nesne ayarlanmış bu değeri ve durumuna geçerli.  
  
> [!NOTE]
>  Yıl değerlerinin ikisi de dahil olmak 100 ve 9999 arasında olmalıdır.  
  
 `lpszDate` Parametresi, çeşitli biçimlerde alabilir. Örneğin, aşağıdaki dizeleri kabul edilebilir tarih/saat biçimlerinden içerir:  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`  
  
 Dize biçiminde bir tarih/saat değerine dönüştürme için kabul edilebilir olup yerel ayar kimliği de etkilenir.  
  
 Durumunda **VAR_DATEVALUEONLY**, değer saat 0 veya gece yarısı olarak ayarlanmış saat. Durumunda **VAR_TIMEVALUEONLY**, tarih değeri 30 Aralık 1899 anlamı tarihine 0 olarak ayarlanır.  
  
 Dize bir tarih/saat değerine dönüştürülemedi mı yoksa bu durum bir sayısal taşması olduysa `COleDateTime` nesnesi geçersiz.  
  
 Uygulama için ve sınırlarını hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="setdate"></a>COleDateTime::SetDate  
 Bu tarihin ayarlar `COleDateTime` nesnesi.  
  
```
int SetDate(  
 int nYear,
 int nMonth,
 int nDay) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nYear`, `nMonth`, `nDay`  
 Bu kopyalanacak tarih bileşenlerini göstermek `COleDateTime` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır değeri bu `COleDateTime` nesne 1 ayarlandığı başarıyla; Aksi takdirde. Dayanarak bu dönüş değeri **DateTimeStatus** numaralandırılmış türü. Daha fazla bilgi için bkz: [SetStatus](#setstatus) üye işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarih için belirtilen değerlere ayarlanır. Saat, saat için 0, gece yarısı ayarlanır.  
  
 Parametre değerleri için sınırları için aşağıdaki tabloya bakın:  
  
|Parametre|Sınırları|  
|---------------|------------|  
|`nYear`|100 - 9999|  
|`nMonth`|1 - 12|  
|`nDay`|0 - 31|  
  
 Ayın gününü taşarsa doğru gününü sonraki ay ve ayın dönüştürülür ve/veya yıl buna uygun olarak artırılır. Sıfır gün değeri önceki ayın son gününü gösterir. Aynı davranıştır `SystemTimeToVariantTime`.  
  
 Parametrelerle belirtilen tarih değeri geçerli değil, bu nesnenin durumu ayarlanırsa **COleDateTime::invalid**. Kullanmanız gereken [GetStatus](#getstatus) geçerliliğini denetlemek için **tarih** değeri ve bu varsayımında bulunmamalıdır değerini [m_dt](#m_dt) değiştirilmemiş olarak kalır.  
  
 Tarih değerlerini bazı örnekleri şunlardır:  
  
|`nYear`|`nMonth`|`nDay`|Değer|  
|-------------|--------------|------------|-----------|  
|2000|2|29|29 Şubat 2000|  
|1776|7|4|4 Temmuz 1776|  
|1925|4|35|35 Nisan 1925 (geçersiz tarih)|  
|10000|1.|1.|1 Ocak 10000 (geçersiz tarih)|  
  
 Tarih ve saat ayarlamak için bkz: [COleDateTime::SetDateTime](#setdatetime).  
  
 Bu değeri sorgu üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]  
  
##  <a name="setdatetime"></a>COleDateTime::SetDateTime  
 Tarih ve saat bu ayarlar `COleDateTime` nesnesi.  
  
```
int SetDateTime(  
 int nYear,
 int nMonth,
 int nDay,
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Bu kopyalanacak tarih ve saat bileşenleri gösteren `COleDateTime` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır değeri bu `COleDateTime` nesne 1 ayarlandığı başarıyla; Aksi takdirde. Dayanarak bu dönüş değeri **DateTimeStatus** numaralandırılmış türü. Daha fazla bilgi için bkz: [SetStatus](#setstatus) üye işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre değerleri için sınırları için aşağıdaki tabloya bakın:  
  
|Parametre|Sınırları|  
|---------------|------------|  
|`nYear`|100 - 9999|  
|`nMonth`|1 - 12|  
|`nDay`|0 - 31|  
|`nHour`|0 - 23|  
|`nMin`|0 - 59|  
|`nSec`|0 - 59|  
  
 Ayın gününü taşarsa doğru gününü sonraki ay ve ayın dönüştürülür ve/veya yıl buna uygun olarak artırılır. Sıfır gün değeri önceki ayın son gününü gösterir. Aynı davranıştır [SystemTimeToVariantTime](http://msdn.microsoft.com/en-us/d9d69521-9b33-4fc5-8a1c-929f216db450).  
  
 Parametrelerle belirtilen tarih veya saat değeri geçerli, bu nesnenin durumu geçersiz ve bu nesnenin değerini ayarlayın değilse değiştirilmez.  
  
 Saat değerleri bazı örnekleri şunlardır:  
  
|`nHour`|`nMin`|`nSec`|Değer|  
|-------------|------------|------------|-----------|  
|1.|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Geçersiz|  
|9|60|0|Geçersiz|  
  
 Tarih değerlerini bazı örnekleri şunlardır:  
  
|`nYear`|`nMonth`|`nDay`|Değer|  
|-------------|--------------|------------|-----------|  
|1995|4|15|15 Nisan 1995|  
|1789|7|14|17 Temmuz 1789|  
|1925|2|30|Geçersiz|  
|10000|1.|1.|Geçersiz|  
  
 Yalnızca tarih ayarlamak için bkz: [COleDateTime::SetDate](#setdate). Yalnızca saati ayarlamak için bkz: [COleDateTime::SetTime](#settime).  
  
 Bu değeri sorgu üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetStatus](#getstatus).  
  
##  <a name="setstatus"></a>COleDateTime::SetStatus  
 Bu durumu ayarlar `COleDateTime` nesnesi.  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *durumu*  
 Bu yeni durum değeri `COleDateTime` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 *Durum* tarafından tanımlanan parametre değeri **DateTimeStatus** numaralandırılmış içinde tanımlanan türü `COleDateTime` sınıfı. Bkz: [COleDateTime::GetStatus](#getstatus) Ayrıntılar için.  
  
> [!CAUTION]
>  Bu işlev, Gelişmiş programlama durumlar için kullanılır. Bu işlev, bu nesne verileri değiştirmez. Durum ayarlamak için çoğunlukla kullanılacak `null` veya **geçersiz**. Unutmayın atama işleci ( [işleç =](#eq)) ve [SetDateTime](#setdatetime) kaynak değerler dayalı bir nesnenin durumu ayarlayın.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetStatus](#getstatus).  
  
##  <a name="settime"></a>COleDateTime::SetTime  
 Bu süreyi ayarlar `COleDateTime` nesnesi.  
  
```
int SetTime(  
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nHour`, `nMin`, `nSec`  
 Bu kopyalanacak zamanı bileşenleri belirtmek `COleDateTime` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır değeri bu `COleDateTime` nesne 1 ayarlandığı başarıyla; Aksi takdirde. Dayanarak bu dönüş değeri **DateTimeStatus** numaralandırılmış türü. Daha fazla bilgi için bkz: [SetStatus](#setstatus) üye işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Süresi belirtilen değerlere ayarlanır. Tarihi, tarih için 0, 30 Aralık 1899 anlamı ayarlanır.  
  
 Parametre değerleri için sınırları için aşağıdaki tabloya bakın:  
  
|Parametre|Sınırları|  
|---------------|------------|  
|`nHour`|0 - 23|  
|`nMin`|0 - 59|  
|`nSec`|0 - 59|  
  
 Parametrelerle belirtilen değer geçerli değil zaman bu nesnenin durumu geçersiz ve bu nesnenin değerini ayarlarsanız değiştirilmez.  
  
 Saat değerleri bazı örnekleri şunlardır:  
  
|`nHour`|`nMin`|`nSec`|Değer|  
|-------------|------------|------------|-----------|  
|1.|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Geçersiz|  
|9|60|0|Geçersiz|  
  
 Tarih ve saat ayarlamak için bkz: [COleDateTime::SetDateTime](#setdatetime).  
  
 Bu değeri sorgu üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [SetDate](#setdate).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleVariant sınıfı](../../mfc/reference/colevariant-class.md)   
 [CTime sınıfı](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)



