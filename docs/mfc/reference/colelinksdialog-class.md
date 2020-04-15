---
title: COleLinksDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
ms.openlocfilehash: f120678c822749c8f27c3c56c95fcdd54647aca3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374928"
---
# <a name="colelinksdialog-class"></a>COleLinksDialog Sınıfı

OLE Edit Links iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Bir `COleLinksDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleLinksDialog::DoModal](#domodal)|OLE Edit Links iletişim kutusunu görüntüler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleLinksDialog::m_el](#m_el)|İletişim kutusunun davranışını kontrol eden OLEUIEDITLINKS türünden bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu `COleLinksDialog` aramak istediğinizde sınıf nesnesi oluşturun. Bir `COleLinksDialog` nesne oluşturulduktan sonra, iletişim kutusundaki denetimdeğerlerini veya durumlarını açmak için [m_el](#m_el) yapısını kullanabilirsiniz. Yapısı `m_el` tip OLEUIEDITLINKS olduğunu. Bu iletişim sınıfını kullanma hakkında daha fazla bilgi için [DoModal](#domodal) üye işlevine bakın.

> [!NOTE]
> Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için Windows SDK'daki [OLEUIEDITLINKS](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) yapısına bakın.

OLE'ye özgü iletişim kutuları yla ilgili daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="colelinksdialogdomodal"></a><a name="domodal"></a>COleLinksDialog::DoModal

OLE Edit Links iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse İDOK.

- Kullanıcı iletişim kutusunu iptal ettiyse IDCANCEL.

- Bir hata oluştuysa IDABORT. IDABORT döndürülürse, `COleDialog::GetLastError` oluşan hata türü hakkında daha fazla bilgi almak için üye işlevi arayın. Olası hataların listesi için Windows SDK'daki [OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[m_el](#m_el) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmayı istiyorsanız, çağrıyapmadan `DoModal`önce ancak iletişim nesnesi oluşturulduktan sonra bunu yapmalısınız.

## <a name="colelinksdialogcolelinksdialog"></a><a name="colelinksdialog"></a>COleLinksDialog::COleLinksDialog

Bir `COleLinksDialog` nesne inşa eder.

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Düzenlenecek bağlantıları içeren OLE belgesine işaret edin.

*pGörünüm*<br/>
*pDoc'taki*geçerli görünüme işaret edilir.

*Dwflags*<br/>
İletişim kutusu görüntülendiğinde Yardım düğmesinin görüntülenip görüntüleneceğini belirtmek için 0 veya ELF_SHOWHELP içeren oluşturma bayrağı.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst `CWnd`veya sahip penceresi nesnesine (tür) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca `COleLinksDialog` bir nesne oluşturuyor. İletişim kutusunu görüntülemek için [DoModal](#domodal) işlevini arayın.

## <a name="colelinksdialogm_el"></a><a name="m_el"></a>COleLinksDialog::m_el

Bağlantıları Edit iletişim kutusunun davranışını denetlemek için kullanılan OLEUIEDITLINKS türü yapısı.

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri doğrudan veya üye işlevler aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK'daki [OLEUIEDITLINKS](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
