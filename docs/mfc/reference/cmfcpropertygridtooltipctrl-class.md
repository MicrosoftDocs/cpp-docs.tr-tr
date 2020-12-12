---
description: 'Daha fazla bilgi edinin: CMFCPropertyGridToolTipCtrl sınıfı'
title: CMFCPropertyGridToolTipCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
ms.openlocfilehash: 5e560d09756be99c00257c351b58223b37a6b5da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289887"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl sınıfı

[CMFCPropertyGridCtrl sınıfının](../../mfc/reference/cmfcpropertygridctrl-class.md) araç ipuçlarını göstermek için kullandığı bir araç ipucu denetimi uygular.

## <a name="syntax"></a>Syntax

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|[CMFCPropertyGridToolTipCtrl:: CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Bir `CMFCPropertyGridToolTipCtrl` nesnesi oluşturur.|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCPropertyGridToolTipCtrl:: Create](#create)|Araç ipucu denetimi için bir pencere oluşturur.|
|[CMFCPropertyGridToolTipCtrl::D eactivate](#deactivate)|Araç ipucu denetimini devre dışı bırakır ve gizler.|
|[CMFCPropertyGridToolTipCtrl:: GetLastRect](#getlastrect)|Araç ipucu denetiminin son konumunun koordinatlarını döndürür.|
|[CMFCPropertyGridToolTipCtrl:: Hide](#hide)|Araç ipucu denetimini gizler.|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini dönüştürmek için [CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı tarafından kullanılır. ( [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)geçersiz kılar.)|
|[CMFCPropertyGridToolTipCtrl:: SetTextMargin](#settextmargin)|Araç ipucu metni ve araç ipucu penceresinin kenarlığı arasındaki boşluğu ayarlar.|
|[CMFCPropertyGridToolTipCtrl:: Track](#track)|Araç ipucu denetimini görüntüler.|

## <a name="remarks"></a>Açıklamalar

İpucu, işaretçi bir özellik adının üzerine geldiğinde görüntülenir. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) sınıfı, Kullanıcı tarafından kolayca okunabilmesi için bir araç ipucu görüntüler. Genellikle, bir araç ipucunun konumu işaretçinin konumuyla belirlenir. Bu sınıfı kullanarak araç ipucu, özellik adının üzerinde görünür ve doğal özellik uzantısına benzer, böylece Özellik adı tamamen görünür olur.

MFC bu denetimi otomatik olarak oluşturur ve [CMFCPropertyGridCtrl sınıfında](../../mfc/reference/cmfcpropertygridctrl-class.md)kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu `CMFCPropertyGridToolTipCtrl` ve araç ipucu denetiminin nasıl görüntüleneceğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertygridtooltipctrl. h

## <a name="cmfcpropertygridtooltipctrlcmfcpropertygridtooltipctrl"></a><a name="cmfcpropertygridtooltipctrl"></a> CMFCPropertyGridToolTipCtrl:: CMFCPropertyGridToolTipCtrl

Bir `CMFCPropertyGridToolTipCtrl` nesnesi oluşturur.

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

## <a name="cmfcpropertygridtooltipctrlcreate"></a><a name="create"></a> CMFCPropertyGridToolTipCtrl:: Create

Araç ipucu denetimi için bir pencere oluşturur.

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Ana pencereye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla oluşturulduysa doğru; Aksi takdirde, FALSE.

## <a name="cmfcpropertygridtooltipctrldeactivate"></a><a name="deactivate"></a> CMFCPropertyGridToolTipCtrl::D eactivate

Araç ipucu denetimini devre dışı bırakır ve gizler.

```cpp
void Deactivate();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, son konumu ve metni boş değerlere ayarlar, böylece gelecekteki [CMFCPropertyGridToolTipCtrl:: Track](#track) çağrısı araç ipucunu görüntüler.

## <a name="cmfcpropertygridtooltipctrlgetlastrect"></a><a name="getlastrect"></a> CMFCPropertyGridToolTipCtrl:: GetLastRect

Araç ipucu denetiminin son konumunun koordinatlarını döndürür.

```cpp
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
dışı Araç ipucu denetiminin son konumunu içerir.

## <a name="cmfcpropertygridtooltipctrlhide"></a><a name="hide"></a> CMFCPropertyGridToolTipCtrl:: Hide

Araç ipucu denetimini gizler.

```cpp
void Hide();
```

## <a name="cmfcpropertygridtooltipctrlsettextmargin"></a><a name="settextmargin"></a> CMFCPropertyGridToolTipCtrl:: SetTextMargin

Araç ipucu metni ve araç ipucu penceresinin kenarlığı arasındaki boşluğu ayarlar.

```cpp
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>Parametreler

*nTextMargin*<br/>
'ndaki Araç İpucu denetim metni ve araç ipucu penceresinin kenarlığı arasındaki boşluğu belirtir. Varsayılan değer 10 pikseldir.

## <a name="cmfcpropertygridtooltipctrltrack"></a><a name="track"></a> CMFCPropertyGridToolTipCtrl:: Track

Araç ipucu denetimini görüntüler.

```cpp
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
'ndaki Araç ipucu denetiminin konumunu ve boyutunu belirtir.

*strText*<br/>
'ndaki Araç ipucunda gösterilecek metni belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *Rect* tarafından belirtilen konumda ve boyutta araç ipucu denetimini görüntüler. Bu yöntemin en son çağrılmasından bu yana konum, boyut ve metin değiştirilmediyseniz, bu yöntemin hiçbir etkisi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
