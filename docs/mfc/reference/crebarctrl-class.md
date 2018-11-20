---
title: CReBarCtrl sınıfı
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
ms.openlocfilehash: 072fcec4944088ab087a6a39c7d8b916c3bc80e2
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52177036"
---
# <a name="crebarctrl-class"></a>CReBarCtrl sınıfı

Alt pencere kapsayıcısı olan bir çubuk barınağı denetiminin işlevselliğini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Oluşturur bir `CReBarCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CReBarCtrl::BeginDrag](#begindrag)|Çubuk barınağı denetimi sürükle ve bırak moduna yerleştirir.|
|[CReBarCtrl::Create](#create)|Çubuk barınağı denetimi oluşturur ve ona ekler `CReBarCtrl` nesne.|
|[CReBarCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir çubuk barınağı denetimi oluşturur ve ona ekler bir `CReBarCtrl` nesne.|
|[CReBarCtrl::DeleteBand](#deleteband)|Bir bandı bir çubuk barınağı denetimi siler.|
|[CReBarCtrl::DragMove](#dragmove)|Rebar denetiminde sürükleme konumu çağrısı yapıldıktan sonra güncelleştirmeleri `BeginDrag`.|
|[CReBarCtrl::EndDrag](#enddrag)|Çubuk barınağı denetiminin sürükle ve bırak işlemi sonlandırır.|
|[CReBarCtrl::GetBandBorders](#getbandborders)|Bir bant kenarlıklarını alır.|
|[CReBarCtrl::GetBandCount](#getbandcount)|Rebar denetiminde bantları sayısını alır.|
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Bir rebar denetiminde belirtilen bir bant hakkındaki bilgileri alır.|
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Bir bant kenar boşlukları alır.|
|[CReBarCtrl::GetBarHeight](#getbarheight)|Çubuk barınağı şeritleri yüksekliğini alır.|
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Çubuk barınağı şeritleri ve kullandığı görüntü listesi hakkındaki bilgileri alır.|
|[CReBarCtrl::GetBkColor](#getbkcolor)|Çubuk barınağı denetiminin varsayılan arka plan rengini alır.|
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Alır [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) yapısı çubuk barınağı denetimi ile ilişkilendirilmiş.|
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Çubuk barınağı denetiminin alır `IDropTarget` arabirim işaretçisi.|
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Genişletilmiş geçerli çubuk barınağı denetiminin stilini alır.|
|[CReBarCtrl::GetImageList](#getimagelist)|Rebar denetimiyle ilişkili görüntü listesini alır.|
|[CReBarCtrl::GetPalette](#getpalette)|Çubuk barınağı denetiminin geçerli palet alır.|
|[CReBarCtrl::GetRect](#getrect)|Bir rebar denetiminde belirli bir bant için sınırlayıcı dikdörtgeni alır.|
|[CReBarCtrl::GetRowCount](#getrowcount)|Bir rebar denetiminde bant satır sayısını alır.|
|[CReBarCtrl::GetRowHeight](#getrowheight)|Bir rebar denetiminde belirtilen bir satırın yüksekliğini alır.|
|[CReBarCtrl::GetTextColor](#gettextcolor)|Çubuk barınağı denetiminin varsayılan metin rengini alır.|
|[CReBarCtrl::GetToolTips](#gettooltips)|Rebar denetimiyle birlikte ilişkili herhangi bir araç ipucu denetimi tanıtıcısını alır.|
|[CReBarCtrl::HitTest](#hittest)|Çubuk barınağı bant bu noktada varsa ekranında, belirli bir noktada bir çubuk barınağı bant hangi kısmı olduğunu belirler.|
|[CReBarCtrl::IDToIndex](#idtoindex)|Bir rebar denetiminde bir bant dizini bant tanımlayıcısını (ID) dönüştürür.|
|[CReBarCtrl::InsertBand](#insertband)|Bir rebar denetiminde yeni bant ekler.|
|[CReBarCtrl::MaximizeBand](#maximizeband)|Bir rebar denetiminde en büyük boyutuna bir bandı yeniden boyutlandırır.|
|[CReBarCtrl::MinimizeBand](#minimizeband)|Bir rebar denetiminde en küçük boyutuna bir bandı yeniden boyutlandırır.|
|[CReBarCtrl::MoveBand](#moveband)|Bir bandı bir dizini diğerine taşır.|
|[CReBarCtrl::PushChevron](#pushchevron)|Program aracılığıyla köşeli çift ayraç iter.|
|[CReBarCtrl::RestoreBand](#restoreband)|Bir rebar denetiminde ideal boyutuna bir bandı yeniden boyutlandırır.|
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Bir rebar denetiminde var olan bir bant özelliklerini ayarlar.|
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Geçerli bir rebar denetiminde belirtilen yerleştirilmiş bant genişliğini ayarlar.|
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Rebar denetimiyle özelliklerini ayarlar.|
|[CReBarCtrl::SetBkColor](#setbkcolor)|Çubuk barınağı denetiminin varsayılan arka plan rengini ayarlar.|
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Bir rebar denetiminde düğmeleri renk düzenini ayarlar.|
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Genişletilmiş stiller geçerli çubuk barınağı denetimi için ayarlar.|
|[CReBarCtrl::SetImageList](#setimagelist)|Çubuk barınağı denetiminin resim listesi ayarlar.|
|[CReBarCtrl::SetOwner](#setowner)|Çubuk barınağı denetiminin sahibi penceresine ayarlar.|
|[CReBarCtrl::SetPalette](#setpalette)|Çubuk barınağı denetiminin geçerli palet ayarlar.|
|[CReBarCtrl::SetTextColor](#settextcolor)|Çubuk barınağı denetiminin varsayılan metin rengini belirler.|
|[CReBarCtrl::SetToolTips](#settooltips)|Rebar denetimiyle birlikte bir araç ipucunu denetimini ilişkilendirir.|
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Çubuk barınağı şeritleri görsel stilini ayarlar.|
|[CReBarCtrl::ShowBand](#showband)|Bir rebar denetiminde belirli bir bant gizler veya gösterir.|
|[CReBarCtrl::SizeToRect](#sizetorect)|Rebar denetimi için belirtilen bir dikdörtgen uyar.|

## <a name="remarks"></a>Açıklamalar

Çubuk barınağı şeritleri bulunduğu uygulama çubuk barınağı bant çubuk barınağı denetimi tarafından bulunan alt pencerenin atar. Genellikle başka bir ortak denetimi alt penceredir.

Bir veya daha fazla bant çubuk barınağı denetimleri içerir. Her bant bir Mandal çubuğu, bir bit eşlem, bir metin etiketi ve alt pencere bir birleşimini içerebilir. Bant, bu öğelerin her biri yalnızca birini içerebilir.

Çubuk barınağı denetimi alt pencere üzerinde belirtilen arka plan bit eşlem görüntüleyebilirsiniz. Tüm çubuk barınağı denetimi bantları, RBBS_FIXEDSIZE stili kullananlar yeniden boyutlandırılabilir. Yeniden konumlandırma veya bir çubuk barınağı denetimi Şerit yeniden boyutlandırma gibi çubuk barınağı denetiminin boyutunu ve konumunu, bant için atanan alt pencerenin yönetir. Yeniden boyutlandırma veya denetiminde bantları sırasını değiştirmek için tıklayın ve bir bandın kavrayıcı çubuğunu sürükleyin.

Aşağıdaki çizim üç bantları içeren bir çubuk barınağı denetim gösterir:

- Bant 0 sabit, saydam araç çubuğu denetimi içerir.

- Bant 1 hem saydam standart ve saydam açılır düğmeler içerir.

- Bant 2 bir birleşik giriş kutusu ve dört standart düğmeleri içerir.

   ![Örnek bir çubuk Barınağı menüsünün](../../mfc/reference/media/vc4scc1.gif "çubuk Barınağı menü örneği")

## <a name="rebar-control"></a>Rebar denetimi

Denetimleri destek rebar:

- Görüntü listeleri.

- İleti işleme.

- Özel çizim işlevselliği.

- Denetim stilleri standart pencere stilleri yanı sıra çeşitli. Bu stiller listesi için bkz. [Rebar denetim stilleri](/windows/desktop/Controls/rebar-control-styles) Windows SDK.

Daha fazla bilgi için [kullanarak CReBarCtrl](../../mfc/using-crebarctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="begindrag"></a>  CReBarCtrl::BeginDrag

Win32 ileti davranışı uygulayan [RB_BEGINDRAG](/windows/desktop/Controls/rb-begindrag)Windows SDK içinde açıklandığı gibi.

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Sürükle ve bırak işlemi etkileyen bant sıfır tabanlı dizini.

*dwPos*<br/>
Başlangıç'ı içeren bir DWORD değeri fare koordinatları. Yatay koordinat GET_X_LPARAM içinde yer alır ve dikey koordinat get_y_lparam kullanın içinde yer alır. Çubuk barınağı şeritleri (DWORD) -1 geçirirseniz, son zamanı adlı denetimin iş parçacığı fare konumu kullanacak `GetMessage` veya `PeekMessage`.

##  <a name="create"></a>  CReBarCtrl::Create

Çubuk barınağı denetimi oluşturur ve ona ekler `CReBarCtrl` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Çubuk barınağı denetim stilleri denetime uygulanan bileşimini belirtir. Bkz: [Rebar denetim stilleri](/windows/desktop/Controls/rebar-control-styles) desteklenen stilleri bir listesi için Windows SDK.

*Rect*<br/>
Bir başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne veya [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) çubuk barınağı denetiminin boyutunu ve konumunu olan yapısı.

*pParentWnd*<br/>
Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) çubuk barınağı denetiminin üst penceresine olan nesne. NULL olmamalıdır.

*nID*<br/>
Barınağı denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Rebar denetimiyle iki adımda oluşturun:

1. Çağrı [CReBarCtrl](#crebarctrl) oluşturmak için bir `CReBarCtrl` nesne.

1. Windows çubuk barınağı denetimi oluşturur ve ona ekler, bu üye işlevi çağrısı `CReBarCtrl` nesne.

Çağırdığınızda `Create`, ortak denetimleri yeniden başlatılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

##  <a name="createex"></a>  CReBarCtrl::CreateEx

Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CReBarCtrl` nesne.

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
Çubuk barınağı denetim stilleri denetime uygulanan bileşimini belirtir. Desteklenen stilleri bir listesi için bkz. [Rebar denetim stilleri](/windows/desktop/Controls/rebar-control-styles) Windows SDK.

