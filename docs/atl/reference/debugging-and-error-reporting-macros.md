---
title: Hata Ayıklama ve Hata Raporlama Makroları
ms.date: 05/06/2019
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
ms.openlocfilehash: 69ab6e17bfb1ec85ddb5b8c19c18010a9b4f3df6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330193"
---
# <a name="debugging-and-error-reporting-macros"></a>Hata Ayıklama ve Hata Raporlama Makroları

Bu makrolar yararlı hata ayıklama ve izleme tesisleri sağlar.

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Çıkış penceresine, çağrıldığında `_Module.Term` algılanan arabirim sızıntılarını yazar.|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Çıkış penceresine `QueryInterface` yapılan tüm çağrıları yazar.|
|[Atlassert](#atlassert)|C çalışma zamanı kitaplığında bulunan [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroile aynı işlevselliği gerçekleştirir.|
|[ATLENSURE](#atlensure)|Parametrelerdoğrulama gerçekleştirir. Gerekirse `AtlThrow` arayın|
|[ATLTRACENOTIMPL](#atltracenotimpl)|Boşaltma aygıtına belirtilen işlevin uygulanmadığını belirten bir ileti gönderir.|
|[ATLTRACE](#atltrace)|Belirtilen bayraklara ve düzeylere göre hata ayıklama penceresi gibi bir çıktı aygıtına uyarıları bildirir. Geriye dönük uyumluluk için dahildir.|
|[ATLTRACE2](#atltrace2)|Belirtilen bayraklara ve düzeylere göre hata ayıklama penceresi gibi bir çıktı aygıtına uyarıları bildirir.|

## <a name="_atl_debug_interfaces"></a><a name="_atl_debug_interfaces"></a>_ATL_DEBUG_INTERFACES

Tüm `AddRef` bunları izlemek ve bileşenlerinizin arabirimlerini `Release` çıkış penceresine çağıracak herhangi bir ATL üstbilgi dosyasını eklemeden önce bu makroyu tanımlayın.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>Açıklamalar

İzleme çıktısı aşağıda gösterildiği gibi görünür:

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

Her iz ilk bölümü her `ATL: QIThunk`zaman olacaktır . Sonraki kullanılan belirli *arabirim thunk* tanımlayan bir değerdir. Arabirim thunk bir başvuru sayısını korumak ve burada kullanılan izleme yeteneğini sağlamak için kullanılan bir nesnedir. `IUnknown` Arabirim istekleri `QueryInterface` dışında her çağrıda yeni bir arabirim thunk oluşturulur (bu durumda, aynı thunk COM kimlik kurallarına uymak için her zaman döndürülür).

Daha sonra hangi `AddRef` `Release` yöntemin çağrıldığını görür sünüz veya belirtirsiniz. Bunu takiben, arabirim başvuru sayısı değiştirilen nesneyi tanımlayan bir değer görürsünüz. İzlenen değer nesnenin **bu** işaretçisidir.

İzlenir başvuru sayısı, o thunk'tan sonra `AddRef` `Release` veya çağrıldıktan sonra yapılan başvuru sayısıdır. Bu başvuru sayısının nesnenin başvuru sayısıyla eşleşmeyebileceğini unutmayın. Her thunk, COM'un başvuru sayma kurallarına tam olarak uymanıza yardımcı olmak için kendi başvuru sayısını korur.

İzlenen son bilgi parçası nesnenin adı dır ve arabirim `AddRef` `Release` veya çağrıdan etkilenir.

Sunucu kapandığında ve `_Module.Term` çağrıldığında algılanan arabirim sızıntıları aşağıdaki gibi günlüğe kaydedilir:

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

Burada sağlanan bilgiler doğrudan önceki izleme ifadelerinde sağlanan bilgilere eşlenir, böylece bir arayüz thunk tüm ömrü boyunca referans sayımları inceleyebilirsiniz. Buna ek olarak, bu arabirim thunk maksimum başvuru sayısı bir göstergesi olsun.

> [!NOTE]
> _ATL_DEBUG_INTERFACES perakende yapılarda kullanılabilir.

## <a name="_atl_debug_qi"></a><a name="_atl_debug_qi"></a>_ATL_DEBUG_QI

Çıkış penceresine `QueryInterface` yapılan tüm çağrıları yazar.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>Açıklamalar

Bir çağrı `QueryInterface` başarısız olursa, çıkış penceresi görüntülenir:

*arayüz adı* - `failed`

## <a name="atlassert"></a><a name="atlassert"></a>Atlassert

ATLASSERT makrosu, C çalışma zamanı kitaplığında bulunan [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroyla aynı işlevselliği gerçekleştirir.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>Parametreler

*booleanExpression*<br/>
Sıfır olmayan veya 0 olarak değerlendiren ifade (işaretçiler dahil).

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, ATLASSERT *booleanExpression'ı* değerlendirir ve sonuç yanlış olduğunda hata ayıklama raporu oluşturur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef.h

## <a name="atlensure"></a><a name="atlensure"></a>ATLENSURE

Bu makro, bir işleve geçirilen parametreleri doğrulamak için kullanılır.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>Parametreler

*booleanExpression*<br/>
Test edilecek bir boolean ifadesini belirtir.

*Hr*<br/>
Döndürmek için bir hata kodu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makrolar, kullanıcıyı yanlış parametre kullanımını algılamak ve bildirmek için bir mekanizma sağlar.

Makro ATLASSERT çağırır ve koşul `AtlThrow`başarısız olursa çağırır.

ATLENSURE durumda, `AtlThrow` E_FAIL ile çağrılır.

ATLENSURE_THROW durumda, `AtlThrow` belirtilen HRESULT ile çağrılır.

ATLENSURE ve ATLASSERT arasındaki fark, ATLENSURE'nin Sürüm yapılarında ve Hata Ayıklama yapılarında bir özel durum oluşturmasıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="atltracenotimpl"></a><a name="atltracenotimpl"></a>ATLTRACENOTIMPL

ATL hata ayıklama oluşturur, dize gönderir *"funcname* uygulanmaz" döküm cihazına ve E_NOTIMPL döndürür.

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>Parametreler

*funcname*<br/>
[içinde] Uygulanmayan işlevin adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Sürüm oluşturur, sadece E_NOTIMPL döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltrace.h

## <a name="atltrace"></a><a name="atltrace"></a>ATLTRACE

Belirtilen bayraklara ve düzeylere göre hata ayıklama penceresi gibi bir çıktı aygıtına uyarıları bildirir. Geriye dönük uyumluluk için dahildir.

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>Parametreler

*Exp*<br/>
[içinde] Çıktı penceresine gönderilecek dize ve değişkenler veya bu iletileri yakan herhangi bir uygulama.

*Kategori*<br/>
[içinde] Rapor verilebilen olay veya yöntem türü. Kategoriler listesi için Açıklamalar'a bakın.

*Düzey*<br/>
[içinde] Raporlamak için izleme düzeyi. Ayrıntılar için Açıklamalar'a bakın.

*lpszFormat*<br/>
[içinde] Boşaltma aygıtına göndermek için biçimlendirilmiş dize.

### <a name="remarks"></a>Açıklamalar

ATLTRACE'in açıklaması için [ATLTRACE2'ye](#atltrace2) bakın. ATLTRACE ve ATLTRACE2 aynı davranışa sahip, ATLTRACE geriye dönük uyumluluk için dahildir.

## <a name="atltrace2"></a><a name="atltrace2"></a>ATLTRACE2

Belirtilen bayraklara ve düzeylere göre hata ayıklama penceresi gibi bir çıktı aygıtına uyarıları bildirir.

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTR lpszFormat,  ...);
```

### <a name="parameters"></a>Parametreler

*Exp*<br/>
[içinde] Çıktı penceresine gönderilecek dize veya bu iletileri yakan herhangi bir uygulama.

*Kategori*<br/>
[içinde] Rapor verilebilen olay veya yöntem türü. Kategoriler listesi için Açıklamalar'a bakın.

*Düzey*<br/>
[içinde] Raporlamak için izleme düzeyi. Ayrıntılar için Açıklamalar'a bakın.

*lpszFormat*<br/>
[içinde] Dökümü `printf`aygıtına göndermek için bir dize oluşturmak için kullanılacak -stil biçimi dizesi.

### <a name="remarks"></a>Açıklamalar

ATLTRACE2'nin kısa biçimi hata ayıklamanın çıkış penceresine bir dize yazar. ATLTRACE2'nin ikinci biçimi de hata ayıklama nın çıkış penceresine çıktı yazar, ancak ATL/MFC İzleme Aracı'nın ayarlarına tabidir (Bkz. [ATLTraceTool Sample](../../overview/visual-cpp-samples.md)). Örneğin, *düzey* 4'e, ATL/MFC İzleme Aracı'nı da 0 düzeyine ayarlarsanız, iletiyi görmezsiniz. *düzeyi* 0, 1, 2, 3 veya 4 olabilir. Varsayılan, 0, yalnızca en ciddi sorunları bildirir.

*Kategori* parametresi, ayarlayabilmek için iz bayraklarını listeler. Bu bayraklar, bildirmek istediğiniz yöntem türlerine karşılık gelir. Aşağıdaki tablolarda *kategori* parametresi için kullanabileceğiniz geçerli izleme bayrakları listelenizdir.

### <a name="atl-trace-flags"></a>ATL İz Bayrakları

|ATL Kategorisi|Açıklama|
|------------------|-----------------|
|`atlTraceGeneral`|Tüm ATL uygulamaları hakkında raporlar. Varsayılan.|
|`atlTraceCOM`|COM yöntemleri hakkında raporlar.|
|`atlTraceQI`|QueryInterface aramaları hakkındaki raporlar.|
|`atlTraceRegistrar`|Nesnelerin kaydı yla ilgili raporlar.|
|`atlTraceRefcount`|Referans sayısını değiştirme raporları.|
|`atlTraceWindowing`|Windows yöntemleri hakkında raporlar; örneğin, geçersiz bir ileti haritası kimliği bildirir.|
|`atlTraceControls`|Denetimler hakkındaki raporlar; örneğin, bir denetim veya penceresi yok edildiğinde raporlar.|
|`atlTraceHosting`|İletileri barındıran raporlar; örneğin, bir kapsayıcıdaki istemci etkinleştirildiğinde raporlar.|
|`atlTraceDBClient`|OLE DB Tüketici Şablonu raporları; örneğin, GetData'ya yapılan bir çağrı başarısız olduğunda, çıktı HRESULT'ı içerebilir.|
|`atlTraceDBProvider`|OLE DB Sağlayıcı Şablonu hakkındaki raporlar; örneğin, bir sütun oluşturma başarısız oldu raporlar.|
|`atlTraceSnapin`|MMC SnapIn uygulaması için raporlar.|
|`atlTraceNotImpl`|Belirtilen işlevin uygulanmadığını bildirir.|
|`atlTraceAllocation`|Atldbgmem.h'deki bellek hata ayıklama araçları tarafından yazdırılan iletileri raporlar.|

### <a name="mfc-trace-flags"></a>MFC İzleme Bayrakları

|MFC Kategorisi|Açıklama|
|------------------|-----------------|
|`traceAppMsg`|Genel amaç, MFC mesajları. Her zaman tavsiye edilir.|
|`traceDumpContext`|[CDumpContext](../../mfc/reference/cdumpcontext-class.md)gelen mesajlar .|
|`traceWinMsg`|MFC'nin ileti işleme kodundan gelen iletiler.|
|`traceMemory`|MFC'nin bellek yönetim kodundan gelen iletiler.|
|`traceCmdRouting`|MFC'nin Windows komut yönlendirme kodundan gelen iletiler.|
|`traceHtml`|MFC'nin DHTML iletişim desteğinden gelen iletiler.|
|`traceSocket`|MFC'nin soket desteğinden gelen iletiler.|
|`traceOle`|MFC'nin OLE desteğinden gelen mesajlar.|
|`traceDatabase`|MFC veritabanı desteğinden gelen iletiler.|
|`traceInternet`|MFC'nin Internet desteğinden gelen iletiler.|

Özel izleme kategorisi bildirmek için sınıfın genel `CTraceCategory` bir örneğini aşağıdaki gibi bildirin:

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

Bu örnekte MY_CATEGORY kategori adı, *kategori* parametresine belirttiğiniz addır. İlk parametre, ATL/MFC İzleme Aracı'nda görünecek kategori adıdır. İkinci parametre varsayılan izleme düzeyidir. Bu parametre isteğe bağlıdır ve varsayılan izleme düzeyi 0'dır.

Kullanıcı tanımlı bir kategori kullanmak için:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

İzleme iletilerine filtre geçmek istediğinizi belirtmek için, bu makrolar için tanımları ekstreden `#include <atlbase.h>` önce Stdafx.h'ye ekleyin.

Alternatif olarak, Filtreyi **Özellik Sayfaları** iletişim kutusundaki önişlemci yönergelerinde ayarlayabilirsiniz. **Önişlemci** sekmesini tıklatın ve ardından genel olarak **Önİşlemci Tanımları'nı** edin meslekler kutusuna ekleyin.

Atlbase.h, ATLTRACE2 makrolarının varsayılan tanımlarını içerir ve atlbase.h işlenmeden önce bu sembolleri tanımlamazsanız bu tanımlar kullanılır.

Sürüm oluşturur, ATLTRACE2 derler `(void) 0`.

ATLTRACE2, biçimlendirdikten sonra damlama aygıtına gönderilecek dize içeriğini en fazla 1023 karakterle sınırlar.

ATLTRACE ve ATLTRACE2 aynı davranışa sahip, ATLTRACE geriye dönük uyumluluk için dahildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[Hata Ayıklama ve Hata Raporlama Genel İşlevleri](../../atl/reference/debugging-and-error-reporting-global-functions.md)
