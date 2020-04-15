---
title: CMFCImageEditorDialog Sınıfı
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 23c2a919428689fe107b82041bd87b758ede2bc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367474"
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog Sınıfı

Sınıf `CMFCImageEditorDialog` bir görüntü düzenleyicisi iletişim kutusunu destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Bir `CMFCImageEditorDialog` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCImageEditorDialog` aşağıdakileri içeren bir iletişim kutusu sağlar:

- Görüntüdeki tek tek pikselleri değiştirmek için kullandığınız resim alanı.

- Resim alanındaki pikselleri değiştirmek için çizim araçları.

- Çizim araçları tarafından kullanılan rengi belirtmek için bir renk paleti.

- Edininizin etkisini görüntüleyen bir önizleme alanı.

Aşağıdaki resimde bir resim düzenleyicisi iletişim kutusu gösterilmektedir.

![CMFCImageEditorDialog iletişim kutusu](../../mfc/reference/media/imageedit.png "CMFCImageEditorDialog iletişim kutusu")

Bir `CMFCImageEditorDialog` nesneyi kullanmanın bir yolu, düzenlenecek bir `CBitmap` görüntüyü aktarmaktır. Görüntü düzenleme alanı sınırlı boyutu olduğundan ve mantıksal piksel boyutu alana uyacak şekilde ayarlandığından büyük bir görüntü oluşturmayın. Modal `DoModal` iletişim kutusunu başlatmak için yöntemi arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[Cmfcımageeditordialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afximageeditordialog.h

## <a name="cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a>CMFCImageEditorDialog::CMFCImageEditorDialog

Bir `CMFCImageEditorDialog` nesne inşa eder.

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>Parametreler

*pBitmap*<br/>
Görüntü için işaretçi.

*pParent*<br/>
Geçerli görüntü düzenleyicisi iletişim kutusunun üst penceresine işaretçi.

*nBitsPiksel*<br/>
Renk derinliği olarak da adlandırılan tek bir pikselin rengini temsil etmek için kullanılan bit sayısı.  *nBitsPixel* parametresi -1 ise, renk derinliği *pBitmap* parametresi tarafından belirtilen görüntüden türetilir. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Görüntüyü değiştirmek için, bir görüntü `CMFCImageEditorDialog` işaretçisini oluşturucuya geçirin. Ardından modal iletişim kutusunu açmak için `DoModal` yöntemi arayın. `DoModal` Yöntem döndüğünde, bit eşlem yeni görüntüyü içerir.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCImageEditorDialog` nasıl inşa edilebildiğini gösterir. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
