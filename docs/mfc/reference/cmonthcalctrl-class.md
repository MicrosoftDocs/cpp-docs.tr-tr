---
title: CMonthCalCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
ms.openlocfilehash: bd062a4e0d4db364c9cb628608c6af165dc0edc2
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777174"
---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl sınıfı

Aylık takvim denetiminin işlevselliğini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|Oluşturur bir `CMonthCalCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMonthCalCtrl::Create](#create)|Ay takvim denetimi oluşturur ve ona ekler `CMonthCalCtrl` nesne.|
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|Geçerli ay Takvim denetimi kenarlığın genişliğini alır.|
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|Geçerli Ay takvim denetimde görüntülenen takvimler sayısını alır.|
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|Geçerli ay Takvim denetimi ile ilgili bilgileri alır.|
|[CMonthCalCtrl::GetCalID](#getcalid)|Geçerli ay Takvim denetimi Takvim tanımlayıcısını alır.|
|[CMonthCalCtrl::GetColor](#getcolor)|Belirtilen bir alan aylık takvim denetiminin rengini alır.|
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|Geçerli ay Takvim denetimi tarafından görüntülenen görünümü alır.|
|[CMonthCalCtrl::GetCurSel](#getcursel)|Şu anda seçtiğiniz tarihe göre gösterildiği gibi sistem saatini alır.|
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|Takvimin en soldaki sütunda görüntülenecek haftanın ilk gününü alır.|
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Ay takvim denetim içinde seçilen gün geçerli maksimum sayısını alır.|
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|"Bugün" dizesi geçerli ay Takvim denetimi için en fazla genişliğini alır.|
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Aylık takvim denetiminin içinde tam bir ay göstermek için gereken en küçük boyut alır.|
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Aylık takvim denetiminin kaydırma ücretine alır.|
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|Aylık takvim denetiminin görünen üst ve alt sınırlarını temsil eden bilgilerini alır tarih.|
|[CMonthCalCtrl::GetRange](#getrange)|Bir ay takvimi ayarlama geçerli minimum ve maksimum tarih alır.|
|[CMonthCalCtrl::GetSelRange](#getselrange)|Kullanıcı tarafından şu anda seçili tarih aralığı üst ve alt sınırlarını temsil eden tarih bilgilerini alır.|
|[CMonthCalCtrl::GetToday](#gettoday)|"Bugün" için bir ay takvimi olarak belirtilen tarih için tarih bilgilerini alır.|
|[CMonthCalCtrl::HitTest](#hittest)|Ekrandaki verilen noktanın hangi bölümünde aylık takvim denetiminin olduğunu belirler.|
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|Geçerli ay Takvim denetimi geçerli görünümünü. yüzyıla uygun görünüm olup olmadığını gösterir.|
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|Geçerli ay Takvim denetimi geçerli görünümünü on görünümü olup olmadığını belirtir.|
|[CMonthCalCtrl::IsMonthView](#ismonthview)|Geçerli ay Takvim denetimi geçerli görünümünü ay görünümü olup olmadığını belirtir.|
|[CMonthCalCtrl::IsYearView](#isyearview)|Geçerli ay Takvim denetimi geçerli görünümünü yıl görünümü olup olmadığını gösterir.|
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|Geçerli ay Takvim denetimi kenarlığı genişliğini belirler.|
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|Geçerli ay Takvim denetimi kenarlığın varsayılan genişliğini ayarlar.|
|[CMonthCalCtrl::SetCalID](#setcalid)|Takvim tanımlayıcısı geçerli ay Takvim denetimi için ayarlar.|
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|Yüzyıl görüntülemek için geçerli aylık takvim denetiminin ayarlar.|
|[CMonthCalCtrl::SetColor](#setcolor)|Belirtilen bir alan aylık takvim denetiminin rengini ayarlar.|
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|Belirtilen görüntülemek için geçerli aylık takvim denetiminin ayarlar.|
|[CMonthCalCtrl::SetCurSel](#setcursel)|Aylık takvim denetiminin seçili tarihini ayarlar.|
|[CMonthCalCtrl::SetDayState](#setdaystate)|Gün için görünen bir ay takvimi ayarlar.|
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|Ayarlar decade görünümüne geçerli ay Takvim denetimi.|
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|Takvimin en soldaki sütunda görüntülenecek haftanın gününü ayarlar.|
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|En fazla bir ay takvimi seçilen gün sayısını ayarlar.|
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Aylık takvim denetiminin kaydırma ücretine ayarlar.|
|[CMonthCalCtrl::SetMonthView](#setmonthview)|Ay görüntülemek için geçerli aylık takvim denetiminin ayarlar.|
|[CMonthCalCtrl::SetRange](#setrange)|Tarihleri ay Takvim denetimi için izin verilen maksimum ve minimum ayarlar.|
|[CMonthCalCtrl::SetSelRange](#setselrange)|Ay takvim seçimini kümeleri belirli bir tarih aralığındaki için denetler.|
|[CMonthCalCtrl::SetToday](#settoday)|Takvim denetiminin gün için geçerli ayarlar.|
|[CMonthCalCtrl::SetYearView](#setyearview)|Ayarlar geçerli ay takvim yılı görünümüne denetler.|
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|En düşük, bir aylık boyutuna repaints aylık takvim denetimi.|
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|Geçerli ay Takvim denetimi için belirtilen bir dikdörtgenine tüm takvimleri içeren küçük dikdörtgen hesaplar.|

## <a name="remarks"></a>Açıklamalar

Aylık takvim denetiminin kullanıcı bir tarih seçebilir, bir basit bir takvim arabirimi ile kullanıcı sağlar. Kullanıcı tarafından görüntülenmesini değiştirebilirsiniz:

- Aydan aya için geri ve İleri, kaydırma.

- Geçerli gün (MCS_NOTODAY stili kullanılmazsa) görüntülemek için hemen metin'yı tıklatın.

- Bir ay ya da açılan menüden bir yıl çekme.

Özelleştirebileceğiniz ay Takvim denetimi oluşturduğunuz nesneye çeşitli stilleri uygulayarak. Bu stiller açıklanan [aylık takvim denetimi stilleri](/windows/desktop/Controls/month-calendar-control-styles) Windows SDK.

Aylık takvim denetiminin birden fazla ay görüntüleyebilir ve (örneğin, tatil) özel günleri kalın belirtebilir tarih.

Aylık takvim denetiminin kullanma hakkında daha fazla bilgi için bkz. [kullanarak CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdtctl.h

##  <a name="cmonthcalctrl"></a>  CMonthCalCtrl::CMonthCalCtrl

Oluşturur bir `CMonthCalCtrl` nesne.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız `Create` sonra nesnesi oluşturun.

##  <a name="create"></a>  CMonthCalCtrl::Create

Ay takvim denetimi oluşturur ve ona ekler `CMonthCalCtrl` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(
    DWORD dwStyle,
    const POINT& pt,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Aylık takvim denetimine uygulanan Windows stilleri birleşimi belirtir. Bkz: [aylık takvim denetimi stilleri](/windows/desktop/Controls/month-calendar-control-styles) stilleri hakkında daha fazla bilgi için Windows SDK.

*Rect*<br/>
Bir başvuru bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı. Aylık takvim denetiminin boyutunu ve konumunu içerir.

*PT*<br/>
Bir başvuru bir [noktası](/previous-versions/dd162805\(v=vs.85\)) aylık takvim denetiminin konumunu tanımlayan yapısı.

*pParentWnd*<br/>
Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) aylık takvim denetiminin üst penceresine olan nesne. NULL olmamalıdır.

*nID*<br/>
Aylık takvim denetiminin denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir ay oluşturma Takvim denetimi iki adımda:

1. Çağrı [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) oluşturmak için bir `CMonthCalCtrl` nesne.

1. Aylık takvim denetiminin oluşturan ve ekler bu üye işlevi çağrısı `CMonthCalCtrl` nesne.

Çağırdığınızda `Create`, ortak denetimleri yeniden başlatılır. Sürümü `Create` , çağrı nasıl boyutlandırılacağını belirler:

- MFC bir ay için denetimin boyutunu otomatik olarak sağlamak için kullandığı bir geçersiz kılma çağrı *pt* parametresi.

- Denetimi kendiniz boyutlandırmak için geçersiz kılmasını kullanan bu işlev çağrısı *rect* parametresi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

##  <a name="getcalendarborder"></a>  CMonthCalCtrl::GetCalendarBorder

Geçerli ay Takvim denetimi kenarlığın genişliğini alır.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin kenarlığının piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_GETCALENDARBORDER](/windows/desktop/Controls/mcm-getcalendarborder) Windows SDK'da açıklanan ileti.

##  <a name="getcalendarcount"></a>  CMonthCalCtrl::GetCalendarCount

Geçerli Ay takvim denetimde görüntülenen takvimler sayısını alır.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ay takvim denetimi şu anda görüntülenen takvimler sayısı. Takvimleri, izin verilen en fazla sayısını 12 ' dir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_GETCALENDARCOUNT](/windows/desktop/Controls/mcm-getcalendarcount) Windows SDK'da açıklanan ileti.

##  <a name="getcalendargridinfo"></a>  CMonthCalCtrl::GetCalendarGridInfo

Geçerli ay Takvim denetimi ile ilgili bilgileri alır.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pmcGridInfo*|[out] İşaretçi bir [MCGRIDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagmcgridinfo) yapısı, geçerli ay Takvim denetimi ile ilgili bilgileri alır. Ayırma ve bu yapı başlatma çağıran sorumludur.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_GETCALENDARGRIDINFO](/windows/desktop/Controls/mcm-getcalendargridinfo) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_monthCalCtrl`, yani aylık takvim denetiminin programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde `GetCalendarGridInfo` geçerli ay Takvim denetimi görüntüler takvim tarihini almak için yöntemi.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

