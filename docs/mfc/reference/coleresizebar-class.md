---
title: COleResizeBar sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
ms.openlocfilehash: 0b950e7533ba6f95c76ef8d4569980a9a82ea591
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769166"
---
# <a name="coleresizebar-class"></a>COleResizeBar sınıfı

Yerleşik OLE öğelerinin yeniden boyutlandırılmasını destekleyen denetim çubuğu türü.

## <a name="syntax"></a>Sözdizimi

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleResizeBar::COleResizeBar](#coleresizebar)|Oluşturur bir `COleResizeBar` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleResizeBar::Create](#create)|Oluşturur ve bir Windows alt penceresi başlatır ve için ilişkilendirir `COleResizeBar` nesne.|

## <a name="remarks"></a>Açıklamalar

`COleResizeBar` nesneler olarak görünür bir [CRectTracker](../../mfc/reference/crecttracker-class.md) taranmış kenarlıklı ve dış yeniden boyutlandırma tutamaçları.

`COleResizeBar` nesneleri, türetilen çerçeve pencere nesneleri genellikle katıştırılmış üyeleri [Coleıpframewnd](../../mfc/reference/coleipframewnd-class.md) sınıfı.

Daha fazla bilgi için bkz [etkinleştirme](../../mfc/activation-cpp.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="coleresizebar"></a>  COleResizeBar::COleResizeBar

Oluşturur bir `COleResizeBar` nesne.

```
COleResizeBar();
```

### <a name="remarks"></a>Açıklamalar

Çağrı `Create` boyutlandırma çubuğu nesnesi oluşturulamıyor.

##  <a name="create"></a>  COleResizeBar::Create

Bir alt pencere oluşturur ve bunu ile ilişkilendirir `COleResizeBar` nesne.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Yeniden boyutlandırma çubuğunun üst penceresine yönelik işaretçi.

*dwStyle*<br/>
Belirtir [pencere stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) öznitelikleri.

*nID*<br/>
Yeniden boyutlandırma çubuğunun alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Yeniden boyutlandırma çubuğunu oluşturulduğu olursa sıfır dışı; Aksi durumda 0.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)
