---
title: CDateTimeCtrl Sınıfı
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
ms.openlocfilehash: 577dde7f4f4209f15590825fdb87fe23f788a1ce
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754614"
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl Sınıfı

Tarih ve saat seçici denetiminin işlevselliğini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CDateTimeCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Bir `CDateTimeCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Geçerli tarih ve saat seçici denetimini kapatır.|
|[CDateTimeCtrl::Oluştur](#create)|Tarih ve saat seçici denetimini oluşturur ve `CDateTimeCtrl` nesneye bağlar.|
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Geçerli tarih ve saat seçici denetimi hakkındaki bilgileri alır.|
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Geçerli tarih veya saati görüntülemek için gereken tarih ve saat seçici denetiminin ideal boyutunu döndürür.|
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Tarih ve saat seçici denetimi nde ay takviminin belirli bir bölümünün rengini alır.|
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|Tarih ve `CMonthCalCtrl` saat seçici denetimiyle ilişkili nesneyi alır.|
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Tarih ve saat seçici denetiminin alt ay takvim denetimi tarafından şu anda kullanılan yazı tipini alır.|
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Geçerli tarih ve saat seçici denetiminin stilini alır.|
|[CDateTimeCtrl::GetRange](#getrange)|Tarih ve saat seçici denetimi için geçerli minimum ve en fazla izin verilen sistem sürelerini alır.|
|[CDateTimeCtrl::GetTime](#gettime)|Bir tarih ve saat seçici denetiminden şu anda seçili `SYSTEMTIME` saati alır ve belirli bir yapıya koyar.|
|[CDateTimeCtrl::SetFormat](#setformat)|Tarih ve saat seçici denetiminin ekranını belirli bir biçim dizesiyle ayarlar.|
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Tarih ve saat seçici denetimi nde ay takviminin belirli bir bölümünün rengini ayarlar.|
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|Tarih ve saat seçici denetiminin alt ay takvim denetiminin kullanacağı yazı tipini ayarlar.|
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Geçerli tarih ve saat seçici denetiminin stilini ayarlar.|
|[CDateTimeCtrl::SetAralığı](#setrange)|Tarih ve saat seçici denetimi için izin verilen minimum ve maksimum sistem sürelerini ayarlar.|
|[CDateTimeCtrl::SetTime](#settime)|Tarih ve saat seçici denetiminde saati ayarlar.|

## <a name="remarks"></a>Açıklamalar

Tarih ve saat seçici denetimi (DTP denetimi), tarih ve saat bilgilerini kullanıcıyla değiştirmek için basit bir arabirim sağlar. Bu arabirim, her biri denetimde depolanan tarih ve saat bilgilerinin bir bölümünü görüntüleyen alanlar içerir. Kullanıcı, belirli bir alandaki dizenin içeriğini değiştirerek denetimde depolanan bilgileri değiştirebilir. Kullanıcı fareyi veya klavyeyi kullanarak alandan alana geçebilir.

Oluşturduğunuzda nesneye çeşitli stiller uygulayarak tarih ve saat seçici denetimini özelleştirebilirsiniz. Tarih ve saat seçici denetimine özgü stiller hakkında daha fazla bilgi için Windows SDK'daki Tarih ve [Saat Seçici Denetim Stilleri'ne](/windows/win32/Controls/date-and-time-picker-control-styles) bakın. Biçim stillerini kullanarak DTP denetiminin ekran biçimini ayarlayabilirsiniz. Bu biçim stilleri Windows SDK konu [Tarih ve Zaman Seçici Denetim Stilleri](/windows/win32/Controls/date-and-time-picker-control-styles)"Biçim stilleri" altında açıklanmıştır.

Tarih ve saat seçici denetimi, [CDateTimeCtrl'ı kullanarak](../../mfc/using-cdatetimectrl.md)açıklanan bildirimleri ve geri aramaları da kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CDateTimeCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdtctl.h

## <a name="cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl

Bir `CDateTimeCtrl` nesne inşa eder.

```
CDateTimeCtrl();
```

## <a name="cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal

Geçerli tarih ve saat seçici denetimini kapatır.

```cpp
void CloseMonthCal() const;
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [DTM_CLOSEMONTHCAL](/windows/win32/Controls/dtm-closemonthcal) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat seçici denetimine programlı olarak erişmek için kullanılan değişkeni, *m_dateTimeCtrl*tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli tarih ve saat seçici denetimi için açılır takvimi kapatır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]

## <a name="cdatetimectrlcreate"></a><a name="create"></a>CDateTimeCtrl::Oluştur

Tarih ve saat seçici denetimini oluşturur ve `CDateTimeCtrl` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Tarih saati denetim stillerinin birleşimini belirtir. Tarih ve saat seçici stilleri hakkında daha fazla bilgi için Windows SDK'daki [Tarih ve Saat Seçici Denetim Stilleri'ne](/windows/win32/Controls/date-and-time-picker-control-styles) bakın.

