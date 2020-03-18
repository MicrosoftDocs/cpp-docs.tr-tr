---
title: COlePasteSpecialDialog sınıfı
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
ms.openlocfilehash: f4174369620f14f2d1ac410aa5d756c75097ad0f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421249"
---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog sınıfı

OLE Paste özel iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|`COlePasteSpecialDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[COlePasteSpecialDialog:: AddFormat](#addformat)|Uygulamanızın yapıştırabileceğiniz biçim listesine özel biçimler ekler.|
|[COlePasteSpecialDialog:: AddLinkEntry](#addlinkentry)|Desteklenen Pano biçimleri listesine yeni bir giriş ekler.|
|[COlePasteSpecialDialog:: AddStandardFormats](#addstandardformats)|Uygulamanızın yapıştırabileceğiniz biçim listesine CF_BITMAP, CF_DIB, CF_METAFILEPICT ve isteğe bağlı olarak CF_LINKSOURCE ekler.|
|[COlePasteSpecialDialog:: CreateItem](#createitem)|Öğeyi kapsayıcı belgesinde belirtilen biçimi kullanarak oluşturur.|
|[COlePasteSpecialDialog::D oModal](#domodal)|OLE Paste özel iletişim kutusunu görüntüler.|
|[COlePasteSpecialDialog:: GetDrawAspect](#getdrawaspect)|Öğenin simge olarak mı çizileceğini söyler.|
|[COlePasteSpecialDialog:: Getıconicmetafile](#geticonicmetafile)|Bu öğenin IIC formuyla ilişkili meta dosyası için bir tanıtıcı alır.|
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Kullanıcı tarafından seçilen kullanılabilir yapıştırma seçeneklerinin dizinini alır.|
|[COlePasteSpecialDialog:: GetSelectionType](#getselectiontype)|Seçilen seçimin türünü alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Name|Açıklama|
|----------|-----------------|
|[COlePasteSpecialDialog:: m_ps](#m_ps)|İletişim kutusunun işlevini denetleyen OLEUıPASTESPECIAL türünde bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu çağırmak istediğinizde `COlePasteSpecialDialog` sınıfından bir nesne oluşturun. `COlePasteSpecialDialog` nesnesi oluşturulduktan sonra, iletişim kutusuna Pano biçimleri eklemek için [AddFormat](#addformat) ve [AddStandardFormats](#addstandardformats) üye işlevlerini kullanabilirsiniz. İletişim kutusundaki denetimlerin değerlerini veya durumlarını başlatmak için [m_ps](#m_ps) yapısını da kullanabilirsiniz. `m_ps` yapısı, OLEUııPASTESPECIAL türündedir.

Daha fazla bilgi için Windows SDK [Oleuıpasteözel](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) yapısına bakın.

OLE 'ye özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

##  <a name="addformat"></a>COlePasteSpecialDialog:: AddFormat

Uygulamanızın, yapıştırma özel işleminde destekleyebileceği biçim listesine yeni biçimler eklemek için bu işlevi çağırın.

```
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

*FMT*<br/>
Eklenecek veri türüne başvuru.

*lpszFormat*<br/>
Kullanıcının biçimini açıklayan dize.

*lpszResult*<br/>
İletişim kutusunda Bu biçim seçilirse sonucu açıklayan dize.

*larına*<br/>
Bu biçim için farklı bağlama ve katıştırma seçenekleri mevcuttur. Bu bayrak, OLEUıPASTEFLAG tarafından numaralandırılan türdeki bir veya daha fazla farklı değerin bit düzeyinde birleşimidir.

*CF*<br/>
Eklenecek Pano biçimi.

*TYMED*<br/>
Bu biçimde kullanılabilen medya türleri. Bu, Numaralandırılmış türdeki bir veya daha fazla değerden bit düzeyinde bir birleşimidir.

*nFormatID*<br/>
Bu biçimi tanımlayan dizenin KIMLIĞI. Bu dizenin biçimi, ' \n ' karakteriyle ayrılmış iki ayrı dizelerdir. İlk dize, *Lpstrformat* parametresine geçirilecek olan ve Ikincisi, *lpstrresult* parametresiyle aynı.

*Benableıcon*<br/>
Liste kutusunda Bu biçim seçildiğinde simge olarak göster onay kutusunun etkinleştirilip etkinleştirilmeyeceğini belirleyen bayrak.

