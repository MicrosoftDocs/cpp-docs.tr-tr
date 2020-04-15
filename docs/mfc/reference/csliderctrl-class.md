---
title: CSliderCtrl Sınıfı
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
ms.openlocfilehash: 24e1cb18f979d1144f15cf6ffedc6cace5f5361e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318222"
---
# <a name="csliderctrl-class"></a>CSliderCtrl Sınıfı

Windows ortak kaydırıcı denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSliderCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Bir `CSliderCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSliderCtrl::ClearSel](#clearsel)|Kaydırıcı denetiminde geçerli seçimi temizler.|
|[CSliderCtrl::ClearTics](#cleartics)|Kaydırıcı denetiminden geçerli onay işaretini kaldırır.|
|[CSliderCtrl::Oluştur](#create)|Kaydırıcı denetimi oluşturur ve nesneye `CSliderCtrl` bağlar.|
|[CSliderCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir kaydırıcı denetimi oluşturur `CSliderCtrl` ve bir nesneye bağlar.|
|[CSliderCtrl::GetBuddy](#getbuddy)|Tutamacı belirli bir konumdaki kaydırıcı denetim arkadaşı penceresine alır.|
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Kaydırıcı denetiminin kanalının boyutunu alır.|
|[CSliderCtrl::GetLineSize](#getlinesize)|Kaydırıcı denetiminin satır boyutunu alır.|
|[CSliderCtrl::GetNumTics](#getnumtics)|Kaydırıcı denetimindeki onay işareti sayısını alır.|
|[CSliderCtrl::GetPageSize](#getpagesize)|Kaydırıcı denetiminin sayfa boyutunu alır.|
|[CSliderCtrl::GetPos](#getpos)|Kaydırıcının geçerli konumunu alır.|
|[CSliderCtrl::GetRange](#getrange)|Kaydırıcı için minimum ve maksimum konumları alır.|
|[CSliderCtrl::GetRangeMax](#getrangemax)|Kaydırıcı için maksimum konumu alır.|
|[CSliderCtrl::GetRangeMin](#getrangemin)|Kaydırıcı için minimum konumu alır.|
|[CSliderCtrl::Seçim Alın](#getselection)|Geçerli seçim aralığını alır.|
|[CSliderCtrl::GetThumbLength](#getthumblength)|Geçerli izleme çubuğu denetiminde kaydırıcının uzunluğunu alır.|
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Kaydırıcı denetiminin başparmağının boyutunu alır.|
|[CSliderCtrl::GetTic](#gettic)|Belirtilen onay işaretinin konumunu alır.|
|[CSliderCtrl::GetTicArray](#getticarray)|Kaydırıcı denetimi için onay işareti konumları dizisini alır.|
|[CSliderCtrl::GetTicPos](#getticpos)|İstemci koordinatlarında belirtilen onay işaretinin konumunu alır.|
|[CSliderCtrl::GetToolTips](#gettooltips)|Varsa kaydırıcı denetimine atanan takım ucu denetimine tutamacı nı alır.|
|[CSliderCtrl::SetBuddy](#setbuddy)|Kaydırıcı denetimi için bir pencereyi kalıb penceresi olarak atar.|
|[CSliderCtrl::SetLineSize](#setlinesize)|Kaydırıcı denetiminin çizgi boyutunu ayarlar.|
|[CSliderCtrl::SetPageSize](#setpagesize)|Kaydırıcı denetiminin sayfa boyutunu ayarlar.|
|[CSliderCtrl::SetPos](#setpos)|Kaydırıcının geçerli konumunu ayarlar.|
|[CSliderCtrl::SetAralığı](#setrange)|Kaydırıcı için minimum ve maksimum konumları ayarlar.|
|[CSliderCtrl::SetRangeMax](#setrangemax)|Kaydırıcı için maksimum konumu ayarlar.|
|[CSliderCtrl::SetRangeMin](#setrangemin)|Kaydırıcı için minimum konumu ayarlar.|
|[CSliderCtrl::SetSelection](#setselection)|Geçerli seçim aralığını ayarlar.|
|[CSliderCtrl::SetThumbLength](#setthumblength)|Geçerli izleme çubuğu denetiminde kaydırıcının uzunluğunu ayarlar.|
|[CSliderCtrl::SetTic](#settic)|Belirtilen onay işaretinin konumunu ayarlar.|
|[CSliderCtrl::SetTicFreq](#setticfreq)|Kaydırıcı denetimi artış başına kene işaretlerinin sıklığını ayarlar.|
|[CSliderCtrl::SetTipSide](#settipside)|Trackbar denetimi tarafından kullanılan bir araç ucu denetimini konumlandırın.|
|[CSliderCtrl::SetToolTips](#settooltips)|Kaydırıcı denetimine bir araç ucu denetimi atar.|

## <a name="remarks"></a>Açıklamalar

"Kaydırıcı denetimi" (izleme çubuğu olarak da bilinir), kaydırıcı ve isteğe bağlı onay işaretleri içeren bir penceredir. Kullanıcı, fareyi veya yön tuşlarını kullanarak kaydırıcıyı hareket ettirdiğinde, denetim değişikliği belirtmek için bildirim iletileri gönderir.

Kaydırıcı denetimleri, kullanıcının bir aralıkta ayrı bir değer veya ardışık değerler kümesi ni seçmesini istediğinizde yararlıdır. Örneğin, kaydırıcıyı belirli bir onay işaretine taşıyarak kullanıcının klavyenin yineleme hızını ayarlamasına izin vermek için kaydırıcı denetimi kullanabilirsiniz.

Bu denetim (ve `CSliderCtrl` bu nedenle sınıf) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Kaydırıcı, ne zaman oluşturduğunuzu belirttiğiniz artışlarla hareket eder. Örneğin, kaydırıcının beş aralıklı olması gerektiğini belirtirseniz, kaydırıcı yalnızca altı konumu kaplayabilir: kaydırıcı denetiminin sol tarafında bir pozisyon ve aralıktaki her artış için bir konum. Genellikle, bu pozisyonların her biri bir onay işareti ile tanımlanır.

Oluşturucuyu ve `Create` üye işlevini kullanarak bir kaydırıcı `CSliderCtrl`oluşturursunuz. Kaydırıcı denetimi oluşturduktan sonra, birçok özelliğini `CSliderCtrl` değiştirmek için üye işlevleri kullanabilirsiniz. Yapabileceğiniz değişiklikler kaydırıcı için minimum ve maksimum konumları ayarlamayı, onay işaretleri çizmeyi, seçim aralığını ayarlamayı ve kaydırıcıyı yeniden konumlandırmayı içerir.

Kullanma `CSliderCtrl`hakkında daha fazla bilgi [Using CSliderCtrl](../../mfc/using-csliderctrl.md)için, [bkz.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CSliderCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="csliderctrlclearsel"></a><a name="clearsel"></a>CSliderCtrl::ClearSel

Kaydırıcı denetiminde geçerli seçimi temizler.

```
void ClearSel(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*bRedraw*<br/>
Bayrağı yeniden çizin. Bu parametre TRUE ise, seçim temizlendikten sonra kaydırıcı yeniden çizilir; aksi takdirde kaydırıcı yeniden çizilmez.

## <a name="csliderctrlcleartics"></a><a name="cleartics"></a>CSliderCtrl::ClearTics

Kaydırıcı denetiminden geçerli onay işaretini kaldırır.

```
void ClearTics(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*bRedraw*<br/>
Bayrağı yeniden çizin. Bu parametre TRUE ise, onay işaretleri temizlendikten sonra kaydırıcı yeniden çizilir; aksi takdirde kaydırıcı yeniden çizilmez.

## <a name="csliderctrlcreate"></a><a name="create"></a>CSliderCtrl::Oluştur

Kaydırıcı denetimi oluşturur ve nesneye `CSliderCtrl` bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Kaydırıcı denetiminin stilini belirtir. Windows SDK'da açıklanan [kaydırıcı denetim stillerinin](/windows/win32/Controls/trackbar-control-styles)herhangi bir birleşimini denetime uygulayın.

*Rect*<br/>
Kaydırıcı denetiminin boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı olabilir.

*pParentWnd*<br/>
Kaydırıcı denetiminin üst penceresini belirtir, `CDialog`genellikle bir . NULL olmamalıdır.

*Nıd*<br/>
Kaydırıcı denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CSliderCtrl` yapı inşa e. Önce oluşturucuyu çağırın, `Create`sonra kaydırıcı denetimini oluşturan ve `CSliderCtrl` nesneye iliştiren , çağırın.

*dwStyle*için ayarlanan değerlere bağlı olarak, kaydırıcı denetimi dikey veya yatay yönlendirmeye sahip olabilir. Her iki tarafta, her iki tarafta da onay işaretleri olabilir veya ikisi birden olamaz. Ardışık değerler aralığını belirtmek için de kullanılabilir.

Genişletilmiş pencere stillerini kaydırıcı denetimine uygulamak için `Create`CreateEx yerine ['yi](#createex) arayın.

## <a name="csliderctrlcreateex"></a><a name="createex"></a>CSliderCtrl::CreateEx

Denetim (alt pencere) oluşturur ve `CSliderCtrl` nesneyle ilişkilendirir.

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
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerilistesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

*Dwstyle*<br/>
Kaydırıcı denetiminin stilini belirtir. Windows SDK'da açıklanan [kaydırıcı denetim stillerinin](/windows/win32/Controls/trackbar-control-styles)herhangi bir birleşimini denetime uygulayın.

*Rect*<br/>
*PParentWnd*istemci koordinatlarında oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Nıd*<br/>
Denetimin alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stil önsöz **WS_EX_** tarafından belirtilen genişletilmiş Windows stilleri uygulamak için [Oluştur](#create) yerine kullanın.

## <a name="csliderctrlcsliderctrl"></a><a name="csliderctrl"></a>CSliderCtrl::CSliderCtrl

Bir `CSliderCtrl` nesne inşa eder.

```
CSliderCtrl();
```

## <a name="csliderctrlgetbuddy"></a><a name="getbuddy"></a>CSliderCtrl::GetBuddy

Tutamacı belirli bir konumdaki kaydırıcı denetim arkadaşı penceresine alır.

```
CWnd* GetBuddy(BOOL fLocation = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*fLokasyon*<br/>
İki arkadaş penceresinden hangisinin alınacağı işlendiğini gösteren boolean değeri. Aşağıdaki değerlerden biri olabilir:

- TRUE Kaydırıcının solundaki tutamacı alır. Kaydırıcı denetimi TBS_VERT stilini kullanıyorsa, ileti kaydırıcının üstündeki dostumu alır.

- FALSE Tutamacı kaydırıcının sağındaki dostuma alır. Kaydırıcı denetimi TBS_VERT stilini kullanıyorsa, ileti kaydırıcının altındaki dostumu alır.

### <a name="return-value"></a>Dönüş Değeri

*FLocation*tarafından belirtilen konumdaki arkadaş penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi veya o konumda arkadaş penceresi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TBM_GETBUDDY](/windows/win32/Controls/tbm-getbuddy)davranışını uygular. Kaydırıcı denetim stillerinin açıklaması için Windows SDK'daki [Trackbar Denetim Stilleri'ne](/windows/win32/Controls/trackbar-control-styles) bakın.

## <a name="csliderctrlgetchannelrect"></a><a name="getchannelrect"></a>CSliderCtrl::GetChannelRect

Kaydırıcı denetiminin kanalı için sınırlayan dikdörtgenin boyutunu ve konumunu alır.

```
void GetChannelRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametreler

*lprc*<br/>
İşlev döndüğünde kanalın sınırlayıcı dikdörtgeninin boyutunu ve konumunu içeren bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Kanal, kaydırıcının üzerinde hareket ettiği ve bir aralık seçildiğinde vurguyu içeren alandır.

## <a name="csliderctrlgetlinesize"></a><a name="getlinesize"></a>CSliderCtrl::GetLineSize

Kaydırıcı denetimi için satırBoyutunu alır.

```
int GetLineSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için bir çizginin boyutu.

### <a name="remarks"></a>Açıklamalar

Satır boyutu, kaydırıcının TB_LINEUP ve TB_LINEDOWN bildirimler için ne kadar hareket ettiğini etkiler. Satır boyutu için varsayılan ayar 1'dir.

## <a name="csliderctrlgetnumtics"></a><a name="getnumtics"></a>CSliderCtrl::GetNumTics

Kaydırıcı denetimindeki onay işareti sayısını alır.

```
UINT GetNumTics() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimindeki onay işareti sayısı.

## <a name="csliderctrlgetpagesize"></a><a name="getpagesize"></a>CSliderCtrl::GetPageSize

Kaydırıcı denetimi için sayfanın boyutunu alır.

```
int GetPageSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için bir sayfanın boyutu.

### <a name="remarks"></a>Açıklamalar

Sayfa boyutu, kaydırıcının TB_PAGEUP ve TB_PAGEDOWN bildirimler için ne kadar hareket ettiğini etkiler.

## <a name="csliderctrlgetpos"></a><a name="getpos"></a>CSliderCtrl::GetPos

Kaydırıcının geçerli konumunu kaydırıcı denetiminde alır.

```
int GetPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli konum.

## <a name="csliderctrlgetrange"></a><a name="getrange"></a>CSliderCtrl::GetRange

Kaydırıcı kontrolünde kaydırıcı için maksimum ve minimum konumları alır.

```
void GetRange(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Minimum konumu alan bir karşıcıya başvuru.

*nMax*<br/>
Maksimum konumu alan bir karşıcıya başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işlev, değerleri *nMin* ve *nMax*tarafından başvurulan tamsayılara kopyalar.

## <a name="csliderctrlgetrangemax"></a><a name="getrangemax"></a>CSliderCtrl::GetRangeMax

Kaydırıcı denetimindeki kaydırıcı için maksimum konumu alır.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kontrol maksimum pozisyondur.

## <a name="csliderctrlgetrangemin"></a><a name="getrangemin"></a>CSliderCtrl::GetRangeMin

Kaydırıcı denetimindeki kaydırıcı için minimum konumu alır.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kontrol minimum pozisyondur.

## <a name="csliderctrlgetselection"></a><a name="getselection"></a>CSliderCtrl::Seçim Alın

Kaydırıcı denetiminde geçerli seçimin başlangıç ve bitiş konumlarını alır.

```
void GetSelection(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Geçerli seçimin başlangıç konumunu alan bir karşıcıya başvuru.

*nMax*<br/>
Geçerli seçimin bitiş konumunu alan bir karşıcıya başvuru.

## <a name="csliderctrlgetthumblength"></a><a name="getthumblength"></a>CSliderCtrl::GetThumbLength

Geçerli izleme çubuğu denetiminde kaydırıcının uzunluğunu alır.

```
int GetThumbLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcının uzunluğu, piksel olarak.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [TBM_GETTHUMBLENGTH](/windows/win32/Controls/tbm-getthumblength) iletisini gönderir.

## <a name="csliderctrlgetthumbrect"></a><a name="getthumbrect"></a>CSliderCtrl::GetThumbRect

Kaydırıcı denetiminde kaydırıcı (başparmak) için sınırlayıcı dikdörtgenin boyutunu ve konumunu alır.

```
void GetThumbRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametreler

*lprc*<br/>
İşlev döndüğünde `CRect` kaydırıcıiçin sınırlayıcı dikdörtgeni içeren bir nesneye işaretçi.

## <a name="csliderctrlgettic"></a><a name="gettic"></a>CSliderCtrl::GetTic

Kaydırıcı denetiminde onay işaretinin konumunu alır.

```
int GetTic(int nTic) const;
```

### <a name="parameters"></a>Parametreler

*nTic*<br/>
Bir onay işareti tanımlayan sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen onay işaretinin konumu veya - *nTic* geçerli bir dizin belirtmiyorsa - 1.

## <a name="csliderctrlgetticarray"></a><a name="getticarray"></a>CSliderCtrl::GetTicArray

Kaydırıcı denetimi için onay işaretlerinin konumlarını içeren dizinin adresini alır.

```
DWORD* GetTicArray() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için onay işareti konumlarını içeren dizinin adresi.

## <a name="csliderctrlgetticpos"></a><a name="getticpos"></a>CSliderCtrl::GetTicPos

Kaydırıcı denetiminde bir onay işaretinin geçerli fiziksel konumunu alır.

```
int GetTicPos(int nTic) const;
```

### <a name="parameters"></a>Parametreler

*nTic*<br/>
Bir onay işareti tanımlayan sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen onay işaretinin istemci koordinatlarında veya - *nTic* geçerli bir dizin belirtmiyorsa - 1'in fiziksel konumu.

## <a name="csliderctrlgettooltips"></a><a name="gettooltips"></a>CSliderCtrl::GetToolTips

Varsa kaydırıcı denetimine atanan takım ucu denetimine tutamacı nı alır.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesine işaretçi veya araç uçları kullanılıyorsa NULL. Kaydırıcı denetimi TBS_TOOLTIPS stilini kullanmıyorsa, iade değeri NULL'dur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/tbm-gettooltips)iletisinin TBM_GETTOOLTIPS davranışını uygular. Bu üye işlevin `CToolTipCtrl` tutamaç yerine bir nesneyi denetime döndürttürün.

Kaydırıcı denetim stillerinin açıklaması için Windows SDK'daki [Trackbar Denetim Stilleri'ne](/windows/win32/Controls/trackbar-control-styles) bakın.

## <a name="csliderctrlsetbuddy"></a><a name="setbuddy"></a>CSliderCtrl::SetBuddy

Kaydırıcı denetimi için bir pencereyi kalıb penceresi olarak atar.

```
CWnd* SetBuddy(
    CWnd* pWndBuddy,
    BOOL fLocation = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWndBuddy*<br/>
Kaydırıcı denetiminin arkadaşı olarak ayarlanacak bir `CWnd` nesneye işaretçi.

*fLokasyon*<br/>
Arkadaş penceresini görüntülemek için hangi konumu belirten değer. Bu değer aşağıdakilerden biri olabilir:

- DOĞRU Trackbar denetimi TBS_HORZ stilini kullanıyorsa, çubuk palet çubuğunun solunda görünür. Trackbar TBS_VERT stilini kullanıyorsa, çubuk izleme çubuğu denetiminin üzerinde görünür.

- YANLIŞ Trackbar denetimi TBS_HORZ stilini kullanıyorsa, çubuk palet çubuğunun sağında görünür. İzleme çubuğu TBS_VERT stilini kullanıyorsa, çubuk izleme çubuğu denetiminin altında görünür.

### <a name="return-value"></a>Dönüş Değeri

Daha önce o konumda kaydırıcı denetimine atanan bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TBM_SETBUDDY](/windows/win32/Controls/tbm-setbuddy)davranışını uygular. Bu üye işlevin hem `CWnd` iade değeri hem de parametresi için pencere tutamaçları yerine nesneleriçin işaretçiler kullandığını unutmayın.

Kaydırıcı denetim stillerinin açıklaması için Windows SDK'daki [Trackbar Denetim Stilleri'ne](/windows/win32/Controls/trackbar-control-styles) bakın.

## <a name="csliderctrlsetlinesize"></a><a name="setlinesize"></a>CSliderCtrl::SetLineSize

Kaydırıcı denetimi için çizginin boyutunu ayarlar.

```
int SetLineSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
Kaydırıcı denetiminin yeni satır boyutu.

### <a name="return-value"></a>Dönüş Değeri

Önceki satır boyutu.

### <a name="remarks"></a>Açıklamalar

Satır boyutu, kaydırıcının TB_LINEUP ve TB_LINEDOWN bildirimler için ne kadar hareket ettiğini etkiler.

## <a name="csliderctrlsetpagesize"></a><a name="setpagesize"></a>CSliderCtrl::SetPageSize

Kaydırıcı denetimi için sayfanın boyutunu ayarlar.

```
int SetPageSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
Kaydırıcı denetiminin yeni sayfa boyutu.

### <a name="return-value"></a>Dönüş Değeri

Önceki sayfa boyutu.

### <a name="remarks"></a>Açıklamalar

Sayfa boyutu, kaydırıcının TB_PAGEUP ve TB_PAGEDOWN bildirimler için ne kadar hareket ettiğini etkiler.

## <a name="csliderctrlsetpos"></a><a name="setpos"></a>CSliderCtrl::SetPos

Kaydırıcının geçerli konumunu kaydırıcı denetiminde ayarlar.

```
void SetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Yeni kaydırıcı konumunu belirtir.

## <a name="csliderctrlsetrange"></a><a name="setrange"></a>CSliderCtrl::SetAralığı

Kaydırıcı kontrolünde kaydırıcı için aralığı (minimum ve maksimum konumlar) ayarlar.

```
void SetRange(
    int nMin,
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Kaydırıcı için minimum konum.

*nMax*<br/>
Kaydırıcı için maksimum konum.

*bRedraw*<br/>
Yeniden çekme bayrağı. Bu parametre TRUE ise, aralık ayarlandıktan sonra kaydırıcı yeniden çizilir; aksi takdirde kaydırıcı yeniden çizilmez.

## <a name="csliderctrlsetrangemax"></a><a name="setrangemax"></a>CSliderCtrl::SetRangeMax

Kaydırıcı denetiminde kaydırıcı için maksimum aralığı ayarlar.

```
void SetRangeMax(
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*nMax*<br/>
Kaydırıcı için maksimum konum.

*bRedraw*<br/>
Yeniden çekme bayrağı. Bu parametre TRUE ise, aralık ayarlandıktan sonra kaydırıcı yeniden çizilir; aksi takdirde kaydırıcı yeniden çizilmez.

## <a name="csliderctrlsetrangemin"></a><a name="setrangemin"></a>CSliderCtrl::SetRangeMin

Kaydırıcı denetiminde kaydırıcı için minimum aralığı ayarlar.

```
void SetRangeMin(
    int nMin,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Kaydırıcı için minimum konum.

*bRedraw*<br/>
Yeniden çekme bayrağı. Bu parametre TRUE ise, aralık ayarlandıktan sonra kaydırıcı yeniden çizilir; aksi takdirde kaydırıcı yeniden çizilmez.

## <a name="csliderctrlsetselection"></a><a name="setselection"></a>CSliderCtrl::SetSelection

Kaydırıcı denetiminde geçerli seçim için başlangıç ve bitiş konumlarını ayarlar.

```
void SetSelection(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
Kaydırıcı için başlangıç pozisyonu.

*nMax*<br/>
Kaydırıcı için bitiş pozisyonu.

## <a name="csliderctrlsetthumblength"></a><a name="setthumblength"></a>CSliderCtrl::SetThumbLength

Geçerli izleme çubuğu denetiminde kaydırıcının uzunluğunu ayarlar.

```
void SetThumbLength(int nLength);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*nUzunluk*|[içinde] Kaydırıcının uzunluğu, piksel olarak.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, izleme çubuğu denetiminin [TBS_FIXEDLENGTH](/windows/win32/Controls/trackbar-control-styles) stiline ayarlanmasını gerektirir.

Bu yöntem, Windows SDK'da açıklanan [TBM_SETTHUMBLENGTH](/windows/win32/Controls/tbm-setthumblength) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_sliderCtrl`geçerli izleme çubuğu denetimine erişmek için kullanılan değişkeni tanımlar. Örnek, izleme çubuğu denetiminin başparmak bileşeninin varsayılan uzunluğunu depolamak için kullanılan bir değişkeni `thumbLength`de tanımlar. Bu değişkenler sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, trackbar denetiminin başparmak bileşenini varsayılan uzunluğunun iki katına ayarlar.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]

## <a name="csliderctrlsettic"></a><a name="settic"></a>CSliderCtrl::SetTic

Kaydırıcı denetiminde onay işaretinin konumunu ayarlar.

```
BOOL SetTic(int nTic);
```

### <a name="parameters"></a>Parametreler

*nTic*<br/>
Onay işaretinin konumu. Bu parametre pozitif bir değer belirtmelidir.

### <a name="return-value"></a>Dönüş Değeri

Onay işareti ayarlanmışsa sıfıra inme; aksi takdirde 0.

## <a name="csliderctrlsetticfreq"></a><a name="setticfreq"></a>CSliderCtrl::SetTicFreq

Onay işaretlerinin kaydırıcıda görüntülenme sıklığını ayarlar.

```
void SetTicFreq(int nFreq);
```

### <a name="parameters"></a>Parametreler

*nFreq*<br/>
Kene işaretlerinin sıklığı.

### <a name="remarks"></a>Açıklamalar

Örneğin, sıklık 2 olarak ayarlanmışsa, kaydırıcının aralığındaki diğer her artış için bir onay işareti görüntülenir. Frekans için varsayılan ayar 1'dir (diğer bir deyişle, aralıktaki her artış bir onay işaretiyle ilişkilidir).

Bu işlevi kullanmak için TBS_AUTOTICKS stili ile denetim oluşturmanız gerekir. Daha fazla bilgi için [Bkz. CSliderCtrl::Oluştur](#create).

## <a name="csliderctrlsettipside"></a><a name="settipside"></a>CSliderCtrl::SetTipSide

Trackbar denetimi tarafından kullanılan bir araç ucu denetimini konumlandırın.

```
int SetTipSide(int nLocation);
```

### <a name="parameters"></a>Parametreler

*nKonum*<br/>
Araç ipucu denetiminin görüntülendiği konumu temsil eden değer. Olası değerlerin listesi için, Windows SDK'da açıklandığı gibi [TBM_SETTIPSIDE](/windows/win32/Controls/tbm-settipside)Win32 iletisi bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Araç ipucu denetiminin önceki konumunu temsil eden bir değer. İade değeri *nLocation*için olası değerlerden birine eşittir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin TBM_SETTIPSIDE davranışını uygular. TBS_TOOLTIPS stili görüntü araç ipuçlarını kullanan kaydırıcı denetimleri. Kaydırıcı denetim stillerinin açıklaması için Windows SDK'daki [Trackbar Denetim Stilleri'ne](/windows/win32/Controls/trackbar-control-styles) bakın.

## <a name="csliderctrlsettooltips"></a><a name="settooltips"></a>CSliderCtrl::SetToolTips

Kaydırıcı denetimine bir araç ucu denetimi atar.

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Parametreler

*pWndTip*<br/>
Kaydırıcı denetimiile kullanılacak araç ipuçlarını içeren [ctoolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/tbm-settooltips)iletisinin TBM_SETTOOLTIPS davranışını uygular. TBS_TOOLTIPS stiliyle kaydırıcı denetimi oluşturulduğunda, kaydırıcının geçerli konumunu görüntüleyerek kaydırıcının yanında görünen varsayılan bir araç ucu denetimi oluşturur. Kaydırıcı denetim stillerinin açıklaması için Windows SDK'daki [Trackbar Denetim Stilleri'ne](/windows/win32/Controls/trackbar-control-styles) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Numune CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CProgressCtrl Sınıfı](../../mfc/reference/cprogressctrl-class.md)
