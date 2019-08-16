---
title: Colet Changesourcedialog sınıfı
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
ms.openlocfilehash: 239d7eed89796f414a7665b203ca50fafec51277
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504395"
---
# <a name="colechangesourcedialog-class"></a>Colet Changesourcedialog sınıfı

OLE değişim kaynağı iletişim kutusu için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleChangeSourceDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Colet Changesourcedialog:: Cotachangesourcedialog](#colechangesourcedialog)|Bir `COleChangeSourceDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Colet Changesourcedialog::D oModal](#domodal)|OLE değişiklik kaynağı iletişim kutusunu görüntüler.|
|[Colet Changesourcedialog:: GetDisplayName](#getdisplayname)|Kaynak görünen adının tamamını alır.|
|[Colet Changesourcedialog:: GetFileName](#getfilename)|Kaynak adından dosya adını alır.|
|[Colet Changesourcedialog:: Getfrompredüzeltmesini](#getfromprefix)|Önceki kaynağın önekini alır.|
|[Colet Changesourcedialog:: GetItemName](#getitemname)|Kaynak adından öğe adını alır.|
|[Colet Changesourcedialog:: GetToPrefix](#gettoprefix)|Yeni kaynağın önekini alır|
|[Colet Changesourcedialog:: ısvalidsource](#isvalidsource)|Kaynağın geçerli olup olmadığını gösterir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Colet Changesourcedialog:: m_cs](#m_cs)|İletişim kutusunun davranışını denetleyen bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu iletişim kutusunu çağırmak istediğinizde `COleChangeSourceDialog` , sınıfının bir nesnesi oluşturun. Bir `COleChangeSourceDialog` nesne oluşturulduktan sonra, iletişim kutusundaki denetimlerin değerlerini veya durumlarını başlatmak için [m_cs](#m_cs) yapısını kullanabilirsiniz. Yapı `m_cs` , [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)türündedir. Bu iletişim kutusu sınıfını kullanma hakkında daha fazla bilgi için bkz. [DoModal](#domodal) üye işlevi.

Daha fazla bilgi için Windows SDK içindeki [Oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

OLE 'e özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

##  <a name="colechangesourcedialog"></a>Colet Changesourcedialog:: Cotachangesourcedialog

Bu işlev bir `COleChangeSourceDialog` nesnesi oluşturur.

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Kaynağı Güncellenme bağlantılı [Colet TItem](../../mfc/reference/coleclientitem-class.md) 'ın işaretçisi.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine (türü `CWnd`) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu göstermek için [DoModal](#domodal) işlevini çağırın.

Daha fazla bilgi için Windows SDK içindeki [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına ve [oleuichangesource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) işlevine bakın.

##  <a name="domodal"></a>Colet Changesourcedialog::D oModal

OLE değişiklik kaynağı iletişim kutusunu göstermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu için tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntüleniyorsa ıDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse ıDCANCEL.

- Bir hata oluştuysa ıDADBORT. IDADBORT döndürülürse, oluşan hata türü hakkında daha fazla bilgi edinmek için [Cotadialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) üye işlevini çağırın. Olası hataların listesi için, Windows SDK içindeki [Oleuichangesource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[M_cs](#m_cs) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmak isterseniz, bunu çağırmadan `DoModal`önce, ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

IDOK `DoModal` döndürürse, iletişim kutusundan Kullanıcı tarafından girilen ayarları veya bilgileri almak için üye işlevlerini çağırabilirsiniz. Aşağıdaki liste tipik sorgu işlevlerini adlandırır:

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

##  <a name="getdisplayname"></a>Colet Changesourcedialog:: GetDisplayName

Bağlı istemci öğesi için tüm görünen adı almak için bu işlevi çağırın.

```
CString GetDisplayName();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturucuda belirtilen [Cotaclientitıtem](../../mfc/reference/coleclientitem-class.md) için kaynak görünen adı (bilinen ad).

##  <a name="getfilename"></a>Colet Changesourcedialog:: GetFileName

Bağlı istemci öğesi için görünen adın dosya bilinen ad bölümünü almak için bu işlevi çağırın.

```
CString GetFileName();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturucuda belirtilen [Colet clientıtem](../../mfc/reference/coleclientitem-class.md) için kaynak görünen adının dosya bilinen adı bölümü.

### <a name="remarks"></a>Açıklamalar

Dosya bilinen adı öğe bilinen adıyla birlikte, tüm görünen adı verir.

##  <a name="getfromprefix"></a>Colet Changesourcedialog:: Getfrompredüzeltmesini

Kaynağın önceki ön ek dizesini almak için bu işlevi çağırın.

```
CString GetFromPrefix();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynağın önceki ön eki dizesi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) , IDOK öğesini döndürdüğünden çağırın.

Bu değer, doğrudan `lpszFrom` [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısının üyesinden gelir.

Daha fazla bilgi için Windows SDK içindeki [Oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

##  <a name="getitemname"></a>Colet Changesourcedialog:: GetItemName

Bağlı istemci öğesinin görünen adının öğe bilinen adını almak için bu işlevi çağırın.

```
CString GetItemName();
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturucuda belirtilen [Cotaclientitıtem](../../mfc/reference/coleclientitem-class.md) için kaynak görünen adının öğe bilinen adı bölümü.

### <a name="remarks"></a>Açıklamalar

Dosya bilinen adı öğe bilinen adıyla birlikte, tüm görünen adı verir.

##  <a name="gettoprefix"></a>Colet Changesourcedialog:: GetToPrefix

Kaynak için yeni önek dizesini almak için bu işlevi çağırın.

```
CString GetToPrefix();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynağın yeni önek dizesi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) , IDOK öğesini döndürdüğünden çağırın.

Bu değer, doğrudan `lpszTo` [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısının üyesinden gelir.

Daha fazla bilgi için Windows SDK içindeki [Oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

##  <a name="m_cs"></a>Colet Changesourcedialog:: m_cs

Bu veri üyesi, [Oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)türünde bir yapıdır.

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>Açıklamalar

`OLEUICHANGESOURCE`OLE değişim kaynağı iletişim kutusunun davranışını denetlemek için kullanılır. Bu yapının üyeleri doğrudan değiştirilebilir.

Daha fazla bilgi için Windows SDK içindeki [Oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

##  <a name="isvalidsource"></a>Colet Changesourcedialog:: ısvalidsource

Yeni kaynağın geçerli olup olmadığını öğrenmek için bu işlevi çağırın.

```
BOOL IsValidSource();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni kaynak geçerliyse sıfır dışı, değilse 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) , IDOK öğesini döndürdüğünden çağırın.

Daha fazla bilgi için Windows SDK içindeki [Oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