##  <a name="getcalid"></a>  CMonthCalCtrl::GetCalID

Geçerli ay Takvim denetimi Takvim tanımlayıcısını alır.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdakilerden birini [Takvim tanımlayıcısı](/windows/desktop/Intl/calendar-identifiers) sabitler.

### <a name="remarks"></a>Açıklamalar

Bir takvim tanımlayıcı bir bölgeye özgü takvim Gregoryen (yerelleştirilmiş), Japonca veya Hicri gibi gösterir takvimler. Uygulamanızın, çeşitli dil işlevleri desteği olan bir takvim tanımlayıcı kullanabilirsiniz.

Bu yöntem gönderir [MCM_GETCALID](/windows/desktop/Controls/mcm-getcalid) Windows SDK'da açıklanan ileti.

##  <a name="getcolor"></a>  CMonthCalCtrl::GetColor

Bir alan ayın rengini Takvim denetimi tarafından belirtilen alır *nRegion*.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>Parametreler

*nRegion*<br/>
Aylık takvim denetiminin rengini alınacağı bölgesi. Değerler listesi için bkz. *nRegion* parametresinin [SetColor](#setcolor).

### <a name="return-value"></a>Dönüş Değeri

A [COLORREF](/windows/desktop/gdi/colorref) başarılı olursa aylık takvim denetiminin kısmı ile ilişkili rengi belirten değer. Aksi takdirde, bu üye işlevi -1 döndürür.

##  <a name="getcurrentview"></a>  CMonthCalCtrl::GetCurrentView

Geçerli ay Takvim denetimi tarafından görüntülenen görünümü alır.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri tarafından belirtilen geçerli görünümü:

|Değer|Açıklama|
|-----------|-------------|
|MCMV_MONTH|Aylık görüntüle|
|MCMV_YEAR|Yıllık görüntüle|
|MCMV_DECADE|On görüntüle|
|MCMV_CENTURY|Yüzyıl görüntüle|

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_monthCalCtrl`, yani aylık takvim denetiminin programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Ay Takvimi görüntüleme aşağıdaki kod örneği raporlar şu anda denetimi görüntüler.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

##  <a name="getcursel"></a>  CMonthCalCtrl::GetCurSel

Şu anda seçtiğiniz tarihe göre gösterildiği gibi sistem saatini alır.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi veya bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesne. Geçerli saati alır.

*pDateTime*<br/>
Bir işaretçi bir [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) şu anda seçili olan tarih bilgi alacak yapısı. Bu parametre, geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; otherwize 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETCURSEL](/windows/desktop/Controls/mcm-getcursel)Windows SDK içinde açıklandığı gibi.

> [!NOTE]
>  Stil MCS_MULTISELECT olarak ayarlanmışsa bu üye işlevi başarısız olur.

MFC'nin uygulamasında `GetCurSel`, belirtebileceğiniz bir `COleDateTime` kullanımı, bir `CTime` kullanımı, veya bir `SYSTEMTIME` yapısı kullanım.

##  <a name="getfirstdayofweek"></a>  CMonthCalCtrl::GetFirstDayOfWeek

Takvimin en soldaki sütunda görüntülenecek haftanın ilk gününü alır.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>Parametreler

*pbLocal*<br/>
BOOL değeri için bir işaretçi. Değer sıfır ise denetimin ayarı Denetim Masası'nda ayarı eşleşmiyor.

### <a name="return-value"></a>Dönüş Değeri

Haftanın ilk gününü temsil eder bir tamsayı değeri. Bkz: **açıklamalar** ne bu tamsayıları temsil hakkında daha fazla bilgi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETFIRSTDAYOFWEEK](/windows/desktop/Controls/mcm-getfirstdayofweek)Windows SDK içinde açıklandığı gibi. Haftanın günü gibi tamsayı olarak temsil edilir.

|Değer|Haftanın günü|
|-----------|---------------------|
|0|Pazartesi|
|1.|Salı|
|2|Çarşamba|
|3|Perşembe|
|4|Cuma|
|5|Cumartesi|
|6|Pazar|

### <a name="example"></a>Örnek

  Örneğin bakın [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek).

##  <a name="getmaxselcount"></a>  CMonthCalCtrl::GetMaxSelCount

Ay takvim denetim içinde seçilen gün geçerli maksimum sayısını alır.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilebilecek gün denetimi için toplam sayısını temsil eder bir tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETMAXSELCOUNT](/windows/desktop/Controls/mcm-getmaxselcount)Windows SDK içinde açıklandığı gibi. Bu üye işlevi MCS_MULTISELECT stili ayarlanmış denetimler için kullanın.

### <a name="example"></a>Örnek

  Örneğin bakın [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount).

##  <a name="getmaxtodaywidth"></a>  CMonthCalCtrl::GetMaxTodayWidth

"Bugün" dizesi geçerli ay Takvim denetimi için en fazla genişliğini alır.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

"Bugün" dizesi piksel cinsinden genişliği.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_monthCalCtrl`, yani aylık takvim denetiminin programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde `GetMaxTodayWidth` yöntemi.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>Açıklamalar

Kullanıcı, geçerli tarihe, aylık takvim denetiminin alt kısmında görüntülenen "Bugün" dize tıklayarak döndürebilir. "Bugün" dize ve tarih metin etiketi içerir.

Bu yöntem gönderir [MCM_GETMAXTODAYWIDTH](/windows/desktop/Controls/mcm-getmaxtodaywidth) Windows SDK'da açıklanan ileti.

##  <a name="getminreqrect"></a>  CMonthCalCtrl::GetMinReqRect

Aylık takvim denetiminin içinde tam bir ay göstermek için gereken en küçük boyut alır.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>Parametreler

*pRect*<br/>
Bir işaretçi bir [RECT](/previous-versions/dd162897\(v=vs.85\)) sınırlayıcı dikdörtgeni bilgi alacak yapısı. Bu parametre, geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bu üye işlevi sıfır döndürür ve `lpRect` uygun sınırlayıcı bilgileri alır. İşlem başarısız olursa, üye işlev 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETMINREQRECT](/windows/desktop/Controls/mcm-getminreqrect)Windows SDK içinde açıklandığı gibi.

