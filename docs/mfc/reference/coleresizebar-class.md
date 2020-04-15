---
title: COleResizeBar Sınıfı
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
ms.openlocfilehash: beb0c37b6ac23310b7d5c8506fbdaf677dd74d8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376147"
---
# <a name="coleresizebar-class"></a>COleResizeBar Sınıfı

Yerinde OLE öğelerinin yeniden boyutlandırılmasını destekleyen bir denetim çubuğu türü.

## <a name="syntax"></a>Sözdizimi

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleResizeBar::COleResizeBar](#coleresizebar)|Bir `COleResizeBar` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleResizeBar::Oluştur](#create)|Bir Windows alt penceresi oluşturur ve baş harflerini oluşturur ve nesneyle `COleResizeBar` ilişkilendirer.|

## <a name="remarks"></a>Açıklamalar

`COleResizeBar`nesneler, yumurtadan çıkmış kenarlıklı ve dış yeniden boyutlandırma kollarına sahip bir [CRectTracker](../../mfc/reference/crecttracker-class.md) olarak görünür.

`COleResizeBar`nesneler genellikle [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) sınıfından türetilen çerçeve penceresi nesnelerinin katıştirilmiş üyeleridir.

Daha fazla bilgi için [Etkinleştirme](../../mfc/activation-cpp.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coleresizebarcoleresizebar"></a><a name="coleresizebar"></a>COleResizeBar::COleResizeBar

Bir `COleResizeBar` nesne inşa eder.

```
COleResizeBar();
```

### <a name="remarks"></a>Açıklamalar

Yeniden `Create` boyutlandırma çubuğu nesnesini oluşturmak için arayın.

## <a name="coleresizebarcreate"></a><a name="create"></a>COleResizeBar::Oluştur

Bir alt pencere oluşturur ve `COleResizeBar` nesneyle ilişkilendirer.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Yeniden boyutlandırma çubuğunun üst penceresine işaretçi.

*Dwstyle*<br/>
[Pencere stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) özniteliklerini belirtir.

*Nıd*<br/>
Yeniden boyutlandırma çubuğunun alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Yeniden boyutlandırma çubuğu oluşturulduysa sıfırsız; aksi takdirde 0.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)
