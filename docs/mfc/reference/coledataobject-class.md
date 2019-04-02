---
title: COleDataObject sınıfı
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
ms.openlocfilehash: 24d79c684226d57839161946255781c3bdd5a043
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779098"
---
# <a name="coledataobject-class"></a>COleDataObject sınıfı

Panodan, sürükle ve bırak ile veya katıştırılmış bir OLE öğesinden farklı biçimlerde veri almak için veri aktarımlarında kullanıldı.

## <a name="syntax"></a>Sözdizimi

```
class COleDataObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDataObject::COleDataObject](#coledataobject)|Oluşturur bir `COleDataObject` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDataObject::Attach](#attach)|Belirtilen OLE veri nesnesine iliştirir `COleDataObject`.|
|[COleDataObject::AttachClipboard](#attachclipboard)|Pano üzerinde veri nesnesi ekler.|
|[COleDataObject::BeginEnumFormats](#beginenumformats)|Bir veya daha sonraki hazırlar `GetNextFormat` çağırır.|
|[COleDataObject::Detach](#detach)|İlişkili ayırır `IDataObject` nesne.|
|[COleDataObject::GetData](#getdata)|Ekli OLE veri nesnesi belirtilen biçimde verilerden kopyalar.|
|[COleDataObject::GetFileData](#getfiledata)|Ekli OLE veri nesnesi veri kopyalayan bir `CFile` belirtilen biçimde işaretçi.|
|[COleDataObject::GetGlobalData](#getglobaldata)|Ekli OLE veri nesnesi veri kopyalayan bir `HGLOBAL` belirtilen biçimde.|
|[COleDataObject::GetNextFormat](#getnextformat)|Sonraki veri biçimi döndürür.|
|[COleDataObject::IsDataAvailable](#isdataavailable)|Verileri bir belirtilen biçimde kullanılabilir olup olmadığını denetler.|
|[COleDataObject::Release](#release)|Ayırır ve ilişkili yayınlar `IDataObject` nesne.|

## <a name="remarks"></a>Açıklamalar

`COleDataObject` bir temel sınıfa sahip değil.

Bu tür veri aktarımları, bir kaynak ve hedef içerir. Veri kaynağı bir nesnenin uygulanan [COleDataSource](../../mfc/reference/coledatasource-class.md) sınıfı. Her bir hedef uygulama içinde bırakılan veri sahip veya bu panodan, bir nesnenin yapıştırma işlemi gerçekleştirmek için sorulan `COleDataObject` sınıfı oluşturulmalıdır.

Bu sınıf verilerini belirtilen biçimde var olup olmadığını belirlemenize olanak sağlar. Ayrıca kullanılabilir veri biçimlerini listeleme veya verilen biçimini kullanılabilir olup olmadığını denetleyin ve ardından tercih edilen biçiminde veri alma. Nesne alma kullanımı dahil olmak üzere birçok farklı yollarla gerçekleştirilebilir bir [CFile](../../mfc/reference/cfile-class.md), HGLOBAL bir ya da bir `STGMEDIUM` yapısı.

Daha fazla bilgi için [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Windows SDK'sındaki yapısı.

Veri nesneleri uygulamanızda kullanma hakkında daha fazla bilgi için bkz [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`COleDataObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="attach"></a>  COleDataObject::Attach

İlişkilendirmek için bu işlevi çağırın `COleDataObject` nesnesi ile bir OLE veri nesnesi.

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpDataObject*<br/>
OLE veri nesneyi işaret eder.

*bAutoRelease*<br/>
OLE veri nesnesi olması gerekiyorsa TRUE olduğunda serbest `COleDataObject` nesnedir yok; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) Windows SDK.

##  <a name="attachclipboard"></a>  COleDataObject::AttachClipboard

Şu anda açık olan panoya veri nesnesi eklemek için bu işlevi çağırın `COleDataObject` nesne.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri nesnesi yayımlanana kadar bu fonksiyonu çağıran Pano kilitler. Veri nesnesi yok Edicisi olarak yayımlanan `COleDataObject`. Daha fazla bilgi için [OpenClipboard](/windows/desktop/api/winuser/nf-winuser-openclipboard) ve [CloseClipboard](/windows/desktop/api/winuser/nf-winuser-closeclipboard) Win32 belgelerine içinde.

##  <a name="beginenumformats"></a>  COleDataObject::BeginEnumFormats

Yapılan sonraki çağrılar hazırlamak için bu işlevi çağırın `GetNextFormat` öğesinden veri biçimleri listesini almak için.

```
void BeginEnumFormats();
```

### <a name="remarks"></a>Açıklamalar

Çağrısı yapıldıktan sonra `BeginEnumFormats`, bu veri nesnesi tarafından desteklenen ilk biçimi konumunu depolanır. Art arda çağrılar `GetNextFormat` veri nesnesi içinde kullanılabilir biçimler listesini numaralandırır.

