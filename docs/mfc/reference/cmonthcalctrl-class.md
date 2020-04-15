---
title: CMonthCalCtrl Sınıfı
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
ms.openlocfilehash: da9d588811361d3dfd72d44d5b9ced8460d23936
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319750"
---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl Sınıfı

Bir aylık takvim denetiminin işlevselliğini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|Bir `CMonthCalCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMonthCalCtrl::Oluştur](#create)|Bir ay takvim denetimi oluşturur ve `CMonthCalCtrl` nesneye bağlar.|
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|Geçerli ay takvim denetiminin kenarlığı genişliğini alır.|
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|Geçerli ay takvim denetiminde görüntülenen takvim sayısını alır.|
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|Geçerli ay takvim denetimi yle ilgili bilgileri alır.|
|[CMonthCalCtrl::GetCalID](#getcalid)|Geçerli ay takvim denetimi için takvim tanımlayıcısını alır.|
|[CMonthCalCtrl::GetColor](#getcolor)|Bir aylık takvim denetiminin belirli bir alanının rengini alır.|
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|Geçerli ay takvim denetimi tarafından görüntülenen görünümü alır.|
|[CMonthCalCtrl::GetCurSel](#getcursel)|Şu anda seçilen tarihe göre sistem saatini alır.|
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|Haftanın ilk gününün takvimin en sol sütununda görüntülenmesini alır.|
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Bir ay takvim denetiminde seçilebilen geçerli maksimum gün sayısını alır.|
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|Geçerli ay takvim denetimi için "Bugün" dizesinin maksimum genişliğini alır.|
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Bir ay takvim denetiminde tam bir ayı göstermek için gereken minimum boyutu alır.|
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Bir aylık takvim denetimi için kaydırma hızını alır.|
|[CMonthCalCtrl::GetMonthAralığı](#getmonthrange)|Bir aylık takvim denetiminin yüksek ve düşük sınırlarını gösteren tarih bilgilerini alır.|
|[CMonthCalCtrl::GetRange](#getrange)|Bir aylık takvim denetiminde ayarlanan geçerli minimum ve maksimum tarihleri alır.|
|[CMonthCalCtrl::GetSelRange](#getselrange)|Kullanıcı tarafından seçilen tarih aralığının üst ve alt sınırlarını gösteren tarih bilgilerini alır.|
|[CMonthCalCtrl::GetToday](#gettoday)|Bir aylık takvim denetimi için "bugün" olarak belirtilen tarihe ait tarih bilgilerini alır.|
|[CMonthCalCtrl::HitTest](#hittest)|Bir ayın takvim denetiminin hangi bölümünün ekranda belirli bir noktada olduğunu belirler.|
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|Geçerli ay takvim denetiminin geçerli görünümünün yüzyıl görünümü olup olmadığını gösterir.|
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|Geçerli ay takvim denetiminin geçerli görünümünün on yıl görünümü olup olmadığını gösterir.|
|[CMonthCalCtrl::IsMonthView](#ismonthview)|Geçerli ay takvim denetiminin geçerli görünümünün ay görünümü olup olmadığını gösterir.|
|[CMonthCalCtrl::IsYearView](#isyearview)|Geçerli ay takvim denetiminin geçerli görünümünün yıl görünümü olup olmadığını gösterir.|
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|Geçerli ay takvim denetiminin kenarlığı genişliğini ayarlar.|
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|Geçerli ay takvim denetiminin kenarlığı varsayılan genişliğini ayarlar.|
|[CMonthCalCtrl::SetCalID](#setcalid)|Geçerli ay takvim denetimi için takvim tanımlayıcısını ayarlar.|
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|Yüzyıl görünümünü görüntülemek için geçerli ay takvim denetimini ayarlar.|
|[CMonthCalCtrl::SetColor](#setcolor)|Bir aylık takvim denetiminin belirli bir alanının rengini ayarlar.|
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|Belirtilen görünümü görüntülemek için geçerli ay takvim denetimini ayarlar.|
|[CMonthCalCtrl::SetCurSel](#setcursel)|Bir aylık takvim denetimi için seçili tarihi ayarlar.|
|[CMonthCalCtrl::SetDayState](#setdaystate)|Bir ay takvim denetiminde ekranı günler için ayarlar.|
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|Geçerli ay takvim denetimini on yıl görünümüne ayarlar.|
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|Takvimin en sol sütununda görüntülenecek haftanın gününü ayarlar.|
|[CMonthCalCtrl::SetMaxSelSayısı](#setmaxselcount)|Bir aylık takvim denetiminde seçilebilen en fazla gün sayısını ayarlar.|
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Kaydırma hızını bir aylık takvim denetimi için ayarlar.|
|[CMonthCalCtrl::SetMonthView](#setmonthview)|Ay görünümünü görüntülemek için geçerli ay takvim denetimini ayarlar.|
|[CMonthCalCtrl::SetAralığı](#setrange)|Bir aylık takvim denetimi için izin verilen minimum ve maksimum tarihleri ayarlar.|
|[CMonthCalCtrl::SetSelRange](#setselrange)|Bir aylık takvim denetimi için seçimi belirli bir tarih aralığına ayarlar.|
|[CMonthCalCtrl::SetToday](#settoday)|Geçerli günün takvim denetimini ayarlar.|
|[CMonthCalCtrl::SetYearView](#setyearview)|Geçerli ay takvim denetimini yıl görünümüne ayarlar.|
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|Ay takvimi denetimini en az bir aylık boyutuna yeniden boyar.|
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|Geçerli ay takvim denetimi için, belirli bir dikdörtgen sığdırılan tüm takvimleri içerebilecek en küçük dikdörtgeni hesaplar.|

## <a name="remarks"></a>Açıklamalar

Ay takvimi denetimi, kullanıcıya, kullanıcının bir tarih seçebileceği basit bir takvim arabirimi sağlar. Kullanıcı ekranı aşağıdaki şekilde değiştirebilir:

- Aydan aya ileri ve geri kaydırma.

- Geçerli günü görüntülemek için Bugün metnini tıklatma (MCS_NOTODAY stili kullanılmazsa).

- Açılır menüden bir ay veya bir yıl seçme.

Oluşturduğunuzda nesneye çeşitli stiller uygulayarak ay takvimi denetimini özelleştirebilirsiniz. Bu stiller, Windows SDK'daki [Ay Takvim Denetim Stilleri'nde](/windows/win32/Controls/month-calendar-control-styles) açıklanmıştır.

Ay takvimi denetimi bir aydan fazla görüntülenebilir ve tarihi kalınarak özel günleri (tatiller gibi) gösterebilir.

Ay takvimi denetimini kullanma hakkında daha fazla bilgi için [bkz.](../../mfc/using-cmonthcalctrl.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdtctl.h

## <a name="cmonthcalctrlcmonthcalctrl"></a><a name="cmonthcalctrl"></a>CMonthCalCtrl::CMonthCalCtrl

Bir `CMonthCalCtrl` nesne inşa eder.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi `Create` yaptıktan sonra aramalısınız.

## <a name="cmonthcalctrlcreate"></a><a name="create"></a>CMonthCalCtrl::Oluştur

Bir ay takvim denetimi oluşturur ve `CMonthCalCtrl` nesneye bağlar.

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

*Dwstyle*<br/>
Ay takvimi denetimine uygulanan Windows stillerinin birleşimini belirtir. Stiller hakkında daha fazla bilgi için Windows SDK'daki [Aylık Takvim Denetim Stilleri'ne](/windows/win32/Controls/month-calendar-control-styles) bakın.

*Rect*<br/>
[RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına bir başvuru. Ay takvim denetiminin konumunu ve boyutunu içerir.

*Pt*<br/>
Ay takvim denetiminin konumunu tanımlayan bir [POINT](/previous-versions/dd162805\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Ay takvimi denetiminin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi. NULL olmamalıdır.

*Nıd*<br/>
Ay takvim denetiminin denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir aylık takvim denetimi oluşturun:

1. Bir `CMonthCalCtrl` nesne oluşturmak için [CMonthCalCtrl'yi](../../mfc/reference/cmonthcalctrl-class.md) arayın.

1. Bir aylık takvim denetimi oluşturan ve `CMonthCalCtrl` nesneye iliştiren bu üye işlevi çağırın.

Aradığınızda, `Create`ortak denetimler baş harfe çağrılır. Aramanız `Create` ın sürümü nasıl boyutlandırıldığını belirler:

- MFC'nin denetimi otomatik olarak bir aya boyutlandırması için *pt* parametresini kullanan geçersiz kılmayı arayın.

- Denetimi kendiniz boyutlandırmak *için, düzeltme* parametresini kullanan bu işlevin geçersiz kılınmasını arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

## <a name="cmonthcalctrlgetcalendarborder"></a><a name="getcalendarborder"></a>CMonthCalCtrl::GetCalendarBorder

Geçerli ay takvim denetiminin kenarlığı genişliğini alır.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim kenarlığı genişliği, piksel.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCALENDARBORDER](/windows/win32/Controls/mcm-getcalendarborder) iletisini gönderir.

## <a name="cmonthcalctrlgetcalendarcount"></a><a name="getcalendarcount"></a>CMonthCalCtrl::GetCalendarCount

Geçerli ay takvim denetiminde görüntülenen takvim sayısını alır.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ay takvimi denetiminde görüntülenen takvim sayısı. İzin verilen en fazla takvim sayısı 12'dir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCALENDARCOUNT](/windows/win32/Controls/mcm-getcalendarcount) iletisini gönderir.

## <a name="cmonthcalctrlgetcalendargridinfo"></a><a name="getcalendargridinfo"></a>CMonthCalCtrl::GetCalendarGridInfo

Geçerli ay takvim denetimi yle ilgili bilgileri alır.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pmcGridInfo*|[çıkış] Geçerli ay takvim denetimi hakkında bilgi alan bir [MCGRIDINFO](/windows/win32/api/commctrl/ns-commctrl-mcgridinfo) yapısını işaretçi. Arayan, bu yapıyı ayırmak ve başlatmaktan sorumludur.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCALENDARGRIDINFO](/windows/win32/Controls/mcm-getcalendargridinfo) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_monthCalCtrl`ay takvim denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `GetCalendarGridInfo` geçerli ay takvim denetiminin görüntülenebilen takvim tarihini almak için yöntemi kullanır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