*Rect*<br/>
Tarih ve saat seçici denetiminin konumu ve boyutu olan [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Tarih ve saat seçici denetiminin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi. NULL olmamalıdır.

*Nıd*<br/>
Tarih ve saat seçici denetiminin denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Oluşturma başarılı olsaydı sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##### <a name="to-create-a-date-and-time-picker-control"></a>Tarih ve saat seçici denetimi oluşturmak için

1. Bir `CDateTimeCtrl` nesne oluşturmak için [CDateTimeCtrl'ı](#cdatetimectrl) arayın.

1. Windows tarih ve saat seçici denetimini oluşturan ve `CDateTimeCtrl` nesneye iliştiren bu üye işlevi arayın.

Aradığınızda, `Create`ortak denetimler baş harfe çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]

## <a name="cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo

Geçerli tarih ve saat seçici denetimi hakkındaki bilgileri alır.

```
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pDateTimePickerInfo*|[çıkış] Geçerli tarih ve saat seçici denetiminin açıklamasını alan [DATETIMEPICKERINFO](/windows/win32/api/commctrl/ns-commctrl-datetimepickerinfo) yapısına işaretçi.<br /><br /> Arayan bu yapıyı ayırmakla sorumludur. Ancak, bu yöntem yapının *cbSize* üyesini önharfe laştırır.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [DTM_GETDATETIMEPICKERINFO](/windows/win32/Controls/dtm-getdatetimepickerinfo) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat seçici denetimine programlı olarak erişmek için kullanılan değişkeni, *m_dateTimeCtrl*tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli tarih ve saat seçici denetimi hakkındaki bilgileri başarıyla alıp almadığı gösterilir.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]

## <a name="cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor

Tarih ve saat seçici denetimi nde ay takviminin belirli bir bölümünün rengini alır.

```
COLORREF GetMonthCalColor(int iColor) const;
```

### <a name="parameters"></a>Parametreler

*iColor*<br/>
Ay takviminin hangi renk alanını alınabilmek için belirten **bir int** değeri. Değerler listesi için [SetMonthCalColor](#setmonthcalcolor)için *iColor* parametresini görün.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ay takvim denetiminin belirtilen bölümünün renk ayarını temsil eden BIR COLORREF değeri. İşlev başarısız olursa -1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/dtm-getmccolor)iletisinin DTM_GETMCCOLOR davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]

## <a name="cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl

Tarih ve `CMonthCalCtrl` saat seçici denetimiyle ilişkili nesneyi alır.

```
CMonthCalCtrl* GetMonthCalCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) nesnesine işaretçi veya başarısız olursa veya pencere görünmüyorsa NULL.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat seçici denetimleri, kullanıcı açılır oka tıkladığında bir alt aylık takvim denetimi oluşturur. Nesneye `CMonthCalCtrl` artık gerek olmadığında, yok edilir, bu nedenle uygulamanız tarih saati seçici denetiminin alt ay takvimini temsil eden nesneyi depolamaya güvenmemelidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]

## <a name="cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont

Tarih ve saat seçici denetiminin ay takvimi denetimi tarafından şu anda kullanılan yazı tipini alır.

