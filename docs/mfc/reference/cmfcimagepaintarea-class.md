---
title: CMFCImagePaintArea Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
ms.openlocfilehash: 4e73bd7bc1a28317dbfc452df1f45541dfcbfd21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374443"
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea Sınıfı

Görüntü düzenleyicisi iletişim kutusundaki görüntüyü değiştirmek için kullandığınız resim alanını sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Bir `CMFCImagePaintArea` nesne inşa eder.|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCImagePaintArea::GetMode](#getmode)|Geçerli çizim modunu alır.|
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Resim alanı için bit eşlem görüntüsünü ayarlar.|
|[CMFCImagePaintArea::SetColor](#setcolor)|Geçerli çizim rengini ayarlar.|
|[CMFCImagePaintArea::SetMode](#setmode)|Geçerli çizim modunu ayarlar.|

### <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan kodunuzdan kullanılmak üzere tasarlanmamıştır.

Çerçeve, resim düzenleyicisi iletişim kutusunda resim alanını görüntülemek için bu sınıfı kullanır. Görüntü düzenleyicisi iletişim kutusu hakkında daha fazla bilgi için [CMFCImageEditorDialog Class'a](../../mfc/reference/cmfcimageeditordialog-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCImagePaintArea` nasıl oluşturulabildiğini, geçerli çizim rengini nasıl ayarlayıp ayarlayamacını, geçerli çizim modunu nasıl ayarlayıp resim alanı için bit eşlemi görüntüsünü ayarlayışmayı gösterir.

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cbutton](../../mfc/reference/cbutton-class.md)

[Cmfcımagepaintarea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afximagepaintarea.h

## <a name="cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a>CMFCImagePaintArea::CMFCImagePaintArea

Bir `CMFCImagePaintArea` nesne inşa eder.

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pParentDlg*|[içinde] Görüntü düzenleyicisinin üst öğesi olan iletişim kutusuna işaretçi.|

## <a name="cmfcimagepaintareagetmode"></a><a name="getmode"></a>CMFCImagePaintArea::GetMode

Geçerli çizim modunu alır.

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli çizim modunu belirten [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) değeri.

## <a name="cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a>CMFCImagePaintArea::SetBitmap

Resim alanı için bit eşlem görüntüsünü ayarlar.

```
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBitmap*|[içinde] Görüntülenecek yeni bitmap görüntüsü.|

### <a name="remarks"></a>Açıklamalar

*pBitmap* NULL ise, bu yöntem değiştirilebilir boya alanının boyutunu sıfıra ayarlar. Aksi takdirde, değiştirilebilir boya alanının boyutunu sağlanan bit eşlem görüntüsünün boyutuna ayarlar.

## <a name="cmfcimagepaintareasetcolor"></a><a name="setcolor"></a>CMFCImagePaintArea::SetColor

Geçerli çizim rengini ayarlar.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*color*|[içinde] Yeni çizim rengi.|

### <a name="remarks"></a>Açıklamalar

Görüntü düzenleyicisi palet çubuğundan veya renk seçiciden bir renk seçtiğinizde, çerçeve geçerli çizim rengini güncelleştirmek için bu yöntemi çağırır. İlk çizim rengi siyahtır (COLORREF değeri 0'dır).

Çizim rengi, IMAGE_EDIT_MODE_COLOR hariç tüm çizim modları için görüntü düzenleyicisi iletişim kutusu tarafından kullanılır. Çizim modları hakkında daha fazla bilgi için [CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırma'](cmfcimagepaintarea-image-edit-mode-enumeration.md)ya bakınız.

## <a name="cmfcimagepaintareasetmode"></a><a name="setmode"></a>CMFCImagePaintArea::SetMode

Geçerli çizim modunu ayarlar.

```
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Modu*|[içinde] Geçerli çizim modunu belirten [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) değeri.|

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog Sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