##  <a name="getmonthdelta"></a>  CMonthCalCtrl::GetMonthDelta

Aylık takvim denetiminin kaydırma ücretine alır.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aylık takvim denetiminin kaydırma oranı. Kullanıcı kaydırma düğmesine bir kez tıkladığında denetimin görünümünü taşır ay sayısı kaydırma hızıdır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETMONTHDELTA](/windows/desktop/Controls/mcm-getmonthdelta)Windows SDK içinde açıklandığı gibi.

##  <a name="getmonthrange"></a>  CMonthCalCtrl::GetMonthRange

Aylık takvim denetiminin görünen üst ve alt sınırlarını temsil eden bilgilerini alır tarih.

```
int GetMonthRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    CTime& refMinRange,
    CTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange,
    DWORD dwFlags) const;
```

### <a name="parameters"></a>Parametreler

*refMinRange*<br/>
Bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) izin verilen en erken tarih içeren bir nesne.

*refMaxRange*<br/>
Bir başvuru bir `COleDateTime` veya `CTime` izin verilen maksimum tarih içeren bir nesne.

*pMinRange*<br/>
Bir işaretçi bir [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) aralığının en düşük bitiş tarihini içeren yapısı.

*pMaxRange*<br/>
Bir işaretçi bir `SYSTEMTIME` tarih aralığı en sonunda içeren yapısı.

