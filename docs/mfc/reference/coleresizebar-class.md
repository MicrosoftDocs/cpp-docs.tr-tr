---
description: 'Daha fazla bilgi edinin: COleResizeBar Class'
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
ms.openlocfilehash: bdd97e854257e2f858b52ed45f4066b26c71394d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226720"
---
# <a name="coleresizebar-class"></a>COleResizeBar sınıfı

Yerinde OLE öğelerinin yeniden boyutlandırılmasını destekleyen bir denetim çubuğu türü.

## <a name="syntax"></a>Syntax

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleResizeBar::COleResizeBar](#coleresizebar)|Bir `COleResizeBar` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleResizeBar:: Create](#create)|Windows alt penceresi oluşturup başlatır ve `COleResizeBar` nesnesiyle ilişkilendirir.|

## <a name="remarks"></a>Açıklamalar

`COleResizeBar` nesneler, taranmış bir kenarlık ve dış yeniden boyutlandırma tutamaçlarıyla bir [CRectTracker](../../mfc/reference/crecttracker-class.md) olarak görünür.

`COleResizeBar` nesneler, genellikle [Coleipframewnd](../../mfc/reference/coleipframewnd-class.md) sınıfından türetilmiş çerçeve pencere nesnelerinin katıştırılmış üyeleridir.

Daha fazla bilgi için [etkinleştirme](../../mfc/activation-cpp.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="coleresizebarcoleresizebar"></a><a name="coleresizebar"></a> COleResizeBar::COleResizeBar

Bir `COleResizeBar` nesnesi oluşturur.

```
COleResizeBar();
```

### <a name="remarks"></a>Açıklamalar

`Create`Yeniden boyutlandırma çubuğu nesnesini oluşturmak için çağırın.

## <a name="coleresizebarcreate"></a><a name="create"></a> COleResizeBar:: Create

Bir alt pencere oluşturur ve `COleResizeBar` nesnesiyle ilişkilendirir.

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
[Pencere stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) özniteliklerini belirtir.

*NID*<br/>
Yeniden boyutlandırma çubuğunun alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Yeniden boyutlandırma çubuğu oluşturulduysa sıfır dışı; Aksi takdirde 0.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek üst PANELI](../../overview/visual-cpp-samples.md)<br/>
[CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cotaserverdoc sınıfı](../../mfc/reference/coleserverdoc-class.md)