## <a name="cmonthcalctrlgetcalid"></a><a name="getcalid"></a>CMonthCalCtrl::GetCalID

Geçerli ay takvim denetimi için takvim tanımlayıcısını alır.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Takvim tanımlayıcı](/windows/win32/Intl/calendar-identifiers) sabitlerinden biri.

### <a name="remarks"></a>Açıklamalar

Takvim tanımlayıcısı, Gregoryen (yerelleştirilmiş), Japonca veya Hicri takvimler gibi bölgeye özgü bir takvimi gösterir. Uygulamanız, çeşitli dil destek işlevlerine sahip bir takvim tanımlayıcısı kullanabilir.

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCALID](/windows/win32/Controls/mcm-getcalid) iletisini gönderir.

## <a name="cmonthcalctrlgetcolor"></a><a name="getcolor"></a>CMonthCalCtrl::GetColor

*NRegion*tarafından belirtilen ay takvim denetiminin bir alanının rengini alır.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>Parametreler

*nBölge*<br/>
Rengin alındığı ay takvim denetiminin bölgesi. Değerler listesi [için, SetColor'un](#setcolor) *nRegion* parametresini görün.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ay takvim denetiminin bölümüyle ilişkili rengi belirten bir [COLORREF](/windows/win32/gdi/colorref) değeri. Aksi takdirde, bu üye işlev -1 döndürür.

## <a name="cmonthcalctrlgetcurrentview"></a><a name="getcurrentview"></a>CMonthCalCtrl::GetCurrentView

Geçerli ay takvim denetimi tarafından görüntülenen görünümü alır.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biriyle gösterilen geçerli görünüm:

|Değer|Anlamı|
|-----------|-------------|
|MCMV_MONTH|Aylık görünüm|
|MCMV_YEAR|Yıllık görünüm|
|MCMV_DECADE|On yıl görünümü|
|MCMV_CENTURY|Yüzyıl görünümü|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_monthCalCtrl`ay takvim denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Ay takvimi denetimini görüntüleyen aşağıdaki kod örneği şu anda görüntülenir.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

## <a name="cmonthcalctrlgetcursel"></a><a name="getcursel"></a>CMonthCalCtrl::GetCurSel

Şu anda seçilen tarihe göre sistem saatini alır.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru. Geçerli saati alır.

*pDateTime*<br/>
Şu anda seçili tarih bilgilerini alacak bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısıiçin bir işaretçi. Bu parametre geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; otherwize 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/mcm-getcursel)iletisinin MCM_GETCURSEL davranışını uygular.

> [!NOTE]
> Stil MCS_MULTISELECT ayarlanırsa bu üye işlev başarısız olur.

MFC'nin `GetCurSel`uygulanmasında, bir `COleDateTime` kullanım, bir `CTime` kullanım veya `SYSTEMTIME` yapı kullanımı belirtebilirsiniz.

## <a name="cmonthcalctrlgetfirstdayofweek"></a><a name="getfirstdayofweek"></a>CMonthCalCtrl::GetFirstDayOfWeek

Haftanın ilk gününün takvimin en sol sütununda görüntülenmesini alır.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>Parametreler

*pbYerel*<br/>
BOOL değeri için bir işaretçi. Değer sıfır değilse, denetimin ayarı denetim panelindeki ayarı eşleştirmez.

### <a name="return-value"></a>Dönüş Değeri

Haftanın ilk gününü temsil eden bir sonda değeri. Bu tümsanelerin neyi temsil ediyor olduğu hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_GETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-getfirstdayofweek)davranışını uygular. Haftanın günleri aşağıdaki gibi, tümsedo olarak temsil edilir.

|Değer|Haftanın günü|
|-----------|---------------------|
|0|Pazartesi|
|1|Salı|
|2|Çarşamba|
|3|Perşembe|
|4|Cuma|
|5|Cumartesi|
|6|Pazar|

### <a name="example"></a>Örnek

  CMonthCalCtrl için örneğe [bakın:SetFirstDayOfWeek](#setfirstdayofweek).

## <a name="cmonthcalctrlgetmaxselcount"></a><a name="getmaxselcount"></a>CMonthCalCtrl::GetMaxSelCount

Bir ay takvim denetiminde seçilebilen geçerli maksimum gün sayısını alır.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim için seçilebilen toplam gün sayısını temsil eden bir tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_GETMAXSELCOUNT](/windows/win32/Controls/mcm-getmaxselcount)davranışını uygular. MCS_MULTISELECT stil kümesine sahip denetimler için bu üye işlevi kullanın.

### <a name="example"></a>Örnek

  [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)için örneğe bakın.

## <a name="cmonthcalctrlgetmaxtodaywidth"></a><a name="getmaxtodaywidth"></a>CMonthCalCtrl::GetMaxTodayWidth

Geçerli ay takvim denetimi için "Bugün" dizesinin maksimum genişliğini alır.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

"Bugün" dizesinin genişliği, piksel olarak.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_monthCalCtrl`ay takvim denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `GetMaxTodayWidth` yöntemi gösterir.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>Açıklamalar

Kullanıcı, ay takvimi denetiminin alt kısmında görüntülenen "Bugün" dizesini tıklatarak geçerli tarihe dönebilir. "Bugün" dizesi etiket metni ve tarih metniiçerir.

Bu yöntem, Windows SDK'da açıklanan [MCM_GETMAXTODAYWIDTH](/windows/win32/Controls/mcm-getmaxtodaywidth) iletisini gönderir.

## <a name="cmonthcalctrlgetminreqrect"></a><a name="getminreqrect"></a>CMonthCalCtrl::GetMinReqRect

Bir ay takvim denetiminde tam bir ayı göstermek için gereken minimum boyutu alır.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>Parametreler

*pRect*<br/>
Sınırlayıcı dikdörtgen bilgileri alacak bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısıiçin bir işaretçi. Bu parametre geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu üye işlev `lpRect` sıfırsız döndürür ve geçerli sınır bilgilerini alır. Başarısız olursa, üye işlev 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/mcm-getminreqrect)iletisi MCM_GETMINREQRECT davranışını uygular.

