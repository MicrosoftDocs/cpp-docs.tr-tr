---
title: Cotaconvertdialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
ms.openlocfilehash: ba57e756457fcffca806eeba7454ddf7bcf99d34
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504302"
---
# <a name="coleconvertdialog-class"></a>Cotaconvertdialog sınıfı

Daha fazla bilgi için Windows SDK [Oleuiconvert](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) yapısına bakın.

## <a name="syntax"></a>Sözdizimi

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copaconvertdialog:: Cotaconvertdialog](#coleconvertdialog)|Bir `COleConvertDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotaconvertdialog::D oConvert](#doconvert)|İletişim kutusunda belirtilen dönüşümü gerçekleştirir.|
|[Cotaconvertdialog::D oModal](#domodal)|OLE Change Item iletişim kutusunu görüntüler.|
|[Cotaconvertdialog:: GetClassID](#getclassid)|Seçili öğeyle ilişkili CLSID 'yi alır.|
|[Cotaconvertdialog:: GetDrawAspect](#getdrawaspect)|Öğenin simge olarak çizilmesi gerekip gerekmediğini belirtir.|
|[Cotaconvertdialog:: Getıconicmetafile](#geticonicmetafile)|Bu öğenin IIC formuyla ilişkili meta dosyası için bir tanıtıcı alır.|
|[Cotaconvertdialog:: GetSelectionType](#getselectiontype)|Seçilen seçimin türünü alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cotaconvertdialog:: m_cv](#m_cv)|İletişim kutusunun davranışını denetleyen bir yapı.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

OLE 'e özgü iletişim kutuları hakkında daha fazla bilgi için [OLE 'deki makale Iletişim kutularına](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxodlgs. h

##  <a name="coleconvertdialog"></a>Copaconvertdialog:: Cotaconvertdialog

Yalnızca bir `COleConvertDialog` nesnesi oluşturur.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülecek veya etkinleştirilecek öğeyi işaret eder.

*dwFlags*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilmiş aşağıdaki değerlerin sayısını içeren oluşturma bayrağı:

- CF_SELECTCONVERTTO, iletişim kutusu çağrıldığında radyo düğmesine Dönüştür düğmesinin başlangıçta seçili olacağını belirtir. Bu varsayılandır.

- CF_SELECTACTIVATEAS, iletişim kutusu çağrıldığında radyo olarak etkinleştir düğmesinin başlangıçta seçili olacağını belirtir.

- CF_SETCONVERTDEFAULT, CLSID 'si `clsidConvertDefault` `m_cv` yapı üyesi tarafından belirtilen sınıfın, radyo Dönüştür düğmesine ayarlandığında sınıf liste kutusunda varsayılan seçim olarak kullanılacağını belirtir.

- CF_SETACTIVATEDEFAULT, CLSID 'si `clsidActivateDefault` `m_cv` yapı üyesi tarafından belirtilen sınıfın, radyo olarak etkinleştir düğmesi seçildiğinde sınıf liste kutusunda varsayılan seçim olarak kullanılacağını belirtir.

- CF_SHOWHELPBUTTON iletişim kutusu çağrıldığında Yardım düğmesinin görüntülendiğini belirtir.

*pClassId*<br/>
Dönüştürülecek veya etkinleştirilecek öğenin CLSID değerini gösterir. NULL ise, *Pitem* Ile ilişkili CLSID kullanılacaktır.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine (türü `CWnd`) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu göstermek için [DoModal](#domodal) işlevini çağırın.

Daha fazla bilgi için bkz. [CLSID anahtarı](/windows/win32/com/clsid-key-hklm) ve [Oleuiconvert](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) yapısı.

##  <a name="doconvert"></a>Cotaconvertdialog::D oConvert

Bu işlevi, [docepclienentidıtem](../../mfc/reference/coleclientitem-class.md)türünde bir nesneyi dönüştürmek ya da etkinleştirmek Için [DoModal](#domodal)'dan başarıyla döndükten sonra çağırın.

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülecek veya etkinleştirilecek öğeyi işaret eder. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Öğe, Dönüştür iletişim kutusunda Kullanıcı tarafından seçilen bilgilere göre dönüştürülür veya etkinleştirilir.

##  <a name="domodal"></a>Cotaconvertdialog::D oModal

OLE Convert iletişim kutusunu göstermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu için tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntüleniyorsa ıDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse ıDCANCEL.

- Bir hata oluştuysa ıDADBORT. IDADBORT döndürülürse, oluşan hata türü hakkında daha fazla bilgi edinmek için [Cotadialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) üye işlevini çağırın. Olası hataların listesi için Windows SDK [Oleuiconvert](/windows/win32/api/oledlg/nf-oledlg-oleuiconvertw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[M_cv](#m_cv) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmak isterseniz, bunu çağırmadan `DoModal`önce, ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

IDOK `DoModal` döndürürse, Kullanıcı tarafından iletişim kutusuna girilen ayarları veya bilgileri almak için diğer üye işlevlerini çağırabilirsiniz.

##  <a name="getclassid"></a>Cotaconvertdialog:: GetClassID

Dönüştür iletişim kutusunda kullanıcının seçtiği öğeyle ilişkili CLSID 'yi almak için bu işlevi çağırın.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dönüştür iletişim kutusunda seçilen öğeyle ilişkili CLSID.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) , IDOK öğesini döndürdüğünden çağırın.

Daha fazla bilgi için Windows SDK [CLSID anahtarı](/windows/win32/com/clsid-key-hklm) bölümüne bakın.

##  <a name="getdrawaspect"></a>Cotaconvertdialog:: GetDrawAspect

Kullanıcının seçili öğeyi simge olarak görüntülemeyi seçmediğini öğrenmek için bu işlevi çağırın.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi işlemek için gereken yöntem.

- Simge olarak göster onay kutusu işaretli değilse, DVASPECT_CONTENT döndürüldü.

- Simge olarak göster onay kutusu işaretliyse DVASPECT_ICON döndürüldü.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) , IDOK öğesini döndürdüğünden çağırın.

En boy çizimi hakkında daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) veri yapısına bakın.

##  <a name="geticonicmetafile"></a>Cotaconvertdialog:: Getıconicmetafile

Seçili öğenin ıfıic boyutunu içeren meta dosyasına bir tanıtıcı almak için bu işlevi çağırın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğenin ı, simge olarak göster onay kutusu, Tamam ' ı seçerek bir iletişim kutusu kapatıldığında, bu dosya için bir işleyici işaretlendi. Aksi takdirde NULL.

##  <a name="getselectiontype"></a>Cotaconvertdialog:: GetSelectionType

Dönüştür iletişim kutusunda seçilen dönüştürme türünü öğrenmek için bu işlevi çağırın.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

Dönüş türü değerleri, `Selection` `COleConvertDialog` sınıfında belirtilen numaralandırma türü tarafından belirtilir.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

Bu değerlerin kısa açıklamaları şu şekilde yapılır:

- `COleConvertDialog::noConversion`İletişim kutusu iptal edildiğinde veya Kullanıcı dönüştürme işlemi seçilmediyse döndürüldü. IDOK `COleConvertDialog::DoModal` döndürülürse, Kullanıcı daha önce seçilmiş olandan farklı bir simge seçmiş olabilir.

- `COleConvertDialog::convertItem`Radyo Dönüştür düğmesine işaretlenirse, Kullanıcı dönüştürmek için farklı bir öğe seçti ve `DoModal` IDOK öğesini geri döndürdü.

- `COleConvertDialog::activateAs`Radyo olarak etkinleştir düğmesi işaretliyse, Kullanıcı etkinleştirilecek farklı bir öğe seçti ve `DoModal` IDOK öğesini döndürdüğünden döndürüldü.

##  <a name="m_cv"></a>Cotaconvertdialog:: m_cv

Dönüştür iletişim kutusunun davranışını denetlemek için kullanılan OLEUICONVERT türünün yapısı.

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri, doğrudan veya üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK [Oleuiconvert](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
