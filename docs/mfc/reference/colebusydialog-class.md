---
description: 'Daha fazla bilgi edinin: Cotabusydialog sınıfı'
title: Cotabusi Iletişim kutusu sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
ms.openlocfilehash: 7191cf193fccbe0883c8c888f888df94e1f70a23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340937"
---
# <a name="colebusydialog-class"></a>Cotabusi Iletişim kutusu sınıfı

OLE sunucusu yanıt vermiyor veya sunucu meşgul iletişim kutuları için kullanılır.

## <a name="syntax"></a>Syntax

```
class COleBusyDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copabusydialog:: Cotabusydialog](#colebusydialog)|Bir `COleBusyDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotabusydialog::D oModal](#domodal)|OLE sunucusu meşgul iletişim kutusunu görüntüler.|
|[Cotabusydialog:: GetSelectionType](#getselectiontype)|İletişim kutusunda yapılan seçimi belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cotabusydialog:: m_bz](#m_bz)|İletişim kutusunun davranışını denetleyen OLEUıBUSY türünün yapısı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutularını çağırmak istediğinizde, sınıfının bir nesnesini oluşturun `COleBusyDialog` . Bir nesne oluşturulduktan sonra `COleBusyDialog` , iletişim kutusundaki denetimlerin değerlerini veya durumlarını başlatmak için [m_bz](#m_bz) yapısını kullanabilirsiniz. `m_bz`Yapı, OLEUıBUSY türündedir. Bu iletişim kutusu sınıfını kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

> [!NOTE]
> Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için Windows SDK [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) yapısına bakın.

OLE 'e özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

## <a name="colebusydialogcolebusydialog"></a><a name="colebusydialog"></a> Copabusydialog:: Cotabusydialog

Bu işlev yalnızca bir `COleBusyDialog` nesne oluşturur.

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*htaskBusy*<br/>
Meşgul olan sunucu görevinin tanıtıcısı.

*Bnotyanýt*<br/>
DOĞRU ise, sunucu meşgul iletişim kutusu yerine yanıt vermiyor iletişim kutusunu çağırın. Yanıt vermiyor iletişim kutusundaki ifade, sunucu meşgul iletişim kutusundaki düğenden biraz farklıdır ve Iptal düğmesi devre dışıdır.

*dwFlags*<br/>
Oluşturma bayrağı. , Bit düzeyinde OR işleci ile birlikte aşağıdaki değerlerden sıfır veya daha fazlasını içerebilir:

- İletişim kutusu çağrılırken Iptal düğmesini devre dışı BZ_DISABLECANCELBUTTON.

- İletişim kutusu çağrılırken düğmeye geçiş BZ_DISABLESWITCHTOBUTTON devre dışı bırakın.

- İletişim kutusunu çağırırken yeniden dene düğmesini devre dışı BZ_DISABLERETRYBUTTON.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine (türü `CWnd` ) işaret eder. NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu göstermek için [DoModal](#domodal)' ı çağırın.

Daha fazla bilgi için Windows SDK [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) yapısına bakın.

## <a name="colebusydialogdomodal"></a><a name="domodal"></a> Cotabusydialog::D oModal

OLE sunucusu meşgul veya sunucu yanıt vermiyor iletişim kutusunu göstermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu için tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntüleniyorsa ıDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse ıDCANCEL.

- Bir hata oluştuysa ıDADBORT. IDADBORT döndürülürse, `COleDialog::GetLastError` oluşan hata türü hakkında daha fazla bilgi edinmek için üye işlevini çağırın. Olası hataların listesi için Windows SDK [OLEUIBUSY](/windows/win32/api/oledlg/nf-oledlg-oleuibusyw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[M_bz](#m_bz) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmak isterseniz, bunu çağırmadan önce `DoModal` , ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

`DoModal`IDOK döndürürse, Kullanıcı tarafından iletişim kutusuna girilen ayarları veya bilgileri almak için diğer üye işlevlerini çağırabilirsiniz.

## <a name="colebusydialoggetselectiontype"></a><a name="getselectiontype"></a> Cotabusydialog:: GetSelectionType

Sunucu meşgul iletişim kutusunda Kullanıcı tarafından seçilen seçim türünü almak için bu işlevi çağırın.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

Dönüş türü değerleri, `Selection` sınıfında belirtilen numaralandırma türü tarafından belirtilir `COleBusyDialog` .

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

Bu değerlerin kısa açıklamaları şu şekilde yapılır:

- `COleBusyDialog::switchTo` Düğmeye geç düğmesine basılmıştı.

- `COleBusyDialog::retry` Yeniden dene düğmesine basılmıştı.

- `COleBusyDialog::callUnblocked` Sunucuyu etkinleştirme çağrısı artık engellenmektedir.

## <a name="colebusydialogm_bz"></a><a name="m_bz"></a> Cotabusydialog:: m_bz

Sunucu meşgul iletişim kutusunun davranışını denetlemek için kullanılan OLEUıBUSY türünün yapısı.

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri doğrudan veya üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Coeldialog sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Coeldialog sınıfı](../../mfc/reference/coledialog-class.md)