## <a name="cmonthcalctrlgetmonthdelta"></a><a name="getmonthdelta"></a>CMonthCalCtrl::GetMonthDelta

Bir aylık takvim denetimi için kaydırma hızını alır.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ay takvim denetimi için kaydırma hızı. Kaydırma hızı, kullanıcı kaydırma düğmesini bir kez tıklattığında denetimin ekranını hareket ettiren ay sayısıdır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_GETMONTHDELTA](/windows/win32/Controls/mcm-getmonthdelta)davranışını uygular.

## <a name="cmonthcalctrlgetmonthrange"></a><a name="getmonthrange"></a>CMonthCalCtrl::GetMonthAralığı

Bir aylık takvim denetiminin yüksek ve düşük sınırlarını gösteren tarih bilgilerini alır.

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
İzin verilen minimum tarihi içeren bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*refMaxRange*<br/>
İzin verilen `COleDateTime` en `CTime` yüksek tarihi içeren bir veya nesneye başvuru.

*pMinAralığı*<br/>
Aralığın en alt ucundaki tarihi içeren bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

*pMaxRange*<br/>
Aralığın en `SYSTEMTIME` yüksek sonundaki tarihi içeren bir yapıya işaretçi.

*Dwflags*<br/>
Alınacak aralık sınırlarının kapsamını belirten değer. Bu değer aşağıdakilerden biri olmalıdır.

