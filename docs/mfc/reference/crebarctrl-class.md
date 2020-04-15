---
title: CReBarCtrl Sınıfı
ms.date: 11/19/2018
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
ms.openlocfilehash: 776892d71e2cb0f5d57512754cd7fa12730eb044
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367440"
---
# <a name="crebarctrl-class"></a>CReBarCtrl Sınıfı

Bir alt pencere için bir kapsayıcı olan bir çubuk denetiminin işlevselliğini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Bir `CReBarCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CReBarCtrl::BeginDrag](#begindrag)|Rebar denetimini sürükle ve bırak moduna yerleştirir.|
|[CReBarCtrl::Oluştur](#create)|Demir çubuğu denetimini oluşturur ve `CReBarCtrl` nesneye bağlar.|
|[CReBarCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir çubuk denetimi oluşturur ve `CReBarCtrl` bir nesneye bağlar.|
|[CReBarCtrl::DeleteBand](#deleteband)|Bir bandı demir çubuğu denetiminden siler.|
|[CReBarCtrl::DragTaşı](#dragmove)|Bir çağrıdan sonra çubuk denetimindeki sürükleme `BeginDrag`konumunu güncelleştirir.|
|[CReBarCtrl::EndDrag](#enddrag)|Çubuk denetiminin sürükle ve bırak işlemini sona erdirir.|
|[CReBarCtrl::GetBandBorders](#getbandborders)|Bir grubun kenarlıklarını alır.|
|[CReBarCtrl::GetBandCount](#getbandcount)|Çubuk denetiminde bulunan bantların sayısını alır.|
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Demir çubuğu denetiminde belirtilen bant la ilgili bilgileri alır.|
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Bir grubun kenar boşluklarını alır.|
|[CReBarCtrl::GetBarHeight](#getbarheight)|Demir çubuğu denetiminin yüksekliğini alır.|
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Demir çubuğu denetimi ve kullandığı resim listesi hakkında bilgi alır.|
|[CReBarCtrl::GetBkColor](#getbkcolor)|Bir çubuk denetiminin varsayılan arka plan rengini alır.|
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Demir çubuğu denetimiyle ilişkili [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) yapısını alır.|
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Bir çubuk denetiminin arabirim işaretçisini `IDropTarget` alır.|
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Geçerli demir çubuğu denetiminin genişletilmiş stilini alır.|
|[CReBarCtrl::GetImageList](#getimagelist)|Bir demir çubuğu denetimiile ilişkili görüntü listesini alır.|
|[CReBarCtrl::GetPalette](#getpalette)|Çubuk denetiminin geçerli paletini alır.|
|[CReBarCtrl::GetRect](#getrect)|Çubuk kontrolünde belirli bir bant için sınırlayıcı dikdörtgeni alır.|
|[CReBarCtrl::GetRowCount](#getrowcount)|Bir çubuk denetimindeki bant satırlarının sayısını alır.|
|[CReBarCtrl::GetRowHeight](#getrowheight)|Bir çubuk denetiminde belirtilen satırın yüksekliğini alır.|
|[CReBarCtrl::GetTextColor](#gettextcolor)|Bir çubuk denetiminin varsayılan metin rengini alır.|
|[CReBarCtrl::GetToolİpuçları](#gettooltips)|Tutamacı, demir çubuğu denetimiyle ilişkili herhangi bir araç ucu denetimine alır.|
|[CReBarCtrl::HitTest](#hittest)|Bu noktada bir çubuk bandı varsa, bir çubuk bandının ekranda belirli bir noktada hangi bölümünün olduğunu belirler.|
|[CReBarCtrl::IDToIndex](#idtoindex)|Bir bant tanımlayıcısını (ID) çubuk denetiminde bir bant dizinine dönüştürür.|
|[CReBarCtrl::InsertBand](#insertband)|Demir çubuğu denetimine yeni bir bant ekler.|
|[CReBarCtrl::Maksimum Bant](#maximizeband)|Bir çubuğu kontrolündeki bir bandı en büyük boyutuna göre yeniden boyutlandırın.|
|[CReBarCtrl::MinimizeBand](#minimizeband)|Bir çubuk kontrolündeki bir bandı en küçük boyutuna göre yeniden boyutlandırın.|
|[CReBarCtrl::MoveBand](#moveband)|Bir grubu bir dizinden diğerine taşır.|
|[CReBarCtrl::PushChevron](#pushchevron)|Programlı bir chevron iter.|
|[CReBarCtrl::Geri Yükleme Bandı](#restoreband)|Bir çubuğu kontrol etme de bir bandı ideal boyutuna göre yeniden boyutlandırıyor.|
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Bir çubuk kontrolünde varolan bir bandın özelliklerini ayarlar.|
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Geçerli demir çubuğu denetiminde belirtilen kenetlenmiş bandın genişliğini ayarlar.|
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Demir çubuğu denetiminin özelliklerini ayarlar.|
|[CReBarCtrl::SetBkColor](#setbkcolor)|Bir çubuk denetiminin varsayılan arka plan rengini ayarlar.|
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Demir çubuğu denetimindeki düğmelerin renk düzenini ayarlar.|
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Geçerli çubuk denetimi için genişletilmiş stilleri ayarlar.|
|[CReBarCtrl::SetImageList](#setimagelist)|Bir çubuk denetiminin resim listesini ayarlar.|
|[CReBarCtrl::SetSahibi](#setowner)|Bir çubuk denetiminin sahibi pencereyi ayarlar.|
|[CReBarCtrl::SetPalette](#setpalette)|Demir çubuğu denetiminin geçerli paletini ayarlar.|
|[CReBarCtrl::SetTextColor](#settextcolor)|Bir çubuk denetiminin varsayılan metin rengini ayarlar.|
|[CReBarCtrl::SetToolTips](#settooltips)|Bir alet ucu denetimini demir çubuğu denetimiyle ilişkilendirir.|
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Demir çubuğu denetiminin görsel stilini ayarlar.|
|[CReBarCtrl::ShowBand](#showband)|Belirli bir grubu demir çubuğu denetiminde gösterir veya gizler.|
|[CReBarCtrl::SizeToRect](#sizetorect)|Çubuk denetimini belirli bir dikdörtgenin yerine sığdırıyor.|

## <a name="remarks"></a>Açıklamalar

Rebar denetiminin bulunduğu uygulama, demir çubuğu denetiminin içerdiği alt pencereyi çubuk bandına atar. Alt pencere genellikle başka bir ortak denetimdir.

Demir denetimleri bir veya daha fazla bant içerir. Her bant bir kavrayan çubuğu, bitmap, metin etiketi ve bir alt pencere nin bir leşimini içerebilir. Bant, bu öğelerin yalnızca birini içerebilir.

Çubuk denetimi, alt pencereyi belirli bir arka plan bit eşlemi üzerinde görüntüleyebilir. RBBS_FIXEDSIZE stilini kullananlar hariç tüm çubuk denetim bantları yeniden boyutlandırılabilir. Bir rebar kontrol bandını yeniden konumlandırDığınızda veya yeniden boyutlandırırken, demir çubuğu denetimi o banda atanan alt pencerenin boyutunu ve konumunu yönetir. Denetimdeki bantların sırasını yeniden boyutlandırmak veya değiştirmek için, bir grubun kavrayıcı çubuğunu tıklatın ve sürükleyin.

Aşağıdaki resimde üç bantiçeren bir çubuk denetimi gösterilmektedir:

- Bant 0 düz, saydam bir araç çubuğu denetimi içerir.

- Bant 1 hem saydam standart hem de saydam açılır bırakma düğmeleri içerir.

- Bant 2 bir açılan kutu ve dört standart düğme içerir.

   ![Rebar menüsü örneği](../../mfc/reference/media/vc4scc1.gif "Rebar menüsü örneği")

## <a name="rebar-control"></a>Demir kontrolü

Rebar denetim desteği:

- Resim listeleri.

- İleti işleme.

- Özel çizim işlevselliği.

- Standart pencere stillerine ek olarak çeşitli denetim stilleri. Bu stillerin listesi için Windows SDK'daki [Rebar Denetim Stilleri'ne](/windows/win32/Controls/rebar-control-styles) bakın.

Daha fazla bilgi için [CReBarCtrl'ı kullanma'ya](../../mfc/using-crebarctrl.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="crebarctrlbegindrag"></a><a name="begindrag"></a>CReBarCtrl::BeginDrag

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_BEGINDRAG](/windows/win32/Controls/rb-begindrag)davranışını uygular.

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Sürükle ve bırak işleminin etkileyeceği bandın sıfır tabanlı dizin.

*dwPos*<br/>
Başlangıç faresi koordinatlarını içeren bir DWORD değeri. Yatay koordinat LOWORD'da, dikey koordinat ise HIWORD'da bulunur. (DWORD)-1'i geçerseniz, rebar denetimi farenin konumunu en son denetim iş `GetMessage` `PeekMessage`parçacığı veya .

## <a name="crebarctrlcreate"></a><a name="create"></a>CReBarCtrl::Oluştur

Demir çubuğu denetimini oluşturur ve `CReBarCtrl` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Denetime uygulanan çubuk denetim stillerinin birleşimini belirtir. Desteklenen stillerin listesi için Windows SDK'daki [Rebar Denetim Stilleri'ne](/windows/win32/Controls/rebar-control-styles) bakın.

*Rect*<br/>
Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına yapılan başvuru, demir çubuğu denetiminin konumu ve boyutudur.

*pParentWnd*<br/>
Çubuk denetiminin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi. NULL olmamalıdır.

*Nıd*<br/>
Demir çubuğu denetiminin denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir çubuk denetimi oluşturun:

1. Bir `CReBarCtrl` nesne oluşturmak için [CReBarCtrl'ı](#crebarctrl) arayın.

1. Windows rebar denetimini oluşturan ve `CReBarCtrl` nesneye iliştiren bu üye işlevi çağırın.

Aradığınızda, `Create`ortak denetimler baş harfe çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

## <a name="crebarctrlcreateex"></a><a name="createex"></a>CReBarCtrl::CreateEx

Denetim (alt pencere) oluşturur ve `CReBarCtrl` nesneyle ilişkilendirir.

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
Denetime uygulanan çubuk denetim stillerinin birleşimini belirtir. Desteklenen stillerin listesi için Windows SDK'daki [Rebar Denetim Stilleri'ne](/windows/win32/Controls/rebar-control-styles) bakın.

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

## <a name="crebarctrlcrebarctrl"></a><a name="crebarctrl"></a>CReBarCtrl::CReBarCtrl

Bir `CReBarCtrl` nesnesi oluşturur.

```
CReBarCtrl();
```

### <a name="example"></a>Örnek

  [CReBarCtrl](#create)örneğine bakın:Oluştur .

## <a name="crebarctrldeleteband"></a><a name="deleteband"></a>CReBarCtrl::DeleteBand

Windows SDK'da açıklandığı gibi Win32 iletisinin [davranışını RB_DELETEBAND](/windows/win32/Controls/rb-deleteband)uygular.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Grubun sıfır tabanlı dizini silinecek.

### <a name="return-value"></a>Dönüş Değeri

Bant başarıyla silinirse sıfırolmayan; aksi takdirde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

## <a name="crebarctrldragmove"></a><a name="dragmove"></a>CReBarCtrl::DragTaşı

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_DRAGMOVE](/windows/win32/Controls/rb-dragmove)davranışını uygular.

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Yeni fare koordinatlarını içeren bir DWORD değeri. Yatay koordinat LOWORD'da, dikey koordinat ise HIWORD'da bulunur. (DWORD)-1'i geçerseniz, rebar denetimi farenin konumunu en son denetim iş `GetMessage` `PeekMessage`parçacığı veya .

## <a name="crebarctrlenddrag"></a><a name="enddrag"></a>CReBarCtrl::EndDrag

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_ENDDRAG](/windows/win32/Controls/rb-enddrag)davranışını uygular.

```
void EndDrag();
```

## <a name="crebarctrlgetbandborders"></a><a name="getbandborders"></a>CReBarCtrl::GetBandBorders

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETBANDBORDERS](/windows/win32/Controls/rb-getbandborders)davranışını uygular.

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Sınırların alınacağı bandın sıfır tabanlı dizin.

*Çhc*<br/>
Bant kenarlıkları alacak bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısıiçin bir işaretçi. Demir çubuğu denetimi RBS_BANDBORDERS stiline sahipse, bu yapının her üyesi, kenarlığı oluşturan bandın ilgili tarafındaki piksel sayısını alır. Demir çubuğu denetimiRBS_BANDBORDERS stiline sahip değilse, bu yapının yalnızca sol üyesi geçerli bilgiler alır. Demir çubuğu denetim stillerinin açıklaması için Windows SDK'daki [Rebar Denetim Stilleri'ne](/windows/win32/Controls/rebar-control-styles) bakın.

## <a name="crebarctrlgetbandcount"></a><a name="getbandcount"></a>CReBarCtrl::GetBandCount

Windows SDK'da açıklandığı gibi Win32 iletisinin [davranışını RB_GETBANDCOUNT](/windows/win32/Controls/rb-getbandcount)uygular.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetime atanan bant ların sayısı.

## <a name="crebarctrlgetbandinfo"></a><a name="getbandinfo"></a>CReBarCtrl::GetBandInfo

Win32 iletisinin davranışını, Windows SDK'da açıklandığı gibi [RB_GETBANDINFO](/windows/win32/Controls/rb-getbandinfo) uygular.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Bilgilerin alınacağı bandın sıfır tabanlı dizini.

*prbbi*<br/>
Bant bilgilerini almak için [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) yapısına işaretçi. Bu yapının `cbSize` üyesini bu `sizeof(REBARBANDINFO)` iletiyi göndermeden önce almak istediğiniz öğelere ayarlamanız ve üyeyi `fMask` ayarlamanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

## <a name="crebarctrlgetbandmargins"></a><a name="getbandmargins"></a>CReBarCtrl::GetBandMargins

Grubun kenar boşluklarını alır.

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>Parametreler

*pMargins*<br/>
Bilgileri alacak bir [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins)yapısına işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [RB_GETBANDMARGINS](/windows/win32/Controls/rb-getbandmargins) iletinin işlevselliğini taklit eder.

## <a name="crebarctrlgetbarheight"></a><a name="getbarheight"></a>CReBarCtrl::GetBarHeight

Demir çubuğunun yüksekliğini alır.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin yüksekliğini, piksellerde temsil eden değer.

## <a name="crebarctrlgetbarinfo"></a><a name="getbarinfo"></a>CReBarCtrl::GetBarInfo

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETBARINFO](/windows/win32/Controls/rb-getbarinfo)davranışını uygular.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>Parametreler

*prbi*<br/>
Rebarinfo denetim bilgilerini alacak bir [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) yapısına işaretçi. Bu iletiyi göndermeden `sizeof(REBARINFO)` önce bu yapının *CBSize* üyesini ayarlamanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

## <a name="crebarctrlgetbkcolor"></a><a name="getbkcolor"></a>CReBarCtrl::GetBkColor

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETBKCOLOR](/windows/win32/Controls/rb-getbkcolor)davranışını uygular.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli varsayılan arka plan rengini temsil eden bir COLORREF değeri.

## <a name="crebarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>CReBarCtrl::GetColorScheme

Demir çubuğu denetimi için [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) yapısını alır.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parametreler

*lpcs*<br/>
Windows SDK'da açıklandığı gibi [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Yapı, `COLORSCHEME` düğme vurgulama rengini ve düğme gölge rengini içerir.

## <a name="crebarctrlgetdroptarget"></a><a name="getdroptarget"></a>CReBarCtrl::GetDropTarget

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETDROPTARGET](/windows/win32/Controls/rb-getdroptarget)davranışını uygular.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Dönüş Değeri

[IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) arabirimine işaretçi.

## <a name="crebarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CReBarCtrl::GetExtendedStyle

Geçerli demir çubuğu denetiminin genişletilmiş stillerini alır.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişletilmiş stilleri gösteren bayrakların bityişli birleşimi (VEYA). Olası bayraklar RBS_EX_SPLITTER ve RBS_EX_TRANSPARENT. Daha fazla bilgi için [CReBarCtrl::SetExtendedStyle](#setextendedstyle) yönteminin *dwMask* parametresini görün.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [RB_GETEXTENDEDSTYLE](/windows/win32/Controls/rb-dragmove) iletisini gönderir.

## <a name="crebarctrlgetimagelist"></a><a name="getimagelist"></a>CReBarCtrl::GetImageList

`CImageList` Bir çubuk denetimi ile ilişkili nesneyi alır.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CImageList](../../mfc/reference/cimagelist-class.md) nesnesine işaretçi. Denetim için görüntü listesi ayarlanınmazsa NULL'u döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) yapısında depolanan boyut ve maske bilgilerini kullanır.

## <a name="crebarctrlgetpalette"></a><a name="getpalette"></a>CReBarCtrl::GetPalette

Çubuk denetiminin geçerli paletini alır.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Dönüş Değeri

Demir çubuğu denetiminin geçerli paletini belirten bir [CPalette](../../mfc/reference/cpalette-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin `CPalette` bir Nesneyi HPALETTE yerine geri dönüş değeri olarak kullandığını unutmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

## <a name="crebarctrlgetrect"></a><a name="getrect"></a>CReBarCtrl::GetRect

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETRECT](/windows/win32/Controls/rb-getrect)davranışını uygular.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Çubuk kontrolündeki bir bandın sıfır tabanlı indeksi.

*Çhc*<br/>
Rebar bandının sınırlarını alacak bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

## <a name="crebarctrlgetrowcount"></a><a name="getrowcount"></a>CReBarCtrl::GetRowCount

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETROWCOUNT](/windows/win32/Controls/rb-getrowcount)davranışını uygular.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimdeki bant satırlarının sayısını temsil eden bir UINT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

## <a name="crebarctrlgetrowheight"></a><a name="getrowheight"></a>CReBarCtrl::GetRowHeight

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETROWHEIGHT](/windows/win32/Controls/rb-getrowheight)davranışını uygular.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>Parametreler

*uRow*<br/>
Yüksekliği alınacak bandın sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Piksellerde satır yüksekliğini temsil eden bir UINT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

## <a name="crebarctrlgettextcolor"></a><a name="gettextcolor"></a>CReBarCtrl::GetTextColor

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETTEXTCOLOR](/windows/win32/Controls/rb-gettextcolor)davranışını uygular.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli varsayılan metin rengini temsil eden bir COLORREF değeri.

## <a name="crebarctrlgettooltips"></a><a name="gettooltips"></a>CReBarCtrl::GetToolİpuçları

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_GETTOOLTIPS](/windows/win32/Controls/rb-gettooltips)davranışını uygular.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

MFC uygulamasının `GetToolTips` bir işaretçiyi `CToolTipCtrl`HWND yerine bir işaretçiye döndürtettiğini unutmayın.

## <a name="crebarctrlhittest"></a><a name="hittest"></a>CReBarCtrl::HitTest

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_HITTEST](/windows/win32/Controls/rb-hittest)davranışını uygular.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>Parametreler

*prbht*<br/>
[RBHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-rbhittestinfo) yapısına işaretçi. İletiyi göndermeden `pt` önce, bu yapının üyesi istemci koordinatlarında test edilecek noktaya başharfle başharfe yönlendirilmelidir.

### <a name="return-value"></a>Dönüş Değeri

Verilen noktada bandın sıfır tabanlı indeksi veya (çubuk bandı yoksa- 1) noktada.

## <a name="crebarctrlidtoindex"></a><a name="idtoindex"></a>CReBarCtrl::IDToIndex

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_IDTOINDEX](/windows/win32/controls/rb-idtoindex)davranışını uygular.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>Parametreler

*uBandID*<br/>
Belirtilen bandın uygulama tanımlı tanımlayıcısı, bant takıldığında `wID` [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) yapısının üyesine geçer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır tabanlı bant dizini veya -1 aksi takdirde. Yinelenen bant dizinleri varsa, ilki döndürülür.

## <a name="crebarctrlinsertband"></a><a name="insertband"></a>CReBarCtrl::InsertBand

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_INSERTBAND](/windows/win32/Controls/rb-insertband)davranışını uygular.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parametreler

*uIndex*<br/>
Bandın eklendiği yerin sıfır tabanlı dizini. Bu parametreyi -1 olarak ayarlarsanız, denetim yeni bandı son konuma ekler.

*prbbi*<br/>
Eklenecek bandı tanımlayan [bir REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) yapısına işaretçi. Bu işlevi aramadan `sizeof(REBARBANDINFO)` önce bu yapının *CBSize* üyesini ayarlamanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

## <a name="crebarctrlmaximizeband"></a><a name="maximizeband"></a>CReBarCtrl::Maksimum Bant

Bir çubuğu kontrolündeki bir bandı en büyük boyutuna göre yeniden boyutlandırın.

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Grubun sıfır tabanlı indeksi en üst düzeye çıkarılacak.

### <a name="remarks"></a>Açıklamalar

Windows SDK'da açıklandığı gibi, `fIdeal` Win32 iletisinin [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) 0 olarak ayarlanmış davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

## <a name="crebarctrlminimizeband"></a><a name="minimizeband"></a>CReBarCtrl::MinimizeBand

Bir çubuk kontrolündeki bir bandı en küçük boyutuna göre yeniden boyutlandırın.

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Bant Sıfır tabanlı indeks en aza indirilecek.

### <a name="remarks"></a>Açıklamalar

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_MINIMIZEBAND](/windows/win32/Controls/rb-minimizeband)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

## <a name="crebarctrlmoveband"></a><a name="moveband"></a>CReBarCtrl::MoveBand

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_MOVEBAND](/windows/win32/Controls/rb-moveband)davranışını uygular.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>Parametreler

*uKaynak*<br/>
Taşınacak bandın sıfır tabanlı dizin.

*Uto*<br/>
Yeni bant konumunun sıfır tabanlı dizin. Bu parametre değeri hiçbir zaman eksi bir bant sayısından büyük olmamalıdır. Bant sayısını elde etmek için [GetBandCount'ı](#getbandcount)arayın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

## <a name="crebarctrlpushchevron"></a><a name="pushchevron"></a>CReBarCtrl::PushChevron

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron)davranışını uygular.

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Chevron itilmesi gereken bandın sıfır tabanlı dizin.

*lAppValue*<br/>
32 bit değeri tanımlanan bir uygulama. Windows SDK'da [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron) içinde *lAppValue'e* bakın.

## <a name="crebarctrlrestoreband"></a><a name="restoreband"></a>CReBarCtrl::Geri Yükleme Bandı

Bir çubuğu kontrol etme de bir bandı ideal boyutuna göre yeniden boyutlandırıyor.

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Grubun sıfır tabanlı indeksi en üst düzeye çıkarılacak.

### <a name="remarks"></a>Açıklamalar

Windows SDK'da açıklandığı gibi, `fIdeal` Win32 iletisinin [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) 1 olarak ayarlanmış davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

## <a name="crebarctrlsetbandinfo"></a><a name="setbandinfo"></a>CReBarCtrl::SetBandInfo

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_SETBANDINFO](/windows/win32/Controls/rb-setbandinfo)davranışını uygular.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Yeni ayarları almak için bandın sıfır tabanlı dizin.

*prbbi*<br/>
Eklenecek bandı tanımlayan bir [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) yapısına işaretçi. Bu iletiyi göndermeden `cbSize` `sizeof(REBARBANDINFO)` önce bu yapının üyesini ayarlamanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

## <a name="crebarctrlsetbandwidth"></a><a name="setbandwidth"></a>CReBarCtrl::SetBandWidth

Geçerli demir çubuğu denetiminde belirtilen kenetlenmiş bandın genişliğini ayarlar.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*uBand*|[içinde] Bir çubuk bandının sıfır tabanlı dizin.|
|*cxGenişlik*|[içinde] Çubuk bandının yeni genişliği, piksel olarak.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [RB_SETBANDWIDTH](/windows/win32/Controls/rb-setbandwidth) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_rebar`geçerli demir çubuğu denetimine erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, her çubuk bandını aynı genişlikte ayarlar.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

