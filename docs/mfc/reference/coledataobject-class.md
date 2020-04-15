---
title: COleDataObject Sınıfı
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
ms.openlocfilehash: 5e1545a033ab482e838fbc944b0ca9b3e543d651
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366124"
---
# <a name="coledataobject-class"></a>COleDataObject Sınıfı

Panodan, sürükle ve bırak'dan veya katıştırılmış bir OLE öğesinden çeşitli biçimlerde veri almak için veri aktarımlarında kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class COleDataObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDataObject::COleDataObject](#coledataobject)|Bir `COleDataObject` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDataObject::Ekle](#attach)|Belirtilen OLE veri nesnesini `COleDataObject`.|
|[COleDataObject::AttachClipboard](#attachclipboard)|Pano'daki veri nesnesini bağlar.|
|[COleDataObject::BeginEnumFormats](#beginenumformats)|Bir veya daha fazla `GetNextFormat` sonraki aramalar için hazırlar.|
|[COleDataObject::Detach](#detach)|İlişkili `IDataObject` nesneyi ayırır.|
|[COleDataObject::Veri Alma](#getdata)|Ekli OLE veri nesnesinden verileri belirli bir biçimde kopyalar.|
|[COleDataObject::GetFileData](#getfiledata)|Ekli OLE veri nesnesinden verileri belirtilen `CFile` biçimde bir işaretçiye kopyalar.|
|[COleDataObject::GetGlobalData](#getglobaldata)|Ekli OLE veri nesnesinden verileri belirtilen `HGLOBAL` biçimde kopyalar.|
|[COleDataObject::GetNextFormat](#getnextformat)|Kullanılabilir sonraki veri biçimini döndürür.|
|[COleDataObject::IsDataAvailable](#isdataavailable)|Verilerin belirli bir biçimde kullanılabilir olup olmadığını denetler.|
|[COleDataObject::Sürüm](#release)|İlişkili `IDataObject` nesneyi ayırır ve salgılar.|

## <a name="remarks"></a>Açıklamalar

`COleDataObject`taban sınıfa sahip değildir.

Bu tür veri aktarımları bir kaynak ve bir hedef içerir. Veri kaynağı [COleDataSource](../../mfc/reference/coledatasource-class.md) sınıfının bir nesnesi olarak uygulanır. Bir hedef uygulamanın içinde veri bırakıldığında veya Pano'dan bir yapıştırma işlemi gerçekleştirmesi istendiğinde, sınıfın bir nesnesi `COleDataObject` oluşturulmalıdır.

Bu sınıf, verilerin belirli bir biçimde var olup olmadığını belirlemenize olanak tanır. Ayrıca kullanılabilir veri biçimlerini sayısala alabilir veya belirli bir biçimde kullanılabilir olup olmadığını denetleyebilir ve ardından verileri tercih edilen biçimde alabilirsiniz. Nesne alma, [CFile,](../../mfc/reference/cfile-class.md)HGLOBAL veya bir `STGMEDIUM` yapı nın kullanımı da dahil olmak üzere birkaç farklı şekilde gerçekleştirilebilir.

Daha fazla bilgi için Windows SDK'daki [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına bakın.

Uygulamanızda veri nesnelerini kullanma hakkında daha fazla bilgi için [Veri Nesneleri ve Veri Kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleDataObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coledataobjectattach"></a><a name="attach"></a>COleDataObject::Ekle

Nesneyi bir OLE veri nesnesiyle `COleDataObject` ilişkilendirmek için bu işlevi çağırın.

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpDataObject*<br/>
Bir OLE veri nesnesine işaret edin.

*bAutoRelease*<br/>
Nesne yok edildiğinde OLE veri nesnesi serbest bırakılırsa `COleDataObject` DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [IDataObject'e](/windows/win32/api/objidl/nn-objidl-idataobject) bakın.

## <a name="coledataobjectattachclipboard"></a><a name="attachclipboard"></a>COleDataObject::AttachClipboard

Pano'da bulunan veri nesnesini `COleDataObject` nesneye eklemek için bu işlevi çağırın.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu işlevi çağırmak, bu veri nesnesi serbest bırakılına kadar Pano'yu kilitler. Veri nesnesi için yıkıcı serbest `COleDataObject`bırakılır. Daha fazla bilgi için Win32 belgesinde [OpenClipboard](/windows/win32/api/winuser/nf-winuser-openclipboard) ve [CloseClipboard'a](/windows/win32/api/winuser/nf-winuser-closeclipboard) bakın.

## <a name="coledataobjectbeginenumformats"></a><a name="beginenumformats"></a>COleDataObject::BeginEnumFormats

Öğeden veri biçimleri listesi `GetNextFormat` almak için sonraki çağrılara hazırlanmak için bu işlevi arayın.

```
void BeginEnumFormats();
```

### <a name="remarks"></a>Açıklamalar

Bir çağrıdan `BeginEnumFormats`sonra , bu veri nesnesi tarafından desteklenen ilk biçimin konumu depolanır. Ardışık `GetNextFormat` çağrılar, veri nesnesindeki kullanılabilir biçimlerin listesini listeler.

Belirli bir biçimde veri kullanılabilirliğini kontrol etmek için [COleDataObject kullanın::IsDataAvailable](#isdataavailable).

Daha fazla bilgi için Windows SDK'daki [IDataObject::EnumFormatEtc'e](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) bakın.

## <a name="coledataobjectcoledataobject"></a><a name="coledataobject"></a>COleDataObject::COleDataObject

Bir `COleDataObject` nesne inşa eder.

```
COleDataObject();
```

### <a name="remarks"></a>Açıklamalar

[COleDataObject::Ekle](#attach) veya [COleDataObject::AttachClipboard](#attachclipboard) diğer `COleDataObject` işlevleri aramadan önce yapılmalıdır.

> [!NOTE]
> Sürükle ve bırak işleyicilerinin parametrelerinden biri, `COleDataObject`sürükle ve bırak'ı desteklemek için bu oluşturucuyu çağırmaya gerek yoktur.

## <a name="coledataobjectdetach"></a><a name="detach"></a>COleDataObject::Detach

Nesneyi `COleDataObject` veri nesnesini serbest bırakmadan ilişkili OLE veri nesnesinden ayırmak için bu işlevi çağırın.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış OLE veri nesnesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="coledataobjectgetdata"></a><a name="getdata"></a>COleDataObject::Veri Alma

Belirtilen biçimde öğeden veri almak için bu işlevi arayın.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin döndürülecek biçimi. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpStgMedium*<br/>
Veri alacak bir [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaret eder.

*lpFormatEtc*<br/>
Verilerin döndürülmek üzere olduğu biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, varsayılan değerler `FORMATETC` yapıdaki diğer alanlar için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)ve [FORMATETC'a](/windows/win32/api/objidl/ns-objidl-formatetc) bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

## <a name="coledataobjectgetfiledata"></a><a name="getfiledata"></a>COleDataObject::GetFileData

Türemiş veya `CFile` türetilmiş bir `CFile`nesne oluşturmak ve belirtilen `CFile` biçimdeki verileri işaretçiye almak için bu işlevi çağırın.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin döndürülecek biçimi. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin döndürülmek üzere olduğu biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, varsayılan değerler `FORMATETC` yapıdaki diğer alanlar için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CFile` verileri `CFile`içeren yeni veya türetilmiş nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Verilerin depolanan ortama bağlı olarak, iade değerine işaret edilen gerçek `CFile` `CSharedFile`tür `COleStreamFile`, , , veya .

> [!NOTE]
> Bu `CFile` işlevin iade değeri tarafından erişilen nesne arayana aittir. Nesneyi silmek ve dosyayı kapatmak arayanın sorumluluğundadır. **delete** `CFile`

Daha fazla bilgi için Windows SDK'daki [FORMATETC'a](/windows/win32/api/objidl/ns-objidl-formatetc) bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

## <a name="coledataobjectgetglobaldata"></a><a name="getglobaldata"></a>COleDataObject::GetGlobalData

Genel bellek bloğu ayırmak ve belirtilen biçimde verileri HGLOBAL'e almak için bu işlevi arayın.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin döndürülecek biçimi. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin döndürülmek üzere olduğu biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, varsayılan değerler `FORMATETC` yapıdaki diğer alanlar için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa verileri içeren genel bellek bloğunun tutamacı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [FORMATETC'a](/windows/win32/api/objidl/ns-objidl-formatetc) bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

## <a name="coledataobjectgetnextformat"></a><a name="getnextformat"></a>COleDataObject::GetNextFormat

Öğeden veri almak için kullanılabilen tüm biçimleri elde etmek için bu işlevi tekrar tekrar arayın.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşlev çağrısı geri döndüğünde biçim bilgilerini alan [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başka bir biçim varsa sıfır alamayın; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

COleDataObject'e yapılan bir çağrıdan [sonra::BeginEnumFormats](#beginenumformats), bu veri nesnesi tarafından desteklenen ilk biçimin konumu depolanır. Ardışık `GetNextFormat` çağrılar, veri nesnesindeki kullanılabilir biçimlerin listesini listeler. Kullanılabilir biçimleri listelemek için bu işlevleri kullanın.

Belirli bir biçimin kullanılabilirliğini kontrol etmek için [COleDataObject'i arayın::IsDataAvailable](#isdataavailable).

Daha fazla bilgi için [Bkz. IEnumXXXX::Windows](/previous-versions//ms695273\(v=vs.85\)) SDK'da sonraki.

## <a name="coledataobjectisdataavailable"></a><a name="isdataavailable"></a>COleDataObject::IsDataAvailable

OLE öğesinden veri almak için belirli bir biçimin kullanılabilir olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
*LpFormatEtc*tarafından işaret edilen yapıda kullanılacak Pano veri formatı. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
İstenilen biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. Yalnızca *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, varsayılan değerler `FORMATETC` yapıdaki diğer alanlar için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Veri belirtilen biçimde varsa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu `GetData`işlev, , `GetFileData`veya `GetGlobalData`.

Daha fazla bilgi için Windows SDK'daki [IDataObject::QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) ve [FORMATETC'a](/windows/win32/api/objidl/ns-objidl-formatetc) bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

### <a name="example"></a>Örnek

  [CRichEditView örneğine bakın:QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).

## <a name="coledataobjectrelease"></a><a name="release"></a>COleDataObject::Sürüm

Daha önce `COleDataObject` nesneyle ilişkili olan [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) nesnesinin sahipliğini serbest bırakmak için bu işlevi çağırın.

```
void Release();
```

### <a name="remarks"></a>Açıklamalar

Arama `IDataObject` `COleDataObject` `Attach` veya açıkça veya `AttachClipboard` çerçeve ile ilişkili ydi. *bAutoRelease* parametresi `Attach` FALSE ise, `IDataObject` nesne serbest bırakılmaz. Bu durumda, arayan IUnknown `IDataObject` arayarak serbest bırakmak için [sorumludur::Sürüm](/windows/win32/api/unknwn/nf-unknwn-iunknown-release).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDataSource Sınıfı](../../mfc/reference/coledatasource-class.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)