|Değer|Anlamı|
|-----------|-------------|
|GMR_DAYSTATE|Yalnızca kısmen görüntülenen görünür aralıktan önceki ve sondaki ayları ekleyin.|
|GMR_VISIBLE|Yalnızca tamamen görüntülenen ayları ekleyin.|

### <a name="return-value"></a>Dönüş Değeri

Birinci ve ikinci sürümlerde *refMinRange* ve *refMaxRange* tarafından belirtilen iki sınıra yayılan aralığı, aylar içinde, ya da üçüncü sürümde *pMinRange* ve *pMaxRange'ı* temsil eden bir karşıcı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_GETMONTHRANGE](/windows/win32/Controls/mcm-getmonthrange)davranışını uygular. MFC'nin `GetMonthRange`uygulamasında, kullanımı, `COleDateTime` `CTime` kullanımı veya `SYSTEMTIME` yapı kullanımını belirtebilirsiniz.

### <a name="example"></a>Örnek

  [CMonthCalCtrl örneğine bakın:SetDayState](#setdaystate).

## <a name="cmonthcalctrlgetrange"></a><a name="getrange"></a>CMonthCalCtrl::GetRange

Bir aylık takvim denetiminde ayarlanan geçerli minimum ve maksimum tarihleri alır.

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

*pMinAralığı*<br/>
Aralığın en `COleDateTime` alt `CTime` ucundaki tarihi içeren bir nesneye, nesneye veya [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

*pMaxRange*<br/>
Aralığın en `COleDateTime` yüksek `CTime` sonundaki tarihi içeren bir nesneye, nesneye veya [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfır (sınır kümesi yoktur) veya sınır bilgilerini belirten aşağıdaki değerlerin bir leşimi olan bir DWORD.

|Değer|Anlamı|
|-----------|-------------|
|GDTR_MAX|Denetim için maksimum sınır ayarlanır; *pMaxRange* geçerlidir ve geçerli tarih bilgilerini içerir.|
|GDTR_MIN|Denetim için minimum bir sınır ayarlanır; *pMinRange* geçerlidir ve geçerli tarih bilgilerini içerir.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_GETRANGE](/windows/win32/Controls/mcm-getrange)davranışını uygular. MFC'nin `GetRange`uygulanmasında, bir `COleDateTime` kullanım, bir `CTime` kullanım veya `SYSTEMTIME` yapı kullanımı belirtebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

## <a name="cmonthcalctrlgetselrange"></a><a name="getselrange"></a>CMonthCalCtrl::GetSelRange

Kullanıcı tarafından seçilen tarih aralığının üst ve alt sınırlarını gösteren tarih bilgilerini alır.

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
İzin verilen minimum tarihi içeren bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*refMaxRange*<br/>
İzin verilen `COleDateTime` en `CTime` yüksek tarihi içeren bir veya nesneye başvuru.

*pMinAralığı*<br/>
Aralığın en alt ucundaki tarihi içeren bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

*pMaxRange*<br/>
Aralığın en `SYSTEMTIME` yüksek sonundaki tarihi içeren bir yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_GETSELRANGE](/windows/win32/Controls/mcm-getselrange)davranışını uygular. `GetSelRange`MCS_MULTISELECT stilini kullanmayan bir aylık takvim denetimine uygulanırsa başarısız olur.

MFC'nin `GetSelRange`uygulamasında, kullanımı, `COleDateTime` `CTime` kullanımı veya `SYSTEMTIME` yapı kullanımını belirtebilirsiniz.

## <a name="cmonthcalctrlgettoday"></a><a name="gettoday"></a>CMonthCalCtrl::GetToday

Bir aylık takvim denetimi için "bugün" olarak belirtilen tarihe ait tarih bilgilerini alır.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Geçerli günü belirten bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*pDateTime*<br/>
Tarih bilgilerini alacak bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi. Bu parametre geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_GETTODAY](/windows/win32/Controls/mcm-gettoday)davranışını uygular. MFC'nin `GetToday`uygulanmasında, bir `COleDateTime` kullanım, bir `CTime` kullanım veya `SYSTEMTIME` yapı kullanımı belirtebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