## <a name="crebarctrlsetbarinfo"></a><a name="setbarinfo"></a>CReBarCtrl::SetBarInfo

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_SETBARINFO](/windows/win32/Controls/rb-setbarinfo)davranışını uygular.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>Parametreler

*prbi*<br/>
Ayarlanacak bilgileri içeren bir [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) yapısına işaretçi. Bu iletiyi göndermeden `cbSize` `sizeof(REBARINFO)` önce bu yapının üyesini ayarlamanız gerekir

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

## <a name="crebarctrlsetbkcolor"></a><a name="setbkcolor"></a>CReBarCtrl::SetBkColor

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_SETBKCOLOR](/windows/win32/Controls/rb-setbkcolor)davranışını uygular.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*Clr*<br/>
Yeni varsayılan arka plan rengini temsil eden COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

Önceki varsayılan arka plan rengini temsil eden bir [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Arka plan rengini ne zaman ayarlayıp varsayılan rengin nasıl ayarlanılacak hakkında daha fazla bilgi için bu konuya bakın.

## <a name="crebarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>CReBarCtrl::SetColorScheme

Demir çubuğu denetimindeki düğmelerin renk düzenini ayarlar.

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parametreler

*lpcs*<br/>
Windows SDK'da açıklandığı gibi [COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme) yapısına işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapı `COLORSCHEME` hem düğme vurgu rengi ve düğme gölge rengi içerir.

## <a name="crebarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CReBarCtrl::SetExtendedStyle

Geçerli çubuk denetimi için genişletilmiş stilleri ayarlar.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Dwmask*|[içinde] *dwStyleEx* parametresinde hangi bayrakların geçerli olduğunu belirten bir bitwise birleşimi (OR). Aşağıdaki değerlerden birini veya birkaçını kullanın:<br /><br /> RBS_EX_SPLITTER: Varsayılan olarak, splitter'i alt takimi yatay modda ve sağda dikey modda gösterin.<br /><br /> RBS_EX_TRANSPARENT: [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) iletiyi üst pencereye iletin.|
|*dwStyleEx*|[içinde] Uygulanacak stilleri belirten bayrakların bitwise birleşimi (VEYA). Bir stil ayarlamak *için, dwMask* parametresinde kullanılan bayrağı belirtin. Stili sıfırlamak için ikili sıfır belirtin.|

### <a name="return-value"></a>Dönüş Değeri

Önceki genişletilmiş stil.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [RB_SETEXTENDEDSTYLE](/windows/win32/Controls/rb-setextendedstyle) iletisini gönderir.

## <a name="crebarctrlsetimagelist"></a><a name="setimagelist"></a>CReBarCtrl::SetImageList

Bir rebar denetimine bir resim listesi atar.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Rebar denetimine atanacak görüntü listesini içeren [bir CImageList](../../mfc/reference/cimagelist-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

## <a name="crebarctrlsetowner"></a><a name="setowner"></a>CReBarCtrl::SetSahibi

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_SETPARENT](/windows/win32/Controls/rb-setparent)davranışını uygular.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Demir çubuğu `CWnd` denetiminin sahibi olarak ayarlanan bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çubuk denetiminin geçerli sahibi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin, pencerelere `CWnd` işlemek yerine, hem geçerli hem de seçili çubuk denetimi sahibi için nesneleriçin işaretçiler kullandığını unutmayın.

> [!NOTE]
> Bu üye işlev, denetim oluşturulduğunda ayarlanan gerçek üst öğeyi değiştirmez; bunun yerine belirttiğiniz pencereye bildirim iletileri gönderir.

## <a name="crebarctrlsetpalette"></a><a name="setpalette"></a>CReBarCtrl::SetPalette

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_SETPALETTE](/windows/win32/Controls/rb-setpalette)davranışını uygular.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>Parametreler

