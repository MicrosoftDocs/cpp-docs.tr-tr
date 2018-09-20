---
title: COleLinksDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs:
- C++
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7c89b6e149a6c8f0eab63ec3f2e1a6301734c9d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448174"
---
# <a name="colelinksdialog-class"></a>COleLinksDialog sınıfı

OLE Edit Links iletişim kutusu için kullanıldı.

## <a name="syntax"></a>Sözdizimi

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Oluşturur bir `COleLinksDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleLinksDialog::DoModal](#domodal)|OLE Edit Links iletişim kutusu görüntüler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleLinksDialog::m_el](#m_el)|İletişim kutusunun davranışını kontrol eden OLEUIEDITLINKS türünden bir yapıyı.|

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi oluşturma `COleLinksDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COleLinksDialog` nesne oluşturulur, kullanabileceğiniz [m_el](#m_el) yapısı değerleri veya durumları iletişim kutusundaki denetimlerin başlatılamadı. `m_el` OLEUIEDITLINKS türünü yapısıdır. Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için [OLEUIEDITLINKS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuieditlinksa) Windows SDK'sındaki yapısı.

Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxodlgs.h

##  <a name="domodal"></a>  COleLinksDialog::DoModal

OLE Edit Links iletişim kutusu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse IDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse IDCANCEL.

- Bir hata oluşursa IDABORT. IDABORT döndürülürse, çağrı `COleDialog::GetLastError` konusu hatanın türü hakkında daha fazla bilgi almak için üye işlevi. Olası hataları bir listesi için bkz. [OleUIEditLinks](/windows/desktop/api/oledlg/nf-oledlg-oleuieditlinksa) Windows SDK'sında işlev.

### <a name="remarks"></a>Açıklamalar

Çeşitli iletişim kutusu denetimleri üyeleri ayarlayarak başlatmak istiyorsanız [m_el](#m_el) yapısı, size bunu çağırmadan önce `DoModal`, ancak iletişim nesnesi oluşturulur.

##  <a name="colelinksdialog"></a>  COleLinksDialog::COleLinksDialog

Oluşturur bir `COleLinksDialog` nesne.

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Düzenlenecek bağlantıları içeren OLE belge işaret eder.

*pView*<br/>
Geçerli görünüme işaret *pDoc*.

*CertOpenStore*<br/>
Oluşturma bayrağı 0 veya iletişim kutusu görüntülendiğinde Yardım düğmesini görüntülenip görüntülenmeyeceğini belirtmek için ELF_SHOWHELP içerir.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür `CWnd`) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim kutusunun üst pencere ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca oluşturan bir `COleLinksDialog` nesne. İletişim kutusunu görüntülemek için çağrı [DoModal](#domodal) işlevi.

##  <a name="m_el"></a>  COleLinksDialog::m_el

Yapı türünü OLEUIEDITLINKS Edit Links iletişim kutusu davranışını denetlemek için kullanılır.

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyelerine, doğrudan ya da üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için [OLEUIEDITLINKS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuieditlinksa) Windows SDK'sındaki yapısı.

## <a name="see-also"></a>Ayrıca Bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