## <a name="cmonthcalctrlhittest"></a><a name="hittest"></a>CMonthCalCtrl::HitTest

Varsa hangi ay takvim denetiminin belirli bir konumda olduğunu belirler.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>Parametreler

*pMCHitTest*<br/>
Ay takvim denetimi için isabet test noktaları içeren bir [MCHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-mchittestinfo) yapısıiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bir DWORD değeri. Yapının **uHit** üyesine `MCHITTESTINFO` eşittir.

### <a name="remarks"></a>Açıklamalar

`HitTest`isabet `MCHITTESTINFO` testi hakkında bilgi içeren yapıyı kullanır.

## <a name="cmonthcalctrliscenturyview"></a><a name="iscenturyview"></a>CMonthCalCtrl::IsCenturyView

Geçerli ay takvim denetiminin geçerli görünümünün yüzyıl görünümü olup olmadığını gösterir.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Doğru, eğer mevcut görüş yüzyıl görüşüise; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir. Bu ileti MCMV_CENTURY döndürürse, bu yöntem TRUE döndürür.

## <a name="cmonthcalctrlisdecadeview"></a><a name="isdecadeview"></a>CMonthCalCtrl::IsDecadeView

Geçerli ay takvim denetiminin geçerli görünümünün on yıl görünümü olup olmadığını gösterir.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünüm on yıl görünümü ise DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir. Bu ileti MCMV_DECADE döndürürse, bu yöntem TRUE döndürür.

## <a name="cmonthcalctrlismonthview"></a><a name="ismonthview"></a>CMonthCalCtrl::IsMonthView

Geçerli ay takvim denetiminin geçerli görünümünün ay görünümü olup olmadığını gösterir.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünüm ay görünümüise DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir. Bu ileti MCMV_MONTH döndürürse, bu yöntem TRUE döndürür.

## <a name="cmonthcalctrlisyearview"></a><a name="isyearview"></a>CMonthCalCtrl::IsYearView

Geçerli ay takvim denetiminin geçerli görünümünün yıl görünümü olup olmadığını gösterir.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünüm yıl görünümü ise DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir. Bu ileti MCMV_YEAR döndürürse, bu yöntem TRUE döndürür.

## <a name="cmonthcalctrlsetcalendarborder"></a><a name="setcalendarborder"></a>CMonthCalCtrl::SetCalendarBorder

Geçerli ay takvim denetiminin kenarlığı genişliğini ayarlar.