*CertOpenStore*<br/>
Alınacak aralığı sınırları kapsamını belirten değer. Bu değer aşağıdakilerden biri olması gerekir.

|Değer|Açıklama|
|-----------|-------------|
|GMR_DAYSTATE|Önceki ve sonraki görünür aralığı yalnızca kısmen görüntülenen ayı sondaki içerir.|
|GMR_VISIBLE|Tamamen görüntülenen ay içerir.|

### <a name="return-value"></a>Dönüş Değeri

İki sınır tarafından kapsanan aylarda, aralığı temsil eden bir tamsayı gösterilen *refMinRange* ve *refMaxRange* birinci ve ikinci sürümlerinde veya *pMinRange* ve *pMaxRange* üçüncü sürümü.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETMONTHRANGE](/windows/desktop/Controls/mcm-getmonthrange)Windows SDK içinde açıklandığı gibi. MFC'nin uygulamasında `GetMonthRange`, belirtebilirsiniz `COleDateTime` kullanımı, bir `CTime` kullanımı veya `SYSTEMTIME` yapı kullanımı.

### <a name="example"></a>Örnek

  Örneğin bakın [CMonthCalCtrl::SetDayState](#setdaystate).

##  <a name="getrange"></a>  CMonthCalCtrl::GetRange

Bir ay takvimi ayarlama geçerli minimum ve maksimum tarih alır.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;

DWORD GetRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Parametreler

*pMinRange*<br/>
Bir işaretçi bir `COleDateTime` nesnesi bir `CTime` nesnesi veya [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) aralığının en düşük bitiş tarihini içeren yapısı.

*pMaxRange*<br/>
Bir işaretçi bir `COleDateTime` nesnesi bir `CTime` nesnesi veya [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) tarih aralığı en sonunda içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfır olabilir bir DWORD (sınırsız ayarlanır) veya limitlerinin belirten aşağıdaki değerlerinin bir birleşimi.

|Değer|Açıklama|
|-----------|-------------|
|GDTR_MAX|Bir üst sınır denetim için ayarlanır; *pMaxRange* geçerli olduğundan ve geçerli tarih bilgileri içerir.|
|GDTR_MIN|Denetim için alt sınır ayarlanır; *pMinRange* geçerli olduğundan ve geçerli tarih bilgileri içerir.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETRANGE](/windows/desktop/Controls/mcm-getrange)Windows SDK içinde açıklandığı gibi. MFC'nin uygulamasında `GetRange`, belirtebileceğiniz bir `COleDateTime` kullanımı, bir `CTime` kullanımı, veya bir `SYSTEMTIME` yapısı kullanım.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

