---
title: CMFCSpinButtonCtrl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 445b857400d8c82109ca7220b84bac692a2abf89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376183"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl Sınıfı

Sınıf, `CMFCSpinButtonCtrl` döndürme düğmesi denetimi çizen görsel bir yöneticiyi destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Varsayılan oluşturucu.|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Geçerli spin düğmesi denetimini yeniden boyar.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda bir spin düğmesi denetimi çizmek için görsel bir yönetici `CSpinButtonCtrl` kullanmak için `CMFCSpinButtonCtrl` sınıfın tüm örneklerini sınıfla değiştirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCSpinButtonCtrl` nasıl oluşturulup `Create` yönteminin kullanılacağını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cspinbuttonctrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxspinbuttonctrl.h

## <a name="cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a>CMFCSpinButtonCtrl::OnDraw

Geçerli spin düğmesi denetimini yeniden boyar.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

### <a name="remarks"></a>Açıklamalar

Çerçeve CWnd işlemek için `CMFCSpinButtonCtrl::OnPaint` yöntem [çağırır::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) iletisi ve `CMFCSpinButtonCtrl::OnDraw` sırayla bu yöntem bu yöntemi çağırır. Çerçevenin spin düğmesi denetimini nasıl çizdiğini özelleştirmek için bu yöntemi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager Sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)
