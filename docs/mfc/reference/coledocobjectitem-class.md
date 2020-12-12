---
description: 'Daha fazla bilgi edinin: Cotadocobjectıtem sınıfı'
title: Cotadocobjectıtem sınıfı
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
ms.openlocfilehash: e483c614f8bc7558a827c51889bbffa7da7419b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227227"
---
# <a name="coledocobjectitem-class"></a>Cotadocobjectıtem sınıfı

Etkin belge kapsamayı uygular.

## <a name="syntax"></a>Syntax

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotadocobjectıtem:: Copadocobjectıtem](#coledocobjectitem)|Bir `COleDocObject` öğe oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotadocobjectıtem::D oDefaultPrinting](#dodefaultprinting)|Varsayılan yazıcı ayarlarını kullanarak kapsayıcı uygulamasının belgesini yazdırır.|
|[Cotadocobjectıtem:: ExecCommand](#execcommand)|Kullanıcı tarafından belirtilen komutu yürütür.|
|[Cotadocobjectıtem:: GetActiveView](#getactiveview)|Belgenin etkin görünümünü alır.|
|[Cotadocobjectıtem:: GetPageCount](#getpagecount)|Kapsayıcı uygulamasının belgesindeki sayfa sayısını alır.|
|[Cotadocobjectıtem:: OnPreparePrinting](#onprepareprinting)|Kapsayıcı uygulamasının belgesini yazdırma için hazırlar.|
|[Cotadocobjectıtem:: OnPrint](#onprint)|Kapsayıcı uygulamasının belgesini yazdırır.|
|[Cotadocobjectıtem:: QueryCommand](#querycommand)|Kullanıcı arabirimi olayları tarafından oluşturulan bir veya daha fazla komutun durumunu sorgular.|
|[Cotadocobjectıtem:: Release](#release)|Bir OLE bağlantılı öğesiyle bağlantıyı serbest bırakır ve açıksa kapatır. İstemci öğesini yok etmez.|

## <a name="remarks"></a>Açıklamalar

MFC 'de etkin bir belge, düzenli ve yerinde düzenlenebilir bir eklemeye benzer şekilde, aşağıdaki farklılıklarla aynı şekilde işlenir:

- `COleDocument`-Derived sınıfı halen ekli olan öğelerin bir listesini tutar; ancak, bu öğeler `COleDocObjectItem` türetilmiş öğeler olabilir.

- Etkin bir belge etkin olduğunda, yerinde etkin olduğunda görünümün tüm istemci alanının tamamını kaplar.

- Etkin bir belge kapsayıcısı, **Yardım** menüsü üzerinde tam denetime sahiptir.

- **Yardım** menüsü, hem etkin belge kapsayıcısı hem de sunucu için menü öğelerini içerir.

Etkin belge kapsayıcısı **Yardım** menüsüne sahip olduğundan, sunucu **Yardım** menüsü iletilerini sunucuya iletmekten kapsayıcı sorumludur. Bu tümleştirme tarafından işlenir `COleDocObjectItem` .

Menü birleştirme ve etkin belge etkinleştirme hakkında daha fazla bilgi için bkz. [etkin belge kapsama](../../mfc/active-document-containment.md)genel bakış.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="coledocobjectitemcoledocobjectitem"></a><a name="coledocobjectitem"></a> Cotadocobjectıtem:: Copadocobjectıtem

Nesneyi başlatmak için bu üye işlevini çağırın `COleDocObjectItem` .

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>Parametreler

*pContainerDoc*<br/>
`COleDocument`Etkin belge kapsayıcısı görevi gören nesnenin işaretçisi. IMPLEMENT_SERIALIZE etkinleştirmek için bu parametre NULL olmalıdır. Normalde OLE öğeleri, NULL olmayan bir belge işaretçisi ile oluşturulur.

## <a name="coledocobjectitemdodefaultprinting"></a><a name="dodefaultprinting"></a> Cotadocobjectıtem::D oDefaultPrinting

Varsayılan ayarları kullanarak Framework tarafından bir belgeye çağırılır.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Print komutunu Gönderen [CView](../../mfc/reference/cview-class.md) nesnesine yönelik bir işaretçi.

*pInfo*<br/>
Yazdırılacak işi açıklayan [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) nesnesine yönelik bir işaretçi.

## <a name="coledocobjectitemexeccommand"></a><a name="execcommand"></a> Cotadocobjectıtem:: ExecCommand

Kullanıcı tarafından belirtilen komutu yürütmek için bu üye işlevi çağırın.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*nCmdID*<br/>
Yürütülecek komutun tanımlayıcısı. *PguidCmdGroup* tarafından tanımlanan grupta olmalıdır.

*nCmdExecOpt*<br/>
Komut yürütme seçeneklerini belirtir. Varsayılan olarak, kullanıcıya sormadan komutu yürütmek üzere ayarlanır. Değerlerin listesi için bkz. [OLECMDEXECOPT](/windows/win32/api/docobj/ne-docobj-olecmdexecopt) .

*pguidCmdGroup*<br/>
Komut grubunun benzersiz tanıtıcısı. Varsayılan olarak, Standart grubunu belirten NULL değeri. *NCmdID* içinde geçirilen komut gruba ait olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK döndürür; Aksi takdirde, aşağıdaki hata kodlarından birini döndürür.

|Değer|Açıklama|
|-----------|-----------------|
|E_UNEXPECTED|Beklenmeyen bir hata oluştu.|
|E_FAIL|Hata oluştu.|
|E_NOTIMPL|MFC 'nin, komutu çevirme ve dağıtma denemesi gerektiğini gösterir.|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* null değil, ancak tanınan bir komut grubu belirtmiyor.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* , Grup pGroup 'ta geçerli bir komut olarak tanınmıyor.|
|OLECMDERR_DISABLED|*NCmdID* tarafından tanımlanan komut devre dışı bırakıldı ve yürütülemiyor.|
|OLECMDERR_NOHELP|Çağıran, *nCmdID* tarafından tanımlanan komutla ilgili yardım almak istedi, ancak kullanılabilir yardım yok.|
|OLECMDERR_CANCELLED|Kullanıcı yürütmeyi iptal etti.|

### <a name="remarks"></a>Açıklamalar

*PguidCmdGroup* ve *nCmdID* parametreleri birlikte çağırmak için komutu benzersiz şekilde tanımlar. *NCmdexecopt* parametresi, tam olarak gerçekleştirilecek eylemi belirtir.

## <a name="coledocobjectitemgetactiveview"></a><a name="getactiveview"></a> Cotadocobjectıtem:: GetActiveView

`IOleDocumentView`Şu anda etkin olan görünümün arabirimine bir işaretçi almak için bu üye işlevi çağırın.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda etkin olan görünümün [IOleDocumentView](/windows/win32/api/docobj/nn-docobj-ioledocumentview) arabirimine yönelik bir işaretçi. Geçerli görünüm yoksa, NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Döndürülen işaretçinin başvuru sayısı, `IOleDocumentView` Bu işlev tarafından döndürülmeden önce arttırılamaz.

## <a name="coledocobjectitemgetpagecount"></a><a name="getpagecount"></a> Cotadocobjectıtem:: GetPageCount

Belgedeki sayfa sayısını almak için bu üye işlevini çağırın.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>Parametreler

*pnFirstPage*<br/>
Belgenin ilk sayfasının numarası için bir işaretçi. , Çağıranın bu sayıya ihtiyaç duymadığını belirten NULL olabilir.

*pcPages*<br/>
Belgedeki toplam sayfa sayısına yönelik bir işaretçi. , Çağıranın bu sayıya ihtiyaç duymadığını belirten NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

## <a name="coledocobjectitemonprepareprinting"></a><a name="onprepareprinting"></a> Cotadocobjectıtem:: OnPreparePrinting

Bu üye işlevi, bir belgeyi yazdırılmak üzere hazırlamak için Framework tarafından çağırılır.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Print komutunu Gönderen [CView](../../mfc/reference/cview-class.md) nesnesine yönelik bir işaretçi.

*pInfo*<br/>
Yazdırılacak işi açıklayan [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) nesnesine yönelik bir işaretçi.

*bPrintAll*<br/>
Belgenin tamamının yazdırılıp yazdırılmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

## <a name="coledocobjectitemonprint"></a><a name="onprint"></a> Cotadocobjectıtem:: OnPrint

Bu üye işlevi, bir belgeyi yazdırmak için çerçevesi tarafından çağırılır.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Print komutunu gönderen CView nesnesine yönelik bir işaretçi.

*pInfo*<br/>
Yazdırılacak işi açıklayan [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) nesnesine yönelik bir işaretçi.

*bPrintAll*<br/>
Belgenin tamamının yazdırılıp yazdırılmadığını belirtir.

## <a name="coledocobjectitemquerycommand"></a><a name="querycommand"></a> Cotadocobjectıtem:: QueryCommand

Kullanıcı arabirimi olayları tarafından oluşturulan bir veya daha fazla komutun durumunu sorgular.

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>Parametreler

*nCmdID*<br/>
sorgulanırken komutun tanımlayıcısı.

*pdwStatus*<br/>
Sorgunun sonucu olarak döndürülen bayrakların işaretçisi. Olası değerler listesi için bkz. [OLECMDF](/windows/win32/api/docobj/ne-docobj-olecmdf).

*pCmdText*<br/>
Tek bir komutun adının ve durum bilgilerinin döndürüleceği bir [OLECMDTEXT](/windows/win32/api/docobj/ns-docobj-olecmdtext) yapısına yönelik işaretçi. Çağıranın bu bilgiye ihtiyacı olmadığını belirtmek için NULL olabilir.

*pguidCmdGroup*<br/>
Komut grubunun benzersiz tanımlayıcısı; Standart grubu belirtmek için NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değerlerinin tüm listesi için, bkz. Windows SDK [IOleCommandTarget:: QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi [IOleCommandTarget:: QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) yönteminin işlevselliğine öykünür.

## <a name="coledocobjectitemrelease"></a><a name="release"></a> Cotadocobjectıtem:: Release

Bir OLE bağlantılı öğesiyle bağlantıyı serbest bırakır ve açıksa kapatır. İstemci öğesini yok etmez.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>Parametreler

*Dwcloseseçeneği*<br/>
OLE öğesinin yüklü duruma döndüğünü ne koşullarda kaydedileceğini belirten bayrak. Olası değerler listesi için bkz. [Colet Clienentidıtem:: Close](../../mfc/reference/coleclientitem-class.md#close).

### <a name="remarks"></a>Açıklamalar

İstemci öğesini yok etmez.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[Colet Clienentidıtem sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Colet Clienentidıtem sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[CDocObjectServerItem sınıfı](../../mfc/reference/cdocobjectserveritem-class.md)
