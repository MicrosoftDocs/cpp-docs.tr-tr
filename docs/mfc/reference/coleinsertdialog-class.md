---
title: COleInsertDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
ms.openlocfilehash: b5de4ff5daa80e1d8727444a4cfd275597e18c08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374969"
---
# <a name="coleinsertdialog-class"></a>COleInsertDialog Sınıfı

OLE Insert Object iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Bir `COleInsertDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleInsertDialog::CreateItem](#createitem)|İletişim kutusunda seçilen öğeyi oluşturur.|
|[COleInsertDialog::DoModal](#domodal)|OLE Insert Object iletişim kutusunu görüntüler.|
|[COleInsertDialog::GetClassID](#getclassid)|CLSID'yi seçilen öğeyle ilişkilendiriyor.|
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Öğeyi simge olarak çizip çizmememi söyler.|
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğenin ikonik formuyla ilişkili metadosyaya bir tanıtıcı alır.|
|[COleInsertDialog::GetPathName](#getpathname)|İletişim kutusunda seçilen dosyaya tam yolu alır.|
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Seçilen nesne türünü alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleInsertDialog::m_io](#m_io)|İletişim kutusunun davranışını kontrol eden OLEUIINSERTOBJECT türünden bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu `COleInsertDialog` aramak istediğinizde sınıf nesnesi oluşturun. Bir `COleInsertDialog` nesne oluşturulduktan sonra, iletişim kutusundaki denetimdeğerlerini veya durumlarını açmak için [m_io](#m_io) yapısını kullanabilirsiniz. Yapısı `m_io` OLEUIINSERTOBJECT tipidir. Bu iletişim sınıfını kullanma hakkında daha fazla bilgi için [DoModal](#domodal) üye işlevine bakın.

> [!NOTE]
> Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için Windows SDK'daki [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) yapısına bakın.

OLE'ye özgü iletişim kutuları yla ilgili daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="coleinsertdialogcoleinsertdialog"></a><a name="coleinsertdialog"></a>COleInsertDialog::COleInsertDialog

Bu işlev yalnızca `COleInsertDialog` bir nesne oluşturuyor.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Bitwise-OR işleci kullanılarak birlilecek aşağıdaki değerlerin herhangi bir sayısını içeren oluşturma bayrağı:

- IOF_SHOWHELP İletişim kutusu çağrıldığında Yardım düğmesinin görüntüleneceğini belirtir.

- IOF_SELECTCREATENEW İletişim kutusu çağrıldığında Yeni Radyo Oluştur düğmesinin seçileceğini belirtir. Bu varsayılandır ve IOF_SELECTCREATEFROMFILE ile kullanılamaz.

- IOF_SELECTCREATEFROMFILE İletişim kutusu çağrıldığında Dosyadan Oluştur radyo düğmesinin seçileceğini belirtir. IOF_SELECTCREATENEW ile kullanılamaz.

- IOF_CHECKLINK Bağlantı onay kutusunun iletişim kutusu çağrıldığında başlangıçta işaretli olacağını belirtir.

- IOF_DISABLELINK Bağlantı onay kutusunun iletişim kutusu çağrıldığında devre dışı bırakıldığını belirtir.

- IOF_CHECKDISPLAYASICON Simge Olarak Görüntü lehinde görüntükutusunun başlangıçta işaretleneceğini, geçerli simgenin görüntüleneceğini ve iletişim kutusu çağrıldığında Simgeyi Değiştir düğmesinin etkinleştirileceğini belirtir.

- IOF_VERIFYSERVERSEXIST, iletişim kutusunun, iletişim kutusu görüntülenmeden önce kayıt veritabanında belirtilen sunucuların var olmasını sağlayarak liste kutusuna eklediği sınıfları doğrulaması gerektiğini belirtir. Bu bayrağı ayarlamak performansı önemli ölçüde bozabilir.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst `CWnd`veya sahip penceresi nesnesine (tür) işaret eder. NULL ise, iletişim nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için [DoModal](#domodal) işlevini arayın.

## <a name="coleinsertdialogcreateitem"></a><a name="createitem"></a>COleInsertDialog::CreateItem

Yalnızca [DoModal](#domodal) IDOK'u döndürürse [COleClientItem](../../mfc/reference/coleclientitem-class.md) türünden bir nesne oluşturmak için bu işlevi arayın.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Oluşturulacak öğeyi işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Öğe oluşturulduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi aramadan önce nesneyi `COleClientItem` ayırmanız gerekir.

## <a name="coleinsertdialogdomodal"></a><a name="domodal"></a>COleInsertDialog::DoModal

OLE Insert Object iletişim kutusunu görüntülemek için bu işlevi arayın.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Aşağıdaki değerlerden biri:

`COleInsertDialog::DocObjectsOnly`yalnızca DocObjects ekler.

`COleInsertDialog::ControlsOnly`yalnızca ActiveX denetimleri ekler.

Sıfır, ne Bir DocObject ne de ActiveX denetimi ekler. Bu değer, yukarıda listelenen ilk prototiple aynı uygulamayla sonuçlanır.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse İDOK.

- Kullanıcı iletişim kutusunu iptal ettiyse IDCANCEL.

- Bir hata oluştuysa IDABORT. IDABORT döndürülürse, [coleDialog'u arayın::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) üye işlevini arayarak oluşan hata türü hakkında daha fazla bilgi alın. Olası hataların listesi için Windows SDK'daki [OleUIInsertObject](/windows/win32/api/oledlg/nf-oledlg-oleuiinsertobjectw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[m_io](#m_io) yapının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmayı istiyorsanız, çağrıyapmadan `DoModal`önce bunu yapmalısınız, ancak iletişim nesnesi oluşturulduktan sonra.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından iletişim kutusuna ayar veya bilgi girişi almak için diğer üye işlevleri arayabilirsiniz.

## <a name="coleinsertdialoggetclassid"></a><a name="getclassid"></a>COleInsertDialog::GetClassID

Seçilen öğeyle ilişkili CLSID'yi yalnızca [DoModal](#domodal) IDOK'u döndürürse ve seçim türü `COleInsertDialog::createNewItem`.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğeyle ilişkili CLSID'yi döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [CLSID Key'e](/windows/win32/com/clsid-key-hklm) bakın.

## <a name="coleinsertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>COleInsertDialog::GetDrawAspect

Kullanıcının seçili öğeyi simge olarak görüntülemeyi seçip seçmediğini belirlemek için bu işlevi arayabilirsiniz.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi işlemek için gereken yöntem.

- DVASPECT_CONTENT Simge Olarak Görüntü le görüntü lenekçe onay kutusu işaretlenmediyse döndürülür.

- DVASPECT_ICON Simge Olarak Görüntü legörüntü onay kutusu işaretlenmişse döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) IDOK'u döndürürse çağırın.

Çizim yönü hakkında daha fazla bilgi için Windows SDK'daki [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) veri yapısına bakın.

## <a name="coleinsertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COleInsertDialog::GetIconicMetafile

Seçili öğenin simgesel yönünü içeren metafile bir tanıtıcı almak için bu işlevi arayın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğenin simgesel yönünü içeren metadosyanın tutamacı, ok **seçilerek**iletişim kutusu kapatıldığında Simge Olarak Görüntüle onay kutusu işaretlenmişse; aksi takdirde NULL.

## <a name="coleinsertdialoggetpathname"></a><a name="getpathname"></a>COleInsertDialog::GetPathName

Yalnızca [DoModal](#domodal) IDOK'u döndürürse ve seçim türü değilse, `COleInsertDialog::createNewItem`seçili dosyanın tam yolunu almak için bu işlevi arayın.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunda seçilen dosyaya tam yol. Seçim türü ise, `createNewItem`bu işlev `CString` sürüm modunda anlamsız bir şekilde döndürür veya hata ayıklama modunda bir tasnife neden olur.

## <a name="coleinsertdialoggetselectiontype"></a><a name="getselectiontype"></a>COleInsertDialog::GetSelectionType

Nesne Ekle iletişim kutusu **Tamam'ı**seçerek kapatıldığında seçim türünü seçmek için bu işlevi arayın.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

İade türü değerleri, sınıfta `Selection` bildirilen numaralandırma türüne `COleInsertDialog` göre belirtilir.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

Bu değerlerin kısa açıklamaları aşağıdaki gibidir:

- `COleInsertDialog::createNewItem`Yeni radyo oluştur düğmesi seçildi.

- `COleInsertDialog::insertFromFile`Dosyadan Oluştur düğmesi radyo bağlantısı seçildi ve Bağlantı onay kutusu işaretlenmedi.

- `COleInsertDialog::linkToFile`Dosyadan Oluştur düğmesi radyo bağlantısı seçildi ve Bağlantı onay kutusu işaretlendi.

## <a name="coleinsertdialogm_io"></a><a name="m_io"></a>COleInsertDialog::m_io

Nesne Ekle iletişim kutusunun davranışını denetlemek için kullanılan OLEUIINSERTOBJECT türünün yapısı.

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri doğrudan veya üye işlevler aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK'daki [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