##  <a name="getselrange"></a>  CMonthCalCtrl::GetSelRange

Kullanıcı tarafından şu anda seçili tarih aralığı üst ve alt sınırlarını temsil eden tarih bilgilerini alır.

```
BOOL GetSelRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange) const;

BOOL GetSelRange(
    CTime& refMinRange,
    CTime& refMaxRange) const;

BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Parametreler

*refMinRange*<br/>
Bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) izin verilen en erken tarih içeren bir nesne.

*refMaxRange*<br/>
Bir başvuru bir `COleDateTime` veya `CTime` izin verilen maksimum tarih içeren bir nesne.

*pMinRange*<br/>
Bir işaretçi bir [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) aralığının en düşük bitiş tarihini içeren yapısı.

*pMaxRange*<br/>
Bir işaretçi bir `SYSTEMTIME` tarih aralığı en sonunda içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETSELRANGE](/windows/desktop/Controls/mcm-getselrange)Windows SDK içinde açıklandığı gibi. `GetSelRange` MCS_MULTISELECT stili kullanmayan bir aylık takvim denetiminin uyguladıysanız başarısız olur.

MFC'nin uygulamasında `GetSelRange`, belirtebilirsiniz `COleDateTime` kullanımı, bir `CTime` kullanımı veya `SYSTEMTIME` yapı kullanımı.

##  <a name="gettoday"></a>  CMonthCalCtrl::GetToday

"Bugün" için bir ay takvimi olarak belirtilen tarih için tarih bilgilerini alır.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) geçerli günü gösteren nesne.

*pDateTime*<br/>
Bir işaretçi bir [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) tarih bilgilerini alacak yapısı. Bu parametre, geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_GETTODAY](/windows/desktop/Controls/mcm-gettoday)Windows SDK içinde açıklandığı gibi. MFC'nin uygulamasında `GetToday`, belirtebileceğiniz bir `COleDateTime` kullanımı, bir `CTime` kullanımı, veya bir `SYSTEMTIME` yapısı kullanım.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

##  <a name="hittest"></a>  CMonthCalCtrl::HitTest

Herhangi biri, ise belirtilen konumda hangi aylık takvim denetiminin belirler.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>Parametreler

*pMCHitTest*<br/>
Bir işaretçi bir [MCHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-mchittestinfo) isabet sınaması içeren yapısı için aylık takvim denetiminin işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Bir DWORD değeri. Eşit **uHit** üyesi `MCHITTESTINFO` yapısı.

### <a name="remarks"></a>Açıklamalar

`HitTest` kullanan `MCHITTESTINFO` yapısı, isabet testi hakkında bilgi içerir.

##  <a name="iscenturyview"></a>  CMonthCalCtrl::IsCenturyView

Geçerli ay Takvim denetimi geçerli görünümünü. yüzyıla uygun görünüm olup olmadığını gösterir.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünümü. yüzyıla uygun görünüm ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK'da açıklanan ileti. Bu yöntem, bu iletiyi MCMV_CENTURY döndürürse, TRUE döndürür.

##  <a name="isdecadeview"></a>  CMonthCalCtrl::IsDecadeView

Geçerli ay Takvim denetimi geçerli görünümünü on görünümü olup olmadığını belirtir.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünümü on görünüm ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK'da açıklanan ileti. Bu yöntem, bu iletiyi MCMV_DECADE döndürürse, TRUE döndürür.

##  <a name="ismonthview"></a>  CMonthCalCtrl::IsMonthView

Geçerli ay Takvim denetimi geçerli görünümünü ay görünümü olup olmadığını belirtir.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünümü ay görünüm ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK'da açıklanan ileti. Bu yöntem, bu iletiyi MCMV_MONTH döndürürse, TRUE döndürür.

##  <a name="isyearview"></a>  CMonthCalCtrl::IsYearView

Geçerli ay Takvim denetimi geçerli görünümünü yıl görünümü olup olmadığını gösterir.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünümü yıl görünüm ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK'da açıklanan ileti. Bu yöntem, bu iletiyi MCMV_YEAR döndürürse, TRUE döndürür.

##  <a name="setcalendarborder"></a>  CMonthCalCtrl::SetCalendarBorder

Geçerli ay Takvim denetimi kenarlığı genişliğini belirler.

```
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*cxyBorder*|[in] Kenarlığın piksel cinsinden genişliği.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarılı olursa kenarlık genişliği kümesine *cxyBorder* parametresi. Kenarlık genişliği Aksi takdirde, geçerli belirtilen varsayılan değere sıfırlanır [tema](/windows/desktop/Controls/visual-styles-overview), veya Temalar kullanılmazsa sıfır.