```
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*cxyBorder*|[içinde] Kenarlığı piksel olarak genişliği.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarılı olursa, kenarlık genişliği *cxyBorder* parametresine ayarlanır. Aksi takdirde, kenarlık genişliği geçerli [tema](/windows/win32/Controls/visual-styles-overview)tarafından belirtilen varsayılan değere sıfırlanır veya temalar kullanılmazsa sıfırlanır.

Bu yöntem, Windows SDK'da açıklanan [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_monthCalCtrl`ay takvim denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, ay takvimi denetiminin kenarlık genişliğini sekiz piksele ayarlar. Bu yöntemin başarılı olup olmadığını belirlemek için [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) yöntemini kullanın.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

## <a name="cmonthcalctrlsetcalendarborderdefault"></a><a name="setcalendarborderdefault"></a>CMonthCalCtrl::SetCalendarBorderDefault

Geçerli ay takvim denetiminin kenarlığı varsayılan genişliğini ayarlar.

```
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>Açıklamalar

Kenarlık genişliği, geçerli [tema](/windows/win32/Controls/visual-styles-overview)tarafından belirtilen varsayılan değere veya temalar kullanılmazsa sıfıra ayarlanır.

Bu yöntem, Windows SDK'da açıklanan [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) iletisini gönderir.

## <a name="cmonthcalctrlsetcalid"></a><a name="setcalid"></a>CMonthCalCtrl::SetCalID

Geçerli ay takvim denetimi için takvim tanımlayıcısını ayarlar.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Aytac*|[içinde] [Takvim tanımlayıcı](/windows/win32/Intl/calendar-identifiers) sabitlerinden biri.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Takvim tanımlayıcısı, Gregoryen (yerelleştirilmiş), Japonca veya Hicri takvimler gibi bölgeye özgü bir takvim belirtir. Takvimi `SetCalID` içeren yerel bilgisayar bilgisayarınıza yüklüyse, *kalid* parametretarafından belirtilen takvimi görüntülemek için yöntemi kullanın.

Bu yöntem, Windows SDK'da açıklanan [MCM_SETCALID](/windows/win32/Controls/mcm-setcalid) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_monthCalCtrl`ay takvim denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, Japon İmparator Dönemi takvimini görüntülemek için ay takvimi denetimini ayarlar. Yöntem `SetCalID` yalnızca bu takvim bilgisayarınızda yüklüyse başarılı olur.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

## <a name="cmonthcalctrlsetcenturyview"></a><a name="setcenturyview"></a>CMonthCalCtrl::SetCenturyView

Yüzyıl görünümünü görüntülemek için geçerli ay takvim denetimini ayarlar.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yüzyıl görünümünü temsil eden görünümü ayarlamak için `MCMV_CENTURY` [CMonthCalCtrl::SetCurrentView](#setcurrentview) yöntemini kullanır.

## <a name="cmonthcalctrlsetcolor"></a><a name="setcolor"></a>CMonthCalCtrl::SetColor

Bir aylık takvim denetiminin belirli bir alanının rengini ayarlar.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>Parametreler

*nBölge*<br/>
Hangi ay takvim renginin ayarlanmasını belirten bir araseger değeri. Bu değer aşağıdakilerden biri olabilir.

|Değer|Anlamı|
|-----------|-------------|
|MCSC_BACKGROUND|Aylar arasında görüntülenen arka plan rengi.|
|MCSC_MONTHBK|Ay içinde görüntülenen arka plan rengi.|
|MCSC_TEXT|Bir ay içinde metni görüntülemek için kullanılan renk.|
|MCSC_TITLEBK|Takvimin başlığında görüntülenen arka plan rengi.|
|MCSC_TITLETEXT|Takvimin başlığındaki metni görüntülemek için kullanılan renk.|
|MCSC_TRAILINGTEXT|Üstbilgi ve sondaki gün metnini görüntülemek için kullanılan renk. Üstbilgi ve sondaki günler, geçerli takvimde görünen önceki ve sonraki aylardan gelen günlerdir.|

*ref*<br/>
Ay takvim denetiminin belirtilen bölümü için yeni renk ayarı için COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ay takvim denetiminin belirtilen bölümü için önceki renk ayarını temsil eden bir COLORREF değeri. Aksi takdirde bu ileti -1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_SETCOLOR](/windows/win32/Controls/mcm-setcolor)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

## <a name="cmonthcalctrlsetcurrentview"></a><a name="setcurrentview"></a>CMonthCalCtrl::SetCurrentView

Belirtilen görünümü görüntülemek için geçerli ay takvim denetimini ayarlar.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwNewView*|[içinde] Aylık, yıllık, on yıl veya yüzyıl görünümünü belirten aşağıdaki değerlerden biri.<br /><br /> MCMV_MONTH: Aylık görünüm<br /><br /> MCMV_YEAR: Yıllık görünüm<br /><br /> MCMV_DECADE: On yıl görünümü<br /><br /> MCMV_CENTURY: Yüzyıl görünümü|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [MCM_SETCURRENTVIEW](/windows/win32/Controls/mcm-setcurrentview) iletisini gönderir.

