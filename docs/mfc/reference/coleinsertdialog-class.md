---
title: Cotaınsertdialog sınıfı
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
ms.openlocfilehash: a884f946b60be0567f39477f434db8efe041e393
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503937"
---
# <a name="coleinsertdialog-class"></a>Cotaınsertdialog sınıfı

OLE nesne Ekle iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotaınsertdialog:: Cotaınsertdialog](#coleinsertdialog)|Bir `COleInsertDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Colet ınsertdialog:: CreateItem](#createitem)|İletişim kutusunda seçilen öğeyi oluşturur.|
|[Colet ınsertdialog::D oModal](#domodal)|OLE nesne Ekle iletişim kutusunu görüntüler.|
|[Colet ınsertdialog:: GetClassID](#getclassid)|Seçili öğeyle ilişkili CLSID 'yi alır.|
|[Cotaınsertdialog:: GetDrawAspect](#getdrawaspect)|Öğenin bir simge olarak çizip çizmeyeceğini söyler.|
|[Cotaınsertdialog:: Getıconicmetafile](#geticonicmetafile)|Bu öğenin IIC formuyla ilişkili meta dosyası için bir tanıtıcı alır.|
|[Colet ınsertdialog:: GetPathName](#getpathname)|İletişim kutusunda seçilen dosyanın tam yolunu alır.|
|[Cotaınsertdialog:: GetSelectionType](#getselectiontype)|Seçilen nesne türünü alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Colet ınsertdialog:: m_io](#m_io)|İletişim kutusunun davranışını denetleyen OLEUııNSERTOBJECT türünde bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu çağırmak istediğinizde `COleInsertDialog` , sınıfının bir nesnesi oluşturun. Bir `COleInsertDialog` nesne oluşturulduktan sonra, iletişim kutusundaki denetimlerin değerlerini veya durumlarını başlatmak için [m_io](#m_io) yapısını kullanabilirsiniz. `m_io` Yapı, OleUIInsertObject türündedir. Bu iletişim kutusu sınıfını kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için Windows SDK [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) yapısına bakın.

OLE 'ye özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

##  <a name="coleinsertdialog"></a>Cotaınsertdialog:: Cotaınsertdialog

Bu işlev yalnızca bir `COleInsertDialog` nesnesi oluşturur.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilecek aşağıdaki değerlerin sayısını içeren oluşturma bayrağı:

- IOF_SHOWHELP iletişim kutusu çağrıldığında Yardım düğmesinin görüntülendiğini belirtir.

- IOF_SELECTCREATENEW iletişim kutusu çağrıldığında yeni radyo oluştur düğmesinin başlangıçta seçili olacağını belirtir. Bu varsayılandır ve IOF_SELECTCREATEFROMFILE ile kullanılamaz.

- IOF_SELECTCREATEFROMFILE iletişim kutusu çağrıldığında Dosyadan Oluştur radyo düğmesinin başlangıçta seçili olacağını belirtir. IOF_SELECTCREATENEW ile kullanılamaz.

- IOF_CHECKLINK iletişim kutusu çağrıldığında bağlantı onay kutusunun başlangıçta denetleneceğini belirtir.

- IOF_DISABLELINK iletişim kutusu çağrıldığında bağlantı onay kutusunun devre dışı bırakılacağını belirtir.

- IOF_CHECKDISPLAYASICON başlangıçta simge olarak göster onay kutusunun işaretli olacağını, geçerli simgenin görüntülendiğini ve iletişim kutusu çağrıldığında simge değiştir düğmesinin etkinleştirileceğini belirtir.

- IOF_VERIFYSERVERSEXIST iletişim kutusunun, kayıt veritabanında belirtilen sunucuların iletişim kutusu görüntülenmeden önce mevcut olduğundan emin olarak liste kutusuna eklediği sınıfları doğrulaması gerektiğini belirtir. Bu bayrağın ayarlanması, performansı önemli ölçüde azaltabilir.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine (türü `CWnd`) işaret eder. NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu göstermek için [DoModal](#domodal) işlevini çağırın.

##  <a name="createitem"></a>Colet ınsertdialog:: CreateItem

Yalnızca [DoModal](#domodal) IDOK döndürürse [Cotaclientidıtem](../../mfc/reference/coleclientitem-class.md) türünde bir nesne oluşturmak için bu işlevi çağırın.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Oluşturulacak öğeyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Öğe oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırabilmeniz `COleClientItem` için önce nesneyi ayırmanız gerekir.

##  <a name="domodal"></a>Colet ınsertdialog::D oModal

OLE nesne Ekle iletişim kutusunu göstermek için bu işlevi çağırın.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Aşağıdaki değerlerden biri:

`COleInsertDialog::DocObjectsOnly`yalnızca DocObjects ekler.

`COleInsertDialog::ControlsOnly`yalnızca ActiveX denetimleri ekler.

Sıfır ne bir DocObject ne de bir ActiveX denetimi ekler. Bu değer, yukarıda listelenen ilk prototiple aynı uygulamayla sonuçlanır.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu için tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntüleniyorsa ıDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse ıDCANCEL.

- Bir hata oluştuysa ıDADBORT. IDADBORT döndürülürse, oluşan hata türü hakkında daha fazla bilgi edinmek için [Cotadialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) üye işlevini çağırın. Olası hataların listesi için Windows SDK [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/nf-oledlg-oleuiinsertobjectw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[M_io](#m_io) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmak isterseniz, bunu çağırmadan `DoModal`önce, ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

IDOK `DoModal` döndürürse, Kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevlerini çağırabilirsiniz.

##  <a name="getclassid"></a>Colet ınsertdialog:: GetClassID

Seçili öğeyle ilişkili CLSID 'yi almak için bu işlevi çağırın, ancak [DoModal](#domodal) IDOK döndürürse ve seçim türü ise `COleInsertDialog::createNewItem`.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğeyle ilişkili CLSID 'yi döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [CLSID anahtarı](/windows/win32/com/clsid-key-hklm) bölümüne bakın.

##  <a name="getdrawaspect"></a>Cotaınsertdialog:: GetDrawAspect

Kullanıcının seçili öğeyi bir simge olarak görüntülemeyi seçmemeyi öğrenmek için bu işlevi çağırın.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi işlemek için gereken yöntem.

- Simge olarak göster onay kutusu işaretli değilse, DVASPECT_CONTENT döndürüldü.

- Simge olarak göster onay kutusu işaretliyse DVASPECT_ICON döndürüldü.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) IDOK döndürürse çağırın.

En boy çizimi hakkında daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) veri yapısına bakın.

##  <a name="geticonicmetafile"></a>Cotaınsertdialog:: Getıconicmetafile

Seçili öğenin ıfıic boyutunu içeren meta dosyasına bir tanıtıcı almak için bu işlevi çağırın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğenin ı, simge olarak göster onay kutusu, **Tamam**' ı seçerek bir iletişim kutusu kapatıldığında, bu dosya için bir işleyici işaretlendi. Aksi takdirde NULL.

##  <a name="getpathname"></a>Colet ınsertdialog:: GetPathName

Seçili dosyanın tam yolunu almak için bu işlevi çağırın, ancak [DoModal](#domodal) IDOK döndürürse ve seçim türü değilse `COleInsertDialog::createNewItem`.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunda seçilen dosyanın tam yolu. Seçim türü ise `createNewItem`, bu işlev yayın modunda anlamlı bir less `CString` döndürür veya hata ayıklama modunda bir onaylama işlemi oluşmasına neden olur.

##  <a name="getselectiontype"></a>Cotaınsertdialog:: GetSelectionType

Nesne Ekle iletişim kutusu kapatıldığında seçili seçim türünü almak için bu işlevi çağırın.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

Dönüş türü değerleri, `Selection` `COleInsertDialog` sınıfında belirtilen numaralandırma türü tarafından belirtilir.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

Bu değerlerin kısa açıklamaları şu şekilde yapılır:

- `COleInsertDialog::createNewItem`Yeni radyo oluştur düğmesi seçildi.

- `COleInsertDialog::insertFromFile`Dosyadan Oluştur radyo düğmesi seçilmiştir ve bağlantı onay kutusu işaretlenmedi.

- `COleInsertDialog::linkToFile`Dosyadan Oluştur radyo düğmesi seçildi ve bağlantı onay kutusu denetlendi.

##  <a name="m_io"></a>Colet ınsertdialog:: m_io

Nesne Ekle iletişim kutusunun davranışını denetlemek için kullanılan OLEUııNSERTOBJECT türünde yapı.

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri, doğrudan veya üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