*Rect*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.

*pParentWnd*<br/>
Denetimin ana penceresine bir işaretçi.

*nID*<br/>
Denetimin alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.

##  <a name="crebarctrl"></a>  CReBarCtrl::CReBarCtrl

Oluşturur bir `CReBarCtrl` nesne.

```
CReBarCtrl();
```

### <a name="example"></a>Örnek

  Örneğin bakın [CReBarCtrl::Create](#create).

##  <a name="deleteband"></a>  CReBarCtrl::DeleteBand

Win32 ileti davranışı uygulayan [RB_DELETEBAND](/windows/desktop/Controls/rb-deleteband)Windows SDK içinde açıklandığı gibi.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Bant silinmek üzere sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bant başarıyla silindi olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

##  <a name="dragmove"></a>  CReBarCtrl::DragMove

Win32 ileti davranışı uygulayan [RB_DRAGMOVE](/windows/desktop/Controls/rb-dragmove)Windows SDK içinde açıklandığı gibi.

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Yeni fare koordinatları içeren bir DWORD değeri. Yatay koordinat GET_X_LPARAM içinde yer alır ve dikey koordinat get_y_lparam kullanın içinde yer alır. Çubuk barınağı şeritleri (DWORD) -1 geçirirseniz, son zamanı adlı denetimin iş parçacığı fare konumu kullanacak `GetMessage` veya `PeekMessage`.

##  <a name="enddrag"></a>  CReBarCtrl::EndDrag

Win32 ileti davranışı uygulayan [RB_ENDDRAG](/windows/desktop/Controls/rb-enddrag)Windows SDK içinde açıklandığı gibi.

```
void EndDrag();
```

##  <a name="getbandborders"></a>  CReBarCtrl::GetBandBorders

Win32 ileti davranışı uygulayan [RB_GETBANDBORDERS](/windows/desktop/Controls/rb-getbandborders)Windows SDK içinde açıklandığı gibi.

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Kenarlıkları alınır bant sıfır tabanlı dizini.

*ÇHC*<br/>
Bir işaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) bant kenarlıklarını alacak yapısı. Çubuk barınağı şeritleri RBS_BANDBORDERS stili varsa, bu yapının her üyesini oluşturan kenarlığın piksel sayısı, bant, karşılık gelen tarafındaki alırsınız. Çubuk barınağı şeritleri RBS_BANDBORDERS stili yoksa, bu yapının yalnızca sol üyesi geçerli bilgilerini alır. Çubuk barınağı denetim stilleri açıklaması için bkz: [çubuk Barınağı denetim stilleri](/windows/desktop/Controls/rebar-control-styles) Windows SDK.

