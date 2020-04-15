---
title: COleConvertDialog Sınıfı
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
ms.openlocfilehash: 6d6690b8d06df29ce9fcd323eb8724009ee3cca9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366174"
---
# <a name="coleconvertdialog-class"></a>COleConvertDialog Sınıfı

Daha fazla bilgi için Windows SDK'daki [OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) yapısına bakın.

## <a name="syntax"></a>Sözdizimi

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Bir `COleConvertDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleConvertDialog::DoConvert](#doconvert)|İletişim kutusunda belirtilen dönüştürmeyi gerçekleştirir.|
|[COleConvertDialog::DoModal](#domodal)|OLE Değişiklik Öğesi iletişim kutusunu görüntüler.|
|[COleConvertDialog::GetClassID](#getclassid)|CLSID'yi seçilen öğeyle ilişkilendiriyor.|
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Öğenin simge olarak çizilip çizilemeyeceğini belirtir.|
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğenin ikonik formuyla ilişkili metadosyaya bir tanıtıcı alır.|
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Seçilen seçim türünü alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleConvertDialog::m_cv](#m_cv)|İletişim kutusunun davranışını denetleyen bir yapı.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

OLE'ye özgü iletişim kutuları hakkında daha fazla bilgi için, [OLE'deki İletişim Kutuları makalesine](../../mfc/dialog-boxes-in-ole.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxodlgs.h

## <a name="coleconvertdialogcoleconvertdialog"></a><a name="coleconvertdialog"></a>COleConvertDialog::COleConvertDialog

Yalnızca bir `COleConvertDialog` nesne yi inşa eder.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülecek veya etkinleştirilecek öğeyi işaret edin.

*Dwflags*<br/>
Bitwise-or işleci kullanılarak birleştirilen aşağıdaki değerlerin herhangi bir sayısını içeren oluşturma bayrağı:

- CF_SELECTCONVERTTO İletişim kutusu çağrıldığında radyoya dönüştür düğmesinin seçileceğini belirtir. Bu varsayılandır.

- CF_SELECTACTIVATEAS İletişim kutusu çağrıldığında radyo olarak etkinleştir düğmesinin seçileceğini belirtir.

- CF_SETCONVERTDEFAULT ClSID `clsidConvertDefault` `m_cv` yapısının üyesi tarafından belirtilen sınıfın, radyoya Dönüştür düğmesi seçildiğinde sınıf listesi kutusunda varsayılan seçim olarak kullanılacağını belirtir.

- CF_SETACTIVATEDEFAULT, `clsidActivateDefault` `m_cv` CLSID'si yapının üyesi tarafından belirtilen sınıfın, radyo olarak etkinleştir düğmesi seçildiğinde sınıf listesi kutusunda varsayılan seçim olarak kullanılacağını belirtir.

- CF_SHOWHELPBUTTON İletişim kutusu çağrıldığında Yardım düğmesinin görüntüleneceğini belirtir.

*pClassID*<br/>
Dönüştürülecek veya etkinleştirilecek maddenin CLSID'sine işaret edilir. NULL ise, *pItem* ile ilişkili CLSID kullanılır.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst `CWnd`veya sahip penceresi nesnesine (tür) işaret eder. NULL ise, iletişim kutusunun ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için [DoModal](#domodal) işlevini arayın.

Daha fazla bilgi için [CLSID Key](/windows/win32/com/clsid-key-hklm) ve [OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) yapısına bakın.

## <a name="coleconvertdialogdoconvert"></a><a name="doconvert"></a>COleConvertDialog::DoConvert

[DoModal'dan](#domodal)başarıyla döndükten sonra, [coleClientItem](../../mfc/reference/coleclientitem-class.md)türünden bir nesneyi dönüştürmek veya etkinleştirmek için bu işlevi arayın.

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülecek veya etkinleştirilecek öğeyi işaret edin. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Öğe, Dönüştür iletişim kutusunda kullanıcı tarafından seçilen bilgilere göre dönüştürülür veya etkinleştirilir.

## <a name="coleconvertdialogdomodal"></a><a name="domodal"></a>COleConvertDialog::DoModal

OLE Convert iletişim kutusunu görüntülemek için bu işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun tamamlanma durumu. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse İDOK.

- Kullanıcı iletişim kutusunu iptal ettiyse IDCANCEL.

- Bir hata oluştuysa IDABORT. IDABORT döndürülürse, [coleDialog'u arayın::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) üye işlevini arayarak oluşan hata türü hakkında daha fazla bilgi alın. Olası hataların listesi için Windows SDK'daki [OleUIConvert](/windows/win32/api/oledlg/nf-oledlg-oleuiconvertw) işlevine bakın.

### <a name="remarks"></a>Açıklamalar

[m_cv](#m_cv) yapısının üyelerini ayarlayarak çeşitli iletişim kutusu denetimlerini başlatmayı istiyorsanız, bunu `DoModal`çağırmadan önce, ancak iletişim nesnesi oluşturulduktan sonra yapmalısınız.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından girilen ayarları veya bilgileri iletişim kutusuna almak için diğer üye işlevleri arayabilirsiniz.

## <a name="coleconvertdialoggetclassid"></a><a name="getclassid"></a>COleConvertDialog::GetClassID

ClSID'yi kullanıcının Convert iletişim kutusunda seçtiği öğeyle ilişkilendirmesini sağlamak için bu işlevi arayın.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Convert iletişim kutusunda seçilen öğeyle ilişkili CLSID.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) IDOK döndükten sonra arayın.

Daha fazla bilgi için Windows SDK'daki [CLSID Key'e](/windows/win32/com/clsid-key-hklm) bakın.

## <a name="coleconvertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>COleConvertDialog::GetDrawAspect

Kullanıcının seçili öğeyi simge olarak görüntülemeyi seçip seçmediğini belirlemek için bu işlevi arayın.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi işlemek için gereken yöntem.

- DVASPECT_CONTENT Simge Olarak Görüntü le görüntü lenekçe onay kutusu işaretlenmediyse döndürülür.

- DVASPECT_ICON Simge Olarak Görüntü legörüntü onay kutusu işaretlenmişse döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca [DoModal](#domodal) IDOK döndükten sonra arayın.

Çizim yönü hakkında daha fazla bilgi için Windows SDK'daki [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) veri yapısına bakın.

## <a name="coleconvertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COleConvertDialog::GetIconicMetafile

Seçili öğenin simgesel yönünü içeren metafile bir tanıtıcı almak için bu işlevi arayın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğenin simgesel yönünü içeren metadosyanın tutamacı, ok seçilerek iletişim kutusu kapatıldığında Simge Olarak Görüntüle onay kutusu işaretlenmişse; aksi takdirde NULL.

## <a name="coleconvertdialoggetselectiontype"></a><a name="getselectiontype"></a>COleConvertDialog::GetSelectionType

Dönüştür iletişim kutusunda seçilen dönüşüm türünü belirlemek için bu işlevi arayın.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

İade türü değerleri, sınıfta `Selection` bildirilen numaralandırma türüne `COleConvertDialog` göre belirtilir.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

Bu değerlerin kısa açıklamaları aşağıdaki gibidir:

- `COleConvertDialog::noConversion`İletişim kutusu iptal edildiyse veya kullanıcı dönüşüm seçmediyse döndürülür. IDOK `COleConvertDialog::DoModal` döndürülürse, kullanıcının daha önce seçilen simgeden farklı bir simge seçmesi mümkündür.

- `COleConvertDialog::convertItem`Radyoya Dönüştür düğmesi işaretlenirse döndürülür, kullanıcı dönüştürmek için `DoModal` farklı bir öğe seçti ve IDOK'yu döndürdü.

- `COleConvertDialog::activateAs`Radyo Olarak Etkinleştir düğmesi işaretlenirse döndürülürse, kullanıcı `DoModal` etkinleştirmek için farklı bir öğe seçti ve İDOK'u döndürdü.

## <a name="coleconvertdialogm_cv"></a><a name="m_cv"></a>COleConvertDialog::m_cv

Convert iletişim kutusunun davranışını denetlemek için kullanılan OLEUICONVERT türünün yapısı.

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyeleri doğrudan veya üye işlevler aracılığıyla değiştirilebilir.

Daha fazla bilgi için Windows SDK'daki [OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) yapısına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
