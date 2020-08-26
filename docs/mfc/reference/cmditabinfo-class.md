---
title: CMDITabInfo sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
ms.openlocfilehash: 8e4053bf16672d693adc104c9e88bb46a67ba7dd
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845919"
---
# <a name="cmditabinfo-class"></a>CMDITabInfo sınıfı

`CMDITabInfo`Sınıfı, parametreleri [Cmdiframewndex:: Enabhadıtabbedgroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) metoduna geçirmek için kullanılır. MDI sekmeli gruplarının davranışını denetlemek için bu sınıfın üyelerini ayarlayın.

## <a name="syntax"></a>Syntax

```
class CMDITabInfo
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMDITabInfo::CMDITabInfo`|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMDITabInfo:: serileştirme](#serialize)|Bu nesneyi veya bir arşivden okur veya yazar.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMDITabInfo:: m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Etkin sekmenin etiketinde bir **Kapat** düğmesinin görüntülenip görüntülenmeyeceğini belirtir.|
|[CMDITabInfo:: m_bAutoColor](#m_bautocolor)|MDI sekmelerinin renkedilip edilmeyeceğini belirtir.|
|[CMDITabInfo:: m_bDocumentMenu](#m_bdocumentmenu)|Sekme grubunun açık belgelerin listesini gösteren bir açılan menü görüntüleyip görüntülemediğini veya kaydırma düğmelerinin görüntülenip görüntülenmeyeceğini belirtir.|
|[CMDITabInfo:: m_bEnableTabSwap](#m_benabletabswap)|Kullanıcının sürükleyerek sekmelerin konumlarını takas edebilir olup olmayacağını belirtir.|
|[CMDITabInfo:: m_bFlatFrame](#m_bflatframe)|Sekmelerin düz bir çerçeveye sahip olup olmadığını belirtir.|
|[CMDITabInfo:: m_bTabCloseButton](#m_btabclosebutton)|Her sekme etiketinin bir **Kapat** düğmesi görüntüleyip görüntülemediğini belirtir.|
|[CMDITabInfo:: m_bTabCustomTooltips](#m_btabcustomtooltips)|Özel araç ipuçlarının etkinleştirilip etkinleştirilmeyeceğini belirtir.|
|[CMDITabInfo:: m_bTabIcons](#m_btabicons)|MDI sekmelerinde simgelerin görüntülenip görüntülenmeyeceğini belirtir.|
|[CMDITabInfo:: m_nTabBorderSize](#m_ntabbordersize)|Her sekme penceresinin kenarlık boyutunu belirtir.|
|[CMDITabInfo:: m_style](#m_style)|Sekme etiketlerinin stilini belirtir.|
|[CMDITabInfo:: m_tabLocation](#m_tablocation)|Sekmeler etiketlerinin sayfanın üstünde mi yoksa altında mı olduğunu belirtir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, Framework 'ün oluşturduğu MDI sekme gruplarının parametrelerini belirtir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, sınıfındaki çeşitli üye değişkenlerinin değerlerinin nasıl ayarlanacağı gösterilmektedir `CMDITabInfo` .

[!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmdiclientareawnd. h

## <a name="cmditabinfom_bactivetabclosebutton"></a><a name="m_bactivetabclosebutton_"></a> CMDITabInfo:: m_bActiveTabCloseButton;

Etkin sekmenin etiketinde bir **Kapat** düğmesinin görüntülenip görüntülenmeyeceğini belirtir.

```
BOOL m_bActiveTabCloseButton;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise etkin sekmenin etiketi bir **Kapat** düğmesi görüntüler. **Kapat** düğmesi sekme alanının sağ üst köşesinden kaldırılacak. Aksi halde, etkin sekmenin etiketi bir **Kapat** düğmesi görüntülemez. **Kapat** düğmesi sekme alanının sağ üst köşesinde görüntülenir.

## <a name="cmditabinfom_bautocolor"></a><a name="m_bautocolor"></a> CMDITabInfo:: m_bAutoColor

Her MDI sekmesinin kendi rengine sahip olup olmadığını belirtir.

```
BOOL m_bAutoColor;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, her sekme kendi rengine sahip olur. Renk kümesi MFC kitaplığı tarafından yönetilir. Aksi halde, sekmeler beyaz görüntülenir. Varsayılan değer FALSE 'dur.

## <a name="cmditabinfom_bdocumentmenu"></a><a name="m_bdocumentmenu"></a> CMDITabInfo:: m_bDocumentMenu

Her sekmenin, sekme alanının sağ kenarında açık belgelerin bir listesini gösteren bir açılan menü görüntüleyip görüntülemediğini belirtir.

```
BOOL m_bDocumentMenu;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, her sekme penceresi, sekme alanının sağ kenarında açık belgelerin bir listesini gösteren bir açılan menü görüntüler. Aksi halde sekme penceresi, sekme alanının sağ kenarında bulunan kaydırma düğmelerini görüntüler. Varsayılan değer FALSE 'dur.

## <a name="cmditabinfom_benabletabswap"></a><a name="m_benabletabswap"></a> CMDITabInfo:: m_bEnableTabSwap

Kullanıcının sürükleyerek sekmelerin konumlarını takas edebilir olup olmayacağını belirtir.

```
BOOL m_bEnableTabSwap;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, Kullanıcı sekmeleri sürükleyerek sekmeler konumlarını değiştirebilir. Aksi takdirde, Kullanıcı sekmelerin konumunu değiştiremez. Varsayılan değer TRUE 'dur.

## <a name="cmditabinfom_bflatframe"></a><a name="m_bflatframe"></a> CMDITabInfo:: m_bFlatFrame

Her sekme penceresinin düz bir çerçeveye sahip olup olmadığını belirtir.

```
BOOL m_bFlatFrame;
```

## <a name="cmditabinfom_btabclosebutton"></a><a name="m_btabclosebutton"></a> CMDITabInfo:: m_bTabCloseButton

Her sekme penceresinin bir **Kapat** düğmesi görüntüleyip görüntülemediğini belirtir.

```
BOOL m_bTabCloseButton;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, her sekme penceresinde sekmenin sağ kenarındaki **Close** düğmesi görüntülenir. Aksi halde **Kapat** düğmesi görüntülenmez. Varsayılan değer TRUE 'dur.

## <a name="cmditabinfom_btabcustomtooltips"></a><a name="m_btabcustomtooltips"></a> CMDITabInfo:: m_bTabCustomTooltips

Sekmelerin araç ipuçlarını görüntüleyip görüntülememeyeceğini belirtir.

```
BOOL m_bTabCustomTooltips;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, uygulama ana çerçeveye bir AFX_WM_ON_GET_TAB_TOOLTIP iletisi gönderir. Bu iletiyi ON_REGISTERED_MESSAGE makrosunu kullanarak işleyebilirsiniz.

## <a name="cmditabinfom_btabicons"></a><a name="m_btabicons"></a> CMDITabInfo:: m_bTabIcons

MDI sekmelerinde simgelerin görüntülenip görüntülenmeyeceğini belirtir.

```
BOOL m_bTabIcons;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, her MDI sekmesinde simgeler görüntülenir. Aksi halde, simgeler sekmeler üzerinde görüntülenmez. Varsayılan değer FALSE 'dur.

## <a name="cmditabinfom_ntabbordersize"></a><a name="m_ntabbordersize"></a> CMDITabInfo:: m_nTabBorderSize

Her sekme penceresinin kenarlık boyutunu piksel cinsinden belirtir.

```
int m_nTabBorderSize;
```

### <a name="remarks"></a>Açıklamalar

[CMFCVisualManager:: GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) varsayılan değeri döndürür.

## <a name="cmditabinfom_style"></a><a name="m_style"></a> CMDITabInfo:: m_style

Sekme etiketlerinin stilini belirtir.

```
CMFCTabCtrl::Style m_style
```

### <a name="remarks"></a>Açıklamalar

Sekme etiketleri için aşağıdaki stillerden birini belirtin:

|Makroya|Açıklama|
|-|-|
|STYLE_3D|3B stili.  |
|STYLE_3D_ONENOTE|Microsoft OneNote stili.  |
|STYLE_3D_VS2005|Microsoft Visual Studio 2005 stili.  |
|STYLE_3D_SCROLLED|dikdörtgen sekme etiketleriyle 3B stili.  |
|STYLE_FLAT_SHARED_HORZ_SCROLL|Paylaşılan yatay kaydırma çubuğu ile düz stil.  |
|STYLE_3D_ROUNDED_SCROLL|yuvarlak sekme etiketleriyle 3B stili.  |

## <a name="cmditabinfom_tablocation"></a><a name="m_tablocation"></a> CMDITabInfo:: m_tabLocation

Sekmeler etiketlerinin sayfanın üstünde mi yoksa altında mı olduğunu belirtir.

```
CMFCTabCtrl::Location m_tabLocation;
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki konum bayraklarından birini sekmeler için geçerlidir:

- LOCATION_BOTTOM: sekmeler etiketleri sayfanın alt kısmında bulunur.

- LOCATION_TOP: sekmeler etiketleri sayfanın en üstünde bulunur

## <a name="cmditabinfoserialize"></a><a name="serialize"></a> CMDITabInfo:: serileştirme

Bu nesneyi bir arşivden veya bir arşive okur veya yazar.

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
'ndaki Seri hale getirilecek bir [CArchive sınıfı](../../mfc/reference/carchive-class.md) nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[CMDIFrameWndEx sınıfı](../../mfc/reference/cmdiframewndex-class.md)<br/>
[MDI sekmeli grupları](../../mfc/mdi-tabbed-groups.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
