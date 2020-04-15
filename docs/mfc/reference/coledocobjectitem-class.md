---
title: COleDocObjectItem Sınıfı
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
ms.openlocfilehash: a696226185dd99b9e277e74d92cbe15c95cc900a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375045"
---
# <a name="coledocobjectitem-class"></a>COleDocObjectItem Sınıfı

Etkin belge çevrelemesini uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Bir `COleDocObject` öğe yi inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Varsayılan yazıcı ayarlarını kullanarak kapsayıcı uygulamasının belgesini yazdırır.|
|[COleDocObjectItem::ExecCommand](#execcommand)|Kullanıcı tarafından belirtilen komutu yürütür.|
|[COleDocObjectItem::GetActiveView](#getactiveview)|Belgenin etkin görünümünü alır.|
|[COleDocObjectItem::GetPageCount](#getpagecount)|Kapsayıcı uygulamanın belgesindeki sayfa sayısını alır.|
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Kapsayıcı uygulamanın belgesini yazdırmak için hazırlar.|
|[COleDocObjectItem::OnPrint](#onprint)|Kapsayıcı uygulamanın belgesini yazdırır.|
|[COleDocObjectItem::QueryCommand](#querycommand)|Kullanıcı arabirimi olayları tarafından oluşturulan bir veya daha fazla komutun durumu için sorgular.|
|[COleDocObjectItem::Sürüm](#release)|OLE bağlantılı bir öğeye bağlantıyı serbest bırakır ve açıksa kapatır. İstemci öğesini yok etmez.|

## <a name="remarks"></a>Açıklamalar

MFC'de, Etkin belge aşağıdaki farklarla birlikte düzenli, yerinde düzenlenebilir katıştırma işlemine benzer şekilde işlenir:

- Türetilmiş `COleDocument`sınıf hala şu anda katıştırılmış öğelerin bir listesini tutar; ancak, bu öğeler `COleDocObjectItem`türetilmiş öğeler olabilir.

- Etkin bir belge etkin olduğunda, yerinde etkin olduğunda görünümün tüm istemci alanını kaplar.

- Etkin belge kapsayıcısı **Yardım** menüsünün tam denetimine sahiptir.

- **Yardım** menüsü, hem Etkin belge kapsayıcısı hem de sunucu için menü öğelerini içerir.

Etkin belge kapsayıcısı **Yardım** menüsüne sahip olduğundan, kapsayıcı sunucu **Yardım** menüsü iletilerini sunucuya iletmekten sorumludur. Bu tümleştirme `COleDocObjectItem`.

Menü birleştirme ve Etkin belge etkinleştirme hakkında daha fazla bilgi için [Bkz. Etkin Belge İçlemesi](../../mfc/active-document-containment.md)Genel Bakış.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[Coleclientıtem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coledocobjectitemcoledocobjectitem"></a><a name="coledocobjectitem"></a>COleDocObjectItem::COleDocObjectItem

Nesneyi başlatmak için `COleDocObjectItem` bu üye işlevi çağırın.

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>Parametreler

*pContainerDoc*<br/>
Etkin belge `COleDocument` kapsayıcısı olarak hareket eden nesneye işaretçi. Bu parametre IMPLEMENT_SERIALIZE sağlamak için NULL olmalıdır. Normalde OLE öğeleri NULL olmayan bir belge işaretçisi ile oluşturulur.

## <a name="coledocobjectitemdodefaultprinting"></a><a name="dodefaultprinting"></a>COleDocObjectItem::DoDefaultPrinting

Varsayılan ayarları kullanarak bir belgeye çerçeve tarafından çağrılır.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Yazdırma komutunu gönderen [cview](../../mfc/reference/cview-class.md) nesnesine işaretçi.

*Pınfo*<br/>
Yazdırılacak işi açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) nesnesine işaretçi.

## <a name="coledocobjectitemexeccommand"></a><a name="execcommand"></a>COleDocObjectItem::ExecCommand

Kullanıcı tarafından belirtilen komutu yürütmek için bu üye işlevini arayın.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*nCmdID*<br/>
Yürütülecek komutun tanımlayıcısı. *pguidCmdGroup*tarafından tanımlanan grupta olmalıdır.

*nCmdExecOpt*<br/>
Komut yürütme seçeneklerini belirtir. Varsayılan olarak, kullanıcı sormadan komutu yürütmek için ayarlayın. Değerler listesi için [OLECMDEXECOPT'a](/windows/win32/api/docobj/ne-docobj-olecmdexecopt) bakın.

*pguidCmdGroup*<br/>
Komut grubunun benzersiz tanımlayıcısı. Varsayılan olarak, standart grubu belirten NULL. *nCmdID'de* geçen komut gruba ait olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK verir; aksi takdirde, aşağıdaki hata kodlarından birini döndürür.

|Değer|Açıklama|
|-----------|-----------------|
|E_unexpected|Beklenmeyen hata oluştu.|
|E_faıl|Hata oluştu.|
|E_notımpl|MFC'nin komutu çevirmeye ve göndermeye çalışması gerektiğini belirtir.|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* NULL değildir, ancak tanınan bir komut grubu belirtmez.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* grup pGroup geçerli bir komut olarak kabul edilmez.|
|OLECMDERR_DISABLED|*nCmdID* tarafından tanımlanan komut devre dışı bırakılır ve yürütülemez.|
|OLECMDERR_NOHELP|Arayan *nCmdID* tarafından tanımlanan komut u yardım istedi, ancak yardım yok.|
|OLECMDERR_CANCELLED|Kullanıcı yürütmeyi iptal etti.|

### <a name="remarks"></a>Açıklamalar

*PguidCmdGroup* ve *nCmdID* parametreleri birlikte çağırmak için komutu benzersiz olarak tanımlar. *nCmdExecOpt* parametresi yapılacak tam eylemi belirtir.

## <a name="coledocobjectitemgetactiveview"></a><a name="getactiveview"></a>COleDocObjectItem::GetActiveView

Şu anda etkin görünümün `IOleDocumentView` arabirimine bir işaretçi almak için bu üye işlevi arayın.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda etkin görünümün [IOleDocumentView](/windows/win32/api/docobj/nn-docobj-ioledocumentview) arabirimine bir işaretçi. Geçerli görünüm yoksa, NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Döndürülen `IOleDocumentView` işaretçideki başvuru sayısı, bu işlev tarafından döndürülmeden önce artımlı değildir.

## <a name="coledocobjectitemgetpagecount"></a><a name="getpagecount"></a>COleDocObjectItem::GetPageCount

Belgedeki sayfa sayısını almak için bu üye işlevini arayın.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>Parametreler

*pnFirstPage*<br/>
Belgenin ilk sayfasının numarasına işaretçi. Arayan kişinin bu numaraya ihtiyacı olmadığını gösteren NULL olabilir.

*pcPages*<br/>
Belgedeki toplam sayfa sayısına işaretçi. Arayan kişinin bu numaraya ihtiyacı olmadığını gösteren NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="coledocobjectitemonprepareprinting"></a><a name="onprepareprinting"></a>COleDocObjectItem::OnPreparePrinting

Bu üye işlev, yazdırmak için bir belge hazırlamak için çerçeve tarafından çağrılır.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Yazdırma komutunu gönderen [cview](../../mfc/reference/cview-class.md) nesnesine işaretçi.

*Pınfo*<br/>
Yazdırılacak işi açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) nesnesine işaretçi.

*bPrintAll*<br/>
Belgenin tamamının yazdırılıp yazdırılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="coledocobjectitemonprint"></a><a name="onprint"></a>COleDocObjectItem::OnPrint

Bu üye işlev, bir belgeyi yazdırmak için çerçeve tarafından çağrılır.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pCaller*<br/>
Yazdırma komutunu gönderen cview nesnesine işaretçi.

*Pınfo*<br/>
Yazdırılacak işi açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) nesnesine işaretçi.

*bPrintAll*<br/>
Belgenin tamamının yazdırılıp yazdırılmayacağını belirtir.

## <a name="coledocobjectitemquerycommand"></a><a name="querycommand"></a>COleDocObjectItem::QueryCommand

Kullanıcı arabirimi olayları tarafından oluşturulan bir veya daha fazla komutun durumu için sorgular.

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>Parametreler

*nCmdID*<br/>
için sorgulanan komutun tanımlayıcısı.

*pdwDurum*<br/>
Sorgu nun bir sonucu olarak döndürülen bayraklar için bir işaretçi. Olası değerlerin listesi için [Bkz. OLECMDF.](/windows/win32/api/docobj/ne-docobj-olecmdf)

*pCmdMetin*<br/>
Tek bir komut için ad ve durum bilgilerini döndürecek bir [OLECMDTEXT](/windows/win32/api/docobj/ns-docobj-olecmdtext) yapısını işaretçi. Arayanın bu bilgilere ihtiyacı olmadığını belirtmek için NULL olabilir.

*pguidCmdGroup*<br/>
Komut grubunun benzersiz tanımlayıcısı; standart grubu belirtmek için NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

İade değerlerinin tam listesi için Windows SDK'daki [IOleCommandTarget::QueryStatus'a](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) bakın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [IOleCommandTarget::QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) yönteminin işlevselliğini taklit eder.

## <a name="coledocobjectitemrelease"></a><a name="release"></a>COleDocObjectItem::Sürüm

OLE bağlantılı bir öğeye bağlantıyı serbest bırakır ve açıksa kapatır. İstemci öğesini yok etmez.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>Parametreler

*dwCloseOption*<br/>
OLE öğesinin yüklenen duruma geri döndüğünde hangi koşullar altında kaydedilince kaydedilmeye karar veren bayrak. Olası değerlerin listesi için [Bkz. COleClientItem::Kapat.](../../mfc/reference/coleclientitem-class.md#close)

### <a name="remarks"></a>Açıklamalar

İstemci öğesini yok etmez.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[CDocObjectServerItem Sınıfı](../../mfc/reference/cdocobjectserveritem-class.md)
