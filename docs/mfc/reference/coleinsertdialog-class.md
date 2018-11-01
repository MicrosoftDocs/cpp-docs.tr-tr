---
title: Coleınsertdialog sınıfı
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
ms.openlocfilehash: c99344c71d3f9789905516d661749b3668b57d50
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546321"
---
# <a name="coleinsertdialog-class"></a>Coleınsertdialog sınıfı

OLE Insert Object iletişim kutusu için kullanıldı.

## <a name="syntax"></a>Sözdizimi

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Oluşturur bir `COleInsertDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleInsertDialog::CreateItem](#createitem)|İletişim kutusunda seçili öğe oluşturur.|
|[COleInsertDialog::DoModal](#domodal)|OLE Insert Object iletişim kutusu görüntüler.|
|[COleInsertDialog::GetClassID](#getclassid)|Seçili öğeyle ilişkili CLSID alır.|
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Bir simge olarak öğeyi çizmek bu seçeneği bildirir.|
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğenin icon formla ilişkili meta dosyası için bir tanıtıcı alır.|
|[COleInsertDialog::GetPathName](#getpathname)|İletişim kutusunda seçilen dosyanın tam yolunu alır.|
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Seçili nesnenin türünü alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleInsertDialog::m_io](#m_io)|İletişim kutusunun davranışını kontrol eden OLEUIINSERTOBJECT türünden bir yapıyı.|

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi oluşturma `COleInsertDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COleInsertDialog` nesne oluşturulur, kullanabileceğiniz [m_io](#m_io) yapısı değerleri veya durumları iletişim kutusundaki denetimlerin başlatılamadı. `m_io` OLEUIINSERTOBJECT türünü yapısıdır. Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Daha fazla bilgi için [OLEUIINSERTOBJECT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta) Windows SDK'sındaki yapısı.

Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxodlgs.h

##  <a name="coleinsertdialog"></a>  COleInsertDialog::COleInsertDialog

Bu işlev yalnızca oluşturan bir `COleInsertDialog` nesne.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilen için aşağıdaki değerlerden herhangi bir sayı içeren oluşturma bayrağı:

- IOF_SHOWHELP iletişim kutusu çağrıldığında Yardım düğmesini gösterileceğini belirtir.

- Yeni Oluştur radyo düğmesinin olacak IOF_SELECTCREATENEW belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını seçili. Bu varsayılandır ve IOF_SELECTCREATEFROMFILE ile kullanılamaz.

- Dosyadan Oluştur radyo düğmesini olacak IOF_SELECTCREATEFROMFILE belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını seçili. IOF_SELECTCREATENEW ile kullanılamaz.

- Bağlantı onay kutusunu olacak IOF_CHECKLINK belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını işaretli.

- İletişim kutusu çağrıldığında IOF_DISABLELINK bağlantı onay kutusunu belirtir devre dışı bırakılır.

- IOF_CHECKDISPLAYASICON simge olarak görüntüle onay kutusu ilk denetlenecek, geçerli simgesi görüntülenir ve iletişim kutusunu çağrıldığında Simge Değiştir düğmesi etkin belirtir.

- İletişim kutusu sınıfları doğrulamalıdır IOF_VERIFYSERVERSEXIST belirten bir iletişim kutusu görüntülenmeden önce belirtilen kayıt defteri veritabanındaki sunucular mevcut sağlayarak liste kutusuna ekler. Bu bayrak ayarlandığında, performansı önemli ölçüde bozabilir.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür `CWnd`) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim nesnenin üst pencere ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için çağrı [DoModal](#domodal) işlevi.

##  <a name="createitem"></a>  COleInsertDialog::CreateItem

Türünde bir nesne oluşturmak için bu işlevi çağırın [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) yalnızca [DoModal](#domodal) IDOK döndürür.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Oluşturulacak öğe işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Öğesi oluşturulduğu andaki olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ayırmanız gerekir `COleClientItem` bu işlev çağrı yapmadan önce nesne.

##  <a name="domodal"></a>  COleInsertDialog::DoModal

OLE Insert Object iletişim kutusunu görüntülemek için bu işlevi çağırın.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
Aşağıdaki değerlerden biri:

`COleInsertDialog::DocObjectsOnly` yalnızca DocObjects ekler.

`COleInsertDialog::ControlsOnly` ActiveX denetimleri ekler.

Sıfır, bir DocObject ne bir ActiveX denetimi ekler. Bu değer sonuçları ilk prototip olarak aynı uygulamada, yukarıda listelenen.

### <a name="return-value"></a>Dönüş Değeri

Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse IDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse IDCANCEL.

- Bir hata oluşursa IDABORT. IDABORT döndürülürse, çağrı [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) konusu hatanın türü hakkında daha fazla bilgi almak için üye işlevi. Olası hataları bir listesi için bkz. [OleUIInsertObject](/windows/desktop/api/oledlg/nf-oledlg-oleuiinsertobjecta) Windows SDK'sında işlev.

### <a name="remarks"></a>Açıklamalar

Çeşitli iletişim kutusu denetimleri üyeleri ayarlayarak başlatmak istiyorsanız [m_io](#m_io) yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.

Varsa `DoModal` döndürür IDOK, diğer üye ayarları veya kullanıcı tarafından iletişim kutusuna giriş bilgileri almak için işlevleri çağırabilir.

##  <a name="getclassid"></a>  COleInsertDialog::GetClassID

Seçili öğeyi yalnızca ilişkili CLSID almak için bu işlevi çağırın [DoModal](#domodal) IDOK ve seçim türü döndürür `COleInsertDialog::createNewItem`.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğeyle ilişkili CLSID değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CLSID anahtar](/windows/desktop/com/clsid-key-hklm) Windows SDK.

##  <a name="getdrawaspect"></a>  COleInsertDialog::GetDrawAspect

Simge olarak seçilen öğeyi görüntülemek bir kullanıcı seçerseniz belirlemek için bu işlevi çağırın.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi işlemek için gereken yöntem.

- Simge olarak görüntüle onay kutusunun işaretli değilse DVASPECT_ICON döndürdü.

- Simge olarak görüntüle onay kutusunu işaretlediyseniz DVASPECT_ICON döndürdü.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca, çağrı [DoModal](#domodal) IDOK döndürür.

En boy çizim daha fazla bilgi için bkz: [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK'sındaki veri yapısı.

##  <a name="geticonicmetafile"></a>  COleInsertDialog::GetIconicMetafile

Seçilen öğenin icon boy içeren meta dosyası için bir tanıtıcı almak için bu işlevi çağırın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Simge olarak görüntüle onay kutusu ise seçili öğe icon yönüyle içeren meta tanıtıcısını seçerek iletişim zaman sonlandırıldı işaretli **Tamam**; Aksi takdirde NULL.

##  <a name="getpathname"></a>  COleInsertDialog::GetPathName

Seçili dosya eksikse tam yolunu almak için bu işlevi çağırın [DoModal](#domodal) IDOK ve seçim türü döndürür `COleInsertDialog::createNewItem`.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunda seçili dosyanın tam yolu. Seçim türü ise `createNewItem`, bu işlev bir anlamsız döndürür `CString` yayın modunda veya onaylama, hata ayıklama modunda neden olur.

##  <a name="getselectiontype"></a>  COleInsertDialog::GetSelectionType

Nesne Ekle iletişim kutusunu seçerek zaman sonlandırıldı seçilen seçim türü almak için bu işlevi çağırın **Tamam**.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

Dönüş türü değerleri tarafından belirtilen `Selection` numaralandırma türü içinde bildirilen `COleInsertDialog` sınıfı.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

Bu değerleri kısa açıklamaları izleyin:

- `COleInsertDialog::createNewItem` Yeni Oluştur radyo düğmesi seçilmiştir.

- `COleInsertDialog::insertFromFile` Dosyadan Oluştur radyo düğmesini seçili ve bağlantı onay kutusunun işaretlenmemiş.

- `COleInsertDialog::linkToFile` Dosyadan Oluştur radyo düğmesini seçili ve bağlantı onay kutusunu denetlendi.

##  <a name="m_io"></a>  COleInsertDialog::m_io

Yapı türünü OLEUIINSERTOBJECT Insert Object iletişim kutusu davranışını denetlemek için kullanılır.

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyelerine, doğrudan ya da üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için [OLEUIINSERTOBJECT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta) Windows SDK'sındaki yapısı.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek OCLIENT](../../visual-cpp-samples.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