Belirli bir biçimde veri kullanılabilirliğini denetlemek için kullanmak [COleDataObject::IsDataAvailable](#isdataavailable).

Daha fazla bilgi için [IDataObject::EnumFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-enumformatetc) Windows SDK.

##  <a name="coledataobject"></a>  COleDataObject::COleDataObject

Oluşturur bir `COleDataObject` nesne.

```
COleDataObject();
```

### <a name="remarks"></a>Açıklamalar

Bir çağrı [COleDataObject::Attach](#attach) veya [COleDataObject::AttachClipboard](#attachclipboard) diğer çağırmadan önce yapılmalıdır `COleDataObject` işlevleri.

> [!NOTE]
>  Parametrelerden biri sürükle ve bırak işleyicisi için bir işaretçi olduğundan bir `COleDataObject`, sürükle ve bırak desteklemek için bu oluşturucuyu çağırmaya gerek yoktur.

##  <a name="detach"></a>  COleDataObject::Detach

Kullanımdan çıkarmak için bu işlevi çağırın `COleDataObject` nesneden serbest veri nesnesi olmadan, ilişkili OLE veri nesnesi.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanımdan çıkarılmamış OLE veri nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="getdata"></a>  COleDataObject::GetData

Öğesinden belirtilen biçimden veri almak için bu işlevi çağırın.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Veri döndürülecek olan biçimi. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*lpStgMedium*<br/>
İşaret eden bir [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) veri alacak yapısı.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) veri olduğu döndürülecek biçimini açıklayan yapısı. Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), ve [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

##  <a name="getfiledata"></a>  COleDataObject::GetFileData

Oluşturmak için bu işlevi çağırın bir `CFile` veya `CFile`-türetilmiş bir nesneye ve içinde belirtilen biçimden veri almak için bir `CFile` işaretçi.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Veri döndürülecek olan biçimi. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) veri olduğu döndürülecek biçimini açıklayan yapısı. Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni işaretçi `CFile` veya `CFile`-türetilmiş bir nesneye veri içeren başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Veriler depolanır Orta bağlı olarak, dönüş değeri tarafından işaret edilen gerçek türü olabilir `CFile`, `CSharedFile`, veya `COleStreamFile`.

> [!NOTE]
>  `CFile` Bu işlevin dönüş değeri tarafından erişilen nesne arayan tarafından ait. Arayanın sorumluluğundadır **Sil** `CFile` nesne, böylece dosyayı kapatma.

Daha fazla bilgi için [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData

Genel bellek bloğu ayrılamadı ve bir HGLOBAL belirtilen biçimden veri almak için bu işlevi çağırın.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Veri döndürülecek olan biçimi. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) veri olduğu döndürülecek biçimini açıklayan yapısı. Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa verileri içeren genel bellek bloğu tanıtıcısı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat

Art arda öğesinden veri almak için kullanılabilir tüm biçimler elde etmek için bu işlevi çağırın.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşaret [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapısı, işlev çağrısı döndürüldüğünde biçim bilgilerini alır.

### <a name="return-value"></a>Dönüş Değeri

Başka bir biçime kullanılabilir olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağrısı yapıldıktan sonra [COleDataObject::BeginEnumFormats](#beginenumformats), bu veri nesnesi tarafından desteklenen ilk biçimi konumunu depolanır. Art arda çağrılar `GetNextFormat` veri nesnesi içinde kullanılabilir biçimler listesini numaralandırır. Kullanılabilir biçimler listelemek için bu işlevleri kullanın.

Verilen biçimini kullanılabilirliği için denetlenecek çağrı [COleDataObject::IsDataAvailable](#isdataavailable).

Daha fazla bilgi için [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) Windows SDK.

##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable

Belirli bir biçimde OLE öğesinden veri almak için kullanılabilir olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Yapı içinde kullanılacak Pano verileri biçimi tarafından işaret edilen *lpFormatEtc*. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) istenen biçimini açıklayan yapısı. Yalnızca Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen biçimde veriler kullanılabilir olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmadan önce yararlıdır `GetData`, `GetFileData`, veya `GetGlobalData`.

Daha fazla bilgi için [IDataObject::QueryGetData](/windows/desktop/api/objidl/nf-objidl-idataobject-querygetdata) ve [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).

##  <a name="release"></a>  COleDataObject::Release

Sahipliğini serbest bırakmak için bu işlevi çağırın [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) önceden ilişkilendirilmiş nesne `COleDataObject` nesne.

```
void Release();
```

### <a name="remarks"></a>Açıklamalar

`IDataObject` İle ilişkilendirildi `COleDataObject` çağırarak `Attach` veya `AttachClipboard` açıkça veya framework tarafından. Varsa *bAutoRelease* parametresinin `Attach` false değerine `IDataObject` nesne değil yayımlanacaktır. Bu durumda, çağıranın serbest için sorumlu `IDataObject` çağırarak [IUnknown::Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDataSource Sınıfı](../../mfc/reference/coledatasource-class.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)
