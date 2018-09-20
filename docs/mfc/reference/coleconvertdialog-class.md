---
title: COleConvertDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1ff8047e6d7291fe55619d8b0a3eabb877b728a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436555"
---
# <a name="coleconvertdialog-class"></a>COleConvertDialog sınıfı

Daha fazla bilgi için [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Windows SDK'sındaki yapısı.

## <a name="syntax"></a>Sözdizimi

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Oluşturur bir `COleConvertDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleConvertDialog::DoConvert](#doconvert)|İletişim kutusunda belirtilen dönüştürmeyi gerçekleştirir.|
|[COleConvertDialog::DoModal](#domodal)|OLE değişiklik öğesi iletişim kutusunu görüntüler.|
|[COleConvertDialog::GetClassID](#getclassid)|Seçili öğeyle ilişkili CLSID alır.|
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Öğeyi bir simge olarak çizileceğini belirtir.|
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğenin icon formla ilişkili meta dosyası için bir tanıtıcı alır.|
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Seçilen seçim türünü alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleConvertDialog::m_cv](#m_cv)|İletişim kutusunun davranışını kontrol eden bir yapı.|

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.

Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxodlgs.h

##  <a name="coleconvertdialog"></a>  COleConvertDialog::COleConvertDialog

Yalnızca oluşturan bir `COleConvertDialog` nesne.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülen veya etkinleştirilmesini öğeyi işaret eder.

*CertOpenStore*<br/>
Aşağıdaki değerlerden herhangi bir sayı içeren oluşturma bayrağı birleştirilmiş bit kullanarak- or işleci:

- Dönüştürülecek radyo düğmesini olacak CF_SELECTCONVERTTO belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını seçili. Bu varsayılandır.

- Etkinleştirme olarak radyo düğmesini olacak CF_SELECTACTIVATEAS belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını seçili.

- CF_SETCONVERTDEFAULT belirtir, CLSID tarafından belirtilen sınıf `clsidConvertDefault` üyesi `m_cv` yapısı kullanılacak sınıfı liste kutusunda varsayılan seçim olarak dönüştürmek için radyo düğmesi seçili olduğunda.

- CF_SETACTIVATEDEFAULT belirtir, CLSID tarafından belirtilen sınıf `clsidActivateDefault` üyesi `m_cv` yapısı kullanılacak sınıfı liste kutusunda varsayılan seçim olarak etkinleştirme olarak radyo düğmesi seçili olduğunda.

- CF_SHOWHELPBUTTON iletişim kutusu çağrıldığında Yardım düğmesini gösterileceğini belirtir.

*pClassID*<br/>
CLSID işaret dönüştürülür veya etkinleştirilmesini öğesi. CLSID değeri NULL ise, ilişkili *pItem* kullanılır.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür `CWnd`) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim kutusunun üst pencere ayarlanır.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için çağrı [DoModal](#domodal) işlevi.

Daha fazla bilgi için [CLSID anahtar](/windows/desktop/com/clsid-key-hklm) ve [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) yapısı.

##  <a name="doconvert"></a>  COleConvertDialog::DoConvert

Başarıyla döndürme sonra bu işlevi çağırın [DoModal](#domodal)öğesine dönüştürmek için veya bir nesne türü etkinleştirmek için [Coleclientıtem](../../mfc/reference/coleclientitem-class.md).

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Dönüştürülen veya etkinleştirilmesini öğeyi işaret eder. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Öğe dönüştürülür veya Dönüştürme iletişim kutusunda kullanıcı tarafından seçilen bilgileri göre etkinleştirildi.

##  <a name="domodal"></a>  COleConvertDialog::DoModal

OLE dönüştürme iletişim kutusunu görüntülemek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:

- İletişim kutusu başarıyla görüntülendiyse IDOK.

- Kullanıcı iletişim kutusunu iptal edildiyse IDCANCEL.

- Bir hata oluşursa IDABORT. IDABORT döndürülürse, çağrı [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) konusu hatanın türü hakkında daha fazla bilgi almak için üye işlevi. Olası hataları bir listesi için bkz. [OleUIConvert](/windows/desktop/api/oledlg/nf-oledlg-oleuiconverta) Windows SDK'sında işlev.

### <a name="remarks"></a>Açıklamalar

Çeşitli iletişim kutusu denetimleri üyeleri ayarlayarak başlatmak istiyorsanız [m_cv](#m_cv) yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.

Varsa `DoModal` döndürür IDOK, diğer üye ayarları veya kullanıcı tarafından iletişim kutusuna giriş bilgi almak için işlevleri çağırabilir.

##  <a name="getclassid"></a>  COleConvertDialog::GetClassID

CLSID almak için bu işlevi kullanıcının dönüştürme iletişim kutusunda seçili öğeyle ilişkili çağrısı.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dönüştür iletişim kutusunda seçilen öğesi ile ilişkilendirilmiş CLSID değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çağrı [DoModal](#domodal) IDOK döndürür.

Daha fazla bilgi için [CLSID anahtar](/windows/desktop/com/clsid-key-hklm) Windows SDK.

##  <a name="getdrawaspect"></a>  COleConvertDialog::GetDrawAspect

Seçilen öğe bir simge olarak görüntülemek kullanıcının seçtiği olup olmadığını belirlemek için bu işlevi çağırın.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi işlemek için gereken yöntem.

- Simge olarak görüntüle onay kutusunun işaretli değilse DVASPECT_ICON döndürdü.

- Simge olarak görüntüle onay kutusunu işaretlediyseniz DVASPECT_ICON döndürdü.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çağrı [DoModal](#domodal) IDOK döndürür.

En boy çizim daha fazla bilgi için bkz: [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK'sındaki veri yapısı.

##  <a name="geticonicmetafile"></a>  COleConvertDialog::GetIconicMetafile

Seçilen öğenin icon boy içeren meta dosyası için bir tanıtıcı almak için bu işlevi çağırın.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Simge olarak görüntüle onay kutusu ise seçili öğe icon yönüyle içeren meta tanıtıcısını iletişim kutusunda Tamam'ı seçerek zaman sonlandırıldı işaretli; bulunmazsa null değerini DÖNDÜRÜR.

##  <a name="getselectiontype"></a>  COleConvertDialog::GetSelectionType

Dönüştür iletişim kutusunda seçili dönüştürme türünü belirlemek için bu işlevi çağırın.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yapılan seçim türü.

### <a name="remarks"></a>Açıklamalar

Dönüş türü değerleri tarafından belirtilen `Selection` numaralandırma türü içinde bildirilen `COleConvertDialog` sınıfı.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

Bu değerleri kısa açıklamaları izleyin:

- `COleConvertDialog::noConversion` Ya da iletişim kutusunu iptal edildi veya seçilen kullanıcı hiçbir dönüştürme döndürdü. Varsa `COleConvertDialog::DoModal` IDOK döndürülen, kullanıcı farklı bir simgeye olandan daha önce seçtiğiniz seçilen mümkündür.

- `COleConvertDialog::convertItem` Dönüştürülecek radyo düğmesini işaretlediyseniz, dönüştürmek için farklı bir öğe seçilen kullanıcı döndürdü ve `DoModal` IDOK döndürdü.

- `COleConvertDialog::activateAs` Radyo düğmesini etkinleştirmek olarak işaretlendiğinde kullanıcı seçili etkinleştirmek için farklı bir öğe döndürdü ve `DoModal` IDOK döndürdü.

##  <a name="m_cv"></a>  COleConvertDialog::m_cv

Yapı türünü OLEUICONVERT Dönüştür iletişim kutusu davranışını denetlemek için kullanılır.

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Açıklamalar

Bu yapının üyelerine, doğrudan ya da üye işlevleri aracılığıyla değiştirilebilir.

Daha fazla bilgi için [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Windows SDK'sındaki yapısı.

## <a name="see-also"></a>Ayrıca Bkz.

[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