##  <a name="getbandcount"></a>  CReBarCtrl::GetBandCount

Win32 ileti davranışı uygulayan [RB_GETBANDCOUNT](/windows/desktop/Controls/rb-getbandcount)Windows SDK içinde açıklandığı gibi.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetime atanmış Bantların sayısı.

##  <a name="getbandinfo"></a>  CReBarCtrl::GetBandInfo

Win32 ileti davranışı uygulayan [RB_GETBANDINFO](/windows/desktop/Controls/rb-getbandinfo) Windows SDK içinde açıklandığı gibi.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Bilgileri alınır bant sıfır tabanlı dizini.

*prbbi*<br/>
Bir işaretçi bir [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) yapısı bant bilgileri almak için. Ayarlamalısınız `cbSize` için bu yapı üyesi `sizeof(REBARBANDINFO)` ve `fMask` üye bu iletiyi göndermeden önce almak istediğiniz öğeleri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="getbandmargins"></a>  CReBarCtrl::GetBandMargins

Kenar boşlukları bant alır.

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>Parametreler

*pMargins*<br/>
Bir işaretçi bir [kenar BOŞLUKLARI](/windows/desktop/api/uxtheme/ns-uxtheme-_margins)bilgi alacak yapısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi işlevselliğine öykünür [RB_GETBANDMARGINS](/windows/desktop/Controls/rb-getbandmargins) Windows SDK içinde açıklandığı gibi ileti.