## <a name="cmonthcalctrlsetcursel"></a><a name="setcursel"></a>CMonthCalCtrl::SetCurSel

Bir aylık takvim denetimi için seçili tarihi ayarlar.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Şu anda seçili ay takvim denetimini gösteren bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*pDateTime*<br/>
Geçerli seçim olarak ayarlanacak tarihi içeren bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/mcm-setcursel)iletisinin MCM_SETCURSEL davranışını uygular. MFC'nin `SetCurSel`uygulanmasında, bir `COleDateTime` kullanım, bir `CTime` kullanım veya `SYSTEMTIME` yapı kullanımı belirtebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

## <a name="cmonthcalctrlsetdaystate"></a><a name="setdaystate"></a>CMonthCalCtrl::SetDayState

Bir ay takvim denetiminde ekranı günler için ayarlar.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>Parametreler

*nAylar*<br/>
*PStates'in* işaret ettiği dizide kaç öğe olduğunu gösteren değer.

*pStates*<br/>
Ay takvimi denetiminin ekranında her gün nasıl çizeceğini tanımlayan bir [MONTHDAYSTATE](/windows/win32/Controls/monthdaystate) değer dizisine işaretçi. MONTHDAYSTATE veri türü, her bitin (1 ile 31) bir ay daki günün durumunu temsil ettiği bir bit alanıdır. Biraz acıklıysa, ilgili gün kalın olarak görüntülenir; aksi takdirde hiçbir vurgu ile görüntülenir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_SETDAYSTATE](/windows/win32/Controls/mcm-setdaystate)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

## <a name="cmonthcalctrlsetdecadeview"></a><a name="setdecadeview"></a>CMonthCalCtrl::SetDecadeView

Geçerli ay takvim denetimini on yıl görünümüne ayarlar.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, on yıl görünümünü temsil eden görünümü ayarlamak için `MCMV_DECADE` [CMonthCalCtrl::SetCurrentView](#setcurrentview) yöntemini kullanır.

## <a name="cmonthcalctrlsetfirstdayofweek"></a><a name="setfirstdayofweek"></a>CMonthCalCtrl::SetFirstDayOfWeek

Takvimin en sol sütununda görüntülenecek haftanın gününü ayarlar.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>Parametreler

*iGün*<br/>
Haftanın ilk günü olarak hangi günün ayarlanış olacağını gösteren bir sonda değeri. Bu değer gün sayılarından biri olmalıdır. Günlük sayıların açıklaması için [GetFirstDayOfWeek'e](#getfirstdayofweek) bakın.

*lpnEski*<br/>
Haftanın ilk gününü önceden ayarlayan bir tamsayı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Haftanın önceki ilk günü, denetim paneli ayarında belirtilen gün olan LOCALE_IFIRSTDAYOFWEEK'nin değeri dışında bir değere ayarlanmışsa sıfır değildir. Aksi takdirde, bu işlev 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/mcm-setfirstdayofweek)iletisinin MCM_SETFIRSTDAYOFWEEK davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

## <a name="cmonthcalctrlsetmaxselcount"></a><a name="setmaxselcount"></a>CMonthCalCtrl::SetMaxSelSayısı

Bir aylık takvim denetiminde seçilebilen en fazla gün sayısını ayarlar.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>Parametreler

*nMax*<br/>
Seçilebilir gün sayısının en yüksek olduğunu temsil edecek şekilde ayarlanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_SETMAXSELCOUNT](/windows/win32/Controls/mcm-setmaxselcount)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

## <a name="cmonthcalctrlsetmonthdelta"></a><a name="setmonthdelta"></a>CMonthCalCtrl::SetMonthDelta

Kaydırma hızını bir aylık takvim denetimi için ayarlar.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>Parametreler

*iDelta*<br/>
Denetimin kaydırma hızı olarak ayarlanacak ay sayısı. Bu değer sıfırsa, ay deltası denetimde görüntülenen ay sayısı olan varsayılana sıfırlanır.

### <a name="return-value"></a>Dönüş Değeri

Önceki kaydırma hızı. Kaydırma hızı önceden ayarlanmadıysa, iade değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/mcm-setmonthdelta)iletisinin MCM_SETMONTHDELTA davranışını uygular.

## <a name="cmonthcalctrlsetmonthview"></a><a name="setmonthview"></a>CMonthCalCtrl::SetMonthView

