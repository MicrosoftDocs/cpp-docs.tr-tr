---
title: CMFCImageEditorDialog sınıfı
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 97f16fa00b2e90fd9c43bf9b6792b4eafe7d7b88
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394534"
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

![CMFCImageEditorDialog iletişim kutusu](../../mfc/reference/media/imageedit.png "CMFCImageEditorDialog iletişim kutusu")

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

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCImageEditorDialog` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
