---
description: 'Daha fazla bilgi edinin: CMFCSpinButtonCtrl sınıfı'
title: CMFCSpinButtonCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 87e9abc94247416704ab801beeaa1953c4cceb46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339649"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl sınıfı

`CMFCSpinButtonCtrl`Sınıfı, bir döndürme düğmesi denetimi çizen bir görsel yöneticiyi destekler.

## <a name="syntax"></a>Syntax

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
|[CMFCSpinButtonCtrl:: OnDraw](#ondraw)|Geçerli döndürme düğmesi denetimini boyar.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda bir döndürme düğmesi denetimi çizmek üzere bir görsel yönetici kullanmak için, sınıfın tüm örneklerini `CSpinButtonCtrl` `CMFCSpinButtonCtrl` sınıfıyla değiştirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu `CMFCSpinButtonCtrl` ve yönteminin nasıl kullanılacağını gösterir `Create` .

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxspinbuttonctrl. h

## <a name="cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a> CMFCSpinButtonCtrl:: OnDraw

Geçerli döndürme düğmesi denetimini boyar.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Framework, `CMFCSpinButtonCtrl::OnPaint` [CWnd:: OnPaint](../../mfc/reference/cwnd-class.md#onpaint) iletisini işlemek için yöntemini çağırır ve sırasıyla bu yöntem bu `CMFCSpinButtonCtrl::OnDraw` yöntemi çağırır. Çerçevenin döndürme düğmesi denetimini nasıl çizdiğini özelleştirmek için bu yöntemi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)
