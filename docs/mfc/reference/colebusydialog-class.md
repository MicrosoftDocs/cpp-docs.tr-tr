---
title: COleBusyDialog Sınıfı
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
ms.openlocfilehash: 5be42463c08cacd83de84900fb4d98771774e897
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364251"
---
# <a name="colebusydialog-class"></a>COleBusyDialog Sınıfı

OLE Server Yanıt Vermiyor veya Server Busy iletişim kutuları için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleBusyDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Bir `COleBusyDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleBusyDialog::DoModal](#domodal)|OLE Server Meşgul iletişim kutusunu görüntüler.|
|[COleBusyDialog::GetSelectionType](#getselectiontype)|İletişim kutusunda yapılan seçimi belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleBusyDialog::m_bz](#m_bz)|İletişim kutusunun davranışını kontrol eden OLEUIBUSY tipinin yapısı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutularını çağırmak `COleBusyDialog` istediğinizde sınıf nesnesi oluşturun. Bir `COleBusyDialog` nesne oluşturulduktan sonra, iletişim kutusundaki denetimdeğerlerini veya durumlarını açmak için [m_bz](#m_bz) yapısını kullanabilirsiniz. Yapısı `m_bz` tip OLEUIBUSY olduğunu. Bu iletişim sınıfını kullanma hakkında daha fazla bilgi için [DoModal](#domodal) üye işlevine bakın.

> [!NOTE]
> Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için Windows SDK'daki [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) yapısına bakın.

OLE'ye özgü iletişim kutuları hakkında daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="colebusydialogcolebusydialog"></a><a name="colebusydialog"></a>COleBusyDialog::COleBusyDialog

Bu işlev yalnızca `COleBusyDialog` bir nesne yi inşa eder.

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*htaskBusy*<br/>
Meşgul sunucu görevi için işleme.

*bNotResponding*<br/>
TRUE ise, Sunucu Meşgul iletişim kutusu yerine Yanıtlanamayan iletişim kutusunu arayın. Yanıt vermiyor iletişim kutusundaki ifadeler Sunucu Meşgul iletişim kutusundaki ifadelerden biraz farklıdır ve İptal düğmesi devre dışı bırakılır.

*Dwflags*<br/>
Yaratılış bayrağı. Bitwise-OR işleci ile birlikte aşağıdaki değerlerin sıfır veya daha fazlasını içerebilir:

- BZ_DISABLECANCELBUTTON iletişim kutusunu ararken İptal düğmesini devre dışı kalın.

- BZ_DISABLESWITCHTOBUTTON iletişim kutusunu ararken Geçiş düğmesini devre dışı kalın.

- BZ_DISABLERETRYBUTTON iletişim kutusunu ararken Yeniden Deneme düğmesini devre dışı kalın.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst `CWnd`veya sahip penceresi nesnesine (tür) işaret eder. NULL ise, iletişim nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için [DoModal'ı](#domodal)arayın.

Daha fazla bilgi için Windows SDK'daki [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) yapısına bakın.

## <a name="colebusydialogdomodal"></a><a name="domodal"></a>COleBusyDialog::DoModal

OLE Server Busy veya Server Not Responding iletişim kutusunu görüntülemek için bu işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse İDOK.

- Kullanıcı iletişim kutusunu iptal ettiyse IDCANCEL.

- Bir hata oluştuysa IDABORT. IDABORT döndürülürse, `COleDialog::GetLastError` oluşan hata türü hakkında daha fazla bilgi almak için üye işlevi arayın. Olası hataların listesi için Windows SDK'daki [OleUIBusy](/windows/win32/api/oledlg/nf-oledlg-oleuibusyw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[m_bz](#m_bz) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmayı istiyorsanız, çağrıyapmadan `DoModal`önce bunu yapmalısınız, ancak iletişim nesnesi oluşturulduktan sonra.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından girilen ayarları veya bilgileri iletişim kutusuna almak için diğer üye işlevleri arayabilirsiniz.

## <a name="colebusydialoggetselectiontype"></a><a name="getselectiontype"></a>COleBusyDialog::GetSelectionType

Sunucu Meşgul iletişim kutusunda kullanıcı tarafından seçilen seçim türünü almak için bu işlevi arayın.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

İade türü değerleri, sınıfta `Selection` bildirilen numaralandırma türüne `COleBusyDialog` göre belirtilir.

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

Bu değerlerin kısa açıklamaları aşağıdaki gibidir:

- `COleBusyDialog::switchTo`Switch To düğmesine basıldı.

- `COleBusyDialog::retry`Yeniden deneme düğmesine basıldı.

- `COleBusyDialog::callUnblocked`Sunucuyu etkinleştirmek için yapılan aramanın engeli kaldırıldı.

## <a name="colebusydialogm_bz"></a><a name="m_bz"></a>COleBusyDialog::m_bz

Sunucu Meşgul iletişim kutusunun davranışını denetlemek için kullanılan OLEUIBUSY türünün yapısı.

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri doğrudan veya üye işlevler aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK'daki [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
