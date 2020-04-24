---
title: CMDITabInfo Sınıfı
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
ms.openlocfilehash: 30bf7726b35d762be2bbbd119e0303894879cd3d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752655"
---
# <a name="cmditabinfo-class"></a>CMDITabInfo Sınıfı

Sınıf, `CMDITabInfo` parametreleri [CMDIFrameWndEx::EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) yöntemine geçirmek için kullanılır. MDI sekmeli grupların davranışını denetlemek için bu sınıfın üyelerini ayarlayın.

## <a name="syntax"></a>Sözdizimi

```
class CMDITabInfo
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMDITabInfo::CMDITabInfo`|Varsayılan oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMDITabInfo::Serialize](#serialize)|Bu nesneyi arşivden veya arşivden okur veya yazar.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Etkin sekme etiketinde **Kapat** düğmesinin görüntülenip görüntülenmediğini belirtir.|
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|MDI sekmelerini renklendirip renklendirmeyeceğini belirtir.|
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Sekme grubunun açılan belgelerin listesini gösteren bir açılır menü veya kaydırma düğmelerini görüntüleyip görüntülemediğini belirtir.|
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Kullanıcının sekme konumlarını sürükleyerek değiştirip değiştiremeyeceğini belirtir.|
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Sekmelerin düz bir çerçevesi olup olmadığını belirtir.|
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Her sekme etiketinin **Kapat** düğmesi gösterip görüntülemediğini belirtir.|
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Özel araç ipuçlarının etkin olup olmadığını belirtir.|
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|MDI sekmelerinde simgelerin gösterip göstermeyeceğini belirtir.|
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Her sekme penceresinin kenarlık boyutunu belirtir.|
|[CMDITabInfo::m_style](#m_style)|Sekme etiketlerinin stilini belirtir.|
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Sekme etiketlerinin sayfanın üst veya alt kısmında bulunup bulunmadığı belirtilir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, çerçevenin oluşturduğu MDI sekmesi gruplarının parametrelerini belirtir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMDITabInfo` sınıftaki çeşitli üye değişkenlerin değerlerinin nasıl ayarlandığını göstermektedir.

[!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmdiclientareawnd.h

## <a name="cmditabinfom_bactivetabclosebutton"></a><a name="m_bactivetabclosebutton_"></a>CMDITabInfo::m_bActiveTabCloseButton;

Etkin sekme etiketinde **Kapat** düğmesinin görüntülenip görüntülenmediğini belirtir.

```
BOOL m_bActiveTabCloseButton;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, etkin sekme etiketi bir **Kapat** düğmesi görüntüler. **Kapat** düğmesi sekme alanının sağ üst köşesinden kaldırılır. Aksi takdirde, etkin sekme etiketi **kapat** düğmesi görüntülemez. **Sekme** alanının sağ üst köşesinde Kapat düğmesi görünür.

## <a name="cmditabinfom_bautocolor"></a><a name="m_bautocolor"></a>CMDITabInfo::m_bAutoColor

Her MDI sekmesinin kendi rengi olup olmadığını belirtir.

```
BOOL m_bAutoColor;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, her sekme kendi renk olacaktır. Renk kümesi MFC kitaplığı tarafından yönetilir. Aksi takdirde, sekmeler beyaz olarak görüntülenir. Varsayılan değer FALSE'dur.

## <a name="cmditabinfom_bdocumentmenu"></a><a name="m_bdocumentmenu"></a>CMDITabInfo::m_bDocumentMenu

Her sekmenin, sekme alanının sağ kenarında açılan belgelerin listesini gösteren bir açılır menü gösterip göstermediğini belirtir.

```
BOOL m_bDocumentMenu;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, her sekme windows sekme alanının sağ kenarında açılan belgelerin listesini gösteren bir açılır menü görüntüler; Aksi takdirde, sekme penceresi sekme alanının sağ kenarında kaydırma düğmelerini görüntüler. Varsayılan değer FALSE'dur.

## <a name="cmditabinfom_benabletabswap"></a><a name="m_benabletabswap"></a>CMDITabInfo::m_bEnableTabSwap

Kullanıcının sekme konumlarını sürükleyerek değiştirip değiştiremeyeceğini belirtir.

```
BOOL m_bEnableTabSwap;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, kullanıcı sekmeleri sürükleyerek sekme konumlarını değiştirebilir. Aksi takdirde, kullanıcı sekme konumlarını değiştiremez. Varsayılan değer TRUE'dur.

## <a name="cmditabinfom_bflatframe"></a><a name="m_bflatframe"></a>CMDITabInfo::m_bFlatFrame

Her sekme penceresinin düz bir çerçevesi olup olmadığını belirtir.

```
BOOL m_bFlatFrame;
```

## <a name="cmditabinfom_btabclosebutton"></a><a name="m_btabclosebutton"></a>CMDITabInfo::m_bTabCloseButton

Her sekme penceresinin **Kapat** düğmesini gösterip görüntülemediğini belirtir.

```
BOOL m_bTabCloseButton;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, her sekme penceresi sekmenin sağ **kenarındaki** **Close** Kapat düğmesini görüntüler. Varsayılan değer TRUE'dur.

## <a name="cmditabinfom_btabcustomtooltips"></a><a name="m_btabcustomtooltips"></a>CMDITabInfo::m_bTabCustomTooltips

Sekmelerin araç uçlarını gösterip göstermediğini belirtir.

```
BOOL m_bTabCustomTooltips;
```

### <a name="remarks"></a>Açıklamalar

DOĞRUysa, uygulama ana çerçeveye AFX_WM_ON_GET_TAB_TOOLTIP bir ileti gönderir. Bu iletiyi ON_REGISTERED_MESSAGE makroyu kullanarak işleyebilirsiniz.

## <a name="cmditabinfom_btabicons"></a><a name="m_btabicons"></a>CMDITabInfo::m_bTabIcons

MDI sekmelerinde simgelerin gösterip göstermeyeceğini belirtir.

```
BOOL m_bTabIcons;
```

### <a name="remarks"></a>Açıklamalar

TRUE ise, simgeler her MDI sekmesinde görüntülenir. Aksi takdirde, sekmelerde simgeler görüntülenmez. Varsayılan değer FALSE'dur.

## <a name="cmditabinfom_ntabbordersize"></a><a name="m_ntabbordersize"></a>CMDITabInfo::m_nTabBorderSize

Her sekme penceresinin kenarlık boyutunu piksel olarak belirtir.

```
int m_nTabBorderSize;
```

### <a name="remarks"></a>Açıklamalar

[CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) varsayılan değeri döndürür.

## <a name="cmditabinfom_style"></a><a name="m_style"></a>CMDITabInfo::m_style

Sekme etiketlerinin stilini belirtir.

```
CMFCTabCtrl::Style m_style
```

### <a name="remarks"></a>Açıklamalar

Sekme etiketleri için aşağıdaki stillerden birini belirtin:

|||
|-|-|
|STYLE_3D|3D tarzı.  |
|STYLE_3D_ONENOTE|Microsoft OneNote stili.  |
|STYLE_3D_VS2005|Microsoft Visual Studio 2005 tarzı.  |
|STYLE_3D_SCROLLED|Dikdörtgen sekmesi etiketleri ile 3B stil.  |
|STYLE_FLAT_SHARED_HORZ_SCROLL|Paylaşılan yatay kaydırma çubuğuna sahip düz stil.  |
|STYLE_3D_ROUNDED_SCROLL|Yuvarlak sekme etiketleri ile 3B stil.  |

## <a name="cmditabinfom_tablocation"></a><a name="m_tablocation"></a>CMDITabInfo::m_tabLocation

Sekme etiketlerinin sayfanın üst veya alt kısmında bulunup bulunmadığı belirtilir.

```
CMFCTabCtrl::Location m_tabLocation;
```

### <a name="remarks"></a>Açıklamalar

Sekmelere aşağıdaki konum bayraklarından birini uygulayın:

- LOCATION_BOTTOM: sekme etiketleri sayfanın alt kısmında yer alır.

- LOCATION_TOP: sekme etiketleri sayfanın üst kısmında yer alır

## <a name="cmditabinfoserialize"></a><a name="serialize"></a>CMDITabInfo::Serialize

Bu nesneyi bir arşivden veya arşivden okur veya yazar.

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
[içinde] Serihale getirmek için [carchive sınıfı](../../mfc/reference/carchive-class.md) nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[CMDIFrameWndEx Sınıfı](../../mfc/reference/cmdiframewndex-class.md)<br/>
[MDI Sekmeli Gruplar](../../mfc/mdi-tabbed-groups.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
