---
title: CDateTimeCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
ms.openlocfilehash: ec9060ba60c4d9877e5ee32bc68da0134f0ccf20
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506992"
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl sınıfı

Tarih ve saat seçici denetiminin işlevselliğini Kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CDateTimeCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDateTimeCtrl:: CDateTimeCtrl](#cdatetimectrl)|Bir `CDateTimeCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDateTimeCtrl:: CloseMonthCal](#closemonthcal)|Geçerli tarih ve saat seçici denetimini kapatır.|
|[CDateTimeCtrl:: Create](#create)|Tarih ve saat seçici denetimini oluşturur ve `CDateTimeCtrl` nesneye ekler.|
|[CDateTimeCtrl:: Getdatetimepickerınfo](#getdatetimepickerinfo)|Geçerli tarih ve saat seçici denetimiyle ilgili bilgileri alır.|
|[CDateTimeCtrl:: Getısatıcıboyutu](#getidealsize)|Geçerli tarih veya saati göstermek için gereken tarih ve saat seçici denetiminin ideal boyutunu döndürür.|
|[CDateTimeCtrl:: GetMonthCalColor](#getmonthcalcolor)|Tarih ve saat seçici denetimindeki ay takviminin belirli bir kısmının rengini alır.|
|[CDateTimeCtrl:: GetMonthCalCtrl](#getmonthcalctrl)|Tarih ve saat seçici denetimiyle ilişkili nesneyialır.`CMonthCalCtrl`|
|[CDateTimeCtrl:: GetMonthCalFont](#getmonthcalfont)|Tarih ve saat seçici denetiminin alt ay Takvim denetimi tarafından kullanılan yazı tipini alır.|
|[CDateTimeCtrl:: GetMonthCalStyle](#getmonthcalstyle)|Geçerli tarih ve saat seçici denetiminin stilini alır.|
|[CDateTimeCtrl:: GetRange](#getrange)|Tarih ve saat seçici denetimi için izin verilen en düşük sistem sürelerini alır.|
|[CDateTimeCtrl:: GetTime](#gettime)|Tarih ve saat seçici denetiminden Şu anda seçili olan saati alır ve belirtilen `SYSTEMTIME` yapıya koyar.|
|[CDateTimeCtrl:: SetFormat](#setformat)|Tarih ve saat seçici denetiminin görüntüsünü, belirli bir biçim dizesine uygun olarak ayarlar.|
|[CDateTimeCtrl:: SetMonthCalColor](#setmonthcalcolor)|Tarih ve saat seçici denetimindeki ay takviminin belirli bir kısmının rengini ayarlar.|
|[CDateTimeCtrl:: SetMonthCalFont](#setmonthcalfont)|Tarih ve saat seçici denetiminin alt ay Takvim denetiminin kullanacağı yazı tipini ayarlar.|
|[CDateTimeCtrl:: SetMonthCalStyle](#setmonthcalstyle)|Geçerli tarih ve saat seçici denetiminin stilini ayarlar.|
|[CDateTimeCtrl:: SetRange](#setrange)|Tarih ve saat seçici denetimi için izin verilen en düşük ve en yüksek sistem sürelerini ayarlar.|
|[CDateTimeCtrl:: SetTime](#settime)|Tarih ve saat seçici denetimindeki saati ayarlar.|

## <a name="remarks"></a>Açıklamalar

Tarih ve saat seçici denetimi (DTP denetimi), bir kullanıcıyla tarih ve saat bilgilerini değiş tokuş etmek için basit bir arabirim sağlar. Bu arabirim, her biri denetimde depolanan tarih ve saat bilgilerinin bir parçasını görüntüleyen alanlar içerir. Kullanıcı, belirli bir alandaki dizenin içeriğini değiştirerek denetimde depolanan bilgileri değiştirebilir. Kullanıcı fare veya klavyeyi kullanarak alandan alana geçebilir.

Tarih ve saat seçici denetimini, nesneyi oluşturduğunuzda nesneye çeşitli stiller uygulayarak özelleştirebilirsiniz. Tarih ve saat Seçici denetimine özgü stiller hakkında daha fazla bilgi için, bkz. Windows SDK [Tarih ve saat Seçici denetim stilleri](/windows/win32/Controls/date-and-time-picker-control-styles) . Biçim stillerini kullanarak DTP denetiminin görüntüleme biçimini ayarlayabilirsiniz. Bu biçim stilleri, Windows SDK konusunun [Tarih ve saat Seçicisi denetim stillerinde](/windows/win32/Controls/date-and-time-picker-control-styles)"biçim stilleri" altında açıklanmaktadır.

Tarih ve saat seçici denetimi Ayrıca, [CDateTimeCtrl kullanma](../../mfc/using-cdatetimectrl.md)bölümünde açıklanan bildirimleri ve geri çağırmaları kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDateTimeCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdtctl. h

##  <a name="cdatetimectrl"></a>CDateTimeCtrl:: CDateTimeCtrl

Bir `CDateTimeCtrl` nesnesi oluşturur.

```
CDateTimeCtrl();
```

##  <a name="closemonthcal"></a>CDateTimeCtrl:: CloseMonthCal

Geçerli tarih ve saat seçici denetimini kapatır.

```
void CloseMonthCal() const;
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [DTM_CLOSEMONTHCAL](/windows/win32/Controls/dtm-closemonthcal) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat Seçici denetimine programlı bir şekilde erişmek için kullanılan *m_dateTimeCtrl*değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli tarih ve saat seçici denetiminin açılan takvimini kapatır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]

##  <a name="create"></a>CDateTimeCtrl:: Create

Tarih ve saat seçici denetimini oluşturur ve `CDateTimeCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Tarih saat denetim stillerinin birleşimini belirtir. Tarih ve saat Seçici stilleri hakkında daha fazla bilgi için Windows SDK [Tarih ve saat Seçicisi denetim stillerine](/windows/win32/Controls/date-and-time-picker-control-styles) bakın.

*Rect*<br/>
Tarih ve saat seçici denetiminin konumu ve boyutu olan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Tarih ve saat seçici denetiminin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi. NULL olmaması gerekir.

*NID*<br/>
Tarih ve saat seçici denetiminin denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Oluşturma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##### <a name="to-create-a-date-and-time-picker-control"></a>Tarih ve saat seçici denetimi oluşturmak için

1. Bir`CDateTimeCtrl` nesne oluşturmak için [CDateTimeCtrl](#cdatetimectrl) çağırın.

1. Windows Tarih ve saat seçici denetimini oluşturan ve `CDateTimeCtrl` nesnesine ekleyen bu üye işlevini çağırın.

' İ çağırdığınızda `Create`ortak denetimler başlatılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]

##  <a name="getdatetimepickerinfo"></a>CDateTimeCtrl:: Getdatetimepickerınfo

Geçerli tarih ve saat seçici denetimiyle ilgili bilgileri alır.

```
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pDateTimePickerInfo*|dışı Geçerli tarih ve saat seçici denetiminin açıklamasını alan [Datetimepickerınfo](/windows/win32/api/commctrl/ns-commctrl-datetimepickerinfo) yapısına yönelik bir işaretçi.<br /><br /> Çağıran, bu yapıyı ayırmaktan sorumludur. Ancak, bu yöntem yapının *cbSize* üyesini başlatır.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [DTM_GETDATETIMEPICKERINFO](/windows/win32/Controls/dtm-getdatetimepickerinfo) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat Seçici denetimine programlı bir şekilde erişmek için kullanılan *m_dateTimeCtrl*değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli tarih ve saat seçici denetimiyle ilgili bilgileri başarıyla alıp almadığını gösterir.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]

##  <a name="getmonthcalcolor"></a>CDateTimeCtrl:: GetMonthCalColor

Tarih ve saat seçici denetimindeki ay takviminin belirli bir kısmının rengini alır.

```
COLORREF GetMonthCalColor(int iColor) const;
```

### <a name="parameters"></a>Parametreler

*ırenkli*<br/>
Alınacak ay takviminin renk alanını belirleyen bir **int** değeri. Değerlerin listesi için bkz. [SetMonthCalColor](#setmonthcalcolor)Için *IColor* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa aylık takvim denetiminin belirtilen bölümü için renk ayarını temsil eden bir COLORREF değeri. İşlev başarısız olursa-1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [DTM_GETMCCOLOR](/windows/win32/Controls/dtm-getmccolor)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]

##  <a name="getmonthcalctrl"></a>CDateTimeCtrl:: GetMonthCalCtrl

Tarih ve saat seçici denetimiyle ilişkili nesneyialır.`CMonthCalCtrl`

```
CMonthCalCtrl* GetMonthCalCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) nesnesine bir işaretçi veya başarısız olursa veya pencere görünür değilse null.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat seçici denetimleri, Kullanıcı açılır oka tıkladığında bir alt ay Takvim denetimi oluşturur. `CMonthCalCtrl` Nesne artık gerekli olmadığında, yok edilir, bu nedenle uygulamanızın tarih saat seçici denetiminin alt ay takvimini temsil eden nesneyi depolamaya dayanmaması gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]

##  <a name="getmonthcalfont"></a>CDateTimeCtrl:: GetMonthCalFont

Tarih ve saat seçici denetiminin aylık Takvim denetimi tarafından şu anda kullanılan yazı tipini alır.

```
CFont* GetMonthCalFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CFont](../../mfc/reference/cfont-class.md) nesnesine yönelik bir işaretçi veya başarısız olursa null.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri tarafından işaret edilen nesnegeçicibirnesnevebirsonrakiboştaişlemesüresiboyuncayokedilir.`CFont`

##  <a name="getmonthcalstyle"></a>CDateTimeCtrl:: GetMonthCalStyle

Geçerli tarih ve saat seçici denetimiyle ilişkili olan açılan ay takvimi denetiminin stilini alır.

```
DWORD GetMonthCalStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saat Seçici denetim stillerinin bit tabanlı birleşimi (veya) olan açılan ay Takvim denetiminin stili. Daha fazla bilgi için bkz. [aylık Takvim denetimi stilleri](/windows/win32/Controls/month-calendar-control-styles).

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [DTM_GETMCSTYLE](/windows/win32/Controls/dtm-getmcstyle) iletisini gönderir.

##  <a name="getrange"></a>CDateTimeCtrl:: GetRange

Tarih ve saat seçici denetimi için izin verilen en düşük sistem sürelerini alır.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;
```

### <a name="parameters"></a>Parametreler

*pMinRange*<br/>
Bir [copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine veya `CDateTimeCtrl` nesne içinde izin verilen en erken zamanı içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine yönelik bir işaretçi.

*pMaxRange*<br/>
Nesnede izin verilen `COleDateTime` `CTime` ensonsaatiiçerenbirnesne`CDateTimeCtrl` veya nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Hangi aralıkların ayarlandığını belirten bayrakları içeren bir DWORD değeri. Eğer

`return value & GDTR_MAX` == 0

ikinci parametre geçerli olur. Benzer şekilde,

`return value & GDTR_MIN` == 0

ardından ilk parametre geçerli olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [DTM_GETRANGE](/windows/win32/Controls/dtm-getrange)davranışını uygular. MFC uygulamasında, ya da `COleDateTime` `CTime` kullanımları belirtebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]

##  <a name="gettime"></a>CDateTimeCtrl:: GetTime

Tarih ve saat seçici denetiminden Şu anda seçili olan saati alır ve belirtilen `SYSTEMTIME` yapıya koyar.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
İlk sürümde, sistem saati bilgilerini alacak bir [Colandatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine başvuru. İkinci sürümde, sistem saati bilgilerini alacak bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*pTimeDest*<br/>
Sistem saati bilgilerini almak için [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi. NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

İlk sürümde, zaman `COleDateTime` nesneye başarıyla yazılmışsa, sıfır dışında bir değer; Aksi takdirde 0. İkinci ve üçüncü sürümlerde, bir DWORD değeri, [Nmdatetimechange](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) yapısında ayarlanan *dwFlag* üyesine eşittir. Daha fazla bilgi için aşağıdaki **açıklamalar** bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [DTM_GETSYSTEMTIME](/windows/win32/Controls/dtm-getsystemtime)davranışını uygular. MFC uygulamasında `GetTime`, veya `COleDateTime` `CTime` sınıflarını kullanabilir veya bir `SYSTEMTIME` yapıyı, zaman bilgilerini depolamak için kullanabilirsiniz.

Yukarıdaki ikinci ve üçüncü sürümlerde DWORD dönüş değeri, tarih ve saat seçici denetiminin "Tarih yok" durumuna ayarlanmış olup olmadığını, [Nmdatetimechange](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) yapısı üye *dwFlags*bölümünde gösterildiği gibi gösterir. Değer GDT_NONE eşitse, denetim "Tarih yok" durumuna ayarlanır ve DTS_SHOWNONE stilini kullanır. Döndürülen değer GDT_VALID eşitse, sistem saati hedef konumda başarıyla depolanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]

##  <a name="getidealsize"></a>CDateTimeCtrl:: Getısatıcıboyutu

Geçerli tarih veya saati göstermek için gereken tarih ve saat seçici denetiminin ideal boyutunu döndürür.

```
BOOL GetIdealSize(LPSIZE psize) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*psıze*|dışı Denetim için ideal boyutu içeren bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısına yönelik işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri her zaman TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [DTM_GETIDEALSIZE](/windows/win32/Controls/dtm-getidealsize) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat Seçici denetimine programlı bir şekilde erişmek için kullanılan *m_dateTimeCtrl*değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat seçici denetimini göstermek için ideal boyutu alır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]

##  <a name="setformat"></a>CDateTimeCtrl:: SetFormat

Tarih ve saat seçici denetiminin görüntüsünü, belirli bir biçim dizesine uygun olarak ayarlar.

```
BOOL SetFormat(LPCTSTR pstrFormat);
```

### <a name="parameters"></a>Parametreler

*pstrFormat*<br/>
İstenen ekranı tanımlayan sıfır ile sonlandırılmış bir biçim dizesinin işaretçisi. Bu parametrenin NULL olarak ayarlanması, geçerli stil için denetimi varsayılan biçim dizesine sıfırlar.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

> [!NOTE]
>  Kullanıcı girişi bu çağrı için başarılı veya başarısız olduğunu tespit etmez.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [DTM_SETFORMAT](/windows/win32/Controls/dtm-setformat)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]

##  <a name="setmonthcalcolor"></a>CDateTimeCtrl:: SetMonthCalColor

Tarih ve saat seçici denetimindeki ay takviminin belirli bir kısmının rengini ayarlar.

```
COLORREF SetMonthCalColor(
    int iColor,
    COLORREF ref);
```

### <a name="parameters"></a>Parametreler

*ırenkli*<br/>
ay Takvim denetiminin hangi alanını ayarlanacağını belirten **int** değeri. Bu değer aşağıdakilerden biri olabilir.

|Değer|Açıklama|
|-----------|-------------|
|MCSC_BACKGROUND|Aylar arasında Görüntülenme arka plan rengini ayarlayın.|
|MCSC_MONTHBK|Bir ay içinde gösterilecek arka plan rengini ayarlayın.|
|MCSC_TEXT|Bir ay içinde metni göstermek için kullanılan rengi ayarlayın.|
|MCSC_TITLEBK|Takvimin başlığında görünen arka plan rengini ayarlayın.|
|MCSC_TITLETEXT|Takvimdeki başlık içinde metni göstermek için kullanılan rengi ayarlayın.|
|MCSC_TRAILINGTEXT|Üstbilgiyi ve sondaki gün metnini göstermek için kullanılan rengi ayarlayın. Üst bilgi ve sondaki günler, geçerli takvimde görüntülenen önceki ve sonraki ayların günlerdir.|

*ref*<br/>
Ay takviminin belirtilen alanı için ayarlanacak rengi temsil eden COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ay Takvim denetiminin belirtilen bölümü için önceki renk ayarını temsil eden bir COLORREF değeri. Aksi takdirde ileti-1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [DTM_SETMCCOLOR](/windows/win32/Controls/dtm-setmccolor)davranışını uygular.

### <a name="example"></a>Örnek

  [CDateTimeCtrl:: GetMonthCalColor](#getmonthcalcolor)örneğine bakın.

##  <a name="setmonthcalfont"></a>CDateTimeCtrl:: SetMonthCalFont

Tarih ve saat seçici denetiminin alt ay Takvim denetiminin kullanacağı yazı tipini ayarlar.

```
void SetMonthCalFont(
    HFONT hFont,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*hFont*<br/>
Ayarlanacak yazı tipi için tanıtıcı.

*bRedraw*<br/>
Yazı tipinin ayarlanmasına hemen sonra denetimin yeniden çizilip çizmeyeceğini belirtir. Bu parametrenin TRUE olarak ayarlanması, denetimin kendisini yeniden çizmesine neden olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [DTM_SETMCFONT](/windows/win32/Controls/dtm-setmcfont)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]

> [!NOTE]
>  Bu kodu kullanırsanız, türetilmiş sınıfınızın bir üyesini türünde `CDialog` `CFont` *m_MonthFont* adlı bir üye yapmak isteyeceksiniz.

##  <a name="setmonthcalstyle"></a>CDateTimeCtrl:: SetMonthCalStyle

Geçerli tarih ve saat seçici denetimiyle ilişkili olan açılan ay takvimi denetiminin stilini ayarlar.

```
DWORD SetMonthCalStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwStyle*|'ndaki Aylık Takvim denetim stillerinin bit tabanlı birleşimi (veya) olan yeni bir aylık Takvim denetimi stili. Daha fazla bilgi için bkz. [aylık Takvim denetimi stilleri](/windows/win32/Controls/month-calendar-control-styles).|

### <a name="return-value"></a>Dönüş Değeri

Açılan aylık takvim denetiminin önceki stili.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [DTM_SETMCSTYLE](/windows/win32/Controls/dtm-setmcstyle) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat Seçici denetimine programlı bir şekilde erişmek için kullanılan *m_dateTimeCtrl*değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat seçici denetimini, hafta numaralarını, haftanın gün sayısının kısaltılmış adlarını ve bugün göstergesinden birini görüntüleyecek şekilde ayarlar.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]

##  <a name="setrange"></a>CDateTimeCtrl:: SetRange

Tarih ve saat seçici denetimi için izin verilen en düşük ve en yüksek sistem sürelerini ayarlar.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);
```

### <a name="parameters"></a>Parametreler

*pMinRange*<br/>
Bir [copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine veya `CDateTimeCtrl` nesne içinde izin verilen en erken zamanı içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine yönelik bir işaretçi.

*pMaxRange*<br/>
Nesnede izin verilen `COleDateTime` `CTime` ensonsaatiiçerenbirnesne`CDateTimeCtrl` veya nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [DTM_SETRANGE](/windows/win32/Controls/dtm-setrange)davranışını uygular. MFC uygulamasında, ya da `COleDateTime` `CTime` kullanımları belirtebilirsiniz. `COleDateTime` Nesnenin durumu null ise, Aralık kaldırılır. `CTime` İşaretçi`COleDateTime` veya işaretçi null ise, Aralık kaldırılır.

### <a name="example"></a>Örnek

  [CDateTimeCtrl:: GetRange](#getrange)örneğine bakın.

##  <a name="settime"></a>CDateTimeCtrl:: SetTime

Tarih ve saat seçici denetimindeki saati ayarlar.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* pTimeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```

### <a name="parameters"></a>Parametreler

*Timeneni*<br/>
Denetimin ayarlanacağı bir [Cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine başvuru.

*Ptimeneni*<br/>
Yukarıdaki ikinci sürümde, denetimin ayarlanacağı saati içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine yönelik bir işaretçi. Yukarıdaki üçüncü sürümde, denetimin ayarlanacağı saati içeren bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [DTM_SETSYSTEMTIME](/windows/win32/Controls/dtm-setsystemtime)davranışını uygular. MFC uygulamasında `SetTime` `SYSTEMTIME` , `COleDateTime` veya`CTime` sınıflarını kullanabilir ya da zaman bilgilerini ayarlamak için bir yapı kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMonthCalCtrl Sınıfı](../../mfc/reference/cmonthcalctrl-class.md)
