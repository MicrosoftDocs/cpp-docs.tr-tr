---
title: CMFCImageEditorDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f360c8fc44fba07aee8287137468937d959c596
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428804"
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog sınıfı

`CMFCImageEditorDialog` Sınıfı, bir Resim Düzenleyicisi iletişim kutusunu destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Oluşturur bir `CMFCImageEditorDialog` nesne.|

## <a name="remarks"></a>Açıklamalar

`CMFCImageEditorDialog` Sınıfı içeren bir iletişim kutusu sağlar:

- Resim alanı bağımsız piksellerde görüntü değiştirmek için kullanın.

- Çizim Araçları piksel resim alanı değiştirmek için.

- Çizim araçları tarafından kullanılır renk belirtmek için bir renk paleti.

- Düzenlemeniz etkisini gösteren bir Önizleme alanı.

Aşağıdaki çizimde, bir Resim Düzenleyicisi iletişim kutusu gösterir.

![CMFCImageEditorDialog iletişim kutusu](../../mfc/reference/media/imageedit.png "imageedit")

Kullanmak için tek yönlü bir `CMFCImageEditorDialog` nesnedir, geçirilecek bir `CBitmap` düzenlenecek görüntü. Büyük resim düzenleme alanı görüntünün sınırlı bir boyuta sahiptir ve mantıksal piksel boyutunu alana uyacak şekilde ayarlanmış olduğundan oluşturmayın. Çağrı `DoModal` kalıcı bir iletişim kutusu başlatmak için yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afximageeditordialog.h

##  <a name="cmfcimageeditordialog"></a>  CMFCImageEditorDialog::CMFCImageEditorDialog

Oluşturur bir `CMFCImageEditorDialog` nesne.

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>Parametreler

*pBitmap*<br/>
Bir görüntü için işaretçi.

*pParent*<br/>
Geçerli Resim Düzenleyicisi iletişim kutusunun üst pencere işaretçisi.

*nBitsPixel*<br/>
Renk derinliği da adlandırılır tek bir piksel rengi temsil etmek için kullanılan bit sayısı.  Varsa *nBitsPixel* parametresi, -1, renk derinliği tarafından belirtilen görüntüsünden türetilir *pBitmap* parametresi. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Görüntü değiştirmek için bir görüntü işaretçisine geçirmek `CMFCImageEditorDialog` Oluşturucusu. Ardından çağırın `DoModal` kalıcı bir iletişim kutusu açmak için yöntemi. Zaman `DoModal` yöntemi döndürür, bit eşlem yeni görüntüyü içerir.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCImageEditorDialog` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
