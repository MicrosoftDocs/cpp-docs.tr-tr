---
title: CMFCImagePaintArea sınıfı
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
ms.openlocfilehash: ee960b27651489ac1c196789d41a6c5ee396b260
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831157"
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea sınıfı

Görüntü Düzenleyici iletişim kutusunda bir görüntüyü değiştirmek için kullandığınız resim alanını sağlar.

## <a name="syntax"></a>Syntax

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|[CMFCImagePaintArea:: CMFCImagePaintArea](#cmfcimagepaintarea)|Bir `CMFCImagePaintArea` nesnesi oluşturur.|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCImagePaintArea:: GetMode](#getmode)|Geçerli çizim modunu alır.|
|[CMFCImagePaintArea:: SetBit eşlem](#setbitmap)|Resim alanı için bit eşlem resmini ayarlar.|
|[CMFCImagePaintArea:: SetColor](#setcolor)|Geçerli çizim rengini ayarlar.|
|[CMFCImagePaintArea:: SetMode](#setmode)|Geçerli çizim modunu ayarlar.|

### <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan kodunuzdan kullanılmaya yönelik değildir.

Çerçeve, resim alanını görüntü Düzenleyici iletişim kutusunda göstermek için bu sınıfı kullanır. Görüntü Düzenleyicisi iletişim kutusu hakkında daha fazla bilgi için bkz. [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu `CMFCImagePaintArea` , geçerli çizim rengini ayarlamayı, geçerli çizim modunu ayarlamayı ve resim alanı için bit eşlem görüntüsünü ayarlamayı gösterir.

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afximagepaintarea. h

## <a name="cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a> CMFCImagePaintArea:: CMFCImagePaintArea

Bir `CMFCImagePaintArea` nesnesi oluşturur.

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>Parametreler

*pParentDlg*\
'ndaki Görüntü düzenleyicisinin üst öğesi olan iletişim kutusu işaretçisi.

## <a name="cmfcimagepaintareagetmode"></a><a name="getmode"></a> CMFCImagePaintArea:: GetMode

Geçerli çizim modunu alır.

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli çizim modunu belirten bir [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) değeri.

## <a name="cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a> CMFCImagePaintArea:: SetBit eşlem

Resim alanı için bit eşlem resmini ayarlar.

```cpp
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*Pbımap*\
'ndaki Görüntülenecek yeni bit eşlem resmi.

### <a name="remarks"></a>Açıklamalar

*Pbımap* null ise, bu yöntem değiştirilebilir boyama alanının boyutunu sıfıra ayarlar. Aksi takdirde, değiştirilebilir boyama alanının boyutunu, belirtilen bit eşlem görüntüsünün boyutuna ayarlar.

## <a name="cmfcimagepaintareasetcolor"></a><a name="setcolor"></a> CMFCImagePaintArea:: SetColor

Geçerli çizim rengini ayarlar.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*\
'ndaki Yeni çizim rengi.

### <a name="remarks"></a>Açıklamalar

Görüntü Düzenleyicisi paleti çubuğundan veya renk seçicisinden bir renk seçtiğinizde, çerçeve geçerli çizim rengini güncelleştirmek için bu yöntemi çağırır. İlk çizim rengi siyah (COLORREF değeri 0).

Çizim rengi, IMAGE_EDIT_MODE_COLOR dışındaki tüm çizim modları için görüntü Düzenleyici iletişim kutusu tarafından kullanılır. Çizim modları hakkında daha fazla bilgi için bkz. [CMFCImagePaintArea:: IMAGE_EDIT_MODE sabit listesi](cmfcimagepaintarea-image-edit-mode-enumeration.md).

## <a name="cmfcimagepaintareasetmode"></a><a name="setmode"></a> CMFCImagePaintArea:: SetMode

Geçerli çizim modunu ayarlar.

```cpp
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>Parametreler

*modundaysa*\
'ndaki Geçerli çizim modunu belirten bir [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
