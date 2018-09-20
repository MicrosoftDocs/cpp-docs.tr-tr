---
title: CMFCSpinButtonCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 756cdffc8f9f726e63b129f5f87a19eec01cd429
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440023"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager Sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)
