---
title: Cotalinksdialog sınıfı
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
ms.openlocfilehash: 911108f9a231b752790abfdf86d1b4042d30b149
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504115"
---
# <a name="colelinksdialog-class"></a>Cotalinksdialog sınıfı

OLE düzenleme bağlantıları iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotalinksdialog:: Cotalinksdialog](#colelinksdialog)|Bir `COleLinksDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotalinksdialog::D oModal](#domodal)|OLE düzenleme bağlantıları iletişim kutusunu görüntüler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cotalinksdialog:: m_el](#m_el)|İletişim kutusunun davranışını denetleyen OLEUıEDITLINKS türünde bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu çağırmak istediğinizde `COleLinksDialog` , sınıfının bir nesnesi oluşturun. Bir `COleLinksDialog` nesne oluşturulduktan sonra, iletişim kutusundaki denetimlerin değerlerini veya durumlarını başlatmak için [m_el](#m_el) yapısını kullanabilirsiniz. Yapı `m_el` , OleUIEditLinks türündedir. Bu iletişim kutusu sınıfını kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için Windows SDK [OleUIEditLinks](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) yapısına bakın.

OLE 'ye özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

##  <a name="domodal"></a>Cotalinksdialog::D oModal

OLE düzenleme bağlantıları iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu için tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntüleniyorsa ıDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse ıDCANCEL.

- Bir hata oluştuysa ıDADBORT. Idadbort döndürülürse, oluşan hata türü hakkında `COleDialog::GetLastError` daha fazla bilgi edinmek için üye işlevini çağırın. Olası hataların listesi için Windows SDK [OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[M_el](#m_el) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmak istiyorsanız, öğesini çağırmadan `DoModal`önce, ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

##  <a name="colelinksdialog"></a>Cotalinksdialog:: Cotalinksdialog

Bir `COleLinksDialog` nesnesi oluşturur.

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Düzenlenecek bağlantıları içeren OLE belgesine işaret eder.

*pView*<br/>
*PDoc*üzerinde geçerli görünümü işaret eder.

*dwFlags*<br/>
İletişim kutusu görüntülendiğinde Yardım düğmesinin görüntülenip görüntülenmeyeceğini belirtmek için 0 veya ELF_SHOWHELP içeren oluşturma bayrağı.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine (türü `CWnd`) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca bir `COleLinksDialog` nesnesi oluşturur. İletişim kutusunu göstermek için [DoModal](#domodal) işlevini çağırın.

##  <a name="m_el"></a>Cotalinksdialog:: m_el

Bağlantıları Düzenle iletişim kutusunun davranışını denetlemek için kullanılan OLEUıEDITLINKS türünün yapısı.

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri, doğrudan veya üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK [OleUIEditLinks](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
