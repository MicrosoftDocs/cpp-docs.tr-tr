---
title: Cotadataobject sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
ms.openlocfilehash: e706489a84ad564949e2c2d3d193173fc19b9828
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421158"
---
# <a name="coledataobject-class"></a>Cotadataobject sınıfı

Panodan, sürükle ve bırak ile veya katıştırılmış bir OLE öğesinden çeşitli biçimlerdeki verileri almak için veri aktarımları kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleDataObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[Colet:: Colondataobject](#coledataobject)|`COleDataObject` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[Coyedataobject:: Attach](#attach)|Belirtilen OLE veri nesnesini `COleDataObject`iliştirir.|
|[Colet:: AttachClipboard](#attachclipboard)|Panodaki veri nesnesini iliştirir.|
|[Colet:: BeginEnumFormats](#beginenumformats)|Bir veya daha fazla sonraki `GetNextFormat` çağrısı için hazırlar.|
|[Colandataobject::D etach](#detach)|İlişkili `IDataObject` nesnesini ayırır.|
|[Coyedataobject:: GetData](#getdata)|Ekli OLE veri nesnesinden verileri belirtilen biçimde kopyalar.|
|[Coyedataobject:: GetFileData](#getfiledata)|Ekli OLE veri nesnesinden verileri, belirtilen biçimdeki `CFile` işaretçisine kopyalar.|
|[Colet:: GetGlobalData](#getglobaldata)|Ekli OLE veri nesnesinden verileri belirtilen biçimde `HGLOBAL` kopyalar.|
|[Colet:: GetNextFormat](#getnextformat)|Kullanılabilir bir sonraki veri biçimini döndürür.|
|[Colet:: IsDataAvailable](#isdataavailable)|Verilerin belirtilen biçimde kullanılabilir olup olmadığını denetler.|
|[Coyedataobject:: Release](#release)|İlişkili `IDataObject` nesnesini ayırır ve serbest bırakır.|

## <a name="remarks"></a>Açıklamalar

`COleDataObject` temel bir sınıfa sahip değil.

Bu tür veri aktarımları bir kaynak ve hedef içerir. Veri kaynağı [Cotadatasource](../../mfc/reference/coledatasource-class.md) sınıfının bir nesnesi olarak uygulanır. Bir hedef uygulamaya veri eklendiğinde veya Panodan bir yapıştırma işlemi gerçekleştirmesi istendiğinde, `COleDataObject` sınıfının bir nesnesi oluşturulmalıdır.

Bu sınıf, verilerin belirtilen biçimde bulunup bulunmadığını belirlemenizi sağlar. Ayrıca kullanılabilir veri biçimlerini numaralandırabilirsiniz veya belirli bir biçimin kullanılabilir olup olmadığını kontrol edip verileri tercih edilen biçimde alın. Nesne alımı, bir [CFile](../../mfc/reference/cfile-class.md), BIR HGLOBAL veya `STGMEDIUM` yapısı kullanımı dahil olmak üzere çeşitli farklı yollarla gerçekleştirilebilir.

Daha fazla bilgi için Windows SDK [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına bakın.

Uygulamanızdaki veri nesnelerini kullanma hakkında daha fazla bilgi için bkz. [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleDataObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

##  <a name="attach"></a>Coyedataobject:: Attach

`COleDataObject` nesnesini OLE veri nesnesiyle ilişkilendirmek için bu işlevi çağırın.

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpDataObject*<br/>
Bir OLE veri nesnesine işaret eder.

*bAutoRelease*<br/>
`COleDataObject` nesnesi yok edildiğinde OLE veri nesnesi yayınlanacaksa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) bölümüne bakın.

##  <a name="attachclipboard"></a>Colet:: AttachClipboard

Panoda olan veri nesnesini `COleDataObject` nesnesine eklemek için bu işlevi çağırın.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu işlevi çağırmak, bu veri nesnesi serbest bırakılana kadar panoyu kilitler. Veri nesnesi `COleDataObject`yıkıcısında serbest bırakılır. Daha fazla bilgi için bkz. Wınpboard ve [CloseClipboard](/windows/win32/api/winuser/nf-winuser-closeclipboard) 'ta Win32 [belgeleyin](/windows/win32/api/winuser/nf-winuser-openclipboard) .

##  <a name="beginenumformats"></a>Colet:: BeginEnumFormats

Öğeden veri biçimlerinin listesini almak için `GetNextFormat` sonraki çağrılara hazırlanmak için bu işlevi çağırın.

```
void BeginEnumFormats();
```

### <a name="remarks"></a>Açıklamalar

`BeginEnumFormats`çağrısından sonra, bu veri nesnesi tarafından desteklenen ilk biçimin konumu depolanır. `GetNextFormat` art arda yapılan çağrılar, veri nesnesindeki kullanılabilir biçimlerin listesini numaralandıracaktır.

Verilerin belirli bir biçimde kullanılabilirliğini denetlemek için, [Copadataobject:: IsDataAvailable](#isdataavailable)kullanın.

Daha fazla bilgi için Windows SDK bkz. [IDataObject:: EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) .

##  <a name="coledataobject"></a>Colet:: Colondataobject

`COleDataObject` nesnesi oluşturur.

```
COleDataObject();
```

### <a name="remarks"></a>Açıklamalar

Diğer `COleDataObject` işlevleri çağrılmadan önce [Cotadataobject:: Attach](#attach) veya [Copadataobject:: AttachClipboard](#attachclipboard) çağrısı yapılmalıdır.

> [!NOTE]
>  Sürükle ve bırak işleyicilerine yönelik parametrelerden biri bir `COleDataObject`işaretçisiyse, sürükle ve bırak desteği için bu oluşturucuyu çağırmanız gerekmez.

##  <a name="detach"></a>Colandataobject::D etach

`COleDataObject` nesnesini, veri nesnesini serbest bırakmadan ilişkili OLE veri nesnesinden ayırmak için bu işlevi çağırın.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış OLE veri nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="getdata"></a>Coyedataobject:: GetData

Öğeden belirtilen biçimdeki verileri almak için bu işlevi çağırın.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin döndürüleceği biçim. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*Lpstgorta*<br/>
Veri alacak bir [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaret eder.

*lpFormatEtc*<br/>
Verilerin döndürüleceği biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *CfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK bkz. [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) .

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

##  <a name="getfiledata"></a>Coyedataobject:: GetFileData

`CFile` veya `CFile`türetilmiş bir nesne oluşturmak ve belirtilen biçimdeki verileri `CFile` işaretçisine almak için bu işlevi çağırın.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin döndürüleceği biçim. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin döndürüleceği biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *CfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa verileri içeren yeni `CFile` veya `CFile`türetilmiş nesne işaretçisi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Verilerin depolandığı ortama bağlı olarak, dönüş değeri tarafından işaret edilen gerçek tür `CFile`, `CSharedFile`veya `COleStreamFile`olabilir.

> [!NOTE]
>  Bu işlevin dönüş değeri tarafından erişilen `CFile` nesnesi, çağırana aittir. `CFile` nesnesini **silmek** için çağıranın sorumluluğundadır ve böylece dosya kapatılıyor.

Daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) bölümüne bakın.

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

##  <a name="getglobaldata"></a>Colet:: GetGlobalData

Genel bir bellek bloğu ayırmak ve belirtilen biçimdeki verileri bir HGLOBAL dosyasına almak için bu işlevi çağırın.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin döndürüleceği biçim. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin döndürüleceği biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *CfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa verileri içeren genel bellek bloğunun tanıtıcısı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) bölümüne bakın.

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

##  <a name="getnextformat"></a>Colet:: GetNextFormat

Öğeden verileri almak için kullanılabilen tüm biçimleri elde etmek için bu işlevi tekrar tekrar çağırın.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşlev çağrısı döndüğünde biçim bilgilerini alan [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başka bir biçim varsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[Cotadataobject:: BeginEnumFormats](#beginenumformats)çağrısından sonra, bu veri nesnesi tarafından desteklenen ilk biçimin konumu depolanır. `GetNextFormat` art arda yapılan çağrılar, veri nesnesindeki kullanılabilir biçimlerin listesini numaralandıracaktır. Kullanılabilir biçimleri listelemek için bu işlevleri kullanın.

Belirli bir biçimin kullanılabilirliğini denetlemek için [Codidataobject:: IsDataAvailable](#isdataavailable)öğesini çağırın.

Daha fazla bilgi için Windows SDK ' de [IEnumXXXX:: Next](/previous-versions//ms695273\(v=vs.85\)) bölümüne bakın.

##  <a name="isdataavailable"></a>Colet:: IsDataAvailable

OLE öğesinden verileri almak için belirli bir biçimin kullanılabilir olup olmadığını öğrenmek için bu işlevi çağırın.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
*LpFormatEtc*tarafından işaret edilen yapıda kullanılacak Pano veri biçimi. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
İstenen biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. Bu parametre için, yalnızca *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Veriler belirtilen biçimde kullanılabilirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetData`, `GetFileData`veya `GetGlobalData`çağrılmadan önce yararlıdır.

Daha fazla bilgi için Windows SDK bkz. [IDataObject:: QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) .

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

### <a name="example"></a>Örnek

  [CRichEditView:: QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)için örneğe bakın.

##  <a name="release"></a>Coyedataobject:: Release

Daha önce `COleDataObject` nesnesiyle ilişkilendirilmiş olan [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) nesnesinin sahipliğini serbest bırakmak için bu işlevi çağırın.

```
void Release();
```

### <a name="remarks"></a>Açıklamalar

`IDataObject`, açıkça veya Framework tarafından `Attach` ya da `AttachClipboard` çağırarak `COleDataObject` ilişkilendirildi. `Attach` *bAutoRelease* parametresi false ise, `IDataObject` nesnesi serbest bırakılır. Bu durumda, arayanın [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)öğesini çağırarak `IDataObject` serbest bırakılmasından sorumludur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDataSource Sınıfı](../../mfc/reference/coledatasource-class.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)