Bu yöntem gönderir [MCM_SETCALENDARBORDER](/windows/desktop/Controls/mcm-setcalendarborder) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_monthCalCtrl`, yani aylık takvim denetiminin programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Ay takvim kenarlık genişliği denetlemek için sekiz piksel aşağıdaki kod örneği ayarlar. Kullanım [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) bu yöntem başarılı olup olmadığını belirlemek için yöntemi.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

##  <a name="setcalendarborderdefault"></a>  CMonthCalCtrl::SetCalendarBorderDefault

Geçerli ay Takvim denetimi kenarlığın varsayılan genişliğini ayarlar.

```
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>Açıklamalar

Kenarlık genişliği geçerli belirtilen varsayılan değere ayarlanır [tema](/windows/desktop/Controls/visual-styles-overview), veya Temalar kullanılmazsa sıfır.

Bu yöntem gönderir [MCM_SETCALENDARBORDER](/windows/desktop/Controls/mcm-setcalendarborder) Windows SDK'da açıklanan ileti.

##  <a name="setcalid"></a>  CMonthCalCtrl::SetCalID

Takvim tanımlayıcısı geçerli ay Takvim denetimi için ayarlar.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*calid*|[in] Aşağıdakilerden birini [Takvim tanımlayıcısı](/windows/desktop/Intl/calendar-identifiers) sabitler.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir takvim Gregoryen (yerelleştirilmiş), Japonca veya Hicri gibi bir bölgeye özgü Takvim belirtir takvimler. Kullanım `SetCalID` yöntemi tarafından belirtilen bir takvim görüntülenecek *calid* Takvim içeren yerel bilgisayarınızda yüklüyse parametresi.

