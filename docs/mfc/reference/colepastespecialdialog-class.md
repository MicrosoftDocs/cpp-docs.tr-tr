---
title: COlePasteSpecialDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
ms.openlocfilehash: 47fb421ef9dedcae7f92d33f55988dbbc2ea452d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753821"
---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog Sınıfı

OLE Yapıştır Özel iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Bir `COlePasteSpecialDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COlePasteSpecialDialog::AddFormat](#addformat)|Uygulamanızın yapıştırabileceği biçimler listesine özel biçimler ekler.|
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Desteklenen Pano biçimleri listesine yeni bir giriş ekler.|
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Uygulamanızın yapıştırabileceği biçimler listesine CF_BITMAP, CF_DIB, CF_METAFILEPICT ve isteğe bağlı olarak CF_LINKSOURCE ekler.|
|[COlePasteSpecialDialog::CreateItem](#createitem)|Belirtilen biçimi kullanarak kapsayıcı belgesinde öğeyi oluşturur.|
|[COlePasteSpecialDialog::DoModal](#domodal)|OLE Yapıştır Özel iletişim kutusunu görüntüler.|
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Öğeyi simge olarak çizip çizmeme yiyemeyeceğini söyler.|
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğenin ikonik formuyla ilişkili metadosyaya bir tanıtıcı alır.|
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Kullanıcı tarafından seçilen kullanılabilir yapıştırıla seçeneklerinin dizini alır.|
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Seçilen seçim türünü alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COlePasteSpecialDialog::m_ps](#m_ps)|İletişim kutusunun işlevini kontrol eden OLEUIPASTESPECIAL türünden bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu `COlePasteSpecialDialog` aramak istediğinizde sınıf nesnesi oluşturun. Bir `COlePasteSpecialDialog` nesne oluşturulduktan sonra, iletişim kutusuna Pano biçimlerini eklemek için [AddFormat](#addformat) ve [AddStandardFormats](#addstandardformats) üye işlevlerini kullanabilirsiniz. İletişim [kutusundaki](#m_ps) denetimdeğerlerini veya durumlarını başlatmayı m_ps yapısını da kullanabilirsiniz. Yapısı `m_ps` tip OLEUIPASTESPECIAL'dir.

Daha fazla bilgi için Windows SDK'daki [OLEUIPASTESPECIAL](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) yapısına bakın.

OLE'ye özgü iletişim kutuları yla ilgili daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="colepastespecialdialogaddformat"></a><a name="addformat"></a>COlePasteSpecialDialog::AddFormat

Uygulamanızın özel yapıştır işleminde destekleyebileceği biçimler listesine yeni biçimler eklemek için bu işlevi arayın.

```cpp
void AddFormat(
    const FORMATETC& formatEtc,
    LPTSTR lpszFormat,
    LPTSTR lpszResult,
    DWORD flags);

void AddFormat(
    UINT cf,
    DWORD tymed,
    UINT nFormatID,
    BOOL bEnableIcon,
    BOOL bLink);