Ay görünümünü görüntülemek için geçerli ay takvim denetimini ayarlar.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ay görünümünü temsil eden MCMV_MONTH görünümü ayarlamak için [CMonthCalCtrl::SetCurrentView](#setcurrentview) yöntemini kullanır.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_monthCalCtrl`ay takvim denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, ay, yıl, on yıl ve yüzyıl görünümlerini görüntülemek için ay takvim denetimini ayarlar.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

## <a name="cmonthcalctrlsetrange"></a><a name="setrange"></a>CMonthCalCtrl::SetAralığı

Bir aylık takvim denetimi için izin verilen en az ve en yüksek tarihleri ayarlar.

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

*pMinAralığı*<br/>
Aralığın en `COleDateTime` alt `CTime` ucundaki tarihi içeren bir nesneye, nesneye veya [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

*pMaxRange*<br/>
Aralığın en `COleDateTime` yüksek `CTime` sonundaki `SYSTEMTIME` tarihi içeren bir nesneye, nesneye veya yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_SETRANGE](/windows/win32/Controls/mcm-setrange)davranışını uygular. MFC'nin `SetRange`uygulamasında, kullanımı, `COleDateTime` `CTime` kullanımı veya `SYSTEMTIME` yapı kullanımını belirtebilirsiniz.

### <a name="example"></a>Örnek

  [CMonthCalCtrl örneğine bakın:GetRange.](#getrange)

## <a name="cmonthcalctrlsetselrange"></a><a name="setselrange"></a>CMonthCalCtrl::SetSelRange

Bir aylık takvim denetimi için seçimi belirli bir tarih aralığına ayarlar.

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

*pMinAralığı*<br/>
Aralığın en `COleDateTime` alt `CTime` ucundaki tarihi içeren bir nesneye, nesneye veya [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

*pMaxRange*<br/>
Aralığın en `COleDateTime` yüksek `CTime` sonundaki `SYSTEMTIME` tarihi içeren bir nesneye, nesneye veya yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [MCM_SETSELRANGE](/windows/win32/Controls/mcm-setselrange)davranışını uygular. MFC'nin `SetSelRange`uygulamasında, kullanımı, `COleDateTime` `CTime` kullanımı veya `SYSTEMTIME` yapı kullanımını belirtebilirsiniz.

## <a name="cmonthcalctrlsettoday"></a><a name="settoday"></a>CMonthCalCtrl::SetToday

Geçerli günün takvim denetimini ayarlar.

```
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Geçerli tarihi içeren bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine başvuru.

*pDateTime*<br/>
İkinci sürümde, geçerli tarih bilgilerini içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine işaretçi. Üçüncü sürümde, geçerli tarih bilgilerini içeren bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/mcm-settoday)iletisinin MCM_SETTODAY davranışını uygular.

### <a name="example"></a>Örnek

  [CMonthCalCtrl örneğine bakın:GetToday](#gettoday).

## <a name="cmonthcalctrlsetyearview"></a><a name="setyearview"></a>CMonthCalCtrl::SetYearView

Geçerli ay takvim denetimini yıl görünümüne ayarlar.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görünümü yıllık görünümü temsil eden MCMV_YEAR ayarlamak için [CMonthCalCtrl::SetCurrentView](#setcurrentview) yöntemini kullanır.

## <a name="cmonthcalctrlsizeminreq"></a><a name="sizeminreq"></a>CMonthCalCtrl::SizeMinReq

Ay takvimi denetimini bir ay gösteren minimum boyuta görüntüler.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>Parametreler

*bRepaint*<br/>
Denetimin yeniden boyanıp boyanmayacağını belirtir. Varsayılan olarak, TRUE. FALSE ise, yeniden boyama oluşur.

### <a name="return-value"></a>Dönüş Değeri

Ay takvim denetimi en aza indirirse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Arama, `SizeMinReq` bir aylık takvim için tüm ay takvim denetimini başarıyla görüntüler.

## <a name="cmonthcalctrlsizerecttomin"></a><a name="sizerecttomin"></a>CMonthCalCtrl::SizeRectToMin

Geçerli ay takvim denetimi için, belirli bir dikdörtgen sığdırılan tüm takvimleri içerebilecek en küçük dikdörtgeni hesaplar.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Lprect*|[içinde] İstenilen sayıda takvim içeren bir dikdörtgen tanımlayan bir [DIKDÖRTGEN](/previous-versions/dd162897\(v=vs.85\)) yapısıişaretçisi.|

### <a name="return-value"></a>Dönüş Değeri

Boyutu *lpRect* parametresi tarafından tanımlanan dikdörtgenden daha az veya eşit olan bir dikdörtgeni tanımlayan bir [DIKDÖRTGEN](/previous-versions/dd162897\(v=vs.85\)) yapısına işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *lpRect* parametresi tarafından belirtilen dikdörtgen de kaç takvim sığabilir hesaplar ve sonra takvim bu sayısını içerebilecek en küçük dikdörtgen döndürür. Bu yöntem, belirtilen dikdörtgeni istenen takvim sayısını tam olarak sığdıracak şekilde küçültür.

Bu yöntem, Windows SDK'da açıklanan [MCM_SIZERECTTOMIN](/windows/win32/Controls/mcm-sizerecttomin) iletisini gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Numune CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDateTimeCtrl Sınıfı](../../mfc/reference/cdatetimectrl-class.md)