##  <a name="getbarheight"></a>  CReBarCtrl::GetBarHeight

Çubuk barınağı çubuğu yüksekliğini alır.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin piksel cinsinden yüksekliği temsil eden değer.

##  <a name="getbarinfo"></a>  CReBarCtrl::GetBarInfo

Win32 ileti davranışı uygulayan [RB_GETBARINFO](/windows/desktop/Controls/rb-getbarinfo)Windows SDK içinde açıklandığı gibi.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>Parametreler

*prbi*<br/>
Bir işaretçi bir [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) çubuk barınağı denetim bilgileri alacak yapısı. Ayarlamalısınız *cbSize* için bu yapı üyesi `sizeof(REBARINFO)` bu iletiyi göndermeden önce.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="getbkcolor"></a>  CReBarCtrl::GetBkColor

Win32 ileti davranışı uygulayan [RB_GETBKCOLOR](/windows/desktop/Controls/rb-getbkcolor)Windows SDK içinde açıklandığı gibi.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli varsayılan arka plan rengi temsil COLORREF değeri.

##  <a name="getcolorscheme"></a>  CReBarCtrl::GetColorScheme

Alır [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) çubuk barınağı şeritleri için yapısı.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parametreler

*lpcs*<br/>
Bir işaretçi bir [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Windows SDK içinde anlatıldığı gibi yapılandırın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

`COLORSCHEME` Yapısı, düğme Vurgu rengi ve düğme gölge rengi içerir.

##  <a name="getdroptarget"></a>  CReBarCtrl::GetDropTarget

Win32 ileti davranışı uygulayan [RB_GETDROPTARGET](/windows/desktop/Controls/rb-getdroptarget)Windows SDK içinde açıklandığı gibi.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [ıdroptarget'ı](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) arabirimi.

##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle

Genişletilmiş stiller geçerli çubuk barınağı denetimi alır.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bitsel bir birleşimi (veya) genişletilmiş stiller belirten bayrak. Olası RBS_EX_SPLITTER ve RBS_EX_TRANSPARENT bayraklar. Daha fazla bilgi için *dwMask* parametresinin [CReBarCtrl::SetExtendedStyle](#setextendedstyle) yöntemi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [RB_GETEXTENDEDSTYLE](/windows/desktop/Controls/rb-dragmove) Windows SDK'da açıklanan ileti.

##  <a name="getimagelist"></a>  CReBarCtrl::GetImageList

Alır `CImageList` rebar denetimiyle birlikte ilişkili nesne.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesne. Hiçbir görüntü listesi denetimi için ayarlanmışsa NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi içinde depolanan boyutu ve maskesi bilgilerini kullanan [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) Windows SDK içinde anlatıldığı gibi yapılandırın.

##  <a name="getpalette"></a>  CReBarCtrl::GetPalette

Çubuk barınağı denetiminin geçerli palet alır.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CPalette](../../mfc/reference/cpalette-class.md) barınağı geçerli palet belirterek nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi kullanan Not bir `CPalette` bir HPALETTE yerine dönüş değeri olarak nesnesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

##  <a name="getrect"></a>  CReBarCtrl::GetRect

Win32 ileti davranışı uygulayan [RB_GETRECT](/windows/desktop/Controls/rb-getrect)Windows SDK içinde açıklandığı gibi.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Rebar denetiminde bir bant sıfır tabanlı dizini.

*ÇHC*<br/>
Bir işaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) çubuk barınağı bant sınırları alacak yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

##  <a name="getrowcount"></a>  CReBarCtrl::GetRowCount

Win32 ileti davranışı uygulayan [RB_GETROWCOUNT](/windows/desktop/Controls/rb-getrowcount)Windows SDK içinde açıklandığı gibi.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimdeki bant satır sayısını temsil eden bir UINT değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

##  <a name="getrowheight"></a>  CReBarCtrl::GetRowHeight

Win32 ileti davranışı uygulayan [RB_GETROWHEIGHT](/windows/desktop/Controls/rb-getrowheight)Windows SDK içinde açıklandığı gibi.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>Parametreler

*uRow*<br/>
Alınan yükseklik olan bant sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Satır yüksekliğini piksel cinsinden temsil eden bir UINT değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

##  <a name="gettextcolor"></a>  CReBarCtrl::GetTextColor

Win32 ileti davranışı uygulayan [RB_GETTEXTCOLOR](/windows/desktop/Controls/rb-gettextcolor)Windows SDK içinde açıklandığı gibi.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli varsayılan metin rengi temsil COLORREF değeri.

##  <a name="gettooltips"></a>  CReBarCtrl::GetToolTips

Win32 ileti davranışı uygulayan [RB_GETTOOLTIPS](/windows/desktop/Controls/rb-gettooltips)Windows SDK içinde açıklandığı gibi.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Unutmayın, MFC uygulaması `GetToolTips` bir işaretçi döndürür bir `CToolTipCtrl`, bir HWND yerine.

##  <a name="hittest"></a>  CReBarCtrl::HitTest

Win32 ileti davranışı uygulayan [RB_HITTEST](/windows/desktop/Controls/rb-hittest)Windows SDK içinde açıklandığı gibi.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>Parametreler

*prbht*<br/>
Bir işaretçi bir [RBHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_rb_hittestinfo) yapısı. Bir ileti göndermeden önce `pt` bu yapı üyesi, istemci koordinatları olarak sınanacak noktasına başlatılması gerekir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen noktasını ya da hiçbir çubuk barınağı bant noktada ise -1 bant sıfır tabanlı dizini.

##  <a name="idtoindex"></a>  CReBarCtrl::IDToIndex

Win32 ileti davranışı uygulayan [RB_IDTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb774496)Windows SDK içinde açıklandığı gibi.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>Parametreler

*uBandID*<br/>
Belirtilen bant, uygulama tanımlı tanımlayıcısını geçirilen `wID` üyesi [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) bant eklendiğinde, yapı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır tabanlı bant dizini veya -1 Aksi takdirde. Yinelenen bant dizinlerini varsa, ilki döndürülür.

##  <a name="insertband"></a>  CReBarCtrl::InsertBand

Win32 ileti davranışı uygulayan [RB_INSERTBAND](/windows/desktop/Controls/rb-insertband)Windows SDK içinde açıklandığı gibi.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parametreler

*uIndex*<br/>
Konumun bant ekleneceği sıfır tabanlı dizini. Bu parametreyi -1 olarak ayarlarsanız, denetimi yeni bant son konumda ekleyin.

*prbbi*<br/>
Bir işaretçi bir [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) eklenecek bant tanımlayan yapısını. Ayarlamalısınız *cbSize* için bu yapı üyesi `sizeof(REBARBANDINFO)` bu işlevi çağırmadan önce.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

##  <a name="maximizeband"></a>  CReBarCtrl::MaximizeBand

Bir rebar denetiminde en büyük boyutuna bir bandı yeniden boyutlandırır.

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Tam ekran için bant sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Win32 ileti davranışı uygulayan [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) ile `fIdeal` Windows SDK'da açıklandığı 0 olarak ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

##  <a name="minimizeband"></a>  CReBarCtrl::MinimizeBand

Bir rebar denetiminde en küçük boyutuna bir bandı yeniden boyutlandırır.

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Bant en aza indirgenebilir için sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Win32 ileti davranışı uygulayan [RB_MINIMIZEBAND](/windows/desktop/Controls/rb-minimizeband)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

##  <a name="moveband"></a>  CReBarCtrl::MoveBand

Win32 ileti davranışı uygulayan [RB_MOVEBAND](/windows/desktop/Controls/rb-moveband)Windows SDK içinde açıklandığı gibi.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>Parametreler

*uFrom*<br/>
Taşınacak bant sıfır tabanlı dizini.

*Otomatik*<br/>
Yeni bant konumunu sıfır tabanlı dizini. Bu parametre değeri hiçbir zaman bir Bantların sayısı değerinden büyük olmalıdır. Bantların sayısı elde etmek için çağrı [GetBandCount](#getbandcount).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="pushchevron"></a>  CReBarCtrl::PushChevron

Win32 ileti davranışı uygulayan [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron)Windows SDK içinde açıklandığı gibi.

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
İtilecek olan köşeli çift ayraç olan bant sıfır tabanlı dizini.

*lAppValue*<br/>
Bir uygulama tanımlı 32-bit değeri. Bkz: *lAppValue* içinde [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron) Windows SDK.

##  <a name="restoreband"></a>  CReBarCtrl::RestoreBand

Bir rebar denetiminde ideal boyutuna bir bandı yeniden boyutlandırır.

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Tam ekran için bant sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Win32 ileti davranışı uygulayan [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) ile `fIdeal` Windows SDK'da açıklandığı 1 olarak ayarlandı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

##  <a name="setbandinfo"></a>  CReBarCtrl::SetBandInfo

Win32 ileti davranışı uygulayan [RB_SETBANDINFO](/windows/desktop/Controls/rb-setbandinfo)Windows SDK içinde açıklandığı gibi.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Yeni ayarları almaları için bant sıfır tabanlı dizini.

*prbbi*<br/>
İşaretçi bir [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) eklenecek bant tanımlayan yapısını. Ayarlamalısınız `cbSize` için bu yapı üyesi `sizeof(REBARBANDINFO)` bu iletiyi göndermeden önce.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

##  <a name="setbandwidth"></a>  CReBarCtrl::SetBandWidth

Geçerli bir rebar denetiminde belirtilen yerleştirilmiş bant genişliğini ayarlar.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*uBand*|[in] Bir rebar bant sıfır tabanlı dizini.|
|*cxWidth*|[in] Yeni çubuk barınağı bant, piksel cinsinden genişliği.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [RB_SETBANDWIDTH](/windows/desktop/Controls/rb-setbandwidth) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_rebar`, yani geçerli çubuk barınağı denetimi erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği her çubuk barınağı bant genişliklerini olacak şekilde ayarlar.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

##  <a name="setbarinfo"></a>  CReBarCtrl::SetBarInfo

Win32 ileti davranışı uygulayan [RB_SETBARINFO](/windows/desktop/Controls/rb-setbarinfo)Windows SDK içinde açıklandığı gibi.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>Parametreler

*prbi*<br/>
Bir işaretçi bir [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) ayarlamak için bilgileri içeren yapısı. Ayarlamalısınız `cbSize` için bu yapı üyesi `sizeof(REBARINFO)` bu iletiyi göndermeden önce

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

##  <a name="setbkcolor"></a>  CReBarCtrl::SetBkColor

Win32 ileti davranışı uygulayan [RB_SETBKCOLOR](/windows/desktop/Controls/rb-setbkcolor)Windows SDK içinde açıklandığı gibi.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*CLR*<br/>
Yeni varsayılan arka plan rengi temsil eden COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

A [COLORREF](/windows/desktop/gdi/colorref) önceki varsayılan arka plan rengini gösteren bir değer.

### <a name="remarks"></a>Açıklamalar

Bu konuda arka plan rengini ayarlamak ne zaman ve varsayılan ayarlama hakkında daha fazla bilgi için bkz.

##  <a name="setcolorscheme"></a>  CReBarCtrl::SetColorScheme

Bir rebar denetiminde düğmeleri renk düzenini ayarlar.

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parametreler

*lpcs*<br/>
Bir işaretçi bir [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Windows SDK içinde anlatıldığı gibi yapılandırın.

### <a name="remarks"></a>Açıklamalar

`COLORSCHEME` Düğme Vurgu rengi hem düğme gölge rengi yapısı içerir.

##  <a name="setextendedstyle"></a>  CReBarCtrl::SetExtendedStyle

Genişletilmiş stiller geçerli çubuk barınağı denetimi için ayarlar.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwMask*|[in] Bitsel bir birleşimi (veya) hangi bayrak belirten bayrakları *dwStyleEx* parametresi geçerlidir. Bir veya daha fazla aşağıdaki değerleri kullanın:<br /><br /> RBS_EX_SPLITTER: varsayılan olarak, bölme ve en altında yatay modda ve sağa doğru dikey modda gösterir.<br /><br /> RBS_EX_TRANSPARENT: İleri [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) üst penceresine ileti.|
|*dwStyleEx*|[in] Bitsel bir birleşimi (veya) stilleri uygulamak için belirten bayrak. Stil ayarlamak için kullanılan aynı bayrağını belirtin *dwMask* parametresi. Bir stil sıfırlamak için ikili sıfır belirtin.|

### <a name="return-value"></a>Dönüş Değeri

Önceki genişletilmiş stili.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [RB_SETEXTENDEDSTYLE](/windows/desktop/Controls/rb-setextendedstyle) Windows SDK'da açıklanan ileti.

##  <a name="setimagelist"></a>  CReBarCtrl::SetImageList

Görüntü listesi için bir çubuk barınağı denetimi atar.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) çubuk barınağı şeritleri için atanan görüntü listesi içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="setowner"></a>  CReBarCtrl::SetOwner

Win32 ileti davranışı uygulayan [RB_SETPARENT](/windows/desktop/Controls/rb-setparent)Windows SDK içinde açıklandığı gibi.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Bir işaretçi bir `CWnd` nesne çubuk barınağı şeritleri sahibi olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) çubuk barınağı şeritleri geçerli sahibi olan nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev işaretçileri kullandığına dikkat edin `CWnd` işleme windows yerine nesneleri hem geçerli ve seçili sahibi çubuk barınağı şeritleri için.

> [!NOTE]
>  Bu üye işlevi, denetimin oluşturulurken ayarlanan gerçek üst değiştirmez. Bunun yerine, belirttiğiniz pencereye bildirim iletileri gönderir.

##  <a name="setpalette"></a>  CReBarCtrl::SetPalette

Win32 ileti davranışı uygulayan [RB_SETPALETTE](/windows/desktop/Controls/rb-setpalette)Windows SDK içinde açıklandığı gibi.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>Parametreler

*hPal*<br/>
Çubuk barınağı şeritleri kullanacağı yeni paletini belirtir bir HPALETTE.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CPalette](../../mfc/reference/cpalette-class.md) barınağı önceki palet belirterek nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi kullanan Not bir `CPalette` bir HPALETTE yerine dönüş değeri olarak nesnesi.

##  <a name="settextcolor"></a>  CReBarCtrl::SetTextColor

Win32 ileti davranışı uygulayan [RB_SETTEXTCOLOR](/windows/desktop/Controls/rb-settextcolor)Windows SDK içinde açıklandığı gibi.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*CLR*<br/>
Yeni metin temsil eden bir COLORREF değer renk `CReBarCtrl` nesne.

### <a name="return-value"></a>Dönüş Değeri

[COLORREF](/windows/desktop/gdi/colorref) önceki metin rengi temsil eden değer ilişkili `CReBarCtrl` nesne.

### <a name="remarks"></a>Açıklamalar

Bir rebar denetiminde metin rengi esnekliği destekleyen sağlanır.

##  <a name="settooltips"></a>  CReBarCtrl::SetToolTips

Rebar denetimiyle birlikte bir araç ipucunu denetimini ilişkilendirir.

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
Bir işaretçi bir [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesi

### <a name="remarks"></a>Açıklamalar

İmha etmeniz gerekir `CToolTipCtrl` ile işiniz bittiğinde nesne.

##  <a name="setwindowtheme"></a>  CReBarCtrl::SetWindowTheme

Çubuk barınağı şeritleri görsel stilini ayarlar.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametreler

*pszSubAppName*<br/>
Ayarlanacak çubuk barınağı görsel stili içeren bir Unicode dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi işlevselliğine öykünür [RB_SETWINDOWTHEME](/windows/desktop/Controls/rb-setwindowtheme) Windows SDK içinde açıklandığı gibi ileti.

##  <a name="showband"></a>  CReBarCtrl::ShowBand

Win32 ileti davranışı uygulayan [RB_SHOWBAND](/windows/desktop/Controls/rb-showband)Windows SDK içinde açıklandığı gibi.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>Parametreler

*uBand*<br/>
Rebar denetiminde bir bant sıfır tabanlı dizini.

*fShow*<br/>
Bant gösterilen veya gizli olmadığını gösterir. Bu değeri TRUE olursa, bandı gösterilir. Aksi takdirde, bant gizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="sizetorect"></a>  CReBarCtrl::SizeToRect

Win32 ileti davranışı uygulayan [RB_SIZETORECT](/windows/desktop/Controls/rb-sizetorect)Windows SDK içinde açıklandığı gibi.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bir başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) çubuk barınağı şeritleri için boyutlandırılmalıdır dikdörtgen belirten bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi kullanan Not bir `CRect` bir parametre olarak nesne yerine `RECT` yapısı.

## <a name="see-also"></a>Ayrıca Bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

