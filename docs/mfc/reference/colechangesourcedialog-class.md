---
title: COleChangeSourceDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
ms.openlocfilehash: 78da0a495de6ea951deab984550756a2d6f3e2bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321867"
---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog Sınıfı

OLE Change Source iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleChangeSourceDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Bir `COleChangeSourceDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleChangeSourceDialog::DoModal](#domodal)|OLE Change Source iletişim kutusunu görüntüler.|
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Tam kaynak görüntüleme adını alır.|
|[COleChangeSourceDialog::GetFileName](#getfilename)|Dosya adını kaynak adından alır.|
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Önceki kaynağın önekisini alır.|
|[COleChangeSourceDialog::GetItemName](#getitemname)|Madde adını kaynak adından alır.|
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Yeni kaynağın önekisini alır|
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Kaynağın geçerli olup olmadığını gösterir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleChangeSourceDialog::m_cs](#m_cs)|İletişim kutusunun davranışını denetleyen bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu `COleChangeSourceDialog` aramak istediğinizde sınıf nesnesi oluşturun. Bir `COleChangeSourceDialog` nesne oluşturulduktan sonra, iletişim kutusundaki denetimdeğerlerini veya durumlarını açmak için [m_cs](#m_cs) yapısını kullanabilirsiniz. Yapısı `m_cs` tip [OLEUICHANGESOURCE.](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) Bu iletişim sınıfını kullanma hakkında daha fazla bilgi için [DoModal](#domodal) üye işlevine bakın.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

OLE'ye özgü iletişim kutuları hakkında daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="colechangesourcedialogcolechangesourcedialog"></a><a name="colechangesourcedialog"></a>COleChangeSourceDialog::COleChangeSourceDialog

Bu işlev bir `COleChangeSourceDialog` nesne oluşturuyor.

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Kaynağı güncelleştirilecek bağlantılı [COleClientItem](../../mfc/reference/coleclientitem-class.md) işaretçisi.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst `CWnd`veya sahip penceresi nesnesine (tür) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için [DoModal](#domodal) işlevini arayın.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına ve [OleUIChangeSource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) işlevine bakın.

## <a name="colechangesourcedialogdomodal"></a><a name="domodal"></a>COleChangeSourceDialog::DoModal

OLE Change Source iletişim kutusunu görüntülemek için bu işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse İDOK.

- Kullanıcı iletişim kutusunu iptal ettiyse IDCANCEL.

- Bir hata oluştuysa IDABORT. IDABORT döndürülürse, [coleDialog'u arayın::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) üye işlevini arayarak oluşan hata türü hakkında daha fazla bilgi alın. Olası hataların listesi için Windows SDK'daki [OleUIChangeSource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[m_cs](#m_cs) yapının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmayı istiyorsanız, çağrıyapmadan `DoModal`önce ancak iletişim nesnesi oluşturulduktan sonra bunu yapmalısınız.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından girilen ayarları veya bilgileri iletişim kutusundan almak için üye işlevleri arayabilirsiniz. Aşağıdaki liste adları tipik sorgu işlevleri:

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

## <a name="colechangesourcedialoggetdisplayname"></a><a name="getdisplayname"></a>COleChangeSourceDialog::GetDisplayName

Bağlı istemci öğesinin tam görüntü adını almak için bu işlevi arayın.

```
CString GetDisplayName();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturucuda belirtilen [COleClientItem](../../mfc/reference/coleclientitem-class.md) için tam kaynak görüntüleme adı (ad).

## <a name="colechangesourcedialoggetfilename"></a><a name="getfilename"></a>COleChangeSourceDialog::GetFileName

Bağlı istemci öğesi için görüntü adının dosya ad bölümünü almak için bu işlevi arayın.

```
CString GetFileName();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturucuda belirtilen [COleClientItem](../../mfc/reference/coleclientitem-class.md) için kaynak görüntü adının dosya takma öğesi bölümü.

### <a name="remarks"></a>Açıklamalar

Dosya adı, öğe lakabıyla birlikte tam görüntü adını verir.

## <a name="colechangesourcedialoggetfromprefix"></a><a name="getfromprefix"></a>COleChangeSourceDialog::GetFromPrefix

Kaynak için önceki önek dizesini almak için bu işlevi arayın.

```
CString GetFromPrefix();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynağın önceki önek dize.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) IDOK döndükten sonra arayın.

Bu değer doğrudan `lpszFrom` [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısının üyesinden gelir.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

## <a name="colechangesourcedialoggetitemname"></a><a name="getitemname"></a>COleChangeSourceDialog::GetItemName

Bağlı istemci öğesi için görüntü adının öğe ad bölümünü almak için bu işlevi arayın.

```
CString GetItemName();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturucuda belirtilen [COleClientItem](../../mfc/reference/coleclientitem-class.md) için kaynak görüntü adının öğe ad bölümü.

### <a name="remarks"></a>Açıklamalar

Dosya adı, öğe lakabıyla birlikte tam görüntü adını verir.

## <a name="colechangesourcedialoggettoprefix"></a><a name="gettoprefix"></a>COleChangeSourceDialog::GetToPrefix

Kaynak için yeni önek dizesini almak için bu işlevi arayın.

```
CString GetToPrefix();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynağın yeni önek dize.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) IDOK döndükten sonra arayın.

Bu değer doğrudan `lpszTo` [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısının üyesinden gelir.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

## <a name="colechangesourcedialogm_cs"></a><a name="m_cs"></a>COleChangeSourceDialog::m_cs

Bu veri üyesi [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)tipi bir yapıdır.

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>Açıklamalar

`OLEUICHANGESOURCE`OLE Change Source iletişim kutusunun davranışını denetlemek için kullanılır. Bu yapının üyeleri doğrudan değiştirilebilir.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

## <a name="colechangesourcedialogisvalidsource"></a><a name="isvalidsource"></a>COleChangeSourceDialog::IsValidSource

Yeni kaynağın geçerli olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL IsValidSource();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni kaynak geçerliyse sıfırsız, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) IDOK döndükten sonra arayın.

Daha fazla bilgi için Windows SDK'daki [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
