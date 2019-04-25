---
title: Coledocobjectıtem sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
ms.openlocfilehash: 382960b4dc4dcfa61c836a87044dd14585756174
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225522"
---
# <a name="coledocobjectitem-class"></a>Coledocobjectıtem sınıfı

Etkin belge kapsamı uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Oluşturur bir `COleDocObject` öğesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Varsayılan yazıcı ayarları kullanarak kapsayıcı uygulamasının belgesini yazdırır.|
|[COleDocObjectItem::ExecCommand](#execcommand)|Kullanıcı tarafından belirtilen komutu yürütür.|
|[COleDocObjectItem::GetActiveView](#getactiveview)|Etkin belge görünümü alır.|
|[COleDocObjectItem::GetPageCount](#getpagecount)|Kapsayıcı uygulamasının belgedeki sayfa sayısını alır.|
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Kapsayıcı uygulamasının belge yazdırma için hazırlar.|
|[COleDocObjectItem::OnPrint](#onprint)|Kapsayıcı uygulamasının belgesini yazdırır.|
|[COleDocObjectItem::QueryCommand](#querycommand)|Kullanıcı arabirimi olayları tarafından oluşturulan bir veya daha fazla komut durumunu sorgular.|
|[COleDocObjectItem::Release](#release)|Bağlantı bağlı öğe OLE serbest bırakır ve açık olması durumunda bunu kapatır. İstemci öğesi yok.|

## <a name="remarks"></a>Açıklamalar

MFC içinde etkin bir belge bir normal, yerinde düzenlenebilir, aşağıdaki farklarla katıştırmak için benzer şekilde işlenir:

- `COleDocument`-Türetilmiş sınıf yine de şu anda katıştırılmış öğeleri listesini tutar; Bununla birlikte, bu öğeler olabilir `COleDocObjectItem`-türetilmiş öğeler.

- Etkin belge etkin olduğunda, yerinde etkin olduğunda görünümün tüm istemci alanını kaplar.

- Etkin belge kapsayıcısı üzerinde tam denetime sahip **yardımcı** menüsü.

- **Yardımcı** menüsü etkin belge kapsayıcı ve sunucu için menü öğelerini içerir.

Etkin belge kapsayıcı sahibi olduğundan **yardımcı** menüsünde kapsayıcıdır sunucu iletmek için sorumlu **yardımcı** sunucuya menü iletileri. Bu tümleştirme tarafından işlenen `COleDocObjectItem`.

Menü birleştirme ve etkin belgeyi etkinleştirme hakkında daha fazla bilgi için bkz: genel bakış [etkin belge kapsaması](../../mfc/active-document-containment.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocıtem](../../mfc/reference/cdocitem-class.md)

[Coleclientıtem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="coledocobjectitem"></a>  COleDocObjectItem::COleDocObjectItem

Bu üye işlevi çağrısı `COleDocObjectItem` nesne.

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>Parametreler

*pContainerDoc*<br/>
Bir işaretçi `COleDocument` etkin belge kapsayıcısı olarak görev yapan bir nesne. Bu parametre öğesini etkinleştirmek için NULL olmalıdır. Normalde OLE öğeleri, NULL olmayan belge işaretçisi ile oluşturulur.

##  <a name="dodefaultprinting"></a>  COleDocObjectItem::DoDefaultPrinting

Varsayılan ayarları kullanarak bir belge için framework tarafından çağırılır.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Bir işaretçi bir [CView](../../mfc/reference/cview-class.md) yazdırma komut gönderilirken bir nesne.

*pInfo*<br/>
Bir işaretçi bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) yazdırılması iş tanımlayan nesne.

##  <a name="execcommand"></a>  COleDocObjectItem::ExecCommand

Kullanıcı tarafından belirtilen komutu yürütmek için bu üye işlevini çağırın.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*nCmdID*<br/>
Yürütülecek komut tanımlayıcısı. Tarafından tanımlanan grubunda olmalıdır *pguidCmdGroup*.

*nCmdExecOpt*<br/>
Komut yürütme seçeneklerini belirtir. Kullanıcıya sormadan komutu yürütmek için varsayılan olarak ayarlayın. Bkz: [OLECMDEXECOPT](/windows/desktop/api/docobj/ne-docobj-olecmdexecopt) değerleri listesi.

*pguidCmdGroup*<br/>
Komut grubu benzersiz tanımlayıcısı. Varsayılan olarak, NULL, standart grubu belirtir. Geçirilen komut *nCmdID* grubuna ait olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa; başarılıysa S_OK döndürür Aksi takdirde, aşağıdaki hata kodlarından birini döndürür.

|Değer|Açıklama|
|-----------|-----------------|
|E_UNEXPECTED|Beklenmeyen bir hata oluştu.|
|E_FAIL|Hata oluştu.|
|E_NOTIMPL|MFC gösterir kendisini çevirin ve komut gönderme denemelisiniz.|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* NULL değil ancak bir tanınan bir komut grubuyla belirtmiyor.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* grubu pGroup geçerli bir komut olarak tanınmıyor.|
|OLECMDERR_DISABLED|Tarafından tanımlanan komutu *nCmdID* devre dışı bırakıldı ve yürütülemez.|
|OLECMDERR_NOHELP|Çağıran tarafından tanımlanan komutu hakkında Yardım için sorulan *nCmdID* ancak Yardım yok.|
|OLECMDERR_CANCELLED|Kullanıcı, yürütme iptal edildi.|

### <a name="remarks"></a>Açıklamalar

*PguidCmdGroup* ve *nCmdID* parametreleri birlikte çağrılacak komutu benzersiz olarak tanımlanabilmesi. *NCmdExecOpt* parametresi tam gerçekleştirilecek eylemi belirtir.

##  <a name="getactiveview"></a>  COleDocObjectItem::GetActiveView

Bu üye işlevi işaretçisi almak için arama `IOleDocumentView` şu anda etkin görünümün arabirimi.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [IOleDocumentView](/windows/desktop/api/docobj/nn-docobj-ioledocumentview) şu anda etkin görünümün arabirimi. Geçerli Görünüm ise NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Döndürülen başvuru sayısını `IOleDocumentView` işaretçi tarafından bu işlev döndürülmeden önce değil artırılır.

##  <a name="getpagecount"></a>  COleDocObjectItem::GetPageCount

Belgedeki sayfa sayısı almak için bu üye işlevini çağırın.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>Parametreler

*pnFirstPage*<br/>
Belgenin ilk sayfa numarası bir işaretçi. Çağıranın bu sayı gerekmiyor gösteren NULL olabilir.

*pcPages*<br/>
Belgedeki sayfa sayısı için bir işaretçi. Çağıranın bu sayı gerekmiyor gösteren NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="onprepareprinting"></a>  COleDocObjectItem::OnPreparePrinting

Bu üye işlevi, bir belge yazdırma için hazırlamak için framework tarafından çağırılır.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Bir işaretçi bir [CView](../../mfc/reference/cview-class.md) yazdırma komut gönderilirken bir nesne.

*pInfo*<br/>
Bir işaretçi bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) yazdırılması iş tanımlayan nesne.

*bPrintAll*<br/>
Tüm belgeyi yazdırılması olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="onprint"></a>  COleDocObjectItem::OnPrint

Bu üye işlevi bir belge yazdırma için framework tarafından çağırılır.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Yazdırma komut gönderilirken bir CView nesnesine bir işaretçi.

*pInfo*<br/>
Bir işaretçi bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) yazdırılması iş tanımlayan nesne.

*bPrintAll*<br/>
Tüm belgeyi yazdırılması olup olmadığını belirtir.

##  <a name="querycommand"></a>  COleDocObjectItem::QueryCommand

Kullanıcı arabirimi olayları tarafından oluşturulan bir veya daha fazla komut durumunu sorgular.

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>Parametreler

*nCmdID*<br/>
için sorgulanan komut tanımlayıcısı.

*pdwStatus*<br/>
Sorgu sonucunda döndürülen bayrakları için bir işaretçi. Olası değerler listesi için bkz. [OLECMDF](/windows/desktop/api/docobj/ne-docobj-olecmdf).

*pCmdText*<br/>
İşaretçi bir [OLECMDTEXT](/windows/desktop/api/docobj/ns-docobj-_tagolecmdtext) yapısı, tek bir komut için adı ve durum bilgilerini döndürmek. Çağıranın bu bilgilere ihtiyacınız olmayan göstermek için NULL olabilir.

*pguidCmdGroup*<br/>
Komut grubu benzersiz tanıtıcısı; Standart grubu belirtmek için boş olabilir.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değerlerinin tam listesi için bkz: [IOleCommandTarget::QueryStatus](/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-querystatus) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi işlevselliğine öykünür [IOleCommandTarget::QueryStatus](/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-querystatus) Windows SDK'da açıklandığı yöntemi.

##  <a name="release"></a>  COleDocObjectItem::Release

Bağlantı bağlı öğe OLE serbest bırakır ve açık olması durumunda bunu kapatır. İstemci öğesi yok.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>Parametreler

*dwCloseOption*<br/>
Hangi şartlar altında OLE öğesi kaydedildiğinde, bu yüklü duruma geri döndüğünde belirten bayrak. Olası değerler listesi için bkz. [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).

### <a name="remarks"></a>Açıklamalar

İstemci öğesi yok.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[CDocObjectServerItem Sınıfı](../../mfc/reference/cdocobjectserveritem-class.md)