```

### <a name="parameters"></a>Parametreler

*Fmt*<br/>
Eklenecek veri türüne başvuru.

*lpszFormat*<br/>
Kullanıcıya biçimi açıklayan dize.

*lpszResult*<br/>
Bu biçim iletişim kutusunda seçilirse sonucu açıklayan dize.

*bayraklar*<br/>
Bu biçim için farklı bağlama ve katıştırma seçenekleri kullanılabilir. Bu bayrak, OLEUIPASTEFLAG numaralandırılmış türündeki farklı değerlerden birinin veya daha fazlasının bitwise kombinasyonudur.

*Cf*<br/>
Eklenecek pano biçimi.

*Tymed*<br/>
Bu biçimde kullanılabilen ortam türleri. Bu, TYMED numaralandırılmış türündeki değerlerden bir veya daha fazlasının bitwise kombinasyonudur.

*nFormatID*<br/>
Bu biçimi tanımlayan dize kimliği. Bu dize biçimi bir '\n' karakteri ile ayrılmış iki ayrı dizeleri dir. İlk dize *lpstrFormat* parametrede geçirilen aynıdır ve ikinci *lpstrResult* parametresi ile aynıdır.

*bEnableIcon*<br/>
Bu biçim liste kutusunda seçildiğinde Simge Olarak Görüntüle onay kutusunun etkinleştirilip etkinleştirilmediğini belirleyen bayrak.

*Yanıp*<br/>
Liste kutusunda bu biçim seçildiğinde Yapıştır Bağlantısı radyo düğmesinin etkin olup olmadığını belirleyen bayrak.

### <a name="remarks"></a>Açıklamalar

Bu işlev, CF_TEXT veya CF_TIFF gibi standart biçimleri veya uygulamanızın sisteme kaydettiği özel biçimleri eklemek için çağrılabilir. Uygulamanıza veri nesnelerini yapıştırma hakkında daha fazla bilgi için [Veri Nesneleri ve Veri Kaynakları: Manipülasyon](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

Daha fazla bilgi için, Windows SDK'daki [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) numaralandırma türü ne ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK'daki [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) numaralandırılmış türüne bakın.

## <a name="colepastespecialdialogaddlinkentry"></a><a name="addlinkentry"></a>COlePasteSpecialDialog::AddLinkEntry

Desteklenen Pano biçimleri listesine yeni bir giriş ekler.

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>Parametreler

*Cf*<br/>
Eklenecek pano biçimi.

### <a name="return-value"></a>Dönüş Değeri

Yeni bağlantı girişiiçin bilgileri içeren bir [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) yapısı.

## <a name="colepastespecialdialogaddstandardformats"></a><a name="addstandardformats"></a>COlePasteSpecialDialog::AddStandardFormats

Uygulamanızın yapıştırabileceği özel bir işlemde destekleyebileceği biçimler listesine aşağıdaki Pano biçimlerini eklemek için bu işlevi arayın:

```cpp
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnableLink*<br/>
Uygulamanızın yapıştırabileceği biçimler listesine CF_LINKSOURCE ekleyip eklemeyin ivediklerini belirleyen bayrak.

### <a name="remarks"></a>Açıklamalar

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **"Gömülü Nesne"**

- (isteğe bağlı olarak) **"Bağlantı Kaynağı"**

Bu biçimler katıştırma ve bağlamayı desteklemek için kullanılır.

## <a name="colepastespecialdialogcolepastespecialdialog"></a><a name="colepastespecialdialog"></a>COlePasteSpecialDialog::COlePasteSpecialDialog

Bir `COlePasteSpecialDialog` nesne inşa eder.

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Oluşturma bayrağı, bitwise-OR işleci kullanarak birleştirilmiş aşağıdaki bayrakların herhangi bir sayı içerir:

- PSF_SELECTPASTE, iletişim kutusu çağrıldığında Yapıştır radyo düğmesinin başlangıçta işaretleneceğini belirtir. PSF_SELECTPASTELINK ile birlikte kullanılamaz. Bu varsayılandır.

- PSF_SELECTPASTELINK, iletişim kutusu çağrıldığında Yapıştır Bağlantısı radyo düğmesinin ilk olarak işaretleneceğini belirtir. PSF_SELECTPASTE ile birlikte kullanılamaz.

- PSF_CHECKDISPLAYASICON, iletişim kutusu çağrıldığında Simge Olarak Görüntüle onay kutusunun ilk olarak işaretli olacağını belirtir.

- PSF_SHOWHELP İletişim kutusu çağrıldığında Yardım düğmesinin görüntüleneceğini belirtir.

