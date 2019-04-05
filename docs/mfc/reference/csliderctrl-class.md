---
title: CSliderCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
ms.openlocfilehash: 4db27112daf65b2c3f477527cd7b4351b91d7f18
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776641"
---
# <a name="csliderctrl-class"></a>CSliderCtrl sınıfı

Windows ortak kaydırıcı denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSliderCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Oluşturur bir `CSliderCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSliderCtrl::ClearSel](#clearsel)|Bir kaydırıcı denetimindeki geçerli bölüm temizler.|
|[CSliderCtrl::ClearTics](#cleartics)|Geçerli değer çizgilerinin bir kaydırıcı denetimi kaldırır.|
|[CSliderCtrl::Create](#create)|Bir kaydırıcı denetimi oluşturur ve ona bağlanan bir `CSliderCtrl` nesne.|
|[CSliderCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir kaydırıcı denetimi oluşturur ve ona ekler bir `CSliderCtrl` nesne.|
|[CSliderCtrl::GetBuddy](#getbuddy)|Belirli bir konumda bir kaydırıcı denetiminin buddy penceresindeki tanıtıcısını alır.|
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Kaydırıcı denetim kanalı VHD'nin boyutunu alır.|
|[CSliderCtrl::GetLineSize](#getlinesize)|Bir kaydırıcı denetimi satır boyutunu alır.|
|[CSliderCtrl::GetNumTics](#getnumtics)|Değer çizgilerinin bir kaydırıcı denetimindeki sayısını alır.|
|[CSliderCtrl::GetPageSize](#getpagesize)|Bir kaydırıcı denetimi sayfa boyutunu alır.|
|[CSliderCtrl::GetPos](#getpos)|Kaydırıcı geçerli konumunu alır.|
|[CSliderCtrl::GetRange](#getrange)|Kaydırıcı için minimum ve maksimum konumları alır.|
|[CSliderCtrl::GetRangeMax](#getrangemax)|Bir kaydırıcının en fazla konumunu alır.|
|[CSliderCtrl::GetRangeMin](#getrangemin)|Kaydırıcı için en düşük konumu alır.|
|[CSliderCtrl::GetSelection](#getselection)|Geçerli seçim aralığını alır.|
|[CSliderCtrl::GetThumbLength](#getthumblength)|Geçerli trackbar denetimi kaydırıcı uzunluğunu alır.|
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Kaydırıcı denetim parmak boyutunu alır.|
|[CSliderCtrl::GetTic](#gettic)|Belirtilen değer çizgisi konumunu alır.|
|[CSliderCtrl::GetTicArray](#getticarray)|Bir kaydırıcı denetimi için onay işareti konumlarına dizisini alır.|
|[CSliderCtrl::GetTicPos](#getticpos)|İstemci koordinatları belirtilen çizgisi konumunu alır.|
|[CSliderCtrl::GetToolTips](#gettooltips)|Kaydırıcı denetimi için atanan araç ipucu denetimi için tanıtıcı varsa alır.|
|[CSliderCtrl::SetBuddy](#setbuddy)|Bir pencere bir kaydırıcı denetiminin buddy penceresindeki olarak atar.|
|[CSliderCtrl::SetLineSize](#setlinesize)|Bir kaydırıcı denetimi satır boyutunu ayarlar.|
|[CSliderCtrl::SetPageSize](#setpagesize)|Bir kaydırıcı denetiminin sayfa boyutunu ayarlar.|
|[CSliderCtrl::SetPos](#setpos)|Kaydırıcı geçerli konumunu ayarlar.|
|[CSliderCtrl::SetRange](#setrange)|Kaydırıcı için minimum ve maksimum konumları ayarlar.|
|[CSliderCtrl::SetRangeMax](#setrangemax)|Bir kaydırıcının en fazla konumunu ayarlar.|
|[CSliderCtrl::SetRangeMin](#setrangemin)|Kaydırıcı için en düşük konumu ayarlar.|
|[CSliderCtrl::SetSelection](#setselection)|Geçerli seçimi aralığı ayarlar.|
|[CSliderCtrl::SetThumbLength](#setthumblength)|Kaydırıcı uzunluğu geçerli trackbar denetimi ayarlar.|
|[CSliderCtrl::SetTic](#settic)|Belirtilen değer çizgisi konumunu ayarlar.|
|[CSliderCtrl::SetTicFreq](#setticfreq)|Kaydırıcı denetimi artırma her değer çizgisi sıklığını ayarlar.|
|[CSliderCtrl::SetTipSide](#settipside)|Konumlar araç ipucu denetimi trackbar denetimi tarafından kullanılır.|
|[CSliderCtrl::SetToolTips](#settooltips)|Araç İpucu denetimi için bir kaydırıcı denetimi atar.|

## <a name="remarks"></a>Açıklamalar

"Kaydırıcı denetimi" (trackbar olarak da bilinir) bir kaydırıcı ve isteğe bağlı bir değer çizgileri içeren bir penceredir. Kullanıcı fare ya da yön tuşlarını kullanarak, kaydırıcıyı hareket ettirdiğinde denetim değişiklik belirtmek için bildirim iletileri gönderir.

Kaydırıcı denetimlerini, bir ayrık değere veya bir dizi ardışık değerleri bir aralıktaki seçmesini istediğinizde kullanışlıdır. Örneğin, verilen değer çizgisi için kaydırıcıyı hareket ettirerek klavye yineleme oranını ayarlamak izin vermek için bir kaydırıcı denetimi kullanabilirsiniz.

Bu denetimi (ve bu nedenle `CSliderCtrl` sınıfı) ve üzeri yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programlar için kullanılabilir.

Kaydırıcı oluşturduğunuzda, belirttiğiniz aralıklarla taşır. Kaydırıcı beş bir dizi olması gerektiğini belirtin, örneğin, kaydırıcıyı yalnızca altı konumları kaplayabilir: kaydırıcı denetimi aralığındaki her artış için bir konum ve sol tarafında bir konumu. Genellikle, her biri bu konumları onay işareti tarafından tanımlanır.

Bir kaydırıcı Oluşturucusu kullanarak oluşturun ve `Create` üye işlevini `CSliderCtrl`. Bir kaydırıcı denetimi oluşturduktan sonra içindeki üye işlevleri kullanabileceğinizi `CSliderCtrl` birçok özelliklerini değiştirmek için. Kaydırıcı için minimum ve maksimum konumlarını ayarlama, değer çizgileri çizim, bir seçim aralığını ayarlama ve kaydırıcıyı yeniden konumlandırma yapabileceğiniz değişiklikleri içerir.

Kullanma hakkında daha fazla bilgi için `CSliderCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [CSliderCtrl kullanma](../../mfc/using-csliderctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSliderCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="clearsel"></a>  CSliderCtrl::ClearSel

Bir kaydırıcı denetimindeki geçerli bölüm temizler.

```
void ClearSel(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*bRedraw*<br/>
Bayrak yeniden çizin. Bu parametre TRUE ise, kaydırıcıyı seçimi tamamlandıktan sonra yeniden çizilir; Aksi takdirde kaydırıcı çizilmez.

##  <a name="cleartics"></a>  CSliderCtrl::ClearTics

Geçerli değer çizgilerinin bir kaydırıcı denetimi kaldırır.

```
void ClearTics(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*bRedraw*<br/>
Bayrak yeniden çizin. Bu parametre TRUE ise, değer çizgilerinin temizlendikten sonra kaydırıcıyı çizilir; Aksi takdirde kaydırıcı çizilmez.

##  <a name="create"></a>  CSliderCtrl::Create

Bir kaydırıcı denetimi oluşturur ve ona bağlanan bir `CSliderCtrl` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Kaydırıcı denetiminin stilini belirtir. Herhangi bir birleşimini uygulamak [kaydırıcı denetim stilleri](/windows/desktop/Controls/trackbar-control-styles)denetlemek için Windows SDK içinde açıklandığı gibi.

*rect*<br/>
Kaydırıcı denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı.

*pParentWnd*<br/>
Kaydırıcı denetiminin üst penceresine, genellikle belirtir bir `CDialog`. NULL olmamalıdır.

*nID*<br/>
Kaydırıcı denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CSliderCtrl` iki adımda. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, kaydırıcı denetimi oluşturur ve ona ekler `CSliderCtrl` nesne.

İçin ayarlanan değerlerle bağlı olarak *dwStyle*, kaydırıcı denetimi dikey veya yatay hizalama olabilir. Değer çizgilerinin iki tarafında olabilir hem yüz veya hiçbiridir. Ayrıca, bir dizi ardışık değerleri belirtmek için de kullanılabilir.

Kaydırıcı denetimi için genişletilmiş pencere stilleri uygulamak için arama [CreateEx](#createex) yerine `Create`.

##  <a name="createex"></a>  CSliderCtrl::CreateEx

Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CSliderCtrl` nesne.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.

*dwStyle*<br/>
Kaydırıcı denetiminin stilini belirtir. Herhangi bir birleşimini uygulamak [kaydırıcı denetim stilleri](/windows/desktop/Controls/trackbar-control-styles)denetlemek için Windows SDK içinde açıklandığı gibi.

*rect*<br/>
Bir başvuru bir [RECT](/previous-versions/dd162897\(v=vs.85\)) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.

*pParentWnd*<br/>
Denetimin ana penceresine bir işaretçi.

*nID*<br/>
Denetimin alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.

##  <a name="csliderctrl"></a>  CSliderCtrl::CSliderCtrl

Oluşturur bir `CSliderCtrl` nesne.

```
CSliderCtrl();
```

##  <a name="getbuddy"></a>  CSliderCtrl::GetBuddy

Belirli bir konumda bir kaydırıcı denetiminin buddy penceresindeki tanıtıcısını alır.

```
CWnd* GetBuddy(BOOL fLocation = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*fLocation*<br/>
Almak için iki buddy penceresinin tutamaçlarından gösteren bir Boole değeri. Aşağıdaki değerlerden biri olabilir:

- TRUE, sol kaydırıcının arkadaş tanıtıcısını alır. Kaydırıcı denetimi TBS_VERT stili kullanıyorsa, kaydırıcıyı yukarıda arkadaş ileti alır.

- FALSE kaydırıcı sağındaki arkadaş tanıtıcısını alır. Kaydırıcı denetimi TBS_VERT stili kullanıyorsa, ileti arkadaş kaydırıcının altına alır.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) tarafından belirtilen konumda buddy penceresindeki nesnesini *fLocation*, veya bu konumda hiçbir buddy penceresindeki yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [TBM_GETBUDDY](/windows/desktop/Controls/tbm-getbuddy)Windows SDK içinde açıklandığı gibi. Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](/windows/desktop/Controls/trackbar-control-styles) Windows SDK.

##  <a name="getchannelrect"></a>  CSliderCtrl::GetChannelRect

Kaydırıcı denetim kanalı için sınırlayıcı dikdörtgeni konumu ve boyutu alır.

```
void GetChannelRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametreler

*lprc*<br/>
Bir işaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) boyutunu ve konumunu kanalının içeren nesne işlevi döndüğünde dikdörtgen çevreleyen.

### <a name="remarks"></a>Açıklamalar

Kanal kaydırıcı taşıyan ve aralığı seçildiğinde vurgulama içeren üzerinden alandır.

##  <a name="getlinesize"></a>  CSliderCtrl::GetLineSize

Bir kaydırıcı denetimi için satır boyutunu alır.

```
int GetLineSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için bir satır boyutu.

### <a name="remarks"></a>Açıklamalar

Satır boyutu için TB_LINEUP ve TB_LINEDOWN bildirimleri ne kadar kaydırıcıyı hareket etkiler. 1 satır boyutu için varsayılan ayardır.

##  <a name="getnumtics"></a>  CSliderCtrl::GetNumTics

Değer çizgilerinin bir kaydırıcı denetimindeki sayısını alır.

```
UINT GetNumTics() const;
```

### <a name="return-value"></a>Dönüş Değeri

Değer çizgilerinin kaydırıcı denetimindeki sayısı.

##  <a name="getpagesize"></a>  CSliderCtrl::GetPageSize

Bir kaydırıcı denetimi için sayfa boyutunu alır.

```
int GetPageSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için bir sayfa boyutu.

### <a name="remarks"></a>Açıklamalar

Sayfa boyutunu TB_PAGEUP ve TB_PAGEDOWN bildirimleri ne kadar kaydırıcıyı hareket etkiler.

##  <a name="getpos"></a>  CSliderCtrl::GetPos

Bir kaydırıcı denetimi kaydırıcı geçerli konumunu alır.

```
int GetPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli konumu.

##  <a name="getrange"></a>  CSliderCtrl::GetRange

Bir kaydırıcı denetimindeki kaydırıcı için maksimum ve minimum konumları alır.

```
void GetRange(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
En düşük konumu alır bir tamsayı başvuru.

*nMax*<br/>
Başvuru tamsayıya maksimum konumunu alır.

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından başvurulan tamsayı değerleri kopyalar *nMin* ve *nMax*.

##  <a name="getrangemax"></a>  CSliderCtrl::GetRangeMax

Bir kaydırıcı denetimi en fazla konumda kaydırıcı alır.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Dönüş Değeri

En fazla denetimin konumu.

##  <a name="getrangemin"></a>  CSliderCtrl::GetRangeMin

Bir kaydırıcı denetimi kaydırıcı için en düşük konumu alır.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin en düşük konumu.

##  <a name="getselection"></a>  CSliderCtrl::GetSelection

Bir kaydırıcı denetimindeki geçerli bölüm başlangıç ve bitiş konumları alır.

```
void GetSelection(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Geçerli seçimi başlangıç konumu alır bir tamsayı başvuru.

*nMax*<br/>
Geçerli seçimi bitiş konumu alır bir tamsayı başvuru.

##  <a name="getthumblength"></a>  CSliderCtrl::GetThumbLength

Geçerli trackbar denetimi kaydırıcı uzunluğunu alır.

```
int GetThumbLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcıyı piksel cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [TBM_GETTHUMBLENGTH](/windows/desktop/Controls/tbm-getthumblength) Windows SDK'da açıklanan ileti.

##  <a name="getthumbrect"></a>  CSliderCtrl::GetThumbRect

Bir kaydırıcı denetimi (Flash) kaydırıcı için sınırlayıcı dikdörtgeni konumu ve boyutu alır.

```
void GetThumbRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametreler

*lprc*<br/>
Bir işaretçi bir `CRect` işlevi döndüğünde dikdörtgen kaydırıcı içeren nesne.

##  <a name="gettic"></a>  CSliderCtrl::GetTic

Bir kaydırıcı denetimi onay işareti konumunu alır.

```
int GetTic(int nTic) const;
```

### <a name="parameters"></a>Parametreler

*nTic*<br/>
Değer çizgisi tanımlama sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen değer çizgisi veya - 1 ise konumunu *nTic* geçerli bir dizin belirtmiyor.

##  <a name="getticarray"></a>  CSliderCtrl::GetTicArray

Bir kaydırıcı denetimi için değer çizgilerinin konumlarını içeren bir dizi adresini alır.

```
DWORD* GetTicArray() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için onay işareti konumlarını içeren bir dizi adresi.

##  <a name="getticpos"></a>  CSliderCtrl::GetTicPos

Bir kaydırıcı denetimindeki çizgisi geçerli fiziksel konumunu alır.

```
int GetTicPos(int nTic) const;
```

### <a name="parameters"></a>Parametreler

*nTic*<br/>
Değer çizgisi tanımlama sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Fiziksel konumunu, istemci koordinatlarında belirtilen değer çizgisi veya - 1 ise *nTic* geçerli bir dizin belirtmiyor.

##  <a name="gettooltips"></a>  CSliderCtrl::GetToolTips

Kaydırıcı denetimi için atanan araç ipucu denetimi için tanıtıcı varsa alır.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesne veya araç ipuçları kullanımda değilse NULL. Kaydırıcı denetimi TBS_TOOLTIPS stili kullanmıyorsa, döndürülen değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [TBM_GETTOOLTIPS](/windows/desktop/Controls/tbm-gettooltips)Windows SDK içinde açıklandığı gibi. Bu üye işlevinin döndürdüğü Not bir `CToolTipCtrl` yerine bir denetim için bir tanıtıcı nesnesi.

Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](/windows/desktop/Controls/trackbar-control-styles) Windows SDK.

##  <a name="setbuddy"></a>  CSliderCtrl::SetBuddy

Bir pencere bir kaydırıcı denetiminin buddy penceresindeki olarak atar.

```
CWnd* SetBuddy(
    CWnd* pWndBuddy,
    BOOL fLocation = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWndBuddy*<br/>
Bir işaretçi bir `CWnd` kaydırıcı denetiminin buddy ayarlanacak nesne.

*fLocation*<br/>
Buddy penceresindeki görüntülenecek konumu belirten değer. Bu değer aşağıdakilerden biri olabilir:

- Trackbar denetimi TBS_HORZ stili kullanıyorsa TRUE arkadaş trackbar solunda görünür. Trackbar TBS_VERT stili kullanıyorsa, buddy trackbar denetimin üstünde görünür.

- Trackbar denetimi TBS_HORZ stili kullanıyorsa FALSE arkadaş trackbar sağında görünür. Trackbar TBS_VERT stili kullanıyorsa, buddy trackbar denetimi altında görünür.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) bu konumdaki kaydırıcı denetimi daha önce atanan nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [TBM_SETBUDDY](/windows/desktop/Controls/tbm-setbuddy)Windows SDK içinde açıklandığı gibi. Bu üye işlev işaretçileri kullandığına dikkat edin `CWnd` pencere işleyicileri, dönüş değeri ve parametresi yerine, nesneleri.

Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](/windows/desktop/Controls/trackbar-control-styles) Windows SDK.

##  <a name="setlinesize"></a>  CSliderCtrl::SetLineSize

Bir kaydırıcı denetimi için satır boyutunu ayarlar.

```
int SetLineSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
Kaydırıcı denetimi yeni satır boyutu.

### <a name="return-value"></a>Dönüş Değeri

Önceki satır boyutu.

### <a name="remarks"></a>Açıklamalar

Satır boyutu için TB_LINEUP ve TB_LINEDOWN bildirimleri ne kadar kaydırıcıyı hareket etkiler.

##  <a name="setpagesize"></a>  CSliderCtrl::SetPageSize

Bir kaydırıcı denetimi için sayfa boyutunu ayarlar.

```
int SetPageSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
Kaydırıcı denetimi yeni sayfa boyutu.

### <a name="return-value"></a>Dönüş Değeri

Önceki sayfa boyutu.

### <a name="remarks"></a>Açıklamalar

Sayfa boyutunu TB_PAGEUP ve TB_PAGEDOWN bildirimleri ne kadar kaydırıcıyı hareket etkiler.

##  <a name="setpos"></a>  CSliderCtrl::SetPos

Kaydırıcı denetiminde kaydırıcı geçerli konumunu ayarlar.

```
void SetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Yeni kaydırıcı konumunu belirtir.

##  <a name="setrange"></a>  CSliderCtrl::SetRange

Bir kaydırıcı denetimi kaydırıcı için (minimum ve maksimum konumlar) aralığı ayarlar.

```
void SetRange(
    int nMin,
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Kaydırıcı için en düşük konumu.

*nMax*<br/>
Maksimum kaydırıcı konumu.

*bRedraw*<br/>
Güncellenmediğini bayrak. Bu parametre TRUE ise, kaydırıcıyı aralığı ayarladıktan sonra çizilir; Aksi takdirde kaydırıcı çizilmez.

##  <a name="setrangemax"></a>  CSliderCtrl::SetRangeMax

En büyük aralık kaydırıcı bir kaydırıcı denetimi için ayarlar.

```
void SetRangeMax(
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*nMax*<br/>
Maksimum kaydırıcı konumu.

*bRedraw*<br/>
Güncellenmediğini bayrak. Bu parametre TRUE ise, kaydırıcıyı aralığı ayarladıktan sonra çizilir; Aksi takdirde kaydırıcı çizilmez.

##  <a name="setrangemin"></a>  CSliderCtrl::SetRangeMin

En küçük aralık kaydırıcı bir kaydırıcı denetimi için ayarlar.

```
void SetRangeMin(
    int nMin,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Kaydırıcı için en düşük konumu.

*bRedraw*<br/>
Güncellenmediğini bayrak. Bu parametre TRUE ise, kaydırıcıyı aralığı ayarladıktan sonra çizilir; Aksi takdirde kaydırıcı çizilmez.

##  <a name="setselection"></a>  CSliderCtrl::SetSelection

Geçerli seçim için başlangıç ve bitiş konumları bir kaydırıcı denetimi ayarlar.

```
void SetSelection(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Kaydırıcı için başlangıç konumu.

*nMax*<br/>
Kaydırıcı için bitiş konumu.

##  <a name="setthumblength"></a>  CSliderCtrl::SetThumbLength

Kaydırıcı uzunluğu geçerli trackbar denetimi ayarlar.

```
void SetThumbLength(int nLength);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*nLength*|[in] Kaydırıcıyı piksel cinsinden uzunluğu.|

### <a name="remarks"></a>Açıklamalar

Trackbar denetimi ayarlanması bu yöntem gerektirir [TBS_FIXEDLENGTH](/windows/desktop/Controls/trackbar-control-styles) stili.

Bu yöntem gönderir [TBM_SETTHUMBLENGTH](/windows/desktop/Controls/tbm-setthumblength) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_sliderCtrl`, yani geçerli trackbar denetimi erişmek için kullanılır. Örnek ayrıca bir değişken tanımlar `thumbLength`, yani trackbar denetimin thumb bileşeni varsayılan uzunluğunu depolamak için kullanılır. Bu değişkenler bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, iki kez varsayılan uzunluğunu trackbar denetimin thumb bileşen ayarlar.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]

##  <a name="settic"></a>  CSliderCtrl::SetTic

Bir kaydırıcı denetimi içinde onay işareti konumunu ayarlar.

```
BOOL SetTic(int nTic);
```

### <a name="parameters"></a>Parametreler

*nTic*<br/>
Değer çizgisinin konumu. Bu parametre, pozitif bir değer belirtmeniz gerekir.

### <a name="return-value"></a>Dönüş Değeri

Değer çizgisi ayarlanmışsa sıfır olmayan; Aksi durumda 0.

##  <a name="setticfreq"></a>  CSliderCtrl::SetTicFreq

İle hangi onay işaretleri bir kaydırıcı görüntülenir sıklığını ayarlar.

```
void SetTicFreq(int nFreq);
```

### <a name="parameters"></a>Parametreler

*nFreq*<br/>
Değer çizgilerinin sıklığı.

### <a name="remarks"></a>Açıklamalar

Örneğin, sıklığı 2 olarak ayarlanırsa, her bir kaydırıcının aralığı artış için onay işareti görüntülenir. 1 sıklığı için varsayılan ayarı (diğer bir deyişle, aralığındaki her artış onay işareti ile ilişkili olan).

Bu işlevi kullanmak için TBS_AUTOTICKS stiliyle denetimi oluşturmanız gerekir. Daha fazla bilgi için [CSliderCtrl::Create](#create).

##  <a name="settipside"></a>  CSliderCtrl::SetTipSide

Konumlar araç ipucu denetimi trackbar denetimi tarafından kullanılır.

```
int SetTipSide(int nLocation);
```

### <a name="parameters"></a>Parametreler

*Nkonum*<br/>
Araç İpucu denetimi görüntülenecek konumu temsil eden değer. Olası değerler listesi için Win32 iletisini görürsünüz [TBM_SETTIPSIDE](/windows/desktop/Controls/tbm-settipside)Windows SDK içinde açıklandığı gibi.

### <a name="return-value"></a>Dönüş Değeri

Araç İpucu denetiminin önceki konumu temsil eden bir değer. Dönüş değeri için olası değerler birini eşittir *Nkonum*.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK'yı açıklandığı TBM_SETTIPSIDE, Win32 ileti davranışı uygular. TBS_TOOLTIPS stili kaydırıcı denetimleri araç ipuçlarının görüntüleyin. Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](/windows/desktop/Controls/trackbar-control-styles) Windows SDK.

##  <a name="settooltips"></a>  CSliderCtrl::SetToolTips

Araç İpucu denetimi için bir kaydırıcı denetimi atar.

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Parametreler

*pWndTip*<br/>
Bir işaretçi bir [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) kaydırıcı denetimi kullanmak için araç ipuçları içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [TBM_SETTOOLTIPS](/windows/desktop/Controls/tbm-settooltips)Windows SDK içinde açıklandığı gibi. Bir kaydırıcı denetimi ile TBS_TOOLTIPS stili oluşturulduğunda, kaydırıcının geçerli konumu görüntüleme kaydırıcıyı yanında görünen varsayılan araç ipucu denetimi oluşturur. Kaydırıcı denetim stilleri açıklaması için bkz: [Trackbar denetimi stilleri](/windows/desktop/Controls/trackbar-control-styles) Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CProgressCtrl sınıfı](../../mfc/reference/cprogressctrl-class.md)
