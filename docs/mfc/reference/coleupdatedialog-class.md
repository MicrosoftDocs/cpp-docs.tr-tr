---
title: COleUpdateDialog Sınıfı
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
ms.openlocfilehash: 9e2c7a8d79ebf5e6483a06354b280e474d7b8e61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374846"
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog Sınıfı

Bir belgede yalnızca varolan bağlantılı veya katıştılı nesneleri güncelleştirmeniz gerektiğinde kullanılması gereken OLE Edit Links iletişim kutusunun özel bir örneği için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleUpdateDialog : public COleLinksDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Bir `COleUpdateDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleUpdateDialog::DoModal](#domodal)|Güncelleştirme modunda **Bağlantıları Edit** iletişim kutusunu görüntüler.|

## <a name="remarks"></a>Açıklamalar

OLE'ye özgü iletişim kutuları yla ilgili daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

[Colelinksdialog](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="coleupdatedialogcoleupdatedialog"></a><a name="coleupdatedialog"></a>COleUpdateDialog::COleUpdateDialog

Bir `COleUpdateDialog` nesne inşa eder.

```
explicit COleUpdateDialog(
    COleDocument* pDoc,
    BOOL bUpdateLinks = TRUE,
    BOOL bUpdateEmbeddings = FALSE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Güncelleştirilmesi gereken bağlantıları içeren belgeyi işaret eder.

*bUpdateLinks*<br/>
Bağlı nesnelerin güncelleştirilip güncelleştirilmeyeceğini belirleyen bayrak.

*bUpdateEmbeddings*<br/>
Katıştılmış nesnelerin güncelleştirilip güncelleştirilmeyeceğini belirleyen bayrak.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst `CWnd`veya sahip penceresi nesnesine (tür) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca `COleUpdateDialog` bir nesne oluşturuyor. İletişim kutusunu görüntülemek için [DoModal'ı](../../mfc/reference/colelinksdialog-class.md#domodal)arayın. Bu sınıf, yalnızca `COleLinksDialog` varolan bağlantılı veya katıştırılmış öğeleri güncelleştirmek istediğinizde yerine kullanılmalıdır.

## <a name="coleupdatedialogdomodal"></a><a name="domodal"></a>COleUpdateDialog::DoModal

Güncelleştirme modunda Bağlantıları Edit iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla döndüyse İDOK.

- Geçerli belgedeki bağlantılı veya katıştırılmış öğelerin hiçbirinin güncelleştirilmesi gerekmiyorsa IDCANCEL.

- Bir hata oluştuysa IDABORT. IDABORT döndürülürse, [coleDialog'u arayın::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) üye işlevini arayarak oluşan hata türü hakkında daha fazla bilgi alın. Olası hataların listesi için Windows SDK'daki [OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Kullanıcı İptal düğmesini seçmedikçe tüm bağlantılar ve/veya katıştırmalar güncelleştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleLinksDialog Sınıfı](../../mfc/reference/colelinksdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleLinksDialog Sınıfı](../../mfc/reference/colelinksdialog-class.md)