*pDataObject*<br/>
Yapıştırma için [COleDataObject'e](../../mfc/reference/coledataobject-class.md) işaret edin. Bu değer NULL ise, `COleDataObject` Pano'dan alır.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst `CWnd`veya sahip penceresi nesnesine (tür) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca `COlePasteSpecialDialog` bir nesne yi inşa eder. İletişim kutusunu görüntülemek için [DoModal](#domodal) işlevini arayın.

Daha fazla bilgi için Windows SDK'daki [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) numaralandırılmış türüne bakın.

## <a name="colepastespecialdialogcreateitem"></a><a name="createitem"></a>COlePasteSpecialDialog::CreateItem

Özel Yapıştır iletişim kutusunda seçilen yeni öğeyi oluşturur.

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>Parametreler

*pNewItem*<br/>
Bir `COleClientItem` örneği işaret edin. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Öğe başarıyla oluşturulduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca [DoModal](#domodal) IDOK döndükten sonra çağrılmalıdır.

## <a name="colepastespecialdialogdomodal"></a><a name="domodal"></a>COlePasteSpecialDialog::DoModal

OLE Yapıştır Özel iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse İDOK.

- Kullanıcı iletişim kutusunu iptal ettiyse IDCANCEL.

- Bir hata oluştuysa IDABORT. IDABORT döndürülürse, `COleDialog::GetLastError` oluşan hata türü hakkında daha fazla bilgi almak için üye işlevi arayın. Olası hataların listesi için Windows SDK'daki [OleUIPasteSpecial](/windows/win32/api/oledlg/nf-oledlg-oleuipastespecialw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[m_ps](#m_ps) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmayı istiyorsanız, çağrıyapmadan `DoModal`önce ancak iletişim nesnesi oluşturulduktan sonra bunu yapmalısınız.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından iletişim kutusuna ayar veya bilgi girişi almak için diğer üye işlevleri arayabilirsiniz.

## <a name="colepastespecialdialoggetdrawaspect"></a><a name="getdrawaspect"></a>COlePasteSpecialDialog::GetDrawAspect

Kullanıcının seçili öğeyi simge olarak görüntülemeyi seçip seçmeyini belirler.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi işlemek için gereken yöntem.

- DVASPECT_CONTENT Görüntülü Ekran simgesi onay kutusu kapatıldığında işaretlenmediyse döndürülür.

- iletişim kutusu kapatıldığında Simge Olarak Görüntüle onay kutusu işaretlenirse DVASPECT_ICON Döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) IDOK döndükten sonra arayın.

Çizim yönü hakkında daha fazla bilgi için Windows SDK'daki [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

## <a name="colepastespecialdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COlePasteSpecialDialog::GetIconicMetafile

Kullanıcı tarafından seçilen öğeyle ilişkili metadosyayı alır.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğenin simgesel yönünü içeren metadosyanın tutamacı, iletişim kutusu **Tamam'ı**seçerek kapatıldığında Simge Olarak Görüntüle onay kutusu seçildiyse; aksi takdirde NULL.

## <a name="colepastespecialdialoggetpasteindex"></a><a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex

Kullanıcının seçtiği girişle ilişkili dizin değerini alır.

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından seçilen `OLEUIPASTEENTRY` yapı dizisine dizin. Yapıştırişlemi gerçekleştirirken seçili dizine karşılık gelen biçim kullanılmalıdır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [OLEUIPASTEENTRY](/windows/win32/api/oledlg/ns-oledlg-oleuipasteentryw) yapısına bakın.

## <a name="colepastespecialdialoggetselectiontype"></a><a name="getselectiontype"></a>COlePasteSpecialDialog::GetSelectionType

Kullanıcının yaptığı seçim türünü belirler.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türünü döndürür.

### <a name="remarks"></a>Açıklamalar

İade türü değerleri, sınıfta `Selection` bildirilen numaralandırma türüne `COlePasteSpecialDialog` göre belirtilir.

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

Bu değerlerin kısa desccriptions izleyin:

- `COlePasteSpecialDialog::pasteLink`Paste Link radyo düğmesi kontrol edildi ve seçilen format standart bir OLE biçimi ydi.

- `COlePasteSpecialDialog::pasteNormal`Paste radyo düğmesi kontrol edildi ve seçilen format standart bir OLE biçimi oldu.

- `COlePasteSpecialDialog::pasteOther`Seçili biçim standart bir OLE biçimi değildir.

- `COlePasteSpecialDialog::pasteStatic`Seçilen biçim bir meta dosyaydı.

## <a name="colepastespecialdialogm_ps"></a><a name="m_ps"></a>COlePasteSpecialDialog::m_ps

Paste Special iletişim kutusunun davranışını kontrol etmek için kullanılan OLEUIPASTESPECIAL tipinin yapısı.

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri doğrudan veya üye işlevler aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK'daki [OLEUIPASTESPECIAL](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
