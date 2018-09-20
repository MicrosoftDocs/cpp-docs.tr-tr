---
title: COleBusyDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
dev_langs:
- C++
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d60a86888f601463fa5c2151eb3243c3f55078ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380379"
---
# <a name="colebusydialog-class"></a>COleBusyDialog sınıfı

OLE Server Not Responding veya Server Busy iletişim kutuları için kullanıldı.

## <a name="syntax"></a>Sözdizimi

```
class COleBusyDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Oluşturur bir `COleBusyDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleBusyDialog::DoModal](#domodal)|OLE sunucu meşgul iletişim kutusunu görüntüler.|
|[COleBusyDialog::GetSelectionType](#getselectiontype)|İletişim kutusunda yaptığınız seçime belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleBusyDialog::m_bz](#m_bz)|Yapı türü iletişim kutusu davranışını denetleyen OLEUIBUSY.|

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi oluşturma `COleBusyDialog` bu iletişim kutularından çağırmak istediğinizde. Sonra bir `COleBusyDialog` nesne oluşturulur, kullanabileceğiniz [m_bz](#m_bz) yapısı değerleri veya durumları iletişim kutusundaki denetimlerin başlatılamadı. `m_bz` OLEUIBUSY türünü yapısıdır. Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Windows SDK'sındaki yapısı.

Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxodlgs.h

##  <a name="colebusydialog"></a>  COleBusyDialog::COleBusyDialog

Bu işlev yalnızca oluşturan bir `COleBusyDialog` nesne.

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*htaskBusy*<br/>
Meşgul sunucu görevini işleyin.

*bNotResponding*<br/>
Doğruysa, yanıt vermeyen iletişim kutusu yerine sunucu meşgul iletişim kutusu çağırın. Yanıt iletişim kutusu içindeki ifadeleri biraz farklı sunucu meşgul iletişim kutusu içindeki ifadeleri ve iptal düğmesi devre dışıdır.

*CertOpenStore*<br/>
Oluşturma bayrak. Sıfır veya daha fazla bit düzeyinde OR işleci ile birlikte aşağıdaki değerleri içerebilir:

- BZ_DISABLECANCELBUTTON iletişim kutusu çağırırken iptal düğmesi devre dışı.

- BZ_DISABLESWITCHTOBUTTON iletişim kutusu çağırırken geçiş yap düğmesi devre dışı.

- BZ_DISABLERETRYBUTTON iletişim kutusu çağırırken yeniden deneme düğmesi devre dışı.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür `CWnd`) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim nesnenin üst pencere ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için çağrı [DoModal](#domodal).

Daha fazla bilgi için [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Windows SDK'sındaki yapısı.

##  <a name="domodal"></a>  COleBusyDialog::DoModal

OLE sunucu meşgul veya sunucu yanıt iletişim kutusunu görüntülemek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse IDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse IDCANCEL.

- Bir hata oluşursa IDABORT. IDABORT döndürülürse, çağrı `COleDialog::GetLastError` konusu hatanın türü hakkında daha fazla bilgi almak için üye işlevi. Olası hataları bir listesi için bkz. [OleUIBusy](/windows/desktop/api/oledlg/nf-oledlg-oleuibusya) Windows SDK'sında işlev.

### <a name="remarks"></a>Açıklamalar

Çeşitli iletişim kutusu denetimleri üyeleri ayarlayarak başlatmak istiyorsanız [m_bz](#m_bz) yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.

Varsa `DoModal` döndürür IDOK, diğer üye ayarları veya kullanıcı tarafından iletişim kutusuna giriş bilgi almak için işlevleri çağırabilir.

##  <a name="getselectiontype"></a>  COleBusyDialog::GetSelectionType

Sunucu meşgul iletişim kutusunda kullanıcı tarafından seçmiş seçim türünü almak için bu işlevi çağırın.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

Dönüş türü değerleri tarafından belirtilen `Selection` numaralandırma türü içinde bildirilen `COleBusyDialog` sınıfı.

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

Bu değerleri kısa açıklamaları izleyin:

- `COleBusyDialog::switchTo` Geçiş için düğmesine basıldı.

- `COleBusyDialog::retry` Yeniden deneme düğmesine basıldı.

- `COleBusyDialog::callUnblocked` Çağrı Sunucusu'nu etkinleştirmek için artık engeli kaldırılır.

##  <a name="m_bz"></a>  COleBusyDialog::m_bz

Yapı türünü OLEUIBUSY sunucu meşgul iletişim kutusu davranışını denetlemek için kullanılır.

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyelerine, doğrudan ya da üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Windows SDK'sındaki yapısı.

## <a name="see-also"></a>Ayrıca Bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