```
CFont* GetMonthCalFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CFont](../../mfc/reference/cfont-class.md) nesnesine işaretçi veya başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

İade `CFont` değeri tarafından işaret edilen nesne geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle

Geçerli tarih ve saat seçici denetimiyle ilişkili açılır ay takvim denetiminin stilini alır.

```
DWORD GetMonthCalStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saat seçici kontrol stillerinin bitwise kombinasyonu (OR) olan açılır ay takvim denetiminin stili. Daha fazla bilgi için [Ay Takvimi Denetim Stilleri'ne](/windows/win32/Controls/month-calendar-control-styles)bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [DTM_GETMCSTYLE](/windows/win32/Controls/dtm-getmcstyle) iletisini gönderir.

## <a name="cdatetimectrlgetrange"></a><a name="getrange"></a>CDateTimeCtrl::GetRange

Tarih ve saat seçici denetimi için geçerli minimum ve en fazla izin verilen sistem sürelerini alır.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;
```

### <a name="parameters"></a>Parametreler

*pMinAralığı*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine veya nesnede izin verilen en erken zamanı `CDateTimeCtrl` içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine işaretçi.

*pMaxRange*<br/>
Bir `COleDateTime` nesneye veya `CTime` nesneye izin verilen en `CDateTimeCtrl` son zamanı içeren bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hangi aralıkların ayarlandığını gösteren bayraklar içeren bir DWORD değeri. Eğer

`return value & GDTR_MAX`== 0

sonra ikinci parametre geçerlidir. Benzer şekilde, eğer

`return value & GDTR_MIN`== 0

sonra ilk parametre geçerlidir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [DTM_GETRANGE](/windows/win32/Controls/dtm-getrange)davranışını uygular. MFC'nin uygulamasında, kullanımları `COleDateTime` veya `CTime` kullanımları belirtebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]

## <a name="cdatetimectrlgettime"></a><a name="gettime"></a>CDateTimeCtrl::GetTime

Bir tarih ve saat seçici denetiminden şu anda seçili `SYSTEMTIME` saati alır ve belirli bir yapıya koyar.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
İlk sürümde, sistem zaman bilgilerini alacak bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine bir başvuru. İkinci sürümde, sistem zaman bilgilerini alacak bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*pTimeDest*<br/>
Sistem zaman bilgilerini almak için [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına bir işaretçi. NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

İlk sürümde, zaman nesneye başarıyla yazılmışsa `COleDateTime` sıfır olmayan; aksi takdirde 0. İkinci ve üçüncü sürümlerde, [NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) yapısında ayarlanan *dwFlag* üyesine eşit bir DWORD değeri. Daha fazla bilgi için aşağıdaki **Açıklamalar** bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [DTM_GETSYSTEMTIME](/windows/win32/Controls/dtm-getsystemtime)davranışını uygular. `GetTime`MFC uygulamasında, zaman bilgilerini `COleDateTime` depolamak için bir `CTime` `SYSTEMTIME` yapı yı kullanabilirsiniz veya sınıflar yapabilirsiniz.

Yukarıdaki ikinci ve üçüncü sürümlerde dword iade değeri, tarih ve saat seçici denetiminin [NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) yapı üyesi *dwFlags'de*belirtildiği gibi "tarih yok" durumuna ayarlanıp ayarlanmadığını gösterir. Döndürülen değer GDT_NONE eşitse, denetim "tarih yok" durumuna ayarlanır ve DTS_SHOWNONE stilini kullanır. Döndürülen değer GDT_VALID eşitse, sistem süresi hedef konumda başarıyla depolanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]

## <a name="cdatetimectrlgetidealsize"></a><a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize

Geçerli tarih veya saati görüntülemek için gereken tarih ve saat seçici denetiminin ideal boyutunu döndürür.

```
BOOL GetIdealSize(LPSIZE psize) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*psize*|[çıkış] Denetim için ideal boyutu içeren bir [BOYUT](/windows/win32/api/windef/ns-windef-size) yapısı işaretçisi.|

### <a name="return-value"></a>Dönüş Değeri

İade değeri her zaman DOĞRU'dur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [DTM_GETIDEALSIZE](/windows/win32/Controls/dtm-getidealsize) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat seçici denetimine programlı olarak erişmek için kullanılan değişkeni, *m_dateTimeCtrl*tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat seçici denetimini görüntülemek için ideal boyutu alır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]

## <a name="cdatetimectrlsetformat"></a><a name="setformat"></a>CDateTimeCtrl::SetFormat

Tarih ve saat seçici denetiminin ekranını belirli bir biçim dizesiyle ayarlar.

```
BOOL SetFormat(LPCTSTR pstrFormat);
```

### <a name="parameters"></a>Parametreler

*pstrFormat*<br/>
İstenilen ekranı tanımlayan sıfır sonlandırılmış biçim dizesine işaretçi. Bu parametreyi NULL olarak ayarlamak, denetimi geçerli stil için varsayılan biçim dizesine sıfırlar.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

> [!NOTE]
> Kullanıcı girişi bu çağrının başarısını veya başarısızlığını belirlemez.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [DTM_SETFORMAT](/windows/win32/Controls/dtm-setformat)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]

## <a name="cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor

Tarih ve saat seçici denetimi nde ay takviminin belirli bir bölümünün rengini ayarlar.

```
COLORREF SetMonthCalColor(
    int iColor,
    COLORREF ref);
```

### <a name="parameters"></a>Parametreler

*iColor*<br/>
ay takvim denetiminin hangi alanının ayarlandığını belirten **int** değeri. Bu değer aşağıdakilerden biri olabilir.

|Değer|Anlamı|
|-----------|-------------|
|MCSC_BACKGROUND|Aylar arasında görüntülenen arka plan rengini ayarlayın.|
|MCSC_MONTHBK|Bir ay içinde görüntülenen arka plan rengini ayarlayın.|
|MCSC_TEXT|Metni bir ay içinde görüntülemek için kullanılan rengi ayarlayın.|
|MCSC_TITLEBK|Takvimin başlığında görüntülenen arka plan rengini ayarlayın.|
|MCSC_TITLETEXT|Takvimin başlığındaki metni görüntülemek için kullanılan rengi ayarlayın.|
|MCSC_TRAILINGTEXT|Üstbilgi ve sondaki gün metnini görüntülemek için kullanılan rengi ayarlayın. Üstbilgi ve sondaki günler, geçerli takvimde görünen önceki ve sonraki aylardan gelen günlerdir.|