Bu yöntem gönderir [MCM_SETCALID](/windows/desktop/Controls/mcm-setcalid) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_monthCalCtrl`, yani aylık takvim denetiminin programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık takvim denetiminin Japonca İmparatorluk dönemi takvim görüntülemek için ayarlar. `SetCalID` Yöntemi yalnızca o takvimin bilgisayarınızda yüklüyse başarılı olur.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

##  <a name="setcenturyview"></a>  CMonthCalCtrl::SetCenturyView

Yüzyıl görüntülemek için geçerli aylık takvim denetiminin ayarlar.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [CMonthCalCtrl::SetCurrentView](#setcurrentview) görünümü ayarlamak için yöntemi `MCMV_CENTURY`, yüzyıl görünümü temsil eder.

##  <a name="setcolor"></a>  CMonthCalCtrl::SetColor

Belirtilen bir alan aylık takvim denetiminin rengini ayarlar.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>Parametreler

*nRegion*<br/>
Ayarlanacak hangi Ay takvim rengini belirten bir tamsayı değeri. Bu değer aşağıdakilerden biri olabilir.

|Değer|Açıklama|
|-----------|-------------|
|MCSC_BACKGROUND|Arasındaki ay görüntülenen arka plan rengi.|
|MCSC_MONTHBK|Ay içinde görüntülenen arka plan rengi.|
|MCSC_TEXT|Bir ay içinde metin görüntülemek için kullanılan renk.|
|MCSC_TITLEBK|Takvimin başlığı görüntülenen arka plan rengi.|
|MCSC_TITLETEXT|Takvimin başlığı içindeki metni görüntülemek için kullanılan renk.|
|MCSC_TRAILINGTEXT|Üstbilgi ve sondaki günlük metnini görüntülemek için kullanılan renk. Üst bilgi ve sondaki gün geçerli Takvim üzerinde görünen önceki ve sonraki aya ait günler geride kaldı.|

*ref*<br/>
Aylık takvim denetiminin belirtilen kısmı için yeni renk ayarı için COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

COLORREF değeri, önceki renk ayarı için belirtilen bölümü aylık takvim denetiminin başarılı olursa temsil eder. Aksi takdirde bu ileti, -1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETCOLOR](/windows/desktop/Controls/mcm-setcolor)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

##  <a name="setcurrentview"></a>  CMonthCalCtrl::SetCurrentView

Belirtilen görüntülemek için geçerli aylık takvim denetiminin ayarlar.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwNewView*|[in] Aylık, yıllık, on veya. yüzyıla uygun görünüm belirten aşağıdaki değerlerden biri.<br /><br /> MCMV_MONTH: Aylık görüntüle<br /><br /> MCMV_YEAR: Yıllık görüntüle<br /><br /> MCMV_DECADE: On görüntüle<br /><br /> MCMV_CENTURY: Yüzyıl görüntüle|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [MCM_SETCURRENTVIEW](/windows/desktop/Controls/mcm-setcurrentview) Windows SDK'da açıklanan ileti.

##  <a name="setcursel"></a>  CMonthCalCtrl::SetCurSel

Aylık takvim denetiminin seçili tarihini ayarlar.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) seçili aylık takvim denetiminin gösteren nesne.

*pDateTime*<br/>
İşaretçi bir [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) geçerli seçimi olarak ayarlanması tarihi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETCURSEL](/windows/desktop/Controls/mcm-setcursel)Windows SDK içinde açıklandığı gibi. MFC'nin uygulamasında `SetCurSel`, belirtebileceğiniz bir `COleDateTime` kullanımı, bir `CTime` kullanımı, veya bir `SYSTEMTIME` yapısı kullanım.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

##  <a name="setdaystate"></a>  CMonthCalCtrl::SetDayState

Gün için görünen bir ay takvimi ayarlar.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>Parametreler

*nMonths*<br/>
Kaç öğenin dizesindedir gösteren değeri, *pStates* işaret eder.

*pStates*<br/>
Bir işaretçi bir [MONTHDAYSTATE](/windows/desktop/Controls/monthdaystate) aylık takvim denetiminin görünümünü her gün nasıl çizer tanımlayan değerleri dizisi. MONTHDAYSTATE veri türü, ayda bir gün durumunu her bit (1 ile 31) temsil ettiği bit alanıdır. Üzerinde bir bit ise, karşılık gelen günün görüntülenir, kalın; Aksi takdirde hiçbir Vurgu ile görüntülenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETDAYSTATE](/windows/desktop/Controls/mcm-setdaystate)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

##  <a name="setdecadeview"></a>  CMonthCalCtrl::SetDecadeView

Ayarlar decade görünümüne geçerli ay Takvim denetimi.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [CMonthCalCtrl::SetCurrentView](#setcurrentview) görünümü ayarlamak için yöntemi `MCMV_DECADE`, decade görünümü temsil eder.

##  <a name="setfirstdayofweek"></a>  CMonthCalCtrl::SetFirstDayOfWeek

Takvimin en soldaki sütunda görüntülenecek haftanın gününü ayarlar.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>Parametreler

*iDay*<br/>
Haftanın ilk günü ayarlanacak gününü temsil eden bir tamsayı değeri var. Bu değer, gün sayıları biri olmalıdır. Bkz: [GetFirstDayOfWeek](#getfirstdayofweek) gün sayıları açıklaması.

*lpnOld*<br/>
Daha önce haftanın ilk gününü belirten bir tamsayı işaretçisi ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Haftanın ilk günü önceki LOCALE_IFIRSTDAYOFWEEK farklı bir değere ayarlanırsa sıfır değilse, Denetim Masası ayarında belirtilen gün olduğu. Aksi takdirde, bu işlev 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETFIRSTDAYOFWEEK](/windows/desktop/Controls/mcm-setfirstdayofweek)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

##  <a name="setmaxselcount"></a>  CMonthCalCtrl::SetMaxSelCount

En fazla bir ay takvimi seçilen gün sayısını ayarlar.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>Parametreler

*nMax*<br/>
Maksimum seçilebilir gün sayısını temsil etmek için ayarlanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETMAXSELCOUNT](/windows/desktop/Controls/mcm-setmaxselcount)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

##  <a name="setmonthdelta"></a>  CMonthCalCtrl::SetMonthDelta

Aylık takvim denetiminin kaydırma ücretine ayarlar.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>Parametreler

*iDelta*<br/>
Denetimin kaydırma oranı ayarlanacak ayların sayısı. Bu değeri sıfır ise, ay delta denetimde görüntülenen ay sayısı, varsayılan olarak sıfırlanıyor.

### <a name="return-value"></a>Dönüş Değeri

Önceki kaydırma oranı. Kaydırma oranı daha önce ayarlanmamışsa, dönüş değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETMONTHDELTA](/windows/desktop/Controls/mcm-setmonthdelta)Windows SDK içinde açıklandığı gibi.

##  <a name="setmonthview"></a>  CMonthCalCtrl::SetMonthView

Ay görüntülemek için geçerli aylık takvim denetiminin ayarlar.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [CMonthCalCtrl::SetCurrentView](#setcurrentview) ay görünümünü temsil eden MCMV_MONTH için görünümü ayarlamak için yöntemi.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_monthCalCtrl`, yani aylık takvim denetiminin programlı olarak erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, ay, yıl, decade ve yüzyıl görünümleri görüntülemek için aylık takvim denetiminin ayarlar.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

##  <a name="setrange"></a>  CMonthCalCtrl::SetRange

Aylık takvim denetiminin için minimum ve maksimum izin verilen tarihleri ayarlar.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);

