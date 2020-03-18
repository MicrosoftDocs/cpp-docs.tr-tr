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
ms.openlocfilehash: 963aecfed4f6eb67a0ab227df06fce98c0778f7f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420206"
---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl sınıfı

Aylık takvim denetiminin işlevselliğini Kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CMonthCalCtrl:: CMonthCalCtrl](#cmonthcalctrl)|`CMonthCalCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CMonthCalCtrl:: Create](#create)|Bir aylık Takvim denetimi oluşturur ve `CMonthCalCtrl` nesnesine iliştirir.|
|[CMonthCalCtrl:: GetCalendarBorder](#getcalendarborder)|Geçerli ay Takvim denetiminin kenarlığının genişliğini alır.|
|[CMonthCalCtrl:: GetCalendarCount](#getcalendarcount)|Geçerli ay Takvim denetiminde gösterilecek takvim sayısını alır.|
|[CMonthCalCtrl:: Gettakvimdeki Dargriınfo](#getcalendargridinfo)|Geçerli ay Takvim denetimiyle ilgili bilgileri alır.|
|[CMonthCalCtrl:: Getcalıd](#getcalid)|Geçerli ay Takvim denetiminin Takvim tanımlayıcısını alır.|
|[CMonthCalCtrl:: GetColor](#getcolor)|Aylık takvim denetiminin belirtilen alanının rengini alır.|
|[CMonthCalCtrl:: GetCurrentView](#getcurrentview)|Geçerli ay Takvim denetimi tarafından şu anda görüntülenen görünümü alır.|
|[CMonthCalCtrl:: GetCurSel](#getcursel)|Sistem saatini şu anda seçili olan tarih ile belirtilen şekilde alır.|
|[CMonthCalCtrl:: GetFirstDayOfWeek](#getfirstdayofweek)|Takvimin en sol sütununda görüntülenecek olan haftanın ilk gününü alır.|
|[CMonthCalCtrl:: GetMaxSelCount](#getmaxselcount)|Aylık takvim denetiminde seçilebilirler geçerli en fazla gün sayısını alır.|
|[CMonthCalCtrl:: GetMaxTodayWidth](#getmaxtodaywidth)|Geçerli ay Takvim denetimi için "Bugün" dizesinin en büyük genişliğini alır.|
|[CMonthCalCtrl:: GetMinReqRect](#getminreqrect)|Aylık takvim denetiminde tam ayı göstermek için gereken en küçük boyutu alır.|
|[CMonthCalCtrl:: GetMonthDelta](#getmonthdelta)|Aylık Takvim denetimi için kaydırma hızını alır.|
|[CMonthCalCtrl:: GetMonthRange](#getmonthrange)|Bir aylık takvim denetiminin görüntüsüne ait yüksek ve düşük limitlerini temsil eden tarih bilgilerini alır.|
|[CMonthCalCtrl:: GetRange](#getrange)|Bir aylık takvim denetiminde ayarlanan geçerli en düşük ve en yüksek tarihleri alır.|
|[CMonthCalCtrl:: GetSelRange](#getselrange)|Kullanıcı tarafından şu anda seçili olan tarih aralığının üst ve alt sınırlarını temsil eden tarih bilgilerini alır.|
|[CMonthCalCtrl:: GetToday](#gettoday)|Aylık Takvim denetimi için "Bugün" olarak belirtilen tarihin tarih bilgilerini alır.|
|[CMonthCalCtrl:: HitTest](#hittest)|Bir aylık takvim denetiminin hangi bölümünün ekranda belirli bir noktada olduğunu belirler.|
|[CMonthCalCtrl:: IsCenturyView](#iscenturyview)|Geçerli ay Takvim denetiminin geçerli görünümünün yüzyıl görünümü olup olmadığını gösterir.|
|[CMonthCalCtrl:: ısdecadeview](#isdecadeview)|Geçerli ay Takvim denetiminin geçerli görünümünün on yıl olmayan görünüm olup olmadığını gösterir.|
|[CMonthCalCtrl:: ısmonthview](#ismonthview)|Geçerli ay Takvim denetiminin geçerli görünümünün ay görünümü olup olmadığını gösterir.|
|[CMonthCalCtrl:: ısyearview](#isyearview)|Geçerli ay Takvim denetiminin geçerli görünümünün yıl görünümü olup olmadığını gösterir.|
|[CMonthCalCtrl:: SetCalendarBorder](#setcalendarborder)|Geçerli ay Takvim denetiminin kenarlığının genişliğini ayarlar.|
|[CMonthCalCtrl:: SetCalendarBorderDefault](#setcalendarborderdefault)|Geçerli ay Takvim denetiminin kenarlığının varsayılan genişliğini ayarlar.|
|[CMonthCalCtrl:: SetCalID](#setcalid)|Geçerli ay Takvim denetiminin Takvim tanımlayıcısını ayarlar.|
|[CMonthCalCtrl:: SetCenturyView](#setcenturyview)|Geçerli ay Takvim denetimini yüzyıl görünümünü görüntüleyecek şekilde ayarlar.|
|[CMonthCalCtrl:: SetColor](#setcolor)|Aylık takvim denetiminin belirtilen alanının rengini ayarlar.|
|[CMonthCalCtrl:: SetCurrentView](#setcurrentview)|Geçerli ay Takvim denetimini belirtilen görünümü görüntüleyecek şekilde ayarlar.|
|[CMonthCalCtrl:: SetCurSel](#setcursel)|Bir aylık Takvim denetimi için şu anda seçili olan tarihi ayarlar.|
|[CMonthCalCtrl:: SetDayState](#setdaystate)|Aylık takvim denetiminde gün görüntülemeyi ayarlar.|
|[CMonthCalCtrl:: SetDecadeView](#setdecadeview)|Geçerli ay Takvim denetimini on yıl görünümü olarak ayarlar.|
|[CMonthCalCtrl:: SetFirstDayOfWeek](#setfirstdayofweek)|Takvimin en sol sütununda görüntülenecek haftanın gününü ayarlar.|
|[CMonthCalCtrl:: SetMaxSelCount](#setmaxselcount)|Aylık takvim denetiminde seçilebilirler maksimum gün sayısını ayarlar.|
|[CMonthCalCtrl:: SetMonthDelta](#setmonthdelta)|Aylık Takvim denetimi için kaydırma hızını ayarlar.|
|[CMonthCalCtrl:: SetMonthView](#setmonthview)|Aylık görünümü görüntülemek için geçerli ay Takvim denetimini ayarlar.|
|[CMonthCalCtrl:: SetRange](#setrange)|Aylık Takvim denetimi için izin verilen en düşük ve en fazla tarihleri ayarlar.|
|[CMonthCalCtrl:: SetSelRange](#setselrange)|Bir aylık takvim denetiminin seçimini belirli bir tarih aralığına ayarlar.|
|[CMonthCalCtrl:: SetToday](#settoday)|Geçerli günün Takvim denetimini ayarlar.|
|[CMonthCalCtrl:: SetYearView](#setyearview)|Geçerli ay Takvim denetimini yıl görünümü olarak ayarlar.|
|[CMonthCalCtrl:: SizeMinReq](#sizeminreq)|Aylık Takvim denetimini minimum, bir aylık boyuta göre boyar.|
|[CMonthCalCtrl:: SizeRectToMin](#sizerecttomin)|Geçerli ay Takvim denetimi için, belirtilen dikdörtgenle sığan tüm takvimleri içerebilen en küçük dikdörtgeni hesaplar.|

## <a name="remarks"></a>Açıklamalar

Aylık Takvim denetimi, kullanıcıya bir tarih seçebileceğiniz basit bir takvim arabirimi sağlar. Kullanıcı ekranı şu şekilde değiştirebilir:

- Aydan aya kadar geriye ve ileriye doğru kaydırma.

- Günün geçerli gününü (MCS_NOTODAY stili kullanılmazsa) göstermek için bugün metnine tıklanın.

- Açılır menüden bir ay veya yıl çekme.

Aylık Takvim denetimini, oluşturduğunuz sırada nesneye çeşitli stiller uygulayarak özelleştirebilirsiniz. Bu stiller Windows SDK [aylık Takvim denetimi stillerinde](/windows/win32/Controls/month-calendar-control-styles) açıklanmıştır.

Aylık Takvim denetimi bir ay daha fazla görüntülenebilir ve tarihi inceleyerek özel günleri (tatiller gibi) belirtebilir.

Aylık Takvim denetimini kullanma hakkında daha fazla bilgi için bkz. [CMonthCalCtrl kullanma](../../mfc/using-cmonthcalctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdtctl. h

##  <a name="cmonthcalctrl"></a>CMonthCalCtrl:: CMonthCalCtrl

`CMonthCalCtrl` nesnesi oluşturur.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>Açıklamalar

Nesnesini oluşturduktan sonra `Create` çağırmanız gerekir.

##  <a name="create"></a>CMonthCalCtrl:: Create

Bir aylık Takvim denetimi oluşturur ve `CMonthCalCtrl` nesnesine iliştirir.

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
Aylık takvim denetimine uygulanan Windows stillerinin birleşimini belirtir. Stiller hakkında daha fazla bilgi için Windows SDK [aylık Takvim denetim stillerine](/windows/win32/Controls/month-calendar-control-styles) bakın.

*Rect*<br/>
Bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru. Aylık takvim denetiminin konumunu ve boyutunu içerir.

*yönergelerinin*<br/>
Aylık takvim denetiminin konumunu tanımlayan bir [nokta](/previous-versions/dd162805\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Aylık takvim denetiminin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi. NULL olmaması gerekir.

*NID*<br/>
Aylık takvim denetiminin denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda aylık Takvim denetimi oluşturun:

1. `CMonthCalCtrl` nesnesi oluşturmak için [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) çağırın.

1. Aylık Takvim denetimi oluşturan ve `CMonthCalCtrl` nesnesine ekleyen bu üye işlevini çağırın.

`Create`çağırdığınızda ortak denetimler başlatılır. Çağırdığınız `Create` sürümü, nasıl boyutlandırıldığını belirler:

- MFC 'nin denetimi bir aya göre otomatik olarak boyutunu yazmak için, *PT* parametresini kullanan geçersiz kılmayı çağırın.

- Denetimi kendiniz yazmak için, *Rect* parametresini kullanan bu işlevin geçersiz kılmasını çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

##  <a name="getcalendarborder"></a>CMonthCalCtrl:: GetCalendarBorder

Geçerli ay Takvim denetiminin kenarlığının genişliğini alır.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim kenarlığının piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_GETCALENDARBORDER](/windows/win32/Controls/mcm-getcalendarborder) iletisini gönderir.

##  <a name="getcalendarcount"></a>CMonthCalCtrl:: GetCalendarCount

Geçerli ay Takvim denetiminde gösterilecek takvim sayısını alır.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aylık takvim denetiminde görüntülenmekte olan takvimlerin sayısı. İzin verilen maksimum takvim sayısı 12 ' dir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_GETCALENDARCOUNT](/windows/win32/Controls/mcm-getcalendarcount) iletisini gönderir.

##  <a name="getcalendargridinfo"></a>CMonthCalCtrl:: Gettakvimdeki Dargriınfo

Geçerli ay Takvim denetimiyle ilgili bilgileri alır.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Pmcgriınfo*|dışı Geçerli ay Takvim denetimi hakkında bilgi alan bir [Mcgriınfo](/windows/win32/api/commctrl/ns-commctrl-mcgridinfo) yapısına yönelik işaretçi. Çağıran, bu yapıyı ayırmaktan ve başlatmaktan sorumludur.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_GETCALENDARGRIDINFO](/windows/win32/Controls/mcm-getcalendargridinfo) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık takvim denetimine programlı bir şekilde erişmek için kullanılan `m_monthCalCtrl`değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli ay Takvim denetiminin görüntülediği takvim tarihini almak için `GetCalendarGridInfo` yöntemini kullanır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

##  <a name="getcalid"></a>CMonthCalCtrl:: Getcalıd

Geçerli ay Takvim denetiminin Takvim tanımlayıcısını alır.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Takvim tanımlayıcı](/windows/win32/Intl/calendar-identifiers) sabitlerinden biri.

### <a name="remarks"></a>Açıklamalar

Takvim tanımlayıcısı, Gregoryen (yerelleştirilmiş), Japonca veya Hicri takvimler gibi bölgeye özgü bir takvimi gösterir. Uygulamanız, çeşitli dil desteği işlevlerine sahip bir Takvim tanımlayıcısı kullanabilir.

Bu yöntem, Windows SDK açıklanan [MCM_GETCALID](/windows/win32/Controls/mcm-getcalid) iletisini gönderir.

##  <a name="getcolor"></a>CMonthCalCtrl:: GetColor

*NRegion*tarafından belirtilen ay Takvim denetimindeki bir alanın rengini alır.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>Parametreler

*nRegion*<br/>
Rengin alındığı ay Takvim denetiminin bölgesi. Değerlerin listesi için bkz. [setColor](#setcolor)'In *nRegion* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, aylık takvim denetiminin bölümüyle ilişkili rengi belirten [colorref](/windows/win32/gdi/colorref) değeri. Aksi takdirde, bu üye işlevi-1 döndürür.

##  <a name="getcurrentview"></a>CMonthCalCtrl:: GetCurrentView

Geçerli ay Takvim denetimi tarafından şu anda görüntülenen görünümü alır.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu değerlerden biri tarafından belirtilen geçerli görünüm:

|Değer|Açıklama|
|-----------|-------------|
|MCMV_MONTH|Aylık görünüm|
|MCMV_YEAR|Yıllık görünüm|
|MCMV_DECADE|On yıl görünümü|
|MCMV_CENTURY|Century görünümü|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık takvim denetimine programlı bir şekilde erişmek için kullanılan `m_monthCalCtrl`değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, şu anda aylık takvim denetiminin görüntülediğini bildirir.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

##  <a name="getcursel"></a>CMonthCalCtrl:: GetCurSel

Sistem saatini şu anda seçili olan tarih ile belirtilen şekilde alır.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
[Colandatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine veya bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru. Geçerli saati alır.

*pDateTime*<br/>
Şu anda seçili olan tarih bilgilerini alacak bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi. Bu parametre geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; diğerwize 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETCURSEL](/windows/win32/Controls/mcm-getcursel)davranışını uygular.

> [!NOTE]
>  Stil MCS_MULTISELECT ayarlandıysa bu üye işlevi başarısız olur.

MFC 'nin `GetCurSel`uygulamasında `COleDateTime` kullanımı, `CTime` kullanımı veya `SYSTEMTIME` yapısı kullanımı belirtebilirsiniz.

##  <a name="getfirstdayofweek"></a>CMonthCalCtrl:: GetFirstDayOfWeek

Takvimin en sol sütununda görüntülenecek olan haftanın ilk gününü alır.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>Parametreler

*pbLocal*<br/>
Bir BOOL değeri işaretçisi. Değer sıfır değilse, denetimin ayarı Denetim Masası 'ndaki ayarla eşleşmez.

### <a name="return-value"></a>Dönüş Değeri

Haftanın ilk gününü temsil eden bir tamsayı değeri. Bu tamsayıların gösterdiği özellikler hakkında daha fazla bilgi için bkz. **açıklamalar** .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-getfirstdayofweek)davranışını uygular. Haftanın günleri aşağıdaki şekilde tamsayılar olarak temsil edilir.

|Değer|Haftanın günü|
|-----------|---------------------|
|0|Pazartesi|
|1\.|Salı|
|2|Çarşamba|
|3|Perşembe|
|4|Cuma|
|5|Cumartesi|
|6|Pazar|

### <a name="example"></a>Örnek

  [CMonthCalCtrl:: SetFirstDayOfWeek](#setfirstdayofweek)için örneğe bakın.

##  <a name="getmaxselcount"></a>CMonthCalCtrl:: GetMaxSelCount

Aylık takvim denetiminde seçilebilirler geçerli en fazla gün sayısını alır.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim için seçilebilirler toplam gün sayısını temsil eden bir tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETMAXSELCOUNT](/windows/win32/Controls/mcm-getmaxselcount)davranışını uygular. MCS_MULTISELECT stil kümesine sahip denetimler için bu üye işlevini kullanın.

### <a name="example"></a>Örnek

  [CMonthCalCtrl:: SetMaxSelCount](#setmaxselcount)örneğine bakın.

##  <a name="getmaxtodaywidth"></a>CMonthCalCtrl:: GetMaxTodayWidth

Geçerli ay Takvim denetimi için "Bugün" dizesinin en büyük genişliğini alır.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

"Bugün" dizesinin piksel cinsinden genişliği.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık takvim denetimine programlı bir şekilde erişmek için kullanılan `m_monthCalCtrl`değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde `GetMaxTodayWidth` yöntemi gösterilmektedir.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>Açıklamalar

Kullanıcı, aylık takvim denetiminin alt kısmında görüntülenecek olan "Bugün" dizesine tıklayarak geçerli tarihe dönebilir. "Bugün" dizesi etiket metnini ve Tarih metnini içerir.

Bu yöntem, Windows SDK açıklanan [MCM_GETMAXTODAYWIDTH](/windows/win32/Controls/mcm-getmaxtodaywidth) iletisini gönderir.

##  <a name="getminreqrect"></a>CMonthCalCtrl:: GetMinReqRect

Aylık takvim denetiminde tam ayı göstermek için gereken en küçük boyutu alır.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>Parametreler

*pRect*<br/>
Bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına, sınırlayıcı dikdörtgen bilgilerini alacak bir işaretçi. Bu parametre geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu üye işlevi sıfır dışı döndürür ve `lpRect` geçerli sınırlayıcı bilgileri alır. Başarısız olursa, üye işlevi 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETMINREQRECT](/windows/win32/Controls/mcm-getminreqrect)davranışını uygular.

##  <a name="getmonthdelta"></a>CMonthCalCtrl:: GetMonthDelta

Aylık Takvim denetimi için kaydırma hızını alır.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aylık Takvim denetimi için kaydırma oranı. Kaydırma hızı, Kullanıcı bir kaydırma düğmesine bir kez tıkladığında denetimin görünümünü taşıdığı ayların sayısıdır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETMONTHDELTA](/windows/win32/Controls/mcm-getmonthdelta)davranışını uygular.

##  <a name="getmonthrange"></a>CMonthCalCtrl:: GetMonthRange

Bir aylık takvim denetiminin görüntüsüne ait yüksek ve düşük limitlerini temsil eden tarih bilgilerini alır.

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
İzin verilen en düşük tarihi içeren bir [Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*refMaxRange*<br/>
İzin verilen en uzun tarihi içeren bir `COleDateTime` veya `CTime` nesnesine başvuru.

*pMinRange*<br/>
Aralığın en düşük sonundaki tarihi içeren bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik işaretçi.

*pMaxRange*<br/>
Aralığın en yüksek sonundaki tarihi içeren `SYSTEMTIME` yapısına yönelik bir işaretçi.

*dwFlags*<br/>
Alınacak Aralık sınırlarının kapsamını belirten değer. Bu değer aşağıdakilerden biri olmalıdır.

|Değer|Açıklama|
|-----------|-------------|
|GMR_DAYSTATE|Yalnızca kısmen görüntülenen görünür aralığın önceki ve sondaki ayları dahil edin.|
|GMR_VISIBLE|Yalnızca tamamen görüntülenen ayları dahil et.|

### <a name="return-value"></a>Dönüş Değeri

İlk ve ikinci sürümlerde *refMinRange* ve *refMaxRange* ile belirtilen iki sınıra göre ve üçüncü sürümdeki *pMinRange* ve *pMaxRange* ile belirtilen aralığı gösteren bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETMONTHRANGE](/windows/win32/Controls/mcm-getmonthrange)davranışını uygular. MFC 'nin `GetMonthRange`uygulamasında `COleDateTime` kullanımı, `CTime` kullanımı veya `SYSTEMTIME` yapısı kullanımı belirtebilirsiniz.

### <a name="example"></a>Örnek

  [CMonthCalCtrl:: SetDayState](#setdaystate)için örneğe bakın.

##  <a name="getrange"></a>CMonthCalCtrl:: GetRange

Bir aylık takvim denetiminde ayarlanan geçerli en düşük ve en yüksek tarihleri alır.

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
`COleDateTime` nesnesine, `CTime` nesnesine veya aralığın en düşük sonundaki tarihi içeren bir [sistem zaman](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

*pMaxRange*<br/>
`COleDateTime` nesnesine, `CTime` nesnesine veya aralığın en yüksek sonundaki tarihi içeren bir [sistem zamanı](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfır (hiçbir sınır ayarlanmamış) veya limit bilgilerini belirten aşağıdaki değerlerin bir birleşimi olan bir DWORD.

|Değer|Açıklama|
|-----------|-------------|
|GDTR_MAX|Denetim için bir maksimum sınır ayarlanır; *pMaxRange* geçerlidir ve geçerli tarih bilgilerini içerir.|
|GDTR_MIN|Denetim için bir minimum sınır ayarlanır; *pMinRange* geçerlidir ve geçerli tarih bilgilerini içerir.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETRANGE](/windows/win32/Controls/mcm-getrange)davranışını uygular. MFC 'nin `GetRange`uygulamasında `COleDateTime` kullanımı, `CTime` kullanımı veya `SYSTEMTIME` yapısı kullanımı belirtebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

##  <a name="getselrange"></a>CMonthCalCtrl:: GetSelRange

Kullanıcı tarafından şu anda seçili olan tarih aralığının üst ve alt sınırlarını temsil eden tarih bilgilerini alır.

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
İzin verilen en düşük tarihi içeren bir [Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*refMaxRange*<br/>
İzin verilen en uzun tarihi içeren bir `COleDateTime` veya `CTime` nesnesine başvuru.

*pMinRange*<br/>
Aralığın en düşük sonundaki tarihi içeren bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik işaretçi.

*pMaxRange*<br/>
Aralığın en yüksek sonundaki tarihi içeren `SYSTEMTIME` yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETSELRANGE](/windows/win32/Controls/mcm-getselrange)davranışını uygular. `GetSelRange`, MCS_MULTISELECT stilini kullanmayan bir aylık takvim denetimine uygulanırsa başarısız olur.

MFC 'nin `GetSelRange`uygulamasında `COleDateTime` kullanımı, `CTime` kullanımı veya `SYSTEMTIME` yapısı kullanımı belirtebilirsiniz.

##  <a name="gettoday"></a>CMonthCalCtrl:: GetToday

Aylık Takvim denetimi için "Bugün" olarak belirtilen tarihin tarih bilgilerini alır.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Geçerli günü belirten [Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru.

*pDateTime*<br/>
Tarih bilgilerini alacak bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi. Bu parametre geçerli bir adres olmalıdır ve NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_GETTODAY](/windows/win32/Controls/mcm-gettoday)davranışını uygular. MFC 'nin `GetToday`uygulamasında `COleDateTime` kullanımı, `CTime` kullanımı veya `SYSTEMTIME` yapısı kullanımı belirtebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

##  <a name="hittest"></a>CMonthCalCtrl:: HitTest

Hangi ay Takvim denetiminin (varsa) belirtilen konumda olduğunu belirler.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>Parametreler

*pMCHitTest*<br/>
Aylık Takvim denetimi için isabet testi noktaları içeren bir [Mchittestınfo](/windows/win32/api/commctrl/ns-commctrl-mchittestinfo) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bir DWORD değeri. `MCHITTESTINFO` yapısının **uHit** üyesine eşittir.

### <a name="remarks"></a>Açıklamalar

`HitTest`, isabet testi hakkında bilgi içeren `MCHITTESTINFO` yapısını kullanır.

##  <a name="iscenturyview"></a>CMonthCalCtrl:: IsCenturyView

Geçerli ay Takvim denetiminin geçerli görünümünün yüzyıl görünümü olup olmadığını gösterir.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünüm yüzyıl görünümse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir. Bu ileti MCMV_CENTURY döndürürse, bu yöntem TRUE değerini döndürür.

##  <a name="isdecadeview"></a>CMonthCalCtrl:: ısdecadeview

Geçerli ay Takvim denetiminin geçerli görünümünün on yıl olmayan görünüm olup olmadığını gösterir.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünüm on yılda bir görünümse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir. Bu ileti MCMV_DECADE döndürürse, bu yöntem TRUE değerini döndürür.

##  <a name="ismonthview"></a>CMonthCalCtrl:: ısmonthview

Geçerli ay Takvim denetiminin geçerli görünümünün ay görünümü olup olmadığını gösterir.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Görünüm ay görünümse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir. Bu ileti MCMV_MONTH döndürürse, bu yöntem TRUE değerini döndürür.

##  <a name="isyearview"></a>CMonthCalCtrl:: ısyearview

Geçerli ay Takvim denetiminin geçerli görünümünün yıl görünümü olup olmadığını gösterir.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli görünüm yıl görünümse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) iletisini gönderir. Bu ileti MCMV_YEAR döndürürse, bu yöntem TRUE değerini döndürür.

##  <a name="setcalendarborder"></a>CMonthCalCtrl:: SetCalendarBorder

Geçerli ay Takvim denetiminin kenarlığının genişliğini ayarlar.

```
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Cxyıborder*|'ndaki Kenarlığın piksel cinsinden genişliği.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarılı olursa, kenarlık genişliği *Cxyıborder* parametresine ayarlanır. Aksi takdirde, kenarlık genişliği geçerli [Tema](/windows/win32/Controls/visual-styles-overview)tarafından belirtilen varsayılan değere sıfırlanır veya temalar kullanılmazsa sıfırdır.

Bu yöntem, Windows SDK açıklanan [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık takvim denetimine programlı bir şekilde erişmek için kullanılan `m_monthCalCtrl`değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık takvim denetiminin kenarlık genişliğini sekiz piksel olarak ayarlar. Bu yöntemin başarılı olup olmadığını anlamak için [CMonthCalCtrl:: GetCalendarBorder](#getcalendarborder) metodunu kullanın.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

##  <a name="setcalendarborderdefault"></a>CMonthCalCtrl:: SetCalendarBorderDefault

Geçerli ay Takvim denetiminin kenarlığının varsayılan genişliğini ayarlar.

```
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>Açıklamalar

Kenarlık genişliği, geçerli [Tema](/windows/win32/Controls/visual-styles-overview)tarafından belirtilen varsayılan değere ayarlanır veya temalar kullanılmazsa sıfırdır.

Bu yöntem, Windows SDK açıklanan [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) iletisini gönderir.

##  <a name="setcalid"></a>CMonthCalCtrl:: SetCalID

Geçerli ay Takvim denetiminin Takvim tanımlayıcısını ayarlar.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*calıd*|'ndaki [Takvim tanımlayıcı](/windows/win32/Intl/calendar-identifiers) sabitlerinden biri.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Takvim tanımlayıcısı, Gregoryen (yerelleştirilmiş), Japonca veya Hicri takvimler gibi bölgelere özgü bir takvimi belirtir. Takvimi içeren yerel ayar bilgisayarınızda yüklüyse, *calıd* parametresi tarafından belirtilen bir takvimi göstermek için `SetCalID` yöntemini kullanın.

Bu yöntem, Windows SDK açıklanan [MCM_SETCALID](/windows/win32/Controls/mcm-setcalid) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık takvim denetimine programlı bir şekilde erişmek için kullanılan `m_monthCalCtrl`değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık Takvim denetimini Japonca Emperor Era takvimini görüntüleyecek şekilde ayarlar. `SetCalID` yöntemi, yalnızca bu takvim bilgisayarınızda yüklüyse başarılı olur.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

##  <a name="setcenturyview"></a>CMonthCalCtrl:: SetCenturyView

Geçerli ay Takvim denetimini yüzyıl görünümünü görüntüleyecek şekilde ayarlar.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görünümü yüzyıl görünümünü temsil eden `MCMV_CENTURY`olarak ayarlamak için [CMonthCalCtrl:: SetCurrentView](#setcurrentview) yöntemini kullanır.

##  <a name="setcolor"></a>CMonthCalCtrl:: SetColor

Aylık takvim denetiminin belirtilen alanının rengini ayarlar.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>Parametreler

*nRegion*<br/>
Hangi ay Takvim renginin ayarlanacağını belirten bir tamsayı değeri. Bu değer aşağıdakilerden biri olabilir.

|Değer|Açıklama|
|-----------|-------------|
|MCSC_BACKGROUND|Aylar arasında görünen arka plan rengi.|
|MCSC_MONTHBK|Ay içinde gösterilecek arka plan rengi.|
|MCSC_TEXT|Bir ay içinde metni göstermek için kullanılan renk.|
|MCSC_TITLEBK|Takvimin başlığında görünen arka plan rengi.|
|MCSC_TITLETEXT|Takvimdeki başlık içindeki metni göstermek için kullanılan renk.|
|MCSC_TRAILINGTEXT|Üstbilgiyi ve sondaki gün metnini göstermek için kullanılan renk. Üst bilgi ve sondaki günler, geçerli takvimde görüntülenen önceki ve sonraki ayların günlerdir.|

*ref*<br/>
Aylık takvim denetiminin belirtilen bölümü için yeni renk ayarı için COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, aylık takvim denetiminin belirtilen bölümü için önceki renk ayarını temsil eden bir COLORREF değeri. Aksi takdirde bu ileti-1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETCOLOR](/windows/win32/Controls/mcm-setcolor)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

##  <a name="setcurrentview"></a>CMonthCalCtrl:: SetCurrentView

Geçerli ay Takvim denetimini belirtilen görünümü görüntüleyecek şekilde ayarlar.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwNewView*|'ndaki Aylık, yıllık, on yıl veya Century görünümü belirten aşağıdaki değerlerden biri.<br /><br /> MCMV_MONTH: aylık görünüm<br /><br /> MCMV_YEAR: yıllık görünüm<br /><br /> MCMV_DECADE: on yıl görünüm<br /><br /> MCMV_CENTURY: Century görünümü|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [MCM_SETCURRENTVIEW](/windows/win32/Controls/mcm-setcurrentview) iletisini gönderir.

##  <a name="setcursel"></a>CMonthCalCtrl:: SetCurSel

Bir aylık Takvim denetimi için şu anda seçili olan tarihi ayarlar.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Şu anda seçili olan ay Takvim denetimini gösteren [Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) veya [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru.

*pDateTime*<br/>
Geçerli seçim olarak ayarlanacak tarihi içeren bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETCURSEL](/windows/win32/Controls/mcm-setcursel)davranışını uygular. MFC 'nin `SetCurSel`uygulamasında `COleDateTime` kullanımı, `CTime` kullanımı veya `SYSTEMTIME` yapısı kullanımı belirtebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

##  <a name="setdaystate"></a>CMonthCalCtrl:: SetDayState

Aylık takvim denetiminde gün görüntülemeyi ayarlar.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>Parametreler

*Nay*<br/>
*Pstates* 'in işaret ettiği dizide kaç öğe olduğunu gösteren değer.

*Piller*<br/>
Aylık takvim denetiminin ekranda her günü nasıl çizileceğini tanımlayan bir [monthdaystate](/windows/win32/Controls/monthdaystate) dizisi değeri işaretçisi. MONTHDAYSTATE veri türü, her bitin (1 ila 31) bir ayın bir günün durumunu temsil ettiği bir bit alanıdır. Bir bit açık ise, karşılık gelen gün kalın olarak görüntülenir; Aksi takdirde, vurgu olmadan görüntülenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETDAYSTATE](/windows/win32/Controls/mcm-setdaystate)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

##  <a name="setdecadeview"></a>CMonthCalCtrl:: SetDecadeView

Geçerli ay Takvim denetimini on yıl görünümü olarak ayarlar.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görünümü, on yıl olan görünümü temsil eden `MCMV_DECADE`olarak ayarlamak için [CMonthCalCtrl:: SetCurrentView](#setcurrentview) yöntemini kullanır.

##  <a name="setfirstdayofweek"></a>CMonthCalCtrl:: SetFirstDayOfWeek

Takvimin en sol sütununda görüntülenecek haftanın gününü ayarlar.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>Parametreler

*IDay*<br/>
Haftanın ilk günü olarak hangi günün ayarlanacağını temsil eden bir tamsayı değeri. Bu değer, gün sayılarınızdan biri olmalıdır. Gün numaralarının açıklaması için bkz. [GetFirstDayOfWeek](#getfirstdayofweek) .

*lpnOld*<br/>
Haftanın ilk gününü daha önce ayarlanmış bir tamsayıya işaret eden işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Haftanın önceki ilk günü, Denetim Masası ayarında belirtilen gün olan LOCALE_IFIRSTDAYOFWEEK dışında bir değere ayarlanmışsa sıfır dışı olur. Aksi takdirde, bu işlev 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-setfirstdayofweek)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

##  <a name="setmaxselcount"></a>CMonthCalCtrl:: SetMaxSelCount

Aylık takvim denetiminde seçilebilirler maksimum gün sayısını ayarlar.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>Parametreler

*Ngünde en çok*<br/>
Seçilebilecek maksimum gün sayısını temsil edecek şekilde ayarlanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETMAXSELCOUNT](/windows/win32/Controls/mcm-setmaxselcount)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

##  <a name="setmonthdelta"></a>CMonthCalCtrl:: SetMonthDelta

Aylık Takvim denetimi için kaydırma hızını ayarlar.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>Parametreler

*IDelta*<br/>
Denetimin kaydırma oranı olarak ayarlanacak ay sayısı. Bu değer sıfırsa, ay Delta değeri varsayılan değere sıfırlanır ve bu, denetimde görüntülenecek ayların sayısıdır.

### <a name="return-value"></a>Dönüş Değeri

Önceki kaydırma oranı. Kaydırma hızı daha önce ayarlanmamışsa, dönüş değeri 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETMONTHDELTA](/windows/win32/Controls/mcm-setmonthdelta)davranışını uygular.

##  <a name="setmonthview"></a>CMonthCalCtrl:: SetMonthView

Aylık görünümü görüntülemek için geçerli ay Takvim denetimini ayarlar.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görünümü ay görünümünü temsil eden MCMV_MONTH olarak ayarlamak için [CMonthCalCtrl:: SetCurrentView](#setcurrentview) yöntemini kullanır.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aylık takvim denetimine programlı bir şekilde erişmek için kullanılan `m_monthCalCtrl`değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, ay Takvim denetimini ay, yıl, Deon ve yüzyıl görünümlerini görüntüleyecek şekilde ayarlar.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

##  <a name="setrange"></a>CMonthCalCtrl:: SetRange

Aylık Takvim denetimi için izin verilen en düşük ve en fazla tarihleri ayarlar.

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
`COleDateTime` nesnesine, `CTime` nesnesine veya aralığın en düşük sonundaki tarihi içeren bir [sistem zaman](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

*pMaxRange*<br/>
`COleDateTime` nesnesine, `CTime` nesnesine veya aralığın en yüksek sonundaki tarihi içeren `SYSTEMTIME` yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETRANGE](/windows/win32/Controls/mcm-setrange)davranışını uygular. MFC 'nin `SetRange`uygulamasında `COleDateTime` kullanımı, `CTime` kullanımı veya `SYSTEMTIME` yapısı kullanımı belirtebilirsiniz.

### <a name="example"></a>Örnek

  [CMonthCalCtrl:: GetRange](#getrange)örneğine bakın.

##  <a name="setselrange"></a>CMonthCalCtrl:: SetSelRange

Bir aylık takvim denetiminin seçimini belirli bir tarih aralığına ayarlar.

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
`COleDateTime` nesnesine, `CTime` nesnesine veya aralığın en düşük sonundaki tarihi içeren bir [sistem zaman](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

*pMaxRange*<br/>
`COleDateTime` nesnesine, `CTime` nesnesine veya aralığın en yüksek sonundaki tarihi içeren `SYSTEMTIME` yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETSELRANGE](/windows/win32/Controls/mcm-setselrange)davranışını uygular. MFC 'nin `SetSelRange`uygulamasında `COleDateTime` kullanımı, `CTime` kullanımı veya `SYSTEMTIME` yapısı kullanımı belirtebilirsiniz.

##  <a name="settoday"></a>CMonthCalCtrl:: SetToday

Geçerli günün Takvim denetimini ayarlar.

```
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parametreler

*refDateTime*<br/>
Geçerli tarihi içeren bir [Colandatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine başvuru.

*pDateTime*<br/>
İkinci sürümde, geçerli tarih bilgilerini içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine yönelik bir işaretçi. Üçüncü sürümde, geçerli tarih bilgilerini içeren bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [MCM_SETTODAY](/windows/win32/Controls/mcm-settoday)davranışını uygular.

### <a name="example"></a>Örnek

  [CMonthCalCtrl:: GetToday](#gettoday)örneğine bakın.

##  <a name="setyearview"></a>CMonthCalCtrl:: SetYearView

Geçerli ay Takvim denetimini yıl görünümü olarak ayarlar.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görünümü yıllık görünümü temsil eden MCMV_YEAR olarak ayarlamak için [CMonthCalCtrl:: SetCurrentView](#setcurrentview) yöntemini kullanır.

##  <a name="sizeminreq"></a>CMonthCalCtrl:: SizeMinReq

Aylık Takvim denetimini bir ay görüntüleyen minimum boyuta görüntüler.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>Parametreler

*bYeniden çizmeyi*<br/>
Denetimin yeniden boyanıp yapılıp yapılmayacağını belirtir. Varsayılan olarak, TRUE. FALSE ise, yeniden boyanması gerçekleşmez.

### <a name="return-value"></a>Dönüş Değeri

Aylık Takvim denetimi en düşük değere boyutlandırıldıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`SizeMinReq` çağrısı, bir ay takvimi için aylık takvim denetiminin tamamını başarıyla görüntülüyor.

##  <a name="sizerecttomin"></a>CMonthCalCtrl:: SizeRectToMin

Geçerli ay Takvim denetimi için, belirtilen dikdörtgenle sığan tüm takvimleri içerebilen en küçük dikdörtgeni hesaplar.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpRect*|'ndaki İstenen sayıda takvim içeren bir dikdörtgeni tanımlayan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına yönelik işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Boyutu *lpRect* parametresi tarafından tanımlanan dikdörtgenden küçük veya ona eşit olan bir dikdörtgeni tanımlayan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *lpRect* parametresi tarafından belirtilen dikdörtgende kaç tane takvimlerin uyalamayacağını hesaplar ve ardından bu sayıda takvim içerebilen en küçük dikdörtgeni döndürür. Aslında, bu yöntem istenen sayıda takvim için tam olarak sığacak şekilde belirtilen dikdörtgeni küçültür.

Bu yöntem, Windows SDK açıklanan [MCM_SIZERECTTOMIN](/windows/win32/Controls/mcm-sizerecttomin) iletisini gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDateTimeCtrl Sınıfı](../../mfc/reference/cdatetimectrl-class.md)
