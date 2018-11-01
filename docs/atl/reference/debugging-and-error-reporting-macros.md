---
title: Hata ayıklama ve hata raporlama makroları
ms.date: 11/04/2016
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
ms.openlocfilehash: 5de597484db727646b80bd522f11465f442393fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522313"
---
# <a name="debugging-and-error-reporting-macros"></a>Hata ayıklama ve hata raporlama makroları

Bu makrolar kullanışlı hata ayıklama ve izleme olanakları sağlayın.

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Yazar, çıkış penceresinde, herhangi bir arabirimde sızıntıları zaman algılanır `_Module.Term` çağrılır.|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Tüm çağrılar için Yazar `QueryInterface` çıkış penceresine.|
|[ATLASSERT](#atlassert)|Aynı işlevi gerçekleştirir [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrosu C Çalışma Zamanı Kitaplığı'nda bulunamadı.|
|[ATLENSURE](#atlensure)|Parametre doğrulama gerçekleştirir. Çağrı `AtlThrow` gerekirse|
|[ATLTRACENOTIMPL](#atltracenotimpl)|Bir ileti, belirtilen işlev uygulanmadı döküm cihaza gönderir.|
|[ATLTRACE](#alttrace)|Belirtilen bayraklar ve düzeylerine göre hata ayıklayıcısı penceresi gibi bir çıktı cihazına uyarılar bildirir. Geriye dönük uyumluluk için dahildir.|
|[ATLTRACE2](#atltrace2)|Belirtilen bayraklar ve düzeylerine göre hata ayıklayıcısı penceresi gibi bir çıktı cihazına uyarılar bildirir.|

##  <a name="_atl_debug_interfaces"></a>  _ATL_DEBUG_INTERFACES

ATL üstbilgi dosyalarını tüm izleme eklemeden önce bu makroyu tanımla `AddRef` ve `Release` çıkış penceresine, bileşenlerin arabirimleri çağırır.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>Açıklamalar

İzleme çıktısı, aşağıda gösterildiği gibi görünür:

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

Her izleme ilk bölümünü her zaman olacaktır `ATL: QIThunk`. Ardından, belirli tanımlayan bir değer olan *dönüştürücü arabirim* kullanılan. Bir arabirim dönüştürücü başvuru sayısı Bakımı ve burada kullanılan izleme yeteneği sağlamak için kullanılan bir nesnedir. Yeni bir arabirim dönüştürücü yapılan her çağrı oluşturulan `QueryInterface` istekleri dışında `IUnknown` arabirimi (Bu durumda, aynı dönüştürücü her COM'ın kimlik kurallarına uyan döndürülür).

Sonraki göreceğiniz `AddRef` veya `Release` belirten hangi yöntemi çağrıldı. Olan arabirimi başvuru sayısını değiştirildi nesneyi tanımlayan bir değer görürsünüz. İzlenen değer **bu** nesne işaretçisi.

Bu dönüştürücü sonra başvuru sayısını izleneceğini başvuru sayısı olan `AddRef` veya `Release` çağrıldı. Bu başvuru sayısı nesne başvuru sayımını eşleşmeyebilir unutmayın. Her dönüştürücü tam başvuru sayımını COM'ın kurallarıyla uyumlu yardımcı olmak için kendi başvuru sayısını tutar.

Son izlenen nesne ve tarafından etkilenen arabirimi adını bilgidir `AddRef` veya `Release` çağırın.

Herhangi bir arabirim sunucu kapatıldığında, algılanan sızıntıları ve `_Module.Term` çağrıldığında kaydedilir şöyle:

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

Bilgileri burada önceki izleme deyimleri içinde sağlanan bilgileri doğrudan eşlenir sağlanan, incelemeniz başvuru arabirimi dönüştürücü tüm kullanım ömrü boyunca sayar. Ayrıca, bu arabirimi dönüştürücü üzerinde en yüksek başvuru sayısı bir göstergesi alın.

> [!NOTE]
> _ATL_DEBUG_INTERFACES perakende sürümlerde kullanılabilir.

##  <a name="_atl_debug_qi"></a>  _ATL_DEBUG_QI

Tüm çağrılar için Yazar `QueryInterface` çıkış penceresine.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>Açıklamalar

Bir çağrı, `QueryInterface` başarısız oldu, çıkış penceresinde görüntülenir:

*Arabirim adı* - `failed`

##  <a name="atlassert"></a>  ATLASSERT

ATLASSERT makro aynı işlevi gerçekleştirir [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrosu C Çalışma Zamanı Kitaplığı'nda bulunamadı.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>Parametreler

*booleanDeyimi*<br/>
İfade (işaretçileri dahil), sıfır ya da 0 olur.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında ATLASSERT değerlendirir *booleanDeyimi* ve sonucun false olduğu bir hata ayıklama raporunu oluşturur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldef.h

##  <a name="atlensure"></a>  ATLENSURE

Bu makro, parametreler bir işleve doğrulamak için kullanılır.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>Parametreler

*booleanDeyimi*<br/>
Test edilecek bir Boole ifadesini belirtir.

*İK*<br/>
Döndürülecek bir hata kodunu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makrolar, algılamak ve hatalı parametre kullanımı kullanıcıya bildirmek için bir mekanizma sağlar.

Makro çağrısı ATLASSERT ve koşul çağrıları başarısız olursa `AtlThrow`.

ATLENSURE durumda `AtlThrow` E_FAIL ile adlandırılır.

ATLENSURE_THROW durumda `AtlThrow` belirtilen HRESULT çağrılır.

ATLENSURE ATLASSERT arasındaki fark, ATLENSURE sürüm yapılarında de hata ayıklama yapıları olduğu gibi bir özel durum oluşturur ' dir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="atltracenotimpl"></a>  ATLTRACENOTIMPL

ATL hata ayıklama yapılarında dize gönderir " *funcname* uygulanmadı" döküm cihaz ve E_NOTIMPL döndürür.

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>Parametreler

*funcname*<br/>
[in] Henüz uygulanmadı işlevinin adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Sürüm yapılarında yalnızca E_NOTIMPL döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltrace.h

##  <a name="atltrace"></a>  ATLTRACE

Belirtilen bayraklar ve düzeylerine göre hata ayıklayıcısı penceresi gibi bir çıktı cihazına uyarılar bildirir. Geriye dönük uyumluluk için dahildir.

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>Parametreler

*exp*<br/>
[in] Visual C++ çıkış penceresine veya bu iletiler yakalar herhangi bir uygulama göndermek için değişkenleri ve dize.

*Kategori*<br/>
[in] Olay ya da rapora olan yöntem türü. Kategori listesi için açıklamalara bakın.

*düzeyi*<br/>
[in] Rapor için izleme düzeyi. Ayrıntılar için açıklamalara bakın.

*lpszFormat*<br/>
[in] Döküm cihaza göndermek için biçimlendirilmiş dize.

### <a name="remarks"></a>Açıklamalar

Bkz: [ATLTRACE2](#atltrace2) ATLTRACE açıklaması. ATLTRACE ve ATLTRACE2 aynı davranışa sahip, ATLTRACE geriye dönük uyumluluk için dahildir.

##  <a name="atltrace2"></a>  ATLTRACE2

Belirtilen bayraklar ve düzeylerine göre hata ayıklayıcısı penceresi gibi bir çıktı cihazına uyarılar bildirir.

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```

### <a name="parameters"></a>Parametreler

*exp*<br/>
[in] Visual C++ çıkış penceresine veya bu iletiler yakalar herhangi bir uygulama göndermek için dize.

*Kategori*<br/>
[in] Olay ya da rapora olan yöntem türü. Kategori listesi için açıklamalara bakın.

*düzeyi*<br/>
[in] Rapor için izleme düzeyi. Ayrıntılar için açıklamalara bakın.

*lpszFormat*<br/>
[in] `printf`-Döküm cihaza göndermek için bir dize oluşturmak için kullanılacak biçim dizesi stili.

### <a name="remarks"></a>Açıklamalar

ATLTRACE2 kısa formunu hata ayıklayıcının çıkış penceresinde bir dize yazar. ATLTRACE2 ikinci biçimi de çıkış hata ayıklayıcının çıkış penceresinde Yazar ancak ATL/MFC izleme aracı ayarlarını tabi olduğunu (bkz [ATLTraceTool örnek](../../visual-cpp-samples.md)). Örneğin, ayarlarsanız *düzeyi* 4 ve ATL/MFC izleme aracı düzeyi 0 ', ileti görüntülenmez. *düzey* 0, 1, 2, 3 veya 4 olabilir. Varsayılan, 0, yalnızca en önemli sorunları bildirir.

*Kategori* parametre kümesi için izleme bayrakları listeler. Bu bayraklar raporlamak istediğiniz yöntemleri türlerine karşılık gelir. Aşağıdaki tablolarda listelemek için kullanabileceğiniz geçerli izleme bayrakları *kategori* parametresi.

### <a name="atl-trace-flags"></a>ATL İzleme Bayrakları

|ATL kategorisi|Açıklama|
|------------------|-----------------|
|`atlTraceGeneral`|Raporlar tüm ATL uygulamalar. Varsayılan.|
|`atlTraceCOM`|COM yöntemleri raporları.|
|`atlTraceQI`|QueryInterface çağrıları raporları.|
|`atlTraceRegistrar`|Kayıt nesnelerin raporları.|
|`atlTraceRefcount`|Başvuru sayısını değiştirme raporlar.|
|`atlTraceWindowing`|Windows yöntemleri raporlarda; Örneğin, bir geçersiz ileti eşleme kimliği bildirir|
|`atlTraceControls`|Denetimleri raporlarda; Örneğin, bir denetim veya kendi penceresini yok edildiğinde bildirir.|
|`atlTraceHosting`|Raporlar; iletileri barındırma Örneğin, bir kapsayıcıdaki bir istemci etkinleştirildiğinde bildirir.|
|`atlTraceDBClient`|OLE DB tüketici şablonu raporlarda; Örneğin, bir çağrı, GetData başarısız için çıkış HRESULT içerebilir.|
|`atlTraceDBProvider`|OLE DB sağlayıcı şablonu raporlarda; Örneğin, bir sütun oluşturulamadı, bildirir.|
|`atlTraceSnapin`|MMC ek bileşenini uygulama raporları.|
|`atlTraceNotImpl`|Belirtilen işlev uygulanmadı bildirir.|
|`atlTraceAllocation`|Hata ayıklama atldbgmem.h araçlarında bellek tarafından yazdırılan iletileri bildirir.|

### <a name="mfc-trace-flags"></a>MFC İzleme Bayrakları

|MFC kategorisi|Açıklama|
|------------------|-----------------|
|`traceAppMsg`|Genel amaçlı, MFC iletileri. Her zaman önerilir.|
|`traceDumpContext`|Gelen iletileri [CDumpContext](../../mfc/reference/cdumpcontext-class.md).|
|`traceWinMsg`|İletileri işleme kodunu MFC'nin iletisi.|
|`traceMemory`|MFC'nin bellek yönetimi koddan iletileri.|
|`traceCmdRouting`|MFC'nin Windows iletileri yönlendirme kod komutu.|
|`traceHtml`|MFC'nin DHTML iletişim destek iletileri.|
|`traceSocket`|MFC'nin yuva desteği iletileri.|
|`traceOle`|MFC'nin OLE desteği iletileri.|
|`traceDatabase`|MFC veritabanı desteği iletileri.|
|`traceInternet`|MFC'nin İnternet'ten gelen iletileri destekler.|

Özel İzleme kategorisi bildirmek için genel bir örneğini bildirmeniz `CTraceCategory` sınıfına aşağıdaki gibi:

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

Kategori adı, bu örnekte, MY_CATEGORY için belirttiğiniz ad olduğu *kategori* parametresi. İlk parametre ATL/MFC İzleme Aracı'nda görüntülenecek kategori addır. İkinci parametre varsayılan izleme düzeydir. Bu parametre isteğe bağlıdır ve varsayılan izleme düzeyi 0'dır.

Bir kullanıcı tanımlı kategori kullanmak için:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

İzleme iletileri filtre uygulamak istediğiniz belirtmek için önce Stdafx.h Bu makroların tanımlarını eklemek `#include <atlbase.h>` deyimi.

Alternatif olarak, önişlemci yönergeleri, filtreyi ayarlayabilirsiniz **özellik sayfaları** iletişim kutusu. Tıklayın **önişlemci** sekmesini ve ardından genel içine Ekle **önişlemci tanımları** düzenleme kutusu.

ATLTRACE2 makro tanımlarını varsayılan Atlbase.h içerir ve bu tanımları atlbase.h işlenmeden önce bu sembolleri tanımlamazsanız kullanılacak.

İçin sürüm yapılarında ATLTRACE2 derler `(void) 0`.

ATLTRACE2 döküm cihaza en fazla 1023 karakter biçimlendirme sonrasında gönderilecek dizenin içeriği sınırlar.

ATLTRACE ve ATLTRACE2 aynı davranışa sahip, ATLTRACE geriye dönük uyumluluk için dahildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)<br/>
[Hata Ayıklama ve Hata Raporlama Genel İşlevleri](../../atl/reference/debugging-and-error-reporting-global-functions.md)
