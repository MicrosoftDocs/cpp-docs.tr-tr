---
title: CReBar Class
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: 5a87f70816e9342c7aa203a53d13699659cebb28
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767268"
---
# <a name="crebar-class"></a>CReBar Class

Düzen, süreklilik ve çubuk barınağı denetimleri için durum bilgileri sağlayan denetim çubuğu.

## <a name="syntax"></a>Sözdizimi

```
class CReBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CReBar::AddBar](#addbar)|Bir bant için bir çubuk barınağı ekler.|
|[CReBar::Create](#create)|Çubuk barınağı denetimi oluşturur ve ona ekler `CReBar` nesne.|
|[CReBar::GetReBarCtrl](#getrebarctrl)|Temel alınan bir ortak denetimi doğrudan erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Bir rebar nesnesi çeşitli alt pencereleri düzenleme kutuları, araç çubukları ve liste kutuları gibi genellikle diğer denetimleri içerebilir. Bir rebar nesneyi kendi alt pencereleri belirtilen bir bit eşlem görüntüleyebilirsiniz. Uygulamanızı çubuk barınağı otomatik olarak yeniden boyutlandırmak veya tıklayarak veya kavrayıcı çubuğunu sürüklerken kullanıcı el ile çubuk barınağı boyutlandırabilirsiniz.

![RebarMenu örneği](../../mfc/reference/media/vc4sc61.gif "RebarMenu örneği")

## <a name="rebar-control"></a>Rebar denetimi

Bir rebar nesnesi bir araç çubuğu nesnesi için benzer şekilde davranır. Bir rebar kendi bantları yeniden boyutlandırmak için tıklatın ve sürükleyin mekanizması kullanır. Rebar denetimiyle, her bant bir Mandal çubuğu, bir bit eşlem, bir metin etiketi ve alt pencere herhangi bir birleşimini sahip olan bir veya daha fazla bant içerebilir. Ancak, bantlar birden fazla alt penceresi içeremez.

`CReBar` kullanan [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) sınıfı, bir uygulama sağlamak için. Çubuk barınağı denetim aracılığıyla erişebileceğiniz [GetReBarCtrl](#getrebarctrl) denetimin özelleştirme seçenekleri yararlanmak için. Çubuk barınağı denetimleri hakkında daha fazla bilgi için bkz: `CReBarCtrl`. Çubuk barınağı denetimleri kullanma hakkında daha fazla bilgi için bkz. [kullanarak CReBarCtrl](../../mfc/using-crebarctrl.md).

> [!CAUTION]
>  Çubuk barınağı ve çubuk barınağı denetimi nesnelerini MFC denetim çubuğu yerleştirme desteklemez. Varsa `CRebar::EnableDocking` , uygulamanızın iddia çağrılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="addbar"></a>  CReBar::AddBar

Çubuk barınağı için bir bant eklemek için bu üye işlevini çağırın.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
Bir işaretçi bir `CWnd` alt pencerenin çubuk barınağı eklenecek nesne. Başvurulan nesnenin bir WS_CHILD olması gerekir.

*lpszText*<br/>
Çubuk barınağı görüntülenecek metni içeren bir dize işaretçisi. Varsayılan olarak null değerini DÖNDÜRÜR. Bulunan metin *lpszText* alt penceresi; bir parçası değil rebar üzerinde olduğu.

*pbmp*<br/>
Bir işaretçi bir `CBitmap` çubuk barınağı arka plan üzerinde görüntülenecek nesne. Varsayılan olarak null değerini DÖNDÜRÜR.

*dwStyle*<br/>
Çubuk barınağı için uygulanacak içeren stil DWORD. Bkz: `fStyle` işlev açıklama Win32 yapısında [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) bant stilleri tam listesi için.

*clrFore*<br/>
Çubuk barınağı ön plan rengi temsil eden bir COLORREF değer.

*clrBack*<br/>
Çubuk barınağı arka plan rengi temsil eden bir COLORREF değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

##  <a name="create"></a>  CReBar::Create

Bir rebar oluşturmak için bu üye işlevini çağırın.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
İşaretçi `CWnd` olan Windows penceresi durum çubuğunun üst nesne. Normalde, çerçeve penceresi.

*dwCtrlStyle*<br/>
Çubuk barınağı denetim stili. Varsayılan olarak, bitişik bantları çubuk barınağı denetimi içinde ayrı çizgilerle görüntüleyen RBS_BANDBORDERS. Bkz: [Rebar denetim stilleri](/windows/desktop/Controls/rebar-control-styles) stilleri bir listesi için Windows SDK.

*dwStyle*<br/>
Çubuk barınağı pencere stilleri.

*nID*<br/>
Barınağının alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [CReBar::AddBar](#addbar).

##  <a name="getrebarctrl"></a>  CReBar::GetReBarCtrl

Bu üye işlevi, temel alınan bir ortak denetimi doğrudan erişim sağlar.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru bir [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Çubuk barınağı özelleştirmede Windows çubuk barınağı ortak denetimi işlevlerini yararlanmak için bu üye işlevini çağırın. Çağırdığınızda `GetReBarCtrl`, bir başvuru nesneye döndürür `CReBarCtrl` ayarlayın ya da üye işlevleri kullanabilmeniz için nesne.

Kullanma hakkında daha fazla bilgi için `CReBarCtrl` , çubuk barınağı özelleştirmek için bkz: [kullanarak CReBarCtrl](../../mfc/using-crebarctrl.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
