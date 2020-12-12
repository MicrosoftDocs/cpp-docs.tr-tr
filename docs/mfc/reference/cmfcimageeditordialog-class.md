---
description: 'Daha fazla bilgi edinin: CMFCImageEditorDialog sınıfı'
title: CMFCImageEditorDialog sınıfı
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 6c25cf4a1a8d0cc5852049a06c3a140cbb00a118
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265395"
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog sınıfı

`CMFCImageEditorDialog`Sınıfı, bir görüntü Düzenleyici iletişim kutusunu destekler.

## <a name="syntax"></a>Syntax

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCImageEditorDialog:: CMFCImageEditorDialog](#cmfcimageeditordialog)|Bir `CMFCImageEditorDialog` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

`CMFCImageEditorDialog`Sınıfı şunları içeren bir iletişim kutusu sağlar:

- Görüntüde tek pikselleri değiştirmek için kullandığınız resim alanı.

- Resim alanındaki pikselleri değiştirmek için çizim araçları.

- Çizim araçları tarafından kullanılan rengi belirtmek için bir renk paleti.

- Düzenlemelerinizin etkisini görüntüleyen bir önizleme alanı.

Aşağıdaki çizimde bir görüntü Düzenleyici iletişim kutusu gösterilmektedir.

![CMFCImageEditorDialog iletişim kutusu](../../mfc/reference/media/imageedit.png "CMFCImageEditorDialog iletişim kutusu")

Bir nesne kullanmanın bir yolu `CMFCImageEditorDialog` , düzenlenecek bir resim geçirmektir `CBitmap` . Görüntü düzenlemenin alanı sınırlı bir boyuta sahip olduğundan ve mantıksal piksel boyutu alana sığacak şekilde ayarlandığından, büyük bir görüntü oluşturmayın. `DoModal`Kalıcı bir iletişim kutusu başlatmak için yöntemini çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afximageeditordialog. h

## <a name="cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a> CMFCImageEditorDialog:: CMFCImageEditorDialog

Bir `CMFCImageEditorDialog` nesnesi oluşturur.

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>Parametreler

*Pbımap*<br/>
Görüntü işaretçisi.

*pParent*<br/>
Geçerli görüntü Düzenleyicisi iletişim kutusunun üst penceresine yönelik işaretçi.

*nBitsPixel*<br/>
Renk derinliği olarak da adlandırılan tek bir pikselin rengini temsil etmek için kullanılan bit sayısı.  *NBitsPixel* parametresi-1 ise, renk derinliği *pbıx* parametresi tarafından belirtilen görüntüden türetilir. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Bir görüntüyü değiştirmek için, oluşturucuya bir görüntü işaretçisi geçirin `CMFCImageEditorDialog` . Ardından, `DoModal` bir kalıcı iletişim kutusu açmak için yöntemini çağırın. `DoModal`Yöntem döndüğünde, bit eşlem yeni görüntüyü içerir.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCImageEditorDialog` . Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)
