---
title: CMFCSpinButtonCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 60808359c11604368493031e1b6f4573b3b2026f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410106"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl sınıfı

`CMFCSpinButtonCtrl` Sınıfı, bir değer değiştirme düğmesi denetimi çizen bir görsel yöneticiyi destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Varsayılan Oluşturucu.|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Geçerli değer değiştirme düğmesi denetimi halinde yeniden boyar.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda bir değer değiştirme düğmesi denetimi çizmek için bir görsel yöneticiyi kullanmak için tüm örneklerinin yerine `CSpinButtonCtrl` sınıfıyla `CMFCSpinButtonCtrl` sınıfı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnenin oluşturulacağı gösterilmektedir `CMFCSpinButtonCtrl` kullanın ve sınıf kendi `Create` yöntemi.

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxspinbuttonctrl.h

##  <a name="ondraw"></a>  CMFCSpinButtonCtrl::OnDraw

Geçerli değer değiştirme düğmesi denetimi halinde yeniden boyar.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Framework çağrıları `CMFCSpinButtonCtrl::OnPaint` işlemek için gereken yöntemini [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) iletisi ve yöntemi sırayla bu ProcessOrder `CMFCSpinButtonCtrl::OnDraw` yöntemi. Framework değer değiştirme düğmesi denetimi çizen biçimini özelleştirmek için bu yöntemi yok sayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager Sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)