*ref*<br/>
Ay takviminin belirtilen alanı için ayarlanacak rengi temsil eden bir COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ayın takvim denetiminin belirtilen bölümü için önceki renk ayarını temsil eden bir COLORREF değeri. Aksi takdirde, ileti -1 döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [DTM_SETMCCOLOR](/windows/win32/Controls/dtm-setmccolor)davranışını uygular.

### <a name="example"></a>Örnek

  [CDateTimeCtrl örneğine bakın:GetMonthCalColor](#getmonthcalcolor).

## <a name="cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a>CDateTimeCtrl::SetMonthCalFont

Tarih ve saat seçici denetiminin alt ay takvim denetiminin kullanacağı yazı tipini ayarlar.

```cpp
void SetMonthCalFont(
    HFONT hFont,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*hFont*<br/>
Ayarlanacak yazı tipine işle.

*bRedraw*<br/>
Yazı tipini ayarladıktan hemen sonra denetimin yeniden çizilip çizilmeyeceğini belirtir. Bu parametrenin TRUE olarak ayarlanması denetimin kendisini yeniden çizmesine neden olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [DTM_SETMCFONT](/windows/win32/Controls/dtm-setmcfont)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]

> [!NOTE]
> Bu kodu kullanırsanız, *m_MonthFont* türü `CFont`adlı türde `CDialog`türemiş sınıfınızın bir üyesi olmak isteyeceksiniz.

## <a name="cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle

Geçerli tarih ve saat seçici denetimiyle ilişkili açılır ay takvim denetiminin stilini ayarlar.

```
DWORD SetMonthCalStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Dwstyle*|[içinde] Ay takvim denetim stillerinin bitwise birleşimi (OR) olan yeni bir ay takvim denetim stili. Daha fazla bilgi için [Ay Takvimi Denetim Stilleri'ne](/windows/win32/Controls/month-calendar-control-styles)bakın.|

### <a name="return-value"></a>Dönüş Değeri

Açılan ay takvim denetiminin önceki stili.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [DTM_SETMCSTYLE](/windows/win32/Controls/dtm-setmcstyle) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, tarih ve saat seçici denetimine programlı olarak erişmek için kullanılan değişkeni, *m_dateTimeCtrl*tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, hafta numaralarını, haftanın günlerinin kısaltılmış adlarını ve bugün göstergesini görüntülemek için tarih ve saat seçici denetimini ayarlar.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]

## <a name="cdatetimectrlsetrange"></a><a name="setrange"></a>CDateTimeCtrl::SetAralığı

Tarih ve saat seçici denetimi için izin verilen minimum ve maksimum sistem sürelerini ayarlar.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);
```

### <a name="parameters"></a>Parametreler

*pMinAralığı*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine veya nesnede izin verilen en erken zamanı `CDateTimeCtrl` içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine işaretçi.

*pMaxRange*<br/>
Bir `COleDateTime` nesneye veya `CTime` nesneye izin verilen en `CDateTimeCtrl` son zamanı içeren bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/dtm-setrange)iletisi DTM_SETRANGE davranışını uygular. MFC'nin uygulamasında, kullanımları `COleDateTime` veya `CTime` kullanımları belirtebilirsiniz. Nesnenin `COleDateTime` NULL durumu varsa, aralık kaldırılır. `CTime` İşaretçi veya `COleDateTime` işaretçi NULL ise, aralık kaldırılır.

### <a name="example"></a>Örnek

  [CDateTimeCtrl örneğine bakın:GetRange.](#getrange)

## <a name="cdatetimectrlsettime"></a><a name="settime"></a>CDateTimeCtrl::SetTime

Tarih ve saat seçici denetiminde saati ayarlar.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* pTimeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```

### <a name="parameters"></a>Parametreler

*zamanYeni*<br/>
Denetimin ayarlanacağı [coleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine yapılan başvuru.

*pTimeYeni*<br/>
Yukarıdaki ikinci sürümde, denetimin ayarlanacağı zamanı içeren bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine işaretçi. Yukarıdaki üçüncü sürümde, denetimin ayarlanacağı zamanı içeren bir [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [DTM_SETSYSTEMTIME](/windows/win32/Controls/dtm-setsystemtime)davranışını uygular. `SetTime`MFC uygulamasında, zaman bilgilerini ayarlamak `COleDateTime` `CTime` için sınıfları kullanabilir `SYSTEMTIME` veya bir yapı kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Numune CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMonthCalCtrl Sınıfı](../../mfc/reference/cmonthcalctrl-class.md)
