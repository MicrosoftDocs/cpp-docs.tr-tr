---
description: 'Daha fazla bilgi için: hata ayıklama ve hata raporlama makroları'
title: Hata ayıklama ve hata raporlama makroları
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
ms.openlocfilehash: 573c3f341ff9f9df58337b75e1080dde960d232c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139951"
---
# <a name="debugging-and-error-reporting-macros"></a>Hata ayıklama ve hata raporlama makroları

Bu makrolar yararlı hata ayıklama ve izleme olanakları sağlar.

|Ad|Açıklama|
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Çıkış penceresine, çağrıldığında algılanan tüm arabirim sızıntılarına yazar `_Module.Term` .|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Tüm çağrıları `QueryInterface` Çıkış penceresine yazar.|
|[ATLASSERT](#atlassert)|C çalışma zamanı kitaplığı 'nda bulunan [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroyla aynı işlevi gerçekleştirir.|
|[ATLENEMIN](#atlensure)|Parametre doğrulaması gerçekleştirir. `AtlThrow`Gerekirse çağır|
|[ATLTRACENOTIMPL](#atltracenotimpl)|Döküm cihazına belirtilen işlevin uygulanmadığından bir ileti gönderir.|
|[ATLTRACE](#atltrace)|Belirtilen bayraklara ve düzeylere göre hata ayıklayıcı penceresi gibi bir çıktı cihazına uyarı bildirir. Geriye dönük uyumluluk için eklenmiştir.|
|[ATLTRACE2](#atltrace2)|Belirtilen bayraklara ve düzeylere göre hata ayıklayıcı penceresi gibi bir çıktı cihazına uyarı bildirir.|

## <a name="_atl_debug_interfaces"></a><a name="_atl_debug_interfaces"></a> _ATL_DEBUG_INTERFACES

Tüm ATL üstbilgi dosyalarını, tümünü izlemek için `AddRef` ve `Release` bileşenlerinizde yer alan tüm çağrıların çıkış penceresine çağrı eklemeden önce bu makroyu tanımlayın.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>Açıklamalar

İzleme çıktısı aşağıda gösterildiği gibi görünür:

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

Her izlemenin ilk bölümü her zaman olur `ATL: QIThunk` . Daha sonra, kullanılan belirli *arabirim dönüştürücü* tanımlayan bir değerdir. Arabirim dönüştürücü, başvuru sayısını korumak ve burada kullanılan izleme özelliğini sağlamak için kullanılan bir nesnedir. Arabirim istekleri hariç her çağrıda yeni bir arabirim Dönüştürücüsü oluşturulur `QueryInterface` `IUnknown` (Bu durumda, com 'un kimlik kurallarına uymak için her seferinde aynı dönüştürücü döndürülür).

Bir sonraki adımda `AddRef` `Release` hangi yöntemin çağrıldığını görürsünüz veya bunu gösterir. Bundan sonra, arabirim başvuru sayısı değiştirilen nesneyi tanımlayan bir değer görürsünüz. İzlenen değer **`this`** nesnenin işaretçisidir.

İzlenen başvuru sayısı, veya çağrıldıktan sonra bu dönüştürücü üzerindeki başvuru sayısıdır `AddRef` `Release` . Bu başvuru sayısının nesnenin başvuru sayısıyla eşleşmediğini unutmayın. Her dönüştürücü, COM 'un başvuru sayma kurallarına tam olarak uyum sağlamak için kendi başvuru sayısını tutar.

İzlenen bilgilerin son parçası nesnenin adı ve `AddRef` veya çağrısından etkilenen arabirimdir `Release` .

Sunucu kapandığında algılanan ve çağrıldığında algılanan tüm arabirim sızıntıları `_Module.Term` şöyle günlüğe kaydedilir:

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

Burada belirtilen bilgiler doğrudan önceki izleme deyimlerinde belirtilen bilgilerle eşlenir. böylece, bir arabirim isleyicinin tüm kullanım ömrü boyunca başvuru sayılarını inceleyebilirsiniz. Ayrıca, bu arabirim dönüştürücü üzerindeki en yüksek başvuru sayısı hakkında bir bildirim alırsınız.

> [!NOTE]
> _ATL_DEBUG_INTERFACES, perakende yapılarında kullanılabilir.

## <a name="_atl_debug_qi"></a><a name="_atl_debug_qi"></a> _ATL_DEBUG_QI

Tüm çağrıları `QueryInterface` Çıkış penceresine yazar.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>Açıklamalar

Çağrısı `QueryInterface` başarısız olursa çıkış penceresi görüntülenir:

*Arabirim adı* - `failed`

## <a name="atlassert"></a><a name="atlassert"></a> ATLASSERT

ATLASSERT makrosu, C çalışma zamanı kitaplığı 'nda bulunan [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroyla aynı işlevselliği gerçekleştirir.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sıfır olmayan veya 0 olarak değerlendirilen ifade (işaretçiler dahil).

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, ATLASSERT, *Boolean* değerlendirir ve sonuç false olduğunda bir hata ayıklama raporu oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef. h

## <a name="atlensure"></a><a name="atlensure"></a> ATLENEMIN

Bu makro, bir işleve geçirilen parametreleri doğrulamak için kullanılır.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sınanacak Boole ifadesini belirtir.

*sa*<br/>
Döndürülecek bir hata kodu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makrolar, kullanıcı hatalı parametre kullanımını tespit etmek ve kullanıcıya bildirmek için bir mekanizma sağlar.

Makro ATLASSERT ve koşul başarısız olursa çağırır `AtlThrow` .

ATLENEMIN durumda, `AtlThrow` E_FAIL ile çağırılır.

ATLENSURE_THROW durumda, `AtlThrow` BELIRTILEN HRESULT ile çağırılır.

ATLENRELEN ve ATLASSERT arasındaki fark, ATLENEMIN 'in sürüm yapılarında ve hata ayıklama yapılarında bir özel durum yaratmanızdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="atltracenotimpl"></a><a name="atltracenotimpl"></a> ATLTRACENOTIMPL

ATL hata ayıklama Derlemeleriyle, " *funcname* uygulanmadı" dizesini döküm cihazına gönderir ve E_NOTIMPL döndürür.

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>Parametreler

*funcname*<br/>
'ndaki Uygulanmayan işlevin adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Yayın yapıları ' nda, yalnızca E_NOTIMPL döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltrace. h

## <a name="atltrace"></a><a name="atltrace"></a> ATLTRACE

Belirtilen bayraklara ve düzeylere göre hata ayıklayıcı penceresi gibi bir çıktı cihazına uyarı bildirir. Geriye dönük uyumluluk için eklenmiştir.

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>Parametreler

*exp*<br/>
'ndaki Çıkış penceresine veya bu iletileri yakaladığı herhangi bir uygulamaya gönderilmek üzere dize ve değişkenler.

*alan*<br/>
'ndaki Raporlanacak olay veya yöntem türü. Kategorilerin listesi için bkz. açıklamalar.

*düzey*<br/>
'ndaki Raporlanacak izlemenin düzeyi. Ayrıntılar için bkz. açıklamalar.

*lpszFormat*<br/>
'ndaki Döküm cihazına gönderilmek üzere biçimlendirilen dize.

### <a name="remarks"></a>Açıklamalar

ATLTRACE açıklaması için bkz. [ATLTRACE2](#atltrace2) . ATLTRACE ve ATLTRACE2 aynı davranışa sahiptir ve geriye dönük uyumluluk için ATLTRACE dahil edilmiştir.

## <a name="atltrace2"></a><a name="atltrace2"></a> ATLTRACE2

Belirtilen bayraklara ve düzeylere göre hata ayıklayıcı penceresi gibi bir çıktı cihazına uyarı bildirir.

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTR lpszFormat,  ...);
```

### <a name="parameters"></a>Parametreler

*exp*<br/>
'ndaki Çıkış penceresine veya bu iletileri yakaladığı herhangi bir uygulamaya göndermek için kullanılan dize.

*alan*<br/>
'ndaki Raporlanacak olay veya yöntem türü. Kategorilerin listesi için bkz. açıklamalar.

*düzey*<br/>
'ndaki Raporlanacak izlemenin düzeyi. Ayrıntılar için bkz. açıklamalar.

*lpszFormat*<br/>
'ndaki `printf`Döküm cihazına göndermek üzere bir dize oluşturmak için kullanılacak olan-stili biçim dizesi.

### <a name="remarks"></a>Açıklamalar

ATLTRACE2 öğesinin kısa biçimi, hata ayıklayıcının çıkış penceresine bir dize yazar. ATLTRACE2 ikinci formu Ayrıca hata ayıklayıcının çıkış penceresine çıktıyı yazar, ancak ATL/MFC Izleme aracının ayarlarına tabidir (bkz. [ATLTraceTool örneği](../../overview/visual-cpp-samples.md)). Örneğin, *düzeyi* 4 ' e ve ATL/MFC izleme aracını 0 düzeyinde ayarlarsanız, iletiyi görmezsiniz. *düzey* 0, 1, 2, 3 veya 4 olabilir. Varsayılan, 0, yalnızca en ciddi sorunları raporlar.

*Category* parametresi, ayarlanacak izleme bayraklarını listeler. Bu bayraklar, raporlamak istediğiniz yöntemlerin türlerine karşılık gelir. Aşağıdaki tablolarda, *Kategori* parametresi için kullanabileceğiniz geçerli izleme bayrakları listelenmektedir.

### <a name="atl-trace-flags"></a>ATL Izleme bayrakları

|ATL kategorisi|Açıklama|
|------------------|-----------------|
|`atlTraceGeneral`|Tüm ATL uygulamalarındaki raporlar. Varsayılan.|
|`atlTraceCOM`|COM yöntemleriyle ilgili raporlar.|
|`atlTraceQI`|QueryInterface çağrılarında raporlar.|
|`atlTraceRegistrar`|Nesnelerin kaydedilmesine ilişkin raporlar.|
|`atlTraceRefcount`|Başvuru sayısı değiştirme raporları.|
|`atlTraceWindowing`|Windows yöntemleriyle ilgili raporlar; Örneğin, geçersiz bir ileti eşleme KIMLIĞI bildirir.|
|`atlTraceControls`|Denetimler hakkında raporlar; Örneğin, bir denetim veya pencere yok edildiğinde raporlar.|
|`atlTraceHosting`|İletileri barındıran raporlar; Örneğin, bir kapsayıcıdaki bir istemci etkinleştirildiğinde raporlar.|
|`atlTraceDBClient`|OLE DB tüketici şablonundaki raporlar; Örneğin, bir GetData çağrısı başarısız olursa, çıktı HRESULT içerebilir.|
|`atlTraceDBProvider`|OLE DB sağlayıcısı şablonundaki raporlar; Örneğin, bir sütunun oluşturulması başarısız olursa raporlar.|
|`atlTraceSnapin`|MMC ek bileşeni uygulamasının raporları.|
|`atlTraceNotImpl`|Belirtilen işlevin uygulanmadığını bildirir.|
|`atlTraceAllocation`|Atldbgmem. h içindeki bellek hata ayıklama araçları tarafından yazdırılan iletileri raporlar.|

### <a name="mfc-trace-flags"></a>MFC Izleme bayrakları

|MFC kategorisi|Açıklama|
|------------------|-----------------|
|`traceAppMsg`|Genel amaçlı, MFC iletileri. Her zaman önerilir.|
|`traceDumpContext`|[CDumpContext](../../mfc/reference/cdumpcontext-class.md)iletileri.|
|`traceWinMsg`|MFC 'nin ileti işleme kodundaki iletiler.|
|`traceMemory`|MFC 'nin bellek yönetim kodundan gelen iletiler.|
|`traceCmdRouting`|MFC 'nin Windows komut yönlendirme kodundaki iletiler.|
|`traceHtml`|MFC 'nin DHTML iletişim kutusu desteğinin iletileri.|
|`traceSocket`|MFC 'nin yuva desteğinin iletileri.|
|`traceOle`|MFC 'nin OLE desteğinin iletileri.|
|`traceDatabase`|MFC 'nin veritabanı desteğinin iletileri.|
|`traceInternet`|MFC 'nin Internet desteğiyle mesajlar.|

Özel bir izleme kategorisi bildirmek için, sınıfının genel bir örneğini `CTraceCategory` Şu şekilde bildirin:

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

Bu örnekteki MY_CATEGORY kategori adı, *Kategori* parametresine belirttiğiniz addır. İlk parametre, ATL/MFC Izleme aracında görünecek kategori adıdır. İkinci parametre varsayılan izleme düzeyidir. Bu parametre isteğe bağlıdır ve varsayılan izleme düzeyi 0 ' dır.

Kullanıcı tanımlı bir kategori kullanmak için:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

İzleme iletilerini filtrelemek istediğinizi belirtmek için, deyimden önce Bu makroların tanımlarını Stbafx. h içine ekleyin `#include <atlbase.h>` .

Alternatif olarak, filtre **özelliğini Özellik sayfaları** iletişim kutusundaki önişlemci yönergeleriyle ayarlayabilirsiniz. **Önişlemci** sekmesine tıklayın ve ardından Genel ' i **Önişlemci tanımları** düzenleme kutusuna ekleyin.

Atlbase. h, ATLTRACE2 makrolarının varsayılan tanımlarını içerir ve bu tanımlar atlbase. h işlenmeden önce bu sembolleri tanımlamazsanız kullanılacaktır.

Yayın yapıları ' nde, ATLTRACE2 derlenir `(void) 0` .

ATLTRACE2, biçimlendirmeden sonra, döküm cihazına en fazla 1023 karakter uzunluğunda olarak gönderilecek dizenin içeriğini sınırlandırır.

ATLTRACE ve ATLTRACE2 aynı davranışa sahiptir ve geriye dönük uyumluluk için ATLTRACE dahil edilmiştir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[Hata ayıklama ve hata raporlama genel Işlevleri](../../atl/reference/debugging-and-error-reporting-global-functions.md)
