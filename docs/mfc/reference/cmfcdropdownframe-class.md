---
title: CMFCDropDownFrame Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
ms.openlocfilehash: 508b27acd0a2004b1b8f75fde0bddcdf91194948
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752434"
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame Sınıfı

Açılan araç çubuklarına ve açılır araç çubuğu düğmelerine açılır çerçeve penceresi işlevselliği sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|`CMFCDropDownFrame::CMFCDropDownFrame`|Varsayılan oluşturucu.|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCDropDownFrame::Oluştur](#create)|Bir `CMFCDropDownFrame` nesnesi oluşturur.|
|`CMFCDropDownFrame::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Açılır çerçevenin üst menü çubuğunu alır.|
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Açılır çerçevenin üst açılır menüsünü alır.|
|`CMFCDropDownFrame::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Açılır çerçeveyi yeniden konumlandırın.|
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Alt açılır araç çubuğu penceresinin otomatik olarak yok edilip edilemeyeceğini ayarlar.|

### <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan kodunuzdan kullanılmak üzere tasarlanmamıştır.

Çerçeve, çerçeve davranışı `CMFCDropDownToolbar` ve `CMFCDropDownToolbarButton` sınıflara sağlamak için bu sınıfı kullanır. Bu sınıflar hakkında daha fazla bilgi için [CMFCDropDropToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) ve [CMFCDropDownToolbarButton Class'a](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCDropDownFrame` `CFrameWnd` nesneye bir nesneye bir işaretçinin nasıl alıneceğini ve alt açılır araç çubuğu penceresini otomatik olarak yok edilecek şekilde nasıl ayarlayabilirsiniz'ı gösterir.

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdropdowntoolbar.h

## <a name="cmfcdropdownframecreate"></a><a name="create"></a>CMFCDropDownFrame::Oluştur

Bir `CMFCDropDownFrame` nesnesi oluşturur.

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pWndParent*|[içinde] Açılır çerçevenin ana penceresi.|
|*X*|[içinde] Aşağı-aşağı çerçevenin konumu için yatay ekran koordinatı.|
|*Y*|[içinde] Aşağı-aşağı çerçevenin konumu için dikey ekran koordinatı.|
|*pWndOriginToolbar*|[içinde] Bu yöntemin yeni açılır çerçeve nesnesini doldurmak için kullandığı açılır düğmelere sahip araç çubuğu.|

### <a name="return-value"></a>Dönüş Değeri

Açılır çerçeve başarıyla oluşturulduysa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, WS_POPUP stili ile açılır çerçeve penceresi oluşturmak için temel [CMiniFrameWnd çağırır::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) yöntemi. Açılan çerçeve penceresi belirtilen ekran koordinatlarında görüntülenir. [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) yöntemi FALSE döndürürse bu yöntem başarısız olur.

Sınıf, `CMFCDropDownFrame` sağlanan `CMFCDropDownToolBar` parametrenin bir kopyasını oluşturur. Bu yöntem, `pWndOriginToolbar` parametreden `m_pWndOriginToolbar` veri üyesine düğme görüntülerini ve düğme durumlarını kopyalar.

## <a name="cmfcdropdownframegetparentmenubar"></a><a name="getparentmenubar"></a>CMFCDropDownFrame::GetParentMenuBar

Açılır çerçevenin üst menü çubuğunu alır.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır çerçevenin üst menü çubuğuna işaretçi veya çerçevenin üst öğesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, üst menü çubuğunu üst düğmeden alır. Açılır çerçevede üst düğme yoksa veya üst menü çubuğu yoksa bu yöntem NULL döndürür.

## <a name="cmfcdropdownframegetparentpopupmenu"></a><a name="getparentpopupmenu"></a>CMFCDropDownFrame::GetParentPopupMenu

Açılır çerçevenin üst açılır menüsünü alır.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan çerçevenin üst açılır menüsüne işaretçi veya çerçevenin üst öğesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, üst düğmeden üst menüyü alır. Açılır çerçevede üst düğme yoksa veya üst düğmede üst menü yoksa bu yöntem NULL döndürür.

## <a name="cmfcdropdownframerecalclayout"></a><a name="recalclayout"></a>CMFCDropDownFrame::RecalcLayout

Açılır çerçeveyi yeniden konumlandırın.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*bNotify*|[içinde] Kullanılma -yan.|

### <a name="remarks"></a>Açıklamalar

Açılır çerçeve oluşturulduğunda veya üst pencere yeniden boyutlandığında çerçeve bu yöntemi çağırır. Bu yöntem, üst pencerenin konumunu ve boyutunu kullanarak açılır çerçevenin konumunu ve boyutunu hesaplar.

## <a name="cmfcdropdownframesetautodestroy"></a><a name="setautodestroy"></a>CMFCDropDownFrame::SetAutoDestroy

Alt açılır araç çubuğu penceresinin otomatik olarak yok edilip edilemeyeceğini ayarlar.

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
[içinde] Ilişkili açılır araç çubuğu penceresini otomatik olarak yok etmek için TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

*bAutoDestroy* TRUE ise, `CMFCDropDownFrame` yıkıcı ilişkili açılır araç çubuğu penceresini yok eder. Varsayılan değer TRUE'dur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolToolBar Sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCDropDownToolbarButton Sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
