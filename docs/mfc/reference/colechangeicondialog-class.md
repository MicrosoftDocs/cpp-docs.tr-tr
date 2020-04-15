---
title: COleChangeIconDialog Sınıfı
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
ms.openlocfilehash: 6cdc0ed6bfa4765817de8b7628f339db5e7e5bf5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369629"
---
# <a name="colechangeicondialog-class"></a>COleChangeIconDialog Sınıfı

OLE Değiştir Simgesi iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleChangeIconDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Bir `COleChangeIconDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|İletişim kutusunda belirtilen değişikliği gerçekleştirir.|
|[COleChangeIconDialog::DoModal](#domodal)|OLE 2 Change Icon iletişim kutusunu görüntüler.|
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğenin ikonik formuyla ilişkili metadosyaya bir tanıtıcı alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleChangeIconDialog::m_ci](#m_ci)|İletişim kutusunun davranışını denetleyen bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu `COleChangeIconDialog` aramak istediğinizde sınıf nesnesi oluşturun. Bir `COleChangeIconDialog` nesne oluşturulduktan sonra, iletişim kutusundaki denetimdeğerlerini veya durumlarını açmak için [m_ci](#m_ci) yapısını kullanabilirsiniz. Yapısı `m_ci` tip OLEUICHANGEICON olduğunu. Bu iletişim sınıfını kullanma hakkında daha fazla bilgi için [DoModal](#domodal) üye işlevine bakın.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) yapısına bakın.

OLE'ye özgü iletişim kutuları hakkında daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeIconDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="colechangeicondialogcolechangeicondialog"></a><a name="colechangeicondialog"></a>COleChangeIconDialog::COleChangeIconDialog

Bu işlev yalnızca `COleChangeIconDialog` bir nesne oluşturuyor.

```
explicit COleChangeIconDialog(
    COleClientItem* pItem,
    DWORD dwFlags = CIF_SELECTCURRENT,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülecek öğeyi işaret edin.

*Dwflags*<br/>
Bitwise-or işleci kullanılarak birleştirilen aşağıdaki değerlerin herhangi bir sayısını içeren oluşturma bayrağı:

- CIF_SELECTCURRENT İletişim kutusu çağrıldığında Geçerli radyo düğmesinin seçileceğini belirtir. Bu varsayılandır.

- CIF_SELECTDEFAULT İletişim kutusu çağrıldığında varsayılan radyo düğmesinin seçileceğini belirtir.

- CIF_SELECTFROMFILE İletişim kutusu çağrıldığında Dosyadan Radyo düğmesinin seçileceğini belirtir.

- CIF_SHOWHELP İletişim kutusu çağrıldığında Yardım düğmesinin görüntüleneceğini belirtir.

- CIF_USEICONEXE Simgenin türden alınmak yerine `szIconExe` [m_ci](#m_ci) alanında belirtilen yürütülebilir maddeden ayıklanması gerektiğini belirtir. Bu, OLE olmayan dosyaları katıştırmak veya bağlamak için yararlıdır.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst `CWnd`veya sahip penceresi nesnesine (tür) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için [DoModal](#domodal) işlevini arayın.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) yapısına bakın.

## <a name="colechangeicondialogdochangeicon"></a><a name="dochangeicon"></a>COleChangeIconDialog::DoChangeIcon

[DoModal](#domodal) IDOK döndükten sonra öğeyi temsil eden simgeyi iletişim kutusunda seçilen simgeyle değiştirmek için bu işlevi arayın.

```
BOOL DoChangeIcon(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Simgesi değişen öğeyi işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Değişiklik başarılı olursa sıfırsız; aksi takdirde 0.

## <a name="colechangeicondialogdomodal"></a><a name="domodal"></a>COleChangeIconDialog::DoModal

OLE Değiştir Simgesi iletişim kutusunu görüntülemek için bu işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse İDOK.

- Kullanıcı iletişim kutusunu iptal ettiyse IDCANCEL.

- Bir hata oluştuysa IDABORT. IDABORT döndürülürse, `COleDialog::GetLastError` oluşan hata türü hakkında daha fazla bilgi almak için üye işlevi arayın. Olası hataların listesi için Windows SDK'daki [OleUIChangeIcon](/windows/win32/api/oledlg/nf-oledlg-oleuichangeiconw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[m_ci](#m_ci) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmayı istiyorsanız, çağrıyapmadan `DoModal`önce bunu yapmalısınız, ancak iletişim nesnesi oluşturulduktan sonra.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından girilen ayarları veya bilgileri iletişim kutusuna almak için diğer üye işlevleri arayabilirsiniz.

## <a name="colechangeicondialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COleChangeIconDialog::GetIconicMetafile

Seçili öğenin simgesel yönünü içeren metafile bir tanıtıcı almak için bu işlevi arayın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu **Tamam**seçilerek kapatılmışsa, yeni simgenin simgesel yönünü içeren metadosyanın tutamacı; aksi takdirde, iletişim kutusu görüntülenmeden önceki simge.

## <a name="colechangeicondialogm_ci"></a><a name="m_ci"></a>COleChangeIconDialog::m_ci

Değiştir Simgesi iletişim kutusunun davranışını denetlemek için kullanılan OLEUICHANGEICON türünün yapısı.

```
OLEUICHANGEICON m_ci;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri doğrudan veya üye işlevler aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