*/*<br/>
Liste kutusunda Bu biçim seçildiğinde bağlantıyı Yapıştır radyo düğmesinin etkinleştirilip etkinleştirilmeyeceğini belirleyen bayrak.

### <a name="remarks"></a>Açıklamalar

Bu işlev, CF_TEXT veya CF_TIFF ya da uygulamanızın sisteme kayıtlı olduğu özel biçimler gibi standart biçimleri eklemek için çağrılabilir. Uygulamanıza veri nesneleri yapıştırma hakkında daha fazla bilgi için [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

Daha fazla bilgi için, Windows SDK [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) sabit listesi türüne ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için, Windows SDK ' de numaralandırılmış tür olan [Oleuıpagesteflag](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) ' a bakın.

##  <a name="addlinkentry"></a>COlePasteSpecialDialog:: AddLinkEntry

Desteklenen Pano biçimleri listesine yeni bir giriş ekler.

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>Parametreler

*CF*<br/>
Eklenecek Pano biçimi.

### <a name="return-value"></a>Dönüş Değeri

Yeni bağlantı girişi bilgilerini içeren bir [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) yapısı.

##  <a name="addstandardformats"></a>COlePasteSpecialDialog:: AddStandardFormats

Aşağıdaki Pano biçimlerini uygulamanızın desteklediği biçim listesine eklemek için bu işlevi çağırın:

```
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnableLink*<br/>
Uygulamanızın yapıştırabileceğiniz biçim listesine CF_LINKSOURCE eklenip eklenmeyeceğini belirleyen bayrak.

### <a name="remarks"></a>Açıklamalar

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **"Katıştırılmış nesne"**

- ı **"Bağlantı kaynağı"**

Bu biçimler ekleme ve bağlamayı desteklemek için kullanılır.

##  <a name="colepastespecialdialog"></a>COlePasteSpecialDialog::COlePasteSpecialDialog

`COlePasteSpecialDialog` nesnesi oluşturur.

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Oluşturma bayrağı, bit düzeyinde OR işleci kullanılarak birleştirilmiş aşağıdaki bayrakların herhangi bir sayısını içerir:

- PSF_SELECTPASTE, iletişim kutusu çağrıldığında radyo Yapıştır düğmesinin başlangıçta denetleneceğini belirtir. PSF_SELECTPASTELINK ile birlikte kullanılamaz. Bu varsayılandır.

- PSF_SELECTPASTELINK, iletişim kutusu çağrıldığında bağlantıyı Yapıştır radyo düğmesinin başlangıçta denetleneceğini belirtir. PSF_SELECTPASTE ile birlikte kullanılamaz.

- PSF_CHECKDISPLAYASICON, iletişim kutusu çağrıldığında simge olarak göster onay kutusunun başlangıçta denetleneceğini belirtir.

- PSF_SHOWHELP, iletişim kutusu çağrıldığında Yardım düğmesinin görüntülendiğini belirtir.

*pDataObject*<br/>
Yapıştırma için [birlikte](../../mfc/reference/coledataobject-class.md) kullanılacak bir işaret gösterir. Bu değer NULL ise panodan `COleDataObject` alır.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine (`CWnd`türü) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca bir `COlePasteSpecialDialog` nesnesi oluşturur. İletişim kutusunu göstermek için [DoModal](#domodal) işlevini çağırın.

Daha fazla bilgi için, Windows SDK ' de numaralandırılmış tür olan [Oleuıpagesteflag](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) ' a bakın.

##  <a name="createitem"></a>COlePasteSpecialDialog:: CreateItem

Özel Yapıştır iletişim kutusunda seçilen yeni öğeyi oluşturur.

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>Parametreler

*pNewItem*<br/>
Bir `COleClientItem` örneğine işaret eder. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Öğe başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca, [DoModal](#domodal) IDOK döndürüldüğünde çağrılmalıdır.

##  <a name="domodal"></a>COlePasteSpecialDialog::D oModal

OLE Paste özel iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu için tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntüleniyorsa ıDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse ıDCANCEL.

- Bir hata oluştuysa ıDADBORT. IDADBORT döndürülürse, oluşan hata türü hakkında daha fazla bilgi edinmek için `COleDialog::GetLastError` member işlevini çağırın. Olası hataların listesi için Windows SDK [Oleuııpastespecial](/windows/win32/api/oledlg/nf-oledlg-oleuipastespecialw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[M_ps](#m_ps) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmak istiyorsanız, bunu `DoModal`çağrılmadan önce, ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

`DoModal` ıDOK döndürürse, Kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevlerini çağırabilirsiniz.

##  <a name="getdrawaspect"></a>COlePasteSpecialDialog:: GetDrawAspect

Kullanıcının seçili öğeyi simge olarak görüntülemeyi seçmeyeceğini belirler.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi işlemek için gereken yöntem.

- İletişim kutusu kapatıldığında simge olarak göster onay kutusu işaretlenmediğinde DVASPECT_CONTENT döndürüldü.

- İletişim kutusu kapatıldığında simge olarak göster onay kutusu işaretliyse DVASPECT_ICON döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) , IDOK öğesini döndürdüğünden çağırın.

En boy çizimi hakkında daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

##  <a name="geticonicmetafile"></a>COlePasteSpecialDialog:: Getıconicmetafile

Kullanıcı tarafından seçilen öğeyle ilişkili dosya dosyasını alır.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu, **Tamam**' ı seçerek seçili öğenin ı, simge olarak göster onay kutusu seçilmişse meta dosyası tutamacı Aksi takdirde NULL.

##  <a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex

Kullanıcının seçtiği girdiyle ilişkili dizin değerini alır.

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından seçilen `OLEUIPASTEENTRY` yapıları dizisinin dizini. Yapıştırma işlemi gerçekleştirilirken seçilen dizine karşılık gelen biçim kullanılmalıdır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [OLEUIPASTEENTRY](/windows/win32/api/oledlg/ns-oledlg-oleuipasteentryw) yapısına bakın.

##  <a name="getselectiontype"></a>COlePasteSpecialDialog:: GetSelectionType

Kullanıcının yaptığı seçimin türünü belirler.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türünü döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş türü değerleri, `COlePasteSpecialDialog` sınıfında bildirildiği `Selection` numaralandırma türü tarafından belirtilir.

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

Bu değerlerin kısa açıklaması şunları izler:

- Bağlantıyı Yapıştır radyo düğmesi işaretli `COlePasteSpecialDialog::pasteLink` ve seçilen biçim standart bir OLE biçimidir.

- `COlePasteSpecialDialog::pasteNormal` radyo düğmesi işaretlendi ve seçilen biçim standart OLE biçimiydi.

- `COlePasteSpecialDialog::pasteOther` seçili biçim standart OLE biçimi değil.

- Seçilen biçim bir meta dosyası `COlePasteSpecialDialog::pasteStatic`.

##  <a name="m_ps"></a>COlePasteSpecialDialog:: m_ps

Özel Yapıştır iletişim kutusunun davranışını denetlemek için kullanılan OLEUıPAGESTESPECIAL türünün yapısı.

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri doğrudan veya üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK [Oleuıpasteözel](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