*hPal*<br/>
Demir çubuğu denetiminin kullanacağı yeni paleti belirten bir HPALETTE.

### <a name="return-value"></a>Dönüş Değeri

Bir [CPalette](../../mfc/reference/cpalette-class.md) nesnesine işaretçi, demir çubuğu denetiminin önceki paletini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin `CPalette` bir Nesneyi HPALETTE yerine geri dönüş değeri olarak kullandığını unutmayın.

## <a name="crebarctrlsettextcolor"></a><a name="settextcolor"></a>CReBarCtrl::SetTextColor

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_SETTEXTCOLOR](/windows/win32/Controls/rb-settextcolor)davranışını uygular.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*Clr*<br/>
`CReBarCtrl` Nesnedeki yeni metin rengini temsil eden bir COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

`CReBarCtrl` Nesneyle ilişkili önceki metin rengini temsil eden [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bir çubuk denetiminde metin rengi esnekliğini desteklemek için sağlanır.

## <a name="crebarctrlsettooltips"></a><a name="settooltips"></a>CReBarCtrl::SetToolTips

Bir araç ipucu denetimini bir demir çubuğu denetimiyle ilişkilendirir.

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesine işaretçi

### <a name="remarks"></a>Açıklamalar

Onunla bittiğinde `CToolTipCtrl` nesneyi yok etmelisiniz.

## <a name="crebarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CReBarCtrl::SetWindowTheme

Demir çubuğu denetiminin görsel stilini ayarlar.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametreler

*pszSubAppName*<br/>
Ayarlanan rebar görsel stilini içeren Unicode dizesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İade değeri kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [RB_SETWINDOWTHEME](/windows/win32/Controls/rb-setwindowtheme) iletinin işlevselliğini taklit eder.

## <a name="crebarctrlshowband"></a><a name="showband"></a>CReBarCtrl::ShowBand

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_SHOWBAND](/windows/win32/Controls/rb-showband)davranışını uygular.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Çubuk kontrolündeki bir bandın sıfır tabanlı indeksi.

*fShow*<br/>
Bandın gösterilmesi veya gizlenip gizlenmemesi gerektiğini gösterir. Bu değer TRUE ise, bant gösterilir. Aksi takdirde, grup gizli olacaktır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

## <a name="crebarctrlsizetorect"></a><a name="sizetorect"></a>CReBarCtrl::SizeToRect

Windows SDK'da açıklandığı gibi Win32 iletisinin [RB_SIZETORECT](/windows/win32/Controls/rb-sizetorect)davranışını uygular.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine yapılan ve demir çubuğu denetiminin boyutlandırılması gereken dikdörtgeni belirten bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin `CRect` bir `RECT` yapı yerine bir nesneyi parametre olarak kullandığını unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
