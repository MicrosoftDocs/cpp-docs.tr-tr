---
description: 'Daha fazla bilgi edinin: Cotachangeicondialog sınıfı'
title: Colet Changeicondialog sınıfı
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
ms.openlocfilehash: 5ec6113bbcf63462380f18c4ac52abbb8706c8d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209964"
---
# <a name="colechangeicondialog-class"></a>Colet Changeicondialog sınıfı

OLE Change Icon iletişim kutusu için kullanılır.

## <a name="syntax"></a>Syntax

```
class COleChangeIconDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Colet Changeicondialog:: Cotachangeicondialog](#colechangeicondialog)|Bir `COleChangeIconDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Colet Changeicondialog::D Ochangeıcon](#dochangeicon)|İletişim kutusunda belirtilen değişikliği gerçekleştirir.|
|[Colet Changeicondialog::D oModal](#domodal)|OLE 2 simge Değiştir iletişim kutusunu görüntüler.|
|[Colet Changeicondialog:: Getıconicmetafile](#geticonicmetafile)|Bu öğenin IIC formuyla ilişkili meta dosyası için bir tanıtıcı alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Colet Changeicondialog:: m_ci](#m_ci)|İletişim kutusunun davranışını denetleyen bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu çağırmak istediğinizde, sınıfının bir nesnesi oluşturun `COleChangeIconDialog` . Bir nesne oluşturulduktan sonra `COleChangeIconDialog` , iletişim kutusundaki denetimlerin değerlerini veya durumlarını başlatmak için [m_ci](#m_ci) yapısını kullanabilirsiniz. `m_ci`Yapı, OLEUICHANGEıCON türündedir. Bu iletişim kutusu sınıfını kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

Daha fazla bilgi için Windows SDK [Oleuichangeıcon](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) yapısına bakın.

OLE 'e özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

`COleChangeIconDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

## <a name="colechangeicondialogcolechangeicondialog"></a><a name="colechangeicondialog"></a> Colet Changeicondialog:: Cotachangeicondialog

Bu işlev yalnızca bir `COleChangeIconDialog` nesnesi oluşturur.

```
explicit COleChangeIconDialog(
    COleClientItem* pItem,
    DWORD dwFlags = CIF_SELECTCURRENT,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülecek öğeyi işaret eder.

*dwFlags*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilmiş aşağıdaki değerlerin sayısını içeren oluşturma bayrağı:

- CIF_SELECTCURRENT, iletişim kutusu çağrıldığında geçerli radyo düğmesinin başlangıçta seçili olacağını belirtir. Bu varsayılan seçenektir.

- CIF_SELECTDEFAULT, iletişim kutusu çağrıldığında varsayılan radyo düğmesinin başlangıçta seçili olacağını belirtir.

- CIF_SELECTFROMFILE, iletişim kutusu çağrıldığında dosya radyo düğmesinin başlangıçta seçilecektir.

- CIF_SHOWHELP, iletişim kutusu çağrıldığında Yardım düğmesinin görüntülendiğini belirtir.

- CIF_USEICONEXE, simgenin, `szIconExe` türden alınmak yerine [m_ci](#m_ci) alanında belirtilen yürütülebilir dosyadan ayıklanmasını belirtir. Bu, OLE olmayan dosyalara ekleme veya bağlama için kullanışlıdır.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine (türü `CWnd` ) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu göstermek için [DoModal](#domodal) işlevini çağırın.

Daha fazla bilgi için Windows SDK [Oleuichangeıcon](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) yapısına bakın.

## <a name="colechangeicondialogdochangeicon"></a><a name="dochangeicon"></a> Colet Changeicondialog::D Ochangeıcon

Bu işlevi, [DoModal](#domodal) , IDOK döndürbaşladıktan sonra iletişim kutusunda seçili bir öğeyi temsil eden simgeyi değiştirmek için çağırın.

```
BOOL DoChangeIcon(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Simgesi değişen öğeyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Değişiklik başarılı olursa sıfır dışı; Aksi takdirde 0.

## <a name="colechangeicondialogdomodal"></a><a name="domodal"></a> Colet Changeicondialog::D oModal

OLE Change Icon iletişim kutusunu göstermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu için tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntüleniyorsa ıDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse ıDCANCEL.

- Bir hata oluştuysa ıDADBORT. IDADBORT döndürülürse, `COleDialog::GetLastError` oluşan hata türü hakkında daha fazla bilgi edinmek için üye işlevini çağırın. Olası hataların listesi için Windows SDK [Oleuichangeıcon](/windows/win32/api/oledlg/nf-oledlg-oleuichangeiconw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[M_ci](#m_ci) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmak isterseniz, bunu çağırmadan önce `DoModal` , ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

`DoModal`IDOK döndürürse, Kullanıcı tarafından iletişim kutusuna girilen ayarları veya bilgileri almak için diğer üye işlevlerini çağırabilirsiniz.

## <a name="colechangeicondialoggeticonicmetafile"></a><a name="geticonicmetafile"></a> Colet Changeicondialog:: Getıconicmetafile

Seçili öğenin ıfıic boyutunu içeren meta dosyasına bir tanıtıcı almak için bu işlevi çağırın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu **Tamam**' ı seçerek, yeni simgenin ıfer en boy oranını içeren dosya tanıtıcısı. Aksi halde, iletişim kutusu görüntülenmeden önceki simgesi.

## <a name="colechangeicondialogm_ci"></a><a name="m_ci"></a> Colet Changeicondialog:: m_ci

Simge Değiştir iletişim kutusunun davranışını denetlemek için kullanılan OLEUICHANGEıCON türü yapı.

```
OLEUICHANGEICON m_ci;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri, doğrudan veya üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK [Oleuichangeıcon](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Coeldialog sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Coeldialog sınıfı](../../mfc/reference/coledialog-class.md)
