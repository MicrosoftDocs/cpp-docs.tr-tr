---
title: Cotaupdatedialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
ms.openlocfilehash: 150e78b7880a61343db21c3c787ffdd1f0b734a5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503165"
---
# <a name="coleupdatedialog-class"></a>Cotaupdatedialog sınıfı

Bir belgede yalnızca mevcut bağlantılı veya katıştırılmış nesneleri güncelleştirmeniz gerektiğinde kullanılması gereken OLE düzenleme bağlantıları iletişim kutusunun özel bir durumu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleUpdateDialog : public COleLinksDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copaupdatedialog:: Cotaupdatedialog](#coleupdatedialog)|Bir `COleUpdateDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotaupdatedialog::D oModal](#domodal)|Güncelleştirme modundaki **Bağlantıları Düzenle** iletişim kutusunu görüntüler.|

## <a name="remarks"></a>Açıklamalar

OLE 'ye özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

[Cotalinksdialog](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

##  <a name="coleupdatedialog"></a>Copaupdatedialog:: Cotaupdatedialog

Bir `COleUpdateDialog` nesnesi oluşturur.

```
explicit COleUpdateDialog(
    COleDocument* pDoc,
    BOOL bUpdateLinks = TRUE,
    BOOL bUpdateEmbeddings = FALSE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Güncelleştirilmesi gerekebilecek bağlantıları içeren belgeyi işaret eder.

*bUpdateLinks*<br/>
Bağlantılı nesnelerin güncelleştirilip güncelleştirilmediğini belirleyen bayrak.

*bupdateembed*<br/>
Katıştırılmış nesnelerin güncelleştirilip güncelleştirilmediğini belirleyen bayrak.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine (türü `CWnd`) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca bir `COleUpdateDialog` nesnesi oluşturur. İletişim kutusunu göstermek için [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)' ı çağırın. Bu sınıf, `COleLinksDialog` yalnızca varolan bağlantılı veya katıştırılmış öğeleri güncelleştirmek istediğinizde yerine kullanılmalıdır.

##  <a name="domodal"></a>Cotaupdatedialog::D oModal

Güncelleştirme modundaki bağlantıları Düzenle iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu için tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla döndürülürse ıDOK.

- Geçerli belgedeki bağlantılı veya gömülü öğelerin hiçbirinin güncelleştirilmesi gerekmiyorsa ıDCANCEL.

- Bir hata oluştuysa ıDADBORT. IDADBORT döndürülürse, oluşan hata türü hakkında daha fazla bilgi edinmek için [Cotadialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) üye işlevini çağırın. Olası hataların listesi için Windows SDK [OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Kullanıcı Iptal düğmesini seçmediği takdirde tüm bağlantılar ve/veya katıştırlar güncelleştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleLinksDialog Sınıfı](../../mfc/reference/colelinksdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleLinksDialog Sınıfı](../../mfc/reference/colelinksdialog-class.md)