BOOL SetRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Parametreler

*pMinRange*<br/>
Bir işaretçi bir `COleDateTime` nesnesi bir `CTime` nesnesi veya [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) aralığının en düşük bitiş tarihini içeren yapısı.

*pMaxRange*<br/>
Bir işaretçi bir `COleDateTime` nesnesi bir `CTime` nesnesi veya `SYSTEMTIME` tarih aralığı en sonunda içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETRANGE](/windows/desktop/Controls/mcm-setrange)Windows SDK içinde açıklandığı gibi. MFC'nin uygulamasında `SetRange`, belirtebilirsiniz `COleDateTime` kullanımı, bir `CTime` kullanımı veya `SYSTEMTIME` yapı kullanımı.

### <a name="example"></a>Örnek

  Örneğin bakın [CMonthCalCtrl::GetRange](#getrange).

##  <a name="setselrange"></a>  CMonthCalCtrl::SetSelRange

Ay takvim seçimini kümeleri belirli bir tarih aralığındaki için denetler.

```
BOOL SetSelRange(
    const COleDateTime& pMinRange,
    const COleDateTime& pMaxRange);

BOOL SetSelRange(
    const CTime& pMinRange,
    const CTime& pMaxRange);

BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Parametreler

*pMinRange*<br/>
Bir işaretçi bir `COleDateTime` nesnesi bir `CTime` nesnesi veya [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) aralığının en düşük bitiş tarihini içeren yapısı.

*pMaxRange*<br/>
Bir işaretçi bir `COleDateTime` nesnesi bir `CTime` nesnesi veya `SYSTEMTIME` tarih aralığı en sonunda içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETSELRANGE](/windows/desktop/Controls/mcm-setselrange)Windows SDK içinde açıklandığı gibi. MFC'nin uygulamasında `SetSelRange`, belirtebilirsiniz `COleDateTime` kullanımı, bir `CTime` kullanımı veya `SYSTEMTIME` yapı kullanımı.

##  <a name="settoday"></a>  CMonthCalCtrl::SetToday

Takvim denetiminin gün için geçerli ayarlar.

```
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
  void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Bir başvuru bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) geçerli tarihi içeren nesne.

*pDateTime*<br/>
İkinci sürümünde, bir işaretçi bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) geçerli tarih bilgileri içeren nesne. Üçüncü sürümünde, bir işaretçi bir [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) geçerli tarih bilgileri içeren yapısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [MCM_SETTODAY](/windows/desktop/Controls/mcm-settoday)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

  Örneğin bakın [CMonthCalCtrl::GetToday](#gettoday).

##  <a name="setyearview"></a>  CMonthCalCtrl::SetYearView

Ayarlar geçerli ay takvim yılı görünümüne denetler.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [CMonthCalCtrl::SetCurrentView](#setcurrentview) yıllık görünümünü temsil eder MCMV_YEAR görünümü ayarlamak için yöntemi.

##  <a name="sizeminreq"></a>  CMonthCalCtrl::SizeMinReq

Görüntüler, bir ay takvimi minimum boyut ay görüntüler.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>Parametreler

*bRepaint*<br/>
Denetimin boyanacak olup olmadığını belirtir. Varsayılan olarak TRUE. FALSE ise, hiçbir yeniden çizerken gerçekleşir.

### <a name="return-value"></a>Dönüş Değeri

Aylık takvim denetiminin için minimum boyutlandırılır olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırma `SizeMinReq` başarıyla bir ayın takvim için tüm ay Takvim denetimi görüntüler.

##  <a name="sizerecttomin"></a>  CMonthCalCtrl::SizeRectToMin

Geçerli ay Takvim denetimi için belirtilen bir dikdörtgenine tüm takvimleri içeren küçük dikdörtgen hesaplar.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpRect*|[in] İşaretçi bir [RECT](/previous-versions/dd162897\(v=vs.85\)) takvimler istenen sayısını içeren bir dikdörtgen tanımlayan yapısını.|

### <a name="return-value"></a>Dönüş Değeri

İşaretçi bir [RECT](/previous-versions/dd162897\(v=vs.85\)) boyutu dikdörtgen küçük veya ona eşit olan bir dikdörtgen tanımlayan yapısını tarafından tanımlanan *lpRect* parametresi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından belirtilen dikdörtgen olarak kaç takvimler sığabilen hesaplar *lpRect* parametresi ve ardından söz konusu sayı kadar takvimleri içeren küçük bir dikdörtgen döndürür. Aslında, bu yöntem, takvimler istenen sayısı tam olarak sığması için belirtilen dikdörtgen küçültür.

Bu yöntem gönderir [MCM_SIZERECTTOMIN](/windows/desktop/Controls/mcm-sizerecttomin) Windows SDK'da açıklanan ileti.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDateTimeCtrl Sınıfı](../../mfc/reference/cdatetimectrl-class.md)
