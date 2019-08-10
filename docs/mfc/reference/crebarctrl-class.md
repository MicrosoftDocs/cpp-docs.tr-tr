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
ms.openlocfilehash: 102c06879ffaedb91f20a4b5085a10015d7a4c8b
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916865"
---
# <a name="crebarctrl-class"></a>CReBarCtrl sınıfı

Bir alt pencerenin kapsayıcısı olan bir Rebar denetiminin işlevselliğini Kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CReBarCtrl:: CReBarCtrl](#crebarctrl)|Bir `CReBarCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CReBarCtrl:: BeginDrag](#begindrag)|Yeniden çubuk denetimini sürükleyip bırakma moduna koyar.|
|[CReBarCtrl:: Create](#create)|Yeniden çubuk denetimini oluşturur ve `CReBarCtrl` nesneye ekler.|
|[CReBarCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir Rebar denetimi oluşturur ve bunu bir `CReBarCtrl` nesneye ekler.|
|[CReBarCtrl::D eleteBand](#deleteband)|Yeniden çubuk denetiminden bir bandı siler.|
|[CReBarCtrl::D ragMove](#dragmove)|Bir çağrısından `BeginDrag`sonra yeniden çubuk denetimindeki sürükleme konumunu günceller.|
|[CReBarCtrl:: EndDrag](#enddrag)|Rebar denetiminin sürükle ve bırak işlemini sonlandırır.|
|[CReBarCtrl:: GetBandBorders](#getbandborders)|Bir bantın kenarlıklarını alır.|
|[CReBarCtrl:: GetBandCount](#getbandcount)|Yeniden çubuk denetimindeki bantların sayısını alır.|
|[CReBarCtrl:: Getbanınfo](#getbandinfo)|Bir Rebar denetiminde belirtilen bir bant hakkındaki bilgileri alır.|
|[CReBarCtrl:: Getbandkenar boşlukları](#getbandmargins)|Bir bandın kenar boşluklarını alır.|
|[CReBarCtrl:: GetBarHeight](#getbarheight)|Rebar denetiminin yüksekliğini alır.|
|[CReBarCtrl:: Getbarınfo](#getbarinfo)|Rebar denetimi ve kullandığı görüntü listesi hakkında bilgi alır.|
|[CReBarCtrl:: GetBkColor](#getbkcolor)|Bir Rebar denetiminin varsayılan arka plan rengini alır.|
|[CReBarCtrl:: GetColorScheme](#getcolorscheme)|Rebar Denetimiyle ilişkili [colorscheme](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) yapısını alır.|
|[CReBarCtrl:: GetDropTarget](#getdroptarget)|Bir Rebar denetiminin `IDropTarget` arabirim işaretçisini alır.|
|[CReBarCtrl:: Gebir Dedstyle](#getextendedstyle)|Geçerli yeniden çubuk denetiminin genişletilmiş stilini alır.|
|[CReBarCtrl:: GetImageList](#getimagelist)|Bir Rebar Denetimiyle ilişkili resim listesini alır.|
|[CReBarCtrl:: GetPalette](#getpalette)|Rebar denetiminin geçerli paletini alır.|
|[CReBarCtrl:: GetRect](#getrect)|Bir Rebar denetimindeki belirli bir bant için sınırlayıcı dikdörtgeni alır.|
|[CReBarCtrl:: GetRowCount](#getrowcount)|Bir Rebar denetimindeki bant satır sayısını alır.|
|[CReBarCtrl:: GetRowHeight](#getrowheight)|Bir Rebar denetimindeki belirtilen satırın yüksekliğini alır.|
|[CReBarCtrl:: GetTextColor](#gettextcolor)|Bir çubuk çubuğu denetiminin varsayılan metin rengini alır.|
|[CReBarCtrl:: GetToolTip 'ler](#gettooltips)|Yeniden çubuk denetimiyle ilişkili herhangi bir araç ipucu denetimine tanıtıcıyı alır.|
|[CReBarCtrl:: HitTest](#hittest)|Bu noktada bir yeniden çubuk bandı varsa, bir yeniden çubuk bandın hangi kısmının ekranda verilen bir noktada olduğunu belirler.|
|[CReBarCtrl:: ıdtoindex](#idtoindex)|Bir bant tanımlayıcısını (ID) bir Rebar denetimindeki bir bant dizinine dönüştürür.|
|[CReBarCtrl:: InsertBand](#insertband)|Bir Rebar denetimine yeni bir bant ekler.|
|[CReBarCtrl:: MaximizeBand](#maximizeband)|Bir Rebar denetimindeki bir bandı en büyük boyutuna göre yeniden boyutlandırır.|
|[CReBarCtrl:: Minimmu Izeband](#minimizeband)|Rebar denetimindeki bir bandı en küçük boyutuna göre yeniden boyutlandırır.|
|[CReBarCtrl:: MoveBand](#moveband)|Bir dizinden diğerine bir bandı gider.|
|[CReBarCtrl::P Ushköşeli ayraç](#pushchevron)|Program aracılığıyla bir köşeli ayracı gönderir.|
|[CReBarCtrl:: RestoreBand](#restoreband)|Bir Rebar denetimindeki bir bandı ideal boyutuna göre yeniden boyutlandırır.|
|[CReBarCtrl:: Setbanınfo](#setbandinfo)|Bir Rebar denetimindeki mevcut bir bandın özelliklerini ayarlar.|
|[CReBarCtrl:: SetBandWidth](#setbandwidth)|Geçerli yeniden çubuk denetimindeki belirtilen sabitlenmiş bandın genişliğini ayarlar.|
|[CReBarCtrl:: Setbarınfo](#setbarinfo)|Bir Rebar denetiminin özelliklerini ayarlar.|
|[CReBarCtrl:: SetBkColor](#setbkcolor)|Bir çubuk, denetimin varsayılan arka plan rengini ayarlar.|
|[CReBarCtrl:: SetColorScheme](#setcolorscheme)|Bir Rebar denetimindeki düğmelerin renk düzenini ayarlar.|
|[CReBarCtrl:: Sebir Dedstyle](#setextendedstyle)|Geçerli Rebar denetimi için Genişletilmiş stilleri ayarlar.|
|[CReBarCtrl:: SetImageList](#setimagelist)|Bir çubuk çubuğu denetiminin resim listesini ayarlar.|
|[CReBarCtrl:: SetOwner](#setowner)|Bir Rebar denetimin sahip penceresini ayarlar.|
|[CReBarCtrl:: SetPalette](#setpalette)|Rebar denetiminin geçerli paletini ayarlar.|
|[CReBarCtrl:: SetTextColor](#settextcolor)|Bir çubuk çubuğu denetiminin varsayılan metin rengini ayarlar.|
|[CReBarCtrl:: SetToolTip 'ler](#settooltips)|Bir araç ipucu denetimini Rebar Denetimiyle ilişkilendirir.|
|[CReBarCtrl:: SetWindowTheme](#setwindowtheme)|Rebar denetiminin görsel stilini ayarlar.|
|[CReBarCtrl:: ShowBand](#showband)|Bir Rebar denetimindeki belirli bir bandı gösterir veya gizler.|
|[CReBarCtrl:: SizeToRect](#sizetorect)|Belirtilen dikdörtgende bir Rebar denetimine uyar.|

## <a name="remarks"></a>Açıklamalar

Rebar denetiminin bulunduğu uygulama, yeniden çubuk bandına yeniden çubuk denetiminin içerdiği alt pencereyi atar. Alt pencere genellikle başka bir ortak denetimdir.

Yeniden çubuk denetimleri bir veya daha fazla bant içerir. Her bant bir kavrayıcı çubuğu, bir bit eşlem, metin etiketi ve bir alt pencere birleşimini içerebilir. Bant, bu öğelerden yalnızca birini içerebilir.

Rebar denetimi, belirtilen bir arka plan bit eşlemi üzerinde alt pencere görüntüleyebilir. Tüm Rebar denetim bantları, RBBS_FIXEDSIZE stilini kullananlar hariç yeniden boyutlandırılabilir. Bir yeniden çubuk denetim bandını yeniden boyutlandırırken veya yeniden boyutlandırdıkça, Rebar denetimi bu bandın atandığı alt pencerenin boyutunu ve konumunu yönetir. Denetim içindeki bantların sırasını yeniden boyutlandırmak veya değiştirmek için bir bandın kavrayıcı çubuğunu tıklatın ve sürükleyin.

Aşağıdaki çizimde, üç bant içeren bir Rebar denetimi gösterilmektedir:

- Bant 0 düz, saydam bir araç çubuğu denetimi içeriyor.

- Bant 1 hem saydam standart hem de şeffaf açılan düğmeler içerir.

- 2\. bant, Birleşik giriş kutusu ve dört standart düğme içerir.

   ![Yeniden çubuk menüsü örneği](../../mfc/reference/media/vc4scc1.gif "Yeniden çubuk menüsü örneği")

## <a name="rebar-control"></a>Rebar denetimi

Rebar denetimleri şunları destekler:

- Görüntü listeleri.

- İleti işleme.

- Özel çizim işlevselliği.

- Standart pencere stillerine ek olarak çeşitli denetim stilleri. Bu stillerin bir listesi için, bkz. Windows SDK [Rebar Control Styles](/windows/desktop/Controls/rebar-control-styles) .

Daha fazla bilgi için bkz. [CReBarCtrl kullanma](../../mfc/using-crebarctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

##  <a name="begindrag"></a>CReBarCtrl:: BeginDrag

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_BEGINDRAG](/windows/desktop/Controls/rb-begindrag)davranışını uygular.

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Sürükle ve bırak işleminin etkileyeceği bantın sıfır tabanlı dizini.

*dwPos*<br/>
Başlangıç fare koordinatlarını içeren bir DWORD değeri. Yatay koordinat LOWORD içinde yer alır ve dikey koordinat HIWORD içinde yer alır. Eğer (DWORD)-1 ' i geçirirseniz, Rebar denetimi denetimin iş parçacığının son kez veya `GetMessage` `PeekMessage`ne zaman çağrıldığı, fare konumunu kullanır.

##  <a name="create"></a>CReBarCtrl:: Create

Yeniden çubuk denetimini oluşturur ve `CReBarCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Denetime uygulanan Rebar denetim stillerinin birleşimini belirtir. Desteklenen stillerin bir listesi için Windows SDK ' deki [yeniden çubuk denetim stillerine](/windows/desktop/Controls/rebar-control-styles) bakın.

*Rect*<br/>
Rebar denetiminin konumu ve boyutu olan bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine veya [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Rebar denetiminin üst penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi. NULL olmaması gerekir.

*NID*<br/>
Rebar denetiminin denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir Rebar denetimi oluşturun:

1. Bir`CReBarCtrl` nesne oluşturmak için [CReBarCtrl](#crebarctrl) 'i çağırın.

1. Windows Rebar denetimini oluşturan ve `CReBarCtrl` nesnesine ekleyen bu üye işlevini çağırın.

' İ çağırdığınızda `Create`ortak denetimler başlatılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

##  <a name="createex"></a>CReBarCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CReBarCtrl` nesneyle ilişkilendirir.

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
Oluşturulmakta olan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Için *dwExStyle* parametresi.

*dwStyle*<br/>
Denetime uygulanan Rebar denetim stillerinin birleşimini belirtir. Desteklenen stillerin bir listesi için, bkz. Windows SDK [yeniden çubuk denetim stilleri](/windows/desktop/Controls/rebar-control-styles) .

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

##  <a name="crebarctrl"></a>CReBarCtrl:: CReBarCtrl

Bir `CReBarCtrl` nesnesi oluşturur.

```
CReBarCtrl();
```

### <a name="example"></a>Örnek

  [CReBarCtrl:: Create](#create)örneğine bakın.

##  <a name="deleteband"></a>CReBarCtrl::D eleteBand

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_DELETEBAND](/windows/desktop/Controls/rb-deleteband)davranışını uygular.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Silinecek bandın sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bant başarıyla silinmişse sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

##  <a name="dragmove"></a>CReBarCtrl::D ragMove

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_DRAGMOVE](/windows/desktop/Controls/rb-dragmove)davranışını uygular.

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Yeni fare koordinatlarını içeren bir DWORD değeri. Yatay koordinat LOWORD içinde yer alır ve dikey koordinat HIWORD içinde yer alır. Eğer (DWORD)-1 ' i geçirirseniz, Rebar denetimi denetimin iş parçacığının son kez veya `GetMessage` `PeekMessage`ne zaman çağrıldığı, fare konumunu kullanır.

##  <a name="enddrag"></a>CReBarCtrl:: EndDrag

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_ENDDRAG](/windows/desktop/Controls/rb-enddrag)davranışını uygular.

```
void EndDrag();
```

##  <a name="getbandborders"></a>CReBarCtrl:: GetBandBorders

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETBANDBORDERS](/windows/desktop/Controls/rb-getbandborders)davranışını uygular.

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Kenarlıkların alınacağı bantın sıfır tabanlı dizini.

*PRC*<br/>
Şerit kenarlıklarını alacak bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına yönelik işaretçi. Rebar denetiminde RBS_BANDBORDERS stili varsa, bu yapının her bir üyesi, bandın karşılık gelen tarafına, kenarlığı oluşturan piksel sayısını alır. Rebar denetiminde RBS_BANDBORDERS stili yoksa, bu yapının yalnızca sol üyesi geçerli bilgileri alır. Rebar denetim stillerinin açıklaması için, bkz. Windows SDK [Rebar Control Styles](/windows/desktop/Controls/rebar-control-styles) .

##  <a name="getbandcount"></a>CReBarCtrl:: GetBandCount

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETBANDCOUNT](/windows/desktop/Controls/rb-getbandcount)davranışını uygular.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetime atanan bantların sayısı.

##  <a name="getbandinfo"></a>CReBarCtrl:: Getbanınfo

Windows SDK açıklanan Win32 ileti [RB_GETBANDINFO](/windows/desktop/Controls/rb-getbandinfo) davranışını uygular.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Bilgilerin alınacağı bantın sıfır tabanlı dizini.

*prbbi*<br/>
Bant bilgilerini almak için [Rebarbanınfo](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) yapısına yönelik bir işaretçi. Bu yapının `cbSize` üyesini olarak `sizeof(REBARBANDINFO)` ayarlamanız ve bu iletiyi göndermeden önce `fMask` üyeyi almak istediğiniz öğelere ayarlamanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="getbandmargins"></a>CReBarCtrl:: Getbandkenar boşlukları

Bandın kenar boşluklarını alır.

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>Parametreler

*Pkenar boşlukları*<br/>
Bilgileri alacak bir [kenar boşluğu](/windows/desktop/api/uxtheme/ns-uxtheme-margins)yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi [RB_GETBANDMARGINS](/windows/desktop/Controls/rb-getbandmargins) iletisinin işlevselliğine öykünür.

##  <a name="getbarheight"></a>CReBarCtrl:: GetBarHeight

Çubuk çubuğunun yüksekliğini alır.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin piksel cinsinden yüksekliğini temsil eden değer.

##  <a name="getbarinfo"></a>CReBarCtrl:: Getbarınfo

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETBARINFO](/windows/desktop/Controls/rb-getbarinfo)davranışını uygular.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>Parametreler

*prbi*<br/>
Rebar denetim bilgilerini alacak bir [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) yapısına yönelik işaretçi. Bu iletiyi göndermeden önce bu yapının *cbSize* üyesini olarak `sizeof(REBARINFO)` ayarlamanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="getbkcolor"></a>CReBarCtrl:: GetBkColor

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETBKCOLOR](/windows/desktop/Controls/rb-getbkcolor)davranışını uygular.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli varsayılan arka plan rengini temsil eden bir COLORREF değeri.

##  <a name="getcolorscheme"></a>CReBarCtrl:: GetColorScheme

Rebar denetimi için [colorscheme](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) yapısını alır.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parametreler

*lpcs*<br/>
Windows SDK bölümünde açıklandığı gibi, [colorscheme](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

`COLORSCHEME` Yapı, düğme vurgu rengini ve düğme gölge rengini içerir.

##  <a name="getdroptarget"></a>CReBarCtrl:: GetDropTarget

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETDROPTARGET](/windows/desktop/Controls/rb-getdroptarget)davranışını uygular.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Dönüş Değeri

[IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) arabirimine yönelik bir işaretçi.

##  <a name="getextendedstyle"></a>CReBarCtrl:: Gebir Dedstyle

Geçerli Rebar denetiminin genişletilmiş stillerini alır.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişletilmiş stilleri gösteren bir bit düzeyinde birleşim (veya) bayrakları. Olası bayraklar RBS_EX_SPLITTER ve RBS_EX_TRANSPARENT ' dir. Daha fazla bilgi için bkz. [CReBarCtrl:: Sedwdedstyle](#setextendedstyle) yönteminin *dwMask* parametresi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [RB_GETEXTENDEDSTYLE](/windows/desktop/Controls/rb-dragmove) iletisini gönderir.

##  <a name="getimagelist"></a>CReBarCtrl:: GetImageList

Bir Rebar Denetimiyle ilişkili nesneyialır.`CImageList`

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi. Denetim için görüntü listesi ayarlanmamışsa NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) yapısında depolanan boyut ve maske bilgilerini kullanır.

##  <a name="getpalette"></a>CReBarCtrl:: GetPalette

Rebar denetiminin geçerli paletini alır.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Dönüş Değeri

Rebar denetiminin geçerli paletini belirten bir [CPalette](../../mfc/reference/cpalette-class.md) nesnesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin bir HPALETTE yerine `CPalette` dönüş değeri olarak bir nesne kullandığını unutmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

##  <a name="getrect"></a>CReBarCtrl:: GetRect

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETRECT](/windows/desktop/Controls/rb-getrect)davranışını uygular.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Rebar denetimindeki bir bandın sıfır tabanlı dizini.

*PRC*<br/>
Yeniden çubuk bantın sınırlarını alacak bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

##  <a name="getrowcount"></a>CReBarCtrl:: GetRowCount

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETROWCOUNT](/windows/desktop/Controls/rb-getrowcount)davranışını uygular.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimdeki bant satır sayısını temsil eden bir UINT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

##  <a name="getrowheight"></a>CReBarCtrl:: GetRowHeight

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETROWHEIGHT](/windows/desktop/Controls/rb-getrowheight)davranışını uygular.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>Parametreler

*Uırow*<br/>
Bantın yüksekliğini elde edecek sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Piksel cinsinden satır yüksekliğini temsil eden bir UINT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

##  <a name="gettextcolor"></a>CReBarCtrl:: GetTextColor

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETTEXTCOLOR](/windows/desktop/Controls/rb-gettextcolor)davranışını uygular.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli varsayılan metin rengini temsil eden bir COLORREF değeri.

##  <a name="gettooltips"></a>CReBarCtrl:: GetToolTip 'ler

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_GETTOOLTIPS](/windows/desktop/Controls/rb-gettooltips)davranışını uygular.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

MFC uygulamasının `GetToolTips` bir HWND yerine bir `CToolTipCtrl`işaretçi döndürdüğünü unutmayın.

##  <a name="hittest"></a>CReBarCtrl:: HitTest

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_HITTEST](/windows/desktop/Controls/rb-hittest)davranışını uygular.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>Parametreler

*prbht*<br/>
[Rbhittestınfo](/windows/desktop/api/commctrl/ns-commctrl-_rb_hittestinfo) yapısına yönelik bir işaretçi. İletiyi göndermeden önce, `pt` bu yapının üyesi, istemci koordinatları ' nde test edilecek noktaya başlatılmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen noktadaki bantın sıfır tabanlı dizini veya noktadan sonra çubuk bandı yoksa-1.

##  <a name="idtoindex"></a>CReBarCtrl:: ıdtoindex

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_IDTOINDEX](/windows/desktop/controls/rb-idtoindex)davranışını uygular.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>Parametreler

*Ubandıd*<br/>
Bant eklendiğinde `wID` [rebarbanınfo](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) yapısının üyesine geçirilen belirtilen bandın uygulama tanımlı tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır tabanlı bant dizini veya-1 yoksa. Yinelenen bant dizinleri varsa, ilki döndürülür.

##  <a name="insertband"></a>CReBarCtrl:: InsertBand

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_INSERTBAND](/windows/desktop/Controls/rb-insertband)davranışını uygular.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parametreler

*Uıındex*<br/>
Bantın ekleneceği konumun sıfır tabanlı dizini. Bu parametreyi-1 olarak ayarlarsanız denetim, son konumdaki yeni bandı ekler.

*prbbi*<br/>
Eklenecek bandı tanımlayan [Rebarbanınfo](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) yapısına yönelik bir işaretçi. Bu işlevi çağırmadan önce bu yapının *cbSize* üyesini olarak `sizeof(REBARBANDINFO)` ayarlamanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

##  <a name="maximizeband"></a>CReBarCtrl:: MaximizeBand

Bir Rebar denetimindeki bir bandı en büyük boyutuna göre yeniden boyutlandırır.

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Üst düzeye eklenecek bandın sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Windows SDK içinde açıklandığı gibi, Win32 iletisinin [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) `fIdeal` davranışını 0 olarak ayarlanmış şekilde uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

##  <a name="minimizeband"></a>CReBarCtrl:: Minimmu Izeband

Rebar denetimindeki bir bandı en küçük boyutuna göre yeniden boyutlandırır.

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Küçültülecek bantın sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_MINIMIZEBAND](/windows/desktop/Controls/rb-minimizeband)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

##  <a name="moveband"></a>CReBarCtrl:: MoveBand

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_MOVEBAND](/windows/desktop/Controls/rb-moveband)davranışını uygular.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>Parametreler

*Uıfrom*<br/>
Taşınacak bantın sıfır tabanlı dizini.

*Tomatik*<br/>
Yeni bant konumunun sıfır tabanlı dizini. Bu parametre değeri hiçbir zamankinden önce bantların sayısından büyük olmamalıdır. Bant sayısını almak için [GetBandCount](#getbandcount)çağrısı yapın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="pushchevron"></a>CReBarCtrl::P Ushköşeli ayraç

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron)davranışını uygular.

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Köşeli ayracın gönderildiği bandın sıfır tabanlı dizini.

*lAppValue*<br/>
Uygulama tanımlı 32 bitlik bir değer. Windows SDK [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron) Içinde *lappvalue* bölümüne bakın.

##  <a name="restoreband"></a>CReBarCtrl:: RestoreBand

Bir Rebar denetimindeki bir bandı ideal boyutuna göre yeniden boyutlandırır.

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Üst düzeye eklenecek bandın sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Windows SDK ' de açıklandığı gibi, Win32 [](/windows/desktop/Controls/rb-maximizeband) iletisinin RB_MAXIMIZEBAND `fIdeal` davranışını 1 olarak ayarlanmış şekilde uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

##  <a name="setbandinfo"></a>CReBarCtrl:: Setbanınfo

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_SETBANDINFO](/windows/desktop/Controls/rb-setbandinfo)davranışını uygular.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Yeni ayarları almak için bandın sıfır tabanlı dizini.

*prbbi*<br/>
Eklenecek bandı tanımlayan [Rebarbanınfo](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) yapısına yönelik işaretçi. Bu iletiyi göndermeden önce `cbSize` bu yapının üyesini olarak `sizeof(REBARBANDINFO)` ayarlamanız gerekir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

##  <a name="setbandwidth"></a>CReBarCtrl:: SetBandWidth

Geçerli yeniden çubuk denetimindeki belirtilen sabitlenmiş bandın genişliğini ayarlar.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ubve*|'ndaki Yeniden çubuk bandın sıfır tabanlı dizini.|
|*cxWidth*|'ndaki Yeniden çubuk bantın piksel cinsinden yeni genişliği.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [RB_SETBANDWIDTH](/windows/desktop/Controls/rb-setbandwidth) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli yeniden çubuk denetimine `m_rebar`erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği her bir çubuk bandı aynı genişlik olacak şekilde ayarlar.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

##  <a name="setbarinfo"></a>CReBarCtrl:: Setbarınfo

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_SETBARINFO](/windows/desktop/Controls/rb-setbarinfo)davranışını uygular.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>Parametreler

*prbi*<br/>
Ayarlanacak bilgileri içeren bir [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) yapısına yönelik işaretçi. Bu iletiyi göndermeden önce `cbSize` bu yapının üyesini olarak `sizeof(REBARINFO)` ayarlamanız gerekir

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

##  <a name="setbkcolor"></a>CReBarCtrl:: SetBkColor

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_SETBKCOLOR](/windows/desktop/Controls/rb-setbkcolor)davranışını uygular.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*clr*<br/>
Yeni varsayılan arka plan rengini temsil eden COLORREF değeri.

### <a name="return-value"></a>Dönüş Değeri

Önceki varsayılan arka plan rengini temsil eden bir [colorref](/windows/desktop/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Arka plan renginin ne zaman ayarlanacağı ve varsayılan olarak nasıl ayarlanacağı hakkında daha fazla bilgi için bu konuya bakın.

##  <a name="setcolorscheme"></a>CReBarCtrl:: SetColorScheme

Bir Rebar denetimindeki düğmelerin renk düzenini ayarlar.

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parametreler

*lpcs*<br/>
Windows SDK bölümünde açıklandığı gibi, [colorscheme](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`COLORSCHEME` Yapı hem düğme vurgu rengini hem de düğme gölge rengini içerir.

##  <a name="setextendedstyle"></a>CReBarCtrl:: Sebir Dedstyle

Geçerli Rebar denetimi için Genişletilmiş stilleri ayarlar.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*dwMask*|'ndaki *DwStyleEx* parametresindeki hangi bayrakların uygulanacağını belirten bir bit düzeyinde BIRLEŞIM (veya) bayrakları. Aşağıdaki değerlerden birini veya daha fazlasını kullanın:<br /><br /> RBS_EX_SPLITTER: Varsayılan olarak, ayırıcıyı yatay modda ve sağ dikey modda gösterin.<br /><br /> RBS_EX_TRANSPARENT: [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) iletisini ana pencereye iletin.|
|*dwStyleEx*|'ndaki Uygulanacak stilleri belirten bir bit düzeyinde birleşim (veya). Bir stil ayarlamak için, *dwMask* parametresinde kullanılan bayrağın aynısını belirtin. Bir stili sıfırlamak için ikili sıfır değerini belirtin.|

### <a name="return-value"></a>Dönüş Değeri

Önceki Genişletilmiş Stil.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [RB_SETEXTENDEDSTYLE](/windows/desktop/Controls/rb-setextendedstyle) iletisini gönderir.

##  <a name="setimagelist"></a>CReBarCtrl:: SetImageList

Bir Rebar denetimine bir görüntü listesi atar.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Rebar denetimine Atanacak görüntü listesini içeren bir [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="setowner"></a>CReBarCtrl:: SetOwner

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_SETPARENT](/windows/desktop/Controls/rb-setparent)davranışını uygular.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Rebar denetiminin sahibi `CWnd` olarak ayarlanacak bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Rebar denetiminin geçerli sahibi olan bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin, Windows için işleyiciler yerine `CWnd` , yeniden çubuk denetiminin hem geçerli hem de seçili sahibi için nesneleri işaretçiler kullandığını unutmayın.

> [!NOTE]
>  Bu üye işlevi, Denetim oluşturulduğunda ayarlanmış olan gerçek üst öğeyi değiştirmez; Bunun yerine, belirttiğiniz pencereye bildirim iletileri gönderir.

##  <a name="setpalette"></a>CReBarCtrl:: SetPalette

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_SETPALETTE](/windows/desktop/Controls/rb-setpalette)davranışını uygular.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>Parametreler

*hPal*<br/>
Rebar denetiminin kullanacağı yeni paleti belirten bir HPALETTE.

### <a name="return-value"></a>Dönüş Değeri

Rebar denetiminin önceki paletini belirten bir [CPalette](../../mfc/reference/cpalette-class.md) nesnesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin bir HPALETTE yerine `CPalette` dönüş değeri olarak bir nesne kullandığını unutmayın.

##  <a name="settextcolor"></a>CReBarCtrl:: SetTextColor

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_SETTEXTCOLOR](/windows/desktop/Controls/rb-settextcolor)davranışını uygular.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*clr*<br/>
`CReBarCtrl` Nesnedeki yeni metin rengini temsil eden bir colorref değeri.

### <a name="return-value"></a>Dönüş Değeri

`CReBarCtrl` Nesneyle ilişkili önceki metin rengini temsil eden [colorref](/windows/desktop/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bir Rebar denetiminde metin rengi esnekliğini desteklemek için sağlanır.

##  <a name="settooltips"></a>CReBarCtrl:: SetToolTip 'ler

Bir araç ipucu denetimini bir Rebar Denetimiyle ilişkilendirir.

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) nesnesi işaretçisi

### <a name="remarks"></a>Açıklamalar

İşlem tamamlandıktan sonra `CToolTipCtrl` nesneyi yok etmeniz gerekir.

##  <a name="setwindowtheme"></a>CReBarCtrl:: SetWindowTheme

Rebar denetiminin görsel stilini ayarlar.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametreler

*Pszalt Ppname*<br/>
Ayarlanacak yeniden çubuk görsel stilini içeren bir Unicode dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi [RB_SETWINDOWTHEME](/windows/desktop/Controls/rb-setwindowtheme) iletisinin işlevselliğine öykünür.

##  <a name="showband"></a>CReBarCtrl:: ShowBand

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_SHOWBAND](/windows/desktop/Controls/rb-showband)davranışını uygular.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>Parametreler

*Ubve*<br/>
Rebar denetimindeki bir bandın sıfır tabanlı dizini.

*fShow*<br/>
Bandın gösterilmesi veya gizlenmesi gerektiğini gösterir. Bu değer TRUE ise, bant gösterilir. Aksi takdirde, bant gizli olacaktır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

##  <a name="sizetorect"></a>CReBarCtrl:: SizeToRect

Windows SDK bölümünde açıklandığı gibi Win32 iletisinin [RB_SIZETORECT](/windows/desktop/Controls/rb-sizetorect)davranışını uygular.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Rebar denetiminin boyutlandırılması gereken dikdörtgeni belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin bir `CRect` `RECT` yapı yerine bir parametre olarak bir nesne kullandığını unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
