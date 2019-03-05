---
title: Colechangeıcondialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
ms.openlocfilehash: eb5fe38d7cf4058e8de31da3de39dca906671a85
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288980"
---
# <a name="colechangeicondialog-class"></a>Colechangeıcondialog sınıfı

OLE Change Icon iletişim kutusu için kullanıldı.

## <a name="syntax"></a>Sözdizimi

```
class COleChangeIconDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Oluşturur bir `COleChangeIconDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|İletişim kutusunda belirtilen değişiklik yapar.|
|[COleChangeIconDialog::DoModal](#domodal)|OLE 2 Change Icon iletişim kutusu görüntüler.|
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğenin icon formla ilişkili meta dosyası için bir tanıtıcı alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleChangeIconDialog::m_ci](#m_ci)|İletişim kutusunun davranışını kontrol eden bir yapı.|

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi oluşturma `COleChangeIconDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COleChangeIconDialog` nesne oluşturulur, kullanabileceğiniz [m_ci](#m_ci) yapısı değerleri veya durumları iletişim kutusundaki denetimlerin başlatılamadı. `m_ci` OLEUICHANGEICON türünü yapısıdır. Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

Daha fazla bilgi için [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Windows SDK'sındaki yapısı.

Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeIconDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxodlgs.h

##  <a name="colechangeicondialog"></a>  COleChangeIconDialog::COleChangeIconDialog

Bu işlev yalnızca oluşturan bir `COleChangeIconDialog` nesne.

```
explicit COleChangeIconDialog(
    COleClientItem* pItem,
    DWORD dwFlags = CIF_SELECTCURRENT,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülecek öğeyi işaret eder.

*CertOpenStore*<br/>
Aşağıdaki değerlerden herhangi bir sayı içeren oluşturma bayrağı birleştirilmiş bit kullanarak- or işleci:

- Geçerli radyo düğmesinin olacak CIF_SELECTCURRENT belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını seçili. Bu varsayılandır.

- Varsayılan radyo düğmesini olacak CIF_SELECTDEFAULT belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını seçili.

- Dosyadan radyo düğmesini olacak CIF_SELECTFROMFILE belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını seçili.

- CIF_SHOWHELP iletişim kutusu çağrıldığında Yardım düğmesini gösterileceğini belirtir.

- CIF_USEICONEXE belirtir simgesi belirtilen yürütülebilir ayıklanacağı `szIconExe` alanını [m_ci](#m_ci) yerine türünden alınan. Bu, ekleme veya OLE dışı dosyalarına bağlama için kullanışlıdır.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür `CWnd`) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim kutusunun üst pencere ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için çağrı [DoModal](#domodal) işlevi.

Daha fazla bilgi için [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Windows SDK'sındaki yapısı.

##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon

Sonra iletişim kutusunda seçilen bir öğeyi temsil eden simgeyi değiştirmek için bu işlevi çağırın [DoModal](#domodal) IDOK döndürür.

```
BOOL DoChangeIcon(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Simgesini değiştirme öğeyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Değişiklik başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="domodal"></a>  COleChangeIconDialog::DoModal

OLE Change Icon iletişim kutusunu görüntülemek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse IDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse IDCANCEL.

- Bir hata oluşursa IDABORT. IDABORT döndürülürse, çağrı `COleDialog::GetLastError` konusu hatanın türü hakkında daha fazla bilgi almak için üye işlevi. Olası hataları bir listesi için bkz. [OleUIChangeIcon](/windows/desktop/api/oledlg/nf-oledlg-oleuichangeicona) Windows SDK'sında işlev.

### <a name="remarks"></a>Açıklamalar

Çeşitli iletişim kutusu denetimleri üyeleri ayarlayarak başlatmak istiyorsanız [m_ci](#m_ci) yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.

Varsa `DoModal` döndürür IDOK, diğer üye ayarları veya kullanıcı tarafından iletişim kutusuna giriş bilgi almak için işlevleri çağırabilir.

##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile

Seçilen öğenin icon boy içeren meta dosyası için bir tanıtıcı almak için bu işlevi çağırın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunu seçerek kapattıysanız yeni simgesine icon yönüyle içeren meta tanıtıcısını **Tamam**; Aksi takdirde, bu simgeyi olan iletişim kutusunda görüntülenen önce.

##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci

Yapı türünü OLEUICHANGEICON Change Icon iletişim kutusu davranışını denetlemek için kullanılır.

```
OLEUICHANGEICON m_ci;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyelerine, doğrudan ya da üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Windows SDK'sındaki yapısı.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
