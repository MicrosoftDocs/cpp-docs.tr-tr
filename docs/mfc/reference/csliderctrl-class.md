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
ms.openlocfilehash: 8fffdfc002b25fdcd72dcbbf53e7e6c321f55296
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502513"
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
|[CSliderCtrl:: CSliderCtrl](#csliderctrl)|Bir `CSliderCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSliderCtrl:: ClearSel](#clearsel)|Kaydırıcı denetimindeki geçerli seçimi temizler.|
|[CSliderCtrl:: Clemakalens](#cleartics)|Kaydırıcı denetiminden geçerli değer çizgilerini kaldırır.|
|[CSliderCtrl:: Create](#create)|Kaydırıcı denetimi oluşturur ve bir `CSliderCtrl` nesneye ekler.|
|[CSliderCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir kaydırıcı denetimi oluşturur ve bunu bir `CSliderCtrl` nesneye ekler.|
|[CSliderCtrl:: Getarkadaş](#getbuddy)|Belirli bir konumdaki kaydırıcı denetim arkadaş penceresine olan tanıtıcıyı alır.|
|[CSliderCtrl:: GetChannelRect](#getchannelrect)|Kaydırıcı denetiminin kanalının boyutunu alır.|
|[CSliderCtrl:: GetLineSize](#getlinesize)|Kaydırıcı denetiminin satır boyutunu alır.|
|[CSliderCtrl:: Getnumtiği](#getnumtics)|Kaydırıcı denetimindeki değer çizgilerinin sayısını alır.|
|[CSliderCtrl:: GetPageSize](#getpagesize)|Kaydırıcı denetiminin sayfa boyutunu alır.|
|[CSliderCtrl:: GetPos](#getpos)|Kaydırıcısının geçerli konumunu alır.|
|[CSliderCtrl:: GetRange](#getrange)|Kaydırıcı için en düşük ve en yüksek konumları alır.|
|[CSliderCtrl:: GetRangeMax](#getrangemax)|Bir Kaydırıcının en büyük konumunu alır.|
|[CSliderCtrl:: GetRangeMin](#getrangemin)|Bir kaydırıcının minimum konumunu alır.|
|[CSliderCtrl:: GetSelection](#getselection)|Geçerli seçimin aralığını alır.|
|[CSliderCtrl:: GetThumbLength](#getthumblength)|Geçerli TrackBar denetimindeki kaydırıcının uzunluğunu alır.|
|[CSliderCtrl:: GetThumbRect](#getthumbrect)|Kaydırıcı denetiminin Thumb boyutunu alır.|
|[CSliderCtrl:: GetTic](#gettic)|Belirtilen değer çizgisi konumunu alır.|
|[CSliderCtrl:: GetTicArray](#getticarray)|Kaydırıcı denetimi için değer çizgisi konumlarının dizisini alır.|
|[CSliderCtrl:: GetTicPos](#getticpos)|İstemci koordinatlarındaki belirtilen değer çizgisi konumunu alır.|
|[CSliderCtrl:: GetToolTip 'ler](#gettooltips)|Varsa kaydırıcı denetimine atanan araç ipucu denetimine yönelik tanıtıcıyı alır.|
|[CSliderCtrl:: Setarkadaş](#setbuddy)|Kaydırıcı denetimi için arkadaş penceresi olarak bir pencere atar.|
|[CSliderCtrl:: SetLineSize](#setlinesize)|Kaydırıcı denetiminin satır boyutunu ayarlar.|
|[CSliderCtrl:: SetPageSize](#setpagesize)|Kaydırıcı denetiminin sayfa boyutunu ayarlar.|
|[CSliderCtrl:: SetPos](#setpos)|Kaydırıcının geçerli konumunu ayarlar.|
|[CSliderCtrl:: SetRange](#setrange)|Kaydırıcı için en düşük ve en yüksek konumları ayarlar.|
|[CSliderCtrl:: SetRangeMax](#setrangemax)|Kaydırıcı için en yüksek konumu ayarlar.|
|[CSliderCtrl:: SetRangeMin](#setrangemin)|Kaydırıcı için en düşük konumu ayarlar.|
|[CSliderCtrl:: SetSelection](#setselection)|Geçerli seçimin aralığını ayarlar.|
|[CSliderCtrl:: SetThumbLength](#setthumblength)|Geçerli TrackBar denetimindeki kaydırıcının uzunluğunu ayarlar.|
|[CSliderCtrl:: SetTic](#settic)|Belirtilen değer çizgisinin konumunu ayarlar.|
|[CSliderCtrl:: SetTicFreq](#setticfreq)|Kaydırıcı denetim artışına göre değer çizgilerinin sıklığını ayarlar.|
|[CSliderCtrl:: SetTipSide](#settipside)|Bir TrackBar denetimi tarafından kullanılan bir araç ipucu denetimini konumlandırır.|
|[CSliderCtrl:: SetToolTip 'ler](#settooltips)|Kaydırıcı denetimine bir araç ipucu denetimi atar.|

## <a name="remarks"></a>Açıklamalar

Bir "kaydırıcı denetimi" (TrackBar olarak da bilinir), kaydırıcı ve isteğe bağlı onay işaretleri içeren bir penceredir. Kullanıcı kaydırıcıyı hareket ettirir, fare veya yön tuşlarını kullanarak denetim, değişikliği belirtmek için bildirim iletileri gönderir.

Kaydırıcı denetimleri, kullanıcının bir aralıktaki bir ayrık değer veya ardışık değerler kümesi seçmesini istediğinizde faydalıdır. Örneğin, kaydırıcıyı verilen bir değer işaretine taşıyarak kullanıcının, klavye yineleme hızını ayarlamaya izin vermek için kaydırıcı denetimini kullanabilirsiniz.

Bu denetim (ve bu nedenle `CSliderCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Kaydırıcı, oluştururken belirttiğiniz artışlarla hareket eder. Örneğin, kaydırıcının beş aralığına sahip olması gerektiğini belirtirseniz kaydırıcı yalnızca altı konum içerebilir: kaydırıcı denetiminin sol tarafındaki bir konum ve aralıktaki her artış için bir konum. Genellikle, bu konumların her biri bir değer çizgisi tarafından tanımlanır.

Oluşturucuyu ve `Create` üye `CSliderCtrl`işlevini kullanarak bir kaydırıcı oluşturursunuz. Kaydırıcı denetimini oluşturduktan sonra, özelliklerinin çoğunu değiştirmek için içindeki `CSliderCtrl` üye işlevlerini kullanabilirsiniz. Yapabileceğiniz değişiklikler kaydırıcı için en düşük ve en yüksek pozisyonları ayarlamayı, değer işaretlerini çizmeyi, seçim aralığını ayarlamayı ve kaydırıcıyı yeniden konumlandırmayı içerir.

Kullanma `CSliderCtrl`hakkında daha fazla bilgi için bkz [](../../mfc/controls-mfc.md) . [CSliderCtrl kullanma](../../mfc/using-csliderctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSliderCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

##  <a name="clearsel"></a>CSliderCtrl:: ClearSel

Kaydırıcı denetimindeki geçerli seçimi temizler.

```
void ClearSel(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*bRedraw*<br/>
Yeniden çizim bayrağı. Bu parametre TRUE ise, seçim temizlenmeden sonra kaydırıcı yeniden çizilir; Aksi takdirde kaydırıcı yeniden çizilmez.

##  <a name="cleartics"></a>CSliderCtrl:: Clemakalens

Kaydırıcı denetiminden geçerli değer çizgilerini kaldırır.

```
void ClearTics(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*bRedraw*<br/>
Yeniden çizim bayrağı. Bu parametre TRUE ise, kademeler temizlendikten sonra kaydırıcı yeniden çizilir; Aksi takdirde kaydırıcı yeniden çizilmez.

##  <a name="create"></a>CSliderCtrl:: Create

Kaydırıcı denetimi oluşturur ve bir `CSliderCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Kaydırıcı denetiminin stilini belirtir. Windows SDK açıklanan [kaydırıcı denetim stillerinin](/windows/win32/Controls/trackbar-control-styles)birleşimini denetime uygulayın.

*Rect*<br/>
Kaydırıcı denetiminin boyutunu ve konumunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısı olabilir.

*pParentWnd*<br/>
Kaydırıcı denetiminin ana penceresini (genellikle a `CDialog`) belirtir. NULL olmaması gerekir.

*NID*<br/>
Kaydırıcı denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda oluşturursunuz `CSliderCtrl` . İlk olarak, oluşturucuyu çağırın ve ardından kaydırıcı denetimini `Create`oluşturan ve `CSliderCtrl` nesneye bağlayan çağırın.

*DwStyle*için ayarlanan değerlere bağlı olarak kaydırıcı denetiminin dikey veya yatay bir yönü olabilir. Her iki tarafta da ya da hiçbiri üzerinde değer çizgisi olabilir. Ardışık değerler aralığını belirtmek için de kullanılabilir.

Kaydırıcı denetimine genişletilmiş pencere stilleri uygulamak için yerine `Create` [CreateEx](#createex) çağırın.

##  <a name="createex"></a>CSliderCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CSliderCtrl` nesneyle ilişkilendirir.

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
Oluşturulmakta olan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Için *dwExStyle* parametresi.

*dwStyle*<br/>
Kaydırıcı denetiminin stilini belirtir. Windows SDK açıklanan [kaydırıcı denetim stillerinin](/windows/win32/Controls/trackbar-control-styles)birleşimini denetime uygulayın.

*Rect*<br/>
*PParentWnd*istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stili önsöz **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için [Create](#create) yerine kullanın.

##  <a name="csliderctrl"></a>CSliderCtrl:: CSliderCtrl

Bir `CSliderCtrl` nesnesi oluşturur.

```
CSliderCtrl();
```

##  <a name="getbuddy"></a>CSliderCtrl:: Getarkadaş

Belirli bir konumdaki kaydırıcı denetim arkadaş penceresine olan tanıtıcıyı alır.

```
CWnd* GetBuddy(BOOL fLocation = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*fLocation*<br/>
Hangi iki arkadaş pencerenin almak için işlediğini belirten bir Boole değeri. Aşağıdaki değerlerden biri olabilir:

- DOĞRU, kaydırıcının sol tarafındaki arkadaş için tanıtıcıyı alır. Kaydırıcı denetimi TBS_VERT stilini kullanıyorsa, ileti kaydırıcının üzerindeki arkadaşları alır.

- FALSE, kaydırıcının sağına doğru olan olan arkadaş tanıtıcısını alır. Kaydırıcı denetimi TBS_VERT stilini kullanıyorsa, ileti kaydırıcının altındaki arkadaşları alır.

### <a name="return-value"></a>Dönüş Değeri

*FLocation*tarafından belirtilen konumdaki arkadaş penceresi olan bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesi işaretçisi veya bu konumda arkadaş penceresi yoksa null.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [TBM_GETBUDDY](/windows/win32/Controls/tbm-getbuddy)davranışını uygular. Kaydırıcı denetim stillerinin açıklaması için, bkz. [TrackBar Control Styles](/windows/win32/Controls/trackbar-control-styles) in Windows SDK.

##  <a name="getchannelrect"></a>CSliderCtrl:: GetChannelRect

Kaydırıcı denetiminin kanalı için sınırlayıcı dikdörtgenin boyutunu ve konumunu alır.

```
void GetChannelRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametreler

*LPRC*<br/>
İşlevin döndürdüğü, kanalın sınırlayıcı dikdörtgeninin boyutunu ve konumunu içeren bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Kanal, kaydırıcının hareket edeceği ve bir Aralık seçildiğinde vurguyu içeren alandır.

##  <a name="getlinesize"></a>CSliderCtrl:: GetLineSize

Kaydırıcı denetimi için çizginin boyutunu alır.

```
int GetLineSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için bir çizginin boyutu.

### <a name="remarks"></a>Açıklamalar

Çizgi boyutu, TB_LINEUP ve TB_LINEDOWN bildirimleri için kaydırıcının ne kadar hareket edeceğini etkiler. Satır boyutu için varsayılan ayar 1 ' dir.

##  <a name="getnumtics"></a>CSliderCtrl:: Getnumtiği

Kaydırıcı denetimindeki değer çizgilerinin sayısını alır.

```
UINT GetNumTics() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimindeki onay işaretlerinin sayısı.

##  <a name="getpagesize"></a>CSliderCtrl:: GetPageSize

Kaydırıcı denetimi için sayfanın boyutunu alır.

```
int GetPageSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için bir sayfanın boyutu.

### <a name="remarks"></a>Açıklamalar

Sayfa boyutu, TB_PAGEUP ve TB_PAGEDOWN bildirimleri için kaydırıcının ne kadar hareket edeceğini etkiler.

##  <a name="getpos"></a>CSliderCtrl:: GetPos

Kaydırıcı denetiminde kaydırıcının geçerli konumunu alır.

```
int GetPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli konum.

##  <a name="getrange"></a>CSliderCtrl:: GetRange

Kaydırıcı denetimindeki kaydırıcı için en yüksek ve en düşük pozisyonları alır.

```
void GetRange(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
En küçük konumu alan bir tamsayıya başvuru.

*Ngünde en çok*<br/>
En yüksek konumu alan bir tamsayıya başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işlev, değerleri *nMin* ve *NMAX*tarafından başvurulan tamsayılara kopyalar.

##  <a name="getrangemax"></a>CSliderCtrl:: GetRangeMax

Kaydırıcı denetimindeki Kaydırıcının en büyük konumunu alır.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin en büyük konumu.

##  <a name="getrangemin"></a>CSliderCtrl:: GetRangeMin

Kaydırıcı denetiminde kaydırıcının minimum konumunu alır.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin en küçük konumu.

##  <a name="getselection"></a>CSliderCtrl:: GetSelection

Kaydırıcı denetimindeki geçerli seçimin başlangıç ve bitiş konumlarını alır.

```
void GetSelection(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
Geçerli seçimin başlangıç konumunu alan bir tamsayıya başvuru.

*Ngünde en çok*<br/>
Geçerli seçimin bitiş konumunu alan bir tamsayıya başvuru.

##  <a name="getthumblength"></a>CSliderCtrl:: GetThumbLength

Geçerli TrackBar denetimindeki kaydırıcının uzunluğunu alır.

```
int GetThumbLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcının piksel cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [TBM_GETTHUMBLENGTH](/windows/win32/Controls/tbm-getthumblength) iletisini gönderir.

##  <a name="getthumbrect"></a>CSliderCtrl:: GetThumbRect

Kaydırıcı denetimindeki kaydırıcı (Thumb) için sınırlayıcı dikdörtgenin boyutunu ve konumunu alır.

```
void GetThumbRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametreler

*LPRC*<br/>
İşlev döndüğünde kaydırıcı için `CRect` sınırlayıcı dikdörtgeni içeren bir nesne işaretçisi.

##  <a name="gettic"></a>CSliderCtrl:: GetTic

Kaydırıcı denetimindeki onay işaretinin konumunu alır.

```
int GetTic(int nTic) const;
```

### <a name="parameters"></a>Parametreler

*Ntik*<br/>
Değer işaretini tanımlayan sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen değer çizgisi veya Eğer *nTic* geçerli bir dizin belirtmezse,-1 ' in konumu.

##  <a name="getticarray"></a>CSliderCtrl:: GetTicArray

Kaydırıcı denetimi için onay işaretlerinin konumlarını içeren dizinin adresini alır.

```
DWORD* GetTicArray() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için değer çizgisi konumlarını içeren dizinin adresi.

##  <a name="getticpos"></a>CSliderCtrl:: GetTicPos

Bir kaydırıcı denetimindeki onay işaretinin geçerli fiziksel konumunu alır.

```
int GetTicPos(int nTic) const;
```

### <a name="parameters"></a>Parametreler

*Ntik*<br/>
Değer işaretini tanımlayan sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen değer çizgisi veya Eğer *nTic* geçerli bir dizin belirtmezse, istemci koordinatlarındaki fiziksel konum.

##  <a name="gettooltips"></a>CSliderCtrl:: GetToolTip 'ler

Varsa kaydırıcı denetimine atanan araç ipucu denetimine yönelik tanıtıcıyı alır.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesi işaretçisi veya araç ipuçları KULLANıMDA değilse null. Kaydırıcı denetimi TBS_TOOLTIPS stilini kullanmıyorsa, dönüş değeri NULL olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [TBM_GETTOOLTIPS](/windows/win32/Controls/tbm-gettooltips)davranışını uygular. Bu üye işlevinin bir denetim tutamacı yerine `CToolTipCtrl` bir nesne döndürdüğünü unutmayın.

Kaydırıcı denetim stillerinin açıklaması için, bkz. [TrackBar Control Styles](/windows/win32/Controls/trackbar-control-styles) in Windows SDK.

##  <a name="setbuddy"></a>CSliderCtrl:: Setarkadaş

Kaydırıcı denetimi için arkadaş penceresi olarak bir pencere atar.

```
CWnd* SetBuddy(
    CWnd* pWndBuddy,
    BOOL fLocation = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pwndarkadaş*<br/>
Kaydırıcı denetiminin arkadaşları olarak `CWnd` ayarlanacak bir nesne işaretçisi.

*fLocation*<br/>
Arkadaş penceresinin görüntüleneceği konumu belirten değer. Bu değer aşağıdakilerden biri olabilir:

- TrackBar denetimi TBS_HORZ stilini kullanıyorsa, arkadaş TrackBar sol tarafında görünür. TrackBar TBS_VERT stilini kullanıyorsa, arkadaş TrackBar denetiminin üzerinde görünür.

- TrackBar, TrackBar denetimi TBS_HORZ stilini kullanıyorsa, arkadaş sağ tarafından görünür. TrackBar TBS_VERT stilini kullanıyorsa, arkadaş TrackBar denetiminin altında görünür.

### <a name="return-value"></a>Dönüş Değeri

Bu konumdaki kaydırıcı denetimine daha önce atanmış olan bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [TBM_SETBUDDY](/windows/win32/Controls/tbm-setbuddy)davranışını uygular. Bu üye işlevin hem dönüş değeri hem de `CWnd` parametresi için pencere tutamaçları yerine nesneler için işaretçiler kullandığını unutmayın.

Kaydırıcı denetim stillerinin açıklaması için, bkz. [TrackBar Control Styles](/windows/win32/Controls/trackbar-control-styles) in Windows SDK.

##  <a name="setlinesize"></a>CSliderCtrl:: SetLineSize

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

Çizgi boyutu, TB_LINEUP ve TB_LINEDOWN bildirimleri için kaydırıcının ne kadar hareket edeceğini etkiler.

##  <a name="setpagesize"></a>CSliderCtrl:: SetPageSize

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

Sayfa boyutu, TB_PAGEUP ve TB_PAGEDOWN bildirimleri için kaydırıcının ne kadar hareket edeceğini etkiler.

##  <a name="setpos"></a>CSliderCtrl:: SetPos

Kaydırıcı denetiminde kaydırıcının geçerli konumunu ayarlar.

```
void SetPos(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Yeni kaydırıcı konumunu belirtir.

##  <a name="setrange"></a>CSliderCtrl:: SetRange

Kaydırıcı denetimindeki kaydırıcı için aralığı (en düşük ve en yüksek konumları) ayarlar.

```
void SetRange(
    int nMin,
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
Kaydırıcı için en küçük konum.

*Ngünde en çok*<br/>
Kaydırıcı için en yüksek konum.

*bRedraw*<br/>
Yeniden çizim bayrağı. Bu parametre TRUE ise, Aralık ayarlandıktan sonra kaydırıcı yeniden çizilir; Aksi takdirde kaydırıcı yeniden çizilmez.

##  <a name="setrangemax"></a>CSliderCtrl:: SetRangeMax

Kaydırıcı denetimindeki kaydırıcı için maksimum aralığı ayarlar.

```
void SetRangeMax(
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*Ngünde en çok*<br/>
Kaydırıcı için en yüksek konum.

*bRedraw*<br/>
Yeniden çizim bayrağı. Bu parametre TRUE ise, Aralık ayarlandıktan sonra kaydırıcı yeniden çizilir; Aksi takdirde kaydırıcı yeniden çizilmez.

##  <a name="setrangemin"></a>CSliderCtrl:: SetRangeMin

Kaydırıcı denetimindeki kaydırıcı için en küçük aralığı ayarlar.

```
void SetRangeMin(
    int nMin,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
Kaydırıcı için en küçük konum.

*bRedraw*<br/>
Yeniden çizim bayrağı. Bu parametre TRUE ise, Aralık ayarlandıktan sonra kaydırıcı yeniden çizilir; Aksi takdirde kaydırıcı yeniden çizilmez.

##  <a name="setselection"></a>CSliderCtrl:: SetSelection

Kaydırıcı denetimindeki geçerli seçimin başlangıç ve bitiş konumlarını ayarlar.

```
void SetSelection(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
Kaydırıcı için başlangıç konumu.

*Ngünde en çok*<br/>
Kaydırıcı için bitiş konumu.

##  <a name="setthumblength"></a>CSliderCtrl:: SetThumbLength

Geçerli TrackBar denetimindeki kaydırıcının uzunluğunu ayarlar.

```
void SetThumbLength(int nLength);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*nLength*|'ndaki Kaydırıcının piksel cinsinden uzunluğu.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, TrackBar denetiminin [TBS_FIXEDLENGTH](/windows/win32/Controls/trackbar-control-styles) stiline ayarlanmasını gerektirir.

Bu yöntem, Windows SDK açıklanan [TBM_SETTHUMBLENGTH](/windows/win32/Controls/tbm-setthumblength) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli TrackBar denetimine erişmek `m_sliderCtrl`için kullanılan değişkenini tanımlar. Örnek ayrıca, TrackBar denetiminin Thumb bileşeninin `thumbLength`varsayılan uzunluğunu depolamak için kullanılan bir değişkenini tanımlar. Bu değişkenler bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, TrackBar denetiminin Thumb bileşenini varsayılan uzunluğunun iki katı olarak ayarlar.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]

##  <a name="settic"></a>CSliderCtrl:: SetTic

Kaydırıcı denetimindeki onay işaretinin konumunu ayarlar.

```
BOOL SetTic(int nTic);
```

### <a name="parameters"></a>Parametreler

*Ntik*<br/>
Değer çizgisinin konumu. Bu parametrenin pozitif bir değer belirtmesi gerekir.

### <a name="return-value"></a>Dönüş Değeri

Değer çizgisi ayarlandıysa sıfır dışı; Aksi takdirde 0.

##  <a name="setticfreq"></a>CSliderCtrl:: SetTicFreq

Kaydırıcı içindeki değer çizgilerinin gösterileceği sıklığı ayarlar.

```
void SetTicFreq(int nFreq);
```

### <a name="parameters"></a>Parametreler

*nFreq*<br/>
Değer çizgilerinin sıklığı.

### <a name="remarks"></a>Açıklamalar

Örneğin sıklık 2 olarak ayarlanırsa, kaydırıcının aralığındaki her bir artış için bir değer çizgisi görüntülenir. Sıklık için varsayılan ayar 1 ' dir (yani aralıktaki her artış bir değer işaretiyle ilişkilendirilir).

Bu işlevi kullanmak için TBS_AUTOTICKS stiliyle denetim oluşturmanız gerekir. Daha fazla bilgi için bkz. [CSliderCtrl:: Create](#create).

##  <a name="settipside"></a>CSliderCtrl:: SetTipSide

Bir TrackBar denetimi tarafından kullanılan bir araç ipucu denetimini konumlandırır.

```
int SetTipSide(int nLocation);
```

### <a name="parameters"></a>Parametreler

*nKonum*<br/>
Tooltip denetiminin görüntüleneceği konumu temsil eden değer. Olası değerler listesi için, Windows SDK açıklanan Win32 iletisi [TBM_SETTIPSIDE](/windows/win32/Controls/tbm-settipside)bakın.

### <a name="return-value"></a>Dönüş Değeri

Araç ipucu denetiminin önceki konumunu temsil eden bir değer. Dönüş değeri *nLocation*için olası değerlerden birine eşit.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin TBM_SETTIPSIDE davranışını uygular. TBS_TOOLTIPS stili görüntüleme araç ipuçlarını kullanan kaydırıcı denetimleri. Kaydırıcı denetim stillerinin açıklaması için, bkz. [TrackBar Control Styles](/windows/win32/Controls/trackbar-control-styles) in Windows SDK.

##  <a name="settooltips"></a>CSliderCtrl:: SetToolTip 'ler

Kaydırıcı denetimine bir araç ipucu denetimi atar.

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Parametreler

*pWndTip*<br/>
Kaydırıcı denetimiyle birlikte kullanılacak araç ipuçlarını içeren [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 iletisinin [TBM_SETTOOLTIPS](/windows/win32/Controls/tbm-settooltips)davranışını uygular. TBS_TOOLTIPS stiliyle bir kaydırıcı denetimi oluşturulduğunda, kaydırıcının geçerli konumunu görüntüleyerek kaydırıcının yanında görünen varsayılan bir araç ipucu denetimi oluşturur. Kaydırıcı denetim stillerinin açıklaması için, bkz. [TrackBar Control Styles](/windows/win32/Controls/trackbar-control-styles) in Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CProgressCtrl Sınıfı](../../mfc/reference/cprogressctrl-class.md)
