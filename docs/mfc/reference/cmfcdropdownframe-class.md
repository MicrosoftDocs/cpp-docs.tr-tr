---
title: CMFCDropDownFrame sınıfı
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
ms.openlocfilehash: d99dae9d8e7eca96c736a33621f0b544f1962f0f
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560900"
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame sınıfı

Açılan araç çubukları ve açılan araç çubuğu düğmelerine açılan çerçeve pencere işlevleri sağlar.

## <a name="syntax"></a>Syntax

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|`CMFCDropDownFrame::CMFCDropDownFrame`|Varsayılan Oluşturucu.|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCDropDownFrame:: Create](#create)|Bir `CMFCDropDownFrame` nesnesi oluşturur.|
|`CMFCDropDownFrame::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCDropDownFrame:: GetParentMenuBar](#getparentmenubar)|Açılan çerçevenin ana menü çubuğunu alır.|
|[CMFCDropDownFrame:: GetParentPopupMenu](#getparentpopupmenu)|Açılan çerçevenin üst açılır menüsünü alır.|
|`CMFCDropDownFrame::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCDropDownFrame:: RecalcLayout](#recalclayout)|Açılan çerçeveyi konumlandırır.|
|[CMFCDropDownFrame:: SetAutoDestroy](#setautodestroy)|Alt açılan araç çubuğu penceresinin otomatik olarak yok edildiğini ayarlar.|

### <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan kodunuzdan kullanılmaya yönelik değildir.

Framework, ve sınıflarına çerçeve davranışı sağlamak için bu sınıfı kullanır `CMFCDropDownToolbar` `CMFCDropDownToolbarButton` . Bu sınıflar hakkında daha fazla bilgi için bkz. [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md) ve [CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir sınıftan bir nesnenin bir işaretçisinin nasıl alınacağını `CMFCDropDownFrame` `CFrameWnd` ve alt açılan araç çubuğu penceresinin otomatik olarak yok edilmesi için nasıl ayarlanacağını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdropdowntoolbar. h

## <a name="cmfcdropdownframecreate"></a><a name="create"></a> CMFCDropDownFrame:: Create

Bir `CMFCDropDownFrame` nesnesi oluşturur.

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>Parametreler

*pWndParent*\
'ndaki Açılan çerçevenin üst penceresi.

*sayı*\
'ndaki Aşağı açılan çerçevenin konumu için yatay ekran koordinatı.

*Iz*\
'ndaki Aşağı açılan çerçevenin konumu için dikey ekran koordinatı.

*pWndOriginToolbar*\
'ndaki Bu yöntemin yeni açılan çerçeve nesnesini doldurmak için kullandığı açılan düğmeleri içeren araç çubuğu.

### <a name="return-value"></a>Dönüş Değeri

Açılan çerçeve başarıyla oluşturulduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, WS_POPUP stiliyle açılan çerçeve penceresini oluşturmak için Base [CMiniFrameWnd:: CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) yöntemini çağırır. Açılan çerçeve penceresi, belirtilen ekran koordinatlarına göre görünür. [CMiniFrameWnd:: CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) yöntemi false döndürürse bu yöntem başarısız olur.

`CMFCDropDownFrame`Sınıfı, belirtilen parametrenin bir kopyasını oluşturur `CMFCDropDownToolBar` . Bu yöntem, düğme görüntülerini ve düğme durumlarını `pWndOriginToolbar` parametresinden `m_pWndOriginToolbar` veri üyesine kopyalar.

## <a name="cmfcdropdownframegetparentmenubar"></a><a name="getparentmenubar"></a> CMFCDropDownFrame:: GetParentMenuBar

Açılan çerçevenin ana menü çubuğunu alır.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır çerçevenin üst menü çubuğuna bir işaretçi veya çerçevenin üst öğesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem üst düğmeden ana menü çubuğunu alır. Bu yöntem, açılan karenin üst düğmesi yoksa veya üst düğmenin üst menü çubuğu yoksa NULL değerini döndürür.

## <a name="cmfcdropdownframegetparentpopupmenu"></a><a name="getparentpopupmenu"></a> CMFCDropDownFrame:: GetParentPopupMenu

Açılan çerçevenin üst açılır menüsünü alır.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır çerçevenin üst açılan menüsüne yönelik bir işaretçi veya çerçevenin üst öğesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem üst menüyü ana düğmeden alır. Bu yöntem, açılan çerçevede üst düğme yoksa veya üst düğmenin üst menü yoksa, NULL değerini döndürür.

## <a name="cmfcdropdownframerecalclayout"></a><a name="recalclayout"></a> CMFCDropDownFrame:: RecalcLayout

Açılan çerçeveyi konumlandırır.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

*bNotify*\
'ndaki Kullanılmayan.

### <a name="remarks"></a>Açıklamalar

Çerçeve, açılan çerçeve oluşturulduğunda veya üst pencere yeniden boyutlandırılırken bu yöntemi çağırır. Bu yöntem, ana pencerenin konumunu ve boyutunu kullanarak açılan çerçevenin konumunu ve boyutunu hesaplar.

## <a name="cmfcdropdownframesetautodestroy"></a><a name="setautodestroy"></a> CMFCDropDownFrame:: SetAutoDestroy

Alt açılan araç çubuğu penceresinin otomatik olarak yok edildiğini ayarlar.

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
'ndaki İlişkili açılan araç çubuğu penceresini otomatik olarak yok etmek için TRUE. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

*BAutoDestroy* değeri true ise, `CMFCDropDownFrame` yıkıcı ilişkili açılan araç çubuğu penceresini yok eder. Varsayılan değer TRUE 'dur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
