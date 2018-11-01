---
title: COleChangeSourceDialog sınıfı
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
ms.openlocfilehash: 4f0dfb1579539ef744f9e16a24acc6c34463a435
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594651"
---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog sınıfı

OLE Change Source iletişim kutusu için kullanıldı.

## <a name="syntax"></a>Sözdizimi

```
class COleChangeSourceDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Oluşturur bir `COleChangeSourceDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleChangeSourceDialog::DoModal](#domodal)|OLE Change Source iletişim kutusu görüntüler.|
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Tam kaynak görünen adını alır.|
|[COleChangeSourceDialog::GetFileName](#getfilename)|Dosya adı, kaynak adından alır.|
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Önceki kaynak önekini alır.|
|[COleChangeSourceDialog::GetItemName](#getitemname)|Öğe adı, kaynak adından alır.|
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Yeni kaynak önekini alır|
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Kaynak geçerli olup olmadığını gösterir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleChangeSourceDialog::m_cs](#m_cs)|İletişim kutusunun davranışını kontrol eden bir yapı.|

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi oluşturma `COleChangeSourceDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COleChangeSourceDialog` nesne oluşturulur, kullanabileceğiniz [m_cs](#m_cs) yapısı değerleri veya durumları iletişim kutusundaki denetimlerin başlatılamadı. `m_cs` Yapısıdır türünü [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea). Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

Daha fazla bilgi için [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK'sındaki yapısı.

Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxodlgs.h

##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog

Bu işlevi oluşturan bir `COleChangeSourceDialog` nesne.

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Bağlı işaretçisi [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) olan kaynağıdır güncelleştirilecek.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür `CWnd`) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim kutusunun üst pencere ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için çağrı [DoModal](#domodal) işlevi.

Daha fazla bilgi için [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) yapısı ve [OleUIChangeSource](/windows/desktop/api/oledlg/nf-oledlg-oleuichangesourcea) Windows SDK'sında işlev.

##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal

OLE Change Source iletişim kutusunu görüntülemek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse IDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse IDCANCEL.

- Bir hata oluşursa IDABORT. IDABORT döndürülürse, çağrı [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) konusu hatanın türü hakkında daha fazla bilgi almak için üye işlevi. Olası hataları bir listesi için bkz. [OleUIChangeSource](/windows/desktop/api/oledlg/nf-oledlg-oleuichangesourcea) Windows SDK'sında işlev.

### <a name="remarks"></a>Açıklamalar

Çeşitli iletişim kutusu denetimleri üyeleri ayarlayarak başlatmak istiyorsanız [m_cs](#m_cs) yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.

Varsa `DoModal` IDOK, döndürür üye iletişim kutusundan kullanıcı tarafından girilen ayarları veya bilgi almak için işlevleri çağırabilir. Aşağıdaki listede, tipik sorgu işlevleri adları:

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName

Bağlı istemci öğesi için tam görünen adın almak için bu işlevi çağırın.

```
CString GetDisplayName();
```

### <a name="return-value"></a>Dönüş Değeri

Tam kaynak görünen adı (ad) [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) oluşturucuda belirtilen.

##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName

Bağlı istemci öğesi için görünen ad dosya adı kısmı almak için bu işlevi çağırın.

```
CString GetFileName();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya kaynak görüntü adı için bilinen ad kısmı [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) oluşturucuda belirtilen.

### <a name="remarks"></a>Açıklamalar

Öğe bilinen adı ile birlikte dosya ad, tam görünen adın sağlar.

##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix

Kaynağı önceki ön ek dizesini almak için bu işlevi çağırın.

```
CString GetFromPrefix();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak önceki önek dizesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çağrı [DoModal](#domodal) IDOK döndürür.

Bu değer, doğrudan gelir `lpszFrom` üyesi [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) yapısı.

Daha fazla bilgi için [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK'sındaki yapısı.

##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName

Bağlı istemci öğesi için görünen ad öğe bilinen adı kısmı almak için bu işlevi çağırın.

```
CString GetItemName();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak görünen adı öğe bilinen adı kısmı [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) oluşturucuda belirtilen.

### <a name="remarks"></a>Açıklamalar

Öğe bilinen adı ile birlikte dosya ad, tam görünen adın sağlar.

##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix

Kaynak için yeni ön ek dizesini almak için bu işlevi çağırın.

```
CString GetToPrefix();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak yeni önek dizesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çağrı [DoModal](#domodal) IDOK döndürür.

Bu değer, doğrudan gelir `lpszTo` üyesi [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) yapısı.

Daha fazla bilgi için [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK'sındaki yapısı.

##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs

Bu veri üyesi türünün bir yapıdır [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea).

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>Açıklamalar

`OLEUICHANGESOURCE` OLE Change Source iletişim kutusu davranışını denetlemek için kullanılır. Bu yapının üyelerine doğrudan değiştirilebilir.

Daha fazla bilgi için [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK'sındaki yapısı.

##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource

Yeni kaynak geçerli olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL IsValidSource();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni kaynak geçerliyse, sıfır olmayan Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çağrı [DoModal](#domodal) IDOK döndürür.

Daha fazla bilgi için [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK'sındaki yapısı.

## <a name="see-also"></a>Ayrıca Bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
