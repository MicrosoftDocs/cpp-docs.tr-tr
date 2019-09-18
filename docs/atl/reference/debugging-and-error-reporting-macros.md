---
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
ms.openlocfilehash: b666ba3debe164118c9b40b90313646592b04876
ms.sourcegitcommit: bf724dfc639b16d5410fab72183f8e6b781338bc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71062044"
---
# <a name="debugging-and-error-reporting-macros"></a>Hata ayıklama ve hata raporlama makroları

Bu makrolar yararlı hata ayıklama ve izleme olanakları sağlar.

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Çıkış penceresine, çağrıldığında algılanan `_Module.Term` tüm arabirim sızıntılarına yazar.|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Tüm çağrıları `QueryInterface` çıkış penceresine yazar.|
|[ATLASSERT](#atlassert)|C çalışma zamanı kitaplığı 'nda bulunan [_Asserte](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrosu ile aynı işlevi gerçekleştirir.|
|[ATLENEMIN](#atlensure)|Parametre doğrulaması gerçekleştirir. Gerekirse `AtlThrow` çağır|
|[ATLTRACENOTIMPL](#atltracenotimpl)|Döküm cihazına belirtilen işlevin uygulanmadığından bir ileti gönderir.|
|[ATLTRACE](#atltrace)|Belirtilen bayraklara ve düzeylere göre hata ayıklayıcı penceresi gibi bir çıktı cihazına uyarı bildirir. Geriye dönük uyumluluk için eklenmiştir.|
|[ATLTRACE2](#atltrace2)|Belirtilen bayraklara ve düzeylere göre hata ayıklayıcı penceresi gibi bir çıktı cihazına uyarı bildirir.|

##  <a name="_atl_debug_interfaces"></a>  _ATL_DEBUG_INTERFACES

Tüm ATL üstbilgi dosyalarını, tümünü izlemek için ve `AddRef` `Release` bileşenlerinizde yer alan tüm çağrıların çıkış penceresine çağrı eklemeden önce bu makroyu tanımlayın.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>Açıklamalar

İzleme çıktısı aşağıda gösterildiği gibi görünür:

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

Her izlemenin ilk bölümü her zaman `ATL: QIThunk`olur. Daha sonra, kullanılan belirli *arabirim dönüştürücü* tanımlayan bir değerdir. Arabirim dönüştürücü, başvuru sayısını korumak ve burada kullanılan izleme özelliğini sağlamak için kullanılan bir nesnedir. Arabirim`IUnknown` istekleri `QueryInterface` hariç her çağrıda yeni bir arabirim Dönüştürücüsü oluşturulur (Bu durumda, com 'un kimlik kurallarına uymak için her seferinde aynı dönüştürücü döndürülür).

Bir sonraki adımda hangi `AddRef` yöntemin `Release` çağrıldığını görürsünüz veya bunu gösterir. Bundan sonra, arabirim başvuru sayısı değiştirilen nesneyi tanımlayan bir değer görürsünüz. İzlenen değer nesnenin **Bu** işaretçisidir.

İzlenen başvuru sayısı, veya `AddRef` `Release` çağrıldıktan sonra bu dönüştürücü üzerindeki başvuru sayısıdır. Bu başvuru sayısının nesnenin başvuru sayısıyla eşleşmediğini unutmayın. Her dönüştürücü, COM 'un başvuru sayma kurallarına tam olarak uyum sağlamak için kendi başvuru sayısını tutar.

İzlenen bilgilerin son parçası nesnenin adı ve `AddRef` veya `Release` çağrısından etkilenen arabirimdir.

Sunucu kapandığında algılanan ve `_Module.Term` çağrıldığında algılanan tüm arabirim sızıntıları şöyle günlüğe kaydedilir:

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

Burada belirtilen bilgiler doğrudan önceki izleme deyimlerinde belirtilen bilgilerle eşlenir. böylece, bir arabirim isleyicinin tüm kullanım ömrü boyunca başvuru sayılarını inceleyebilirsiniz. Ayrıca, bu arabirim dönüştürücü üzerindeki en yüksek başvuru sayısı hakkında bir bildirim alırsınız.

> [!NOTE]
> _ATL_DEBUG_ıNTERFACES, perakende yapılarda kullanılabilir.

##  <a name="_atl_debug_qi"></a>  _ATL_DEBUG_QI

Tüm çağrıları `QueryInterface` çıkış penceresine yazar.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>Açıklamalar

Çağrısı `QueryInterface` başarısız olursa çıkış penceresi görüntülenir:

*Arabirim adı* - `failed`

##  <a name="atlassert"></a>ATLASSERT

ATLASSERT makrosu, C çalışma zamanı kitaplığı 'nda bulunan [_Asserte](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrosu ile aynı işlevi gerçekleştirir.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sıfır olmayan veya 0 olarak değerlendirilen ifade (işaretçiler dahil).

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, ATLASSERT, *Boolean* değerlendirir ve sonuç false olduğunda bir hata ayıklama raporu oluşturur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef. h

##  <a name="atlensure"></a>ATLENEMIN

Bu makro, bir işleve geçirilen parametreleri doğrulamak için kullanılır.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sınanacak Boole ifadesini belirtir.

*HR*<br/>
Döndürülecek bir hata kodu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makrolar, kullanıcı hatalı parametre kullanımını tespit etmek ve kullanıcıya bildirmek için bir mekanizma sağlar.

Makro ATLASSERT ve koşul başarısız olursa `AtlThrow`çağırır.

Atlenemin durumunda, `AtlThrow` E_FAIL ile çağırılır.

ATLENSURE_THROW durumunda, `AtlThrow` Belirtilen HRESULT ile çağırılır.

ATLENRELEN ve ATLASSERT arasındaki fark, ATLENEMIN 'in sürüm yapılarında ve hata ayıklama yapılarında bir özel durum yaratmanızdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="atltracenotimpl"></a>ATLTRACENOTIMPL

ATL hata ayıklama Derlemeleriyle, " *funcname* uygulanmadı" dizesini döküm cihazına GÖNDERIR ve E_NOTIMPL döndürür.

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

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltrace. h

##  <a name="atltrace"></a>ATLTRACE

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

*Kategori*<br/>
'ndaki Raporlanacak olay veya yöntem türü. Kategorilerin listesi için bkz. açıklamalar.

*düzeyde*<br/>
'ndaki Raporlanacak izlemenin düzeyi. Ayrıntılar için bkz. açıklamalar.

*lpszFormat*<br/>
'ndaki Döküm cihazına gönderilmek üzere biçimlendirilen dize.

### <a name="remarks"></a>Açıklamalar

ATLTRACE açıklaması için bkz. [ATLTRACE2](#atltrace2) . ATLTRACE ve ATLTRACE2 aynı davranışa sahiptir ve geriye dönük uyumluluk için ATLTRACE dahil edilmiştir.

##  <a name="atltrace2"></a>ATLTRACE2

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

*Kategori*<br/>
'ndaki Raporlanacak olay veya yöntem türü. Kategorilerin listesi için bkz. açıklamalar.

*düzeyde*<br/>
'ndaki Raporlanacak izlemenin düzeyi. Ayrıntılar için bkz. açıklamalar.

*lpszFormat*<br/>
'ndaki Döküm cihazına göndermek üzere bir dize oluşturmak için kullanılacak olan -stilibiçimdizesi.`printf`

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

Özel bir izleme kategorisi bildirmek için, `CTraceCategory` sınıfının genel bir örneğini şu şekilde bildirin:

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

Kategori adı, bu örnekteki MY_CATEGORY, *Kategori* parametresine belirttiğiniz addır. İlk parametre, ATL/MFC Izleme aracında görünecek kategori adıdır. İkinci parametre varsayılan izleme düzeyidir. Bu parametre isteğe bağlıdır ve varsayılan izleme düzeyi 0 ' dır.

Kullanıcı tanımlı bir kategori kullanmak için:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

İzleme iletilerini filtrelemek istediğinizi belirtmek için, `#include <atlbase.h>` deyimden önce Bu makroların tanımlarını stbafx. h içine ekleyin.

Alternatif olarak, filtre **özelliğini Özellik sayfaları** iletişim kutusundaki önişlemci yönergeleriyle ayarlayabilirsiniz. **Önişlemci** sekmesine tıklayın ve ardından Genel ' i **Önişlemci tanımları** düzenleme kutusuna ekleyin.

Atlbase. h, ATLTRACE2 makrolarının varsayılan tanımlarını içerir ve bu tanımlar atlbase. h işlenmeden önce bu sembolleri tanımlamazsanız kullanılacaktır.

Yayın yapıları ' nde, ATLTRACE2 derlenir `(void) 0`.

ATLTRACE2, biçimlendirmeden sonra, döküm cihazına en fazla 1023 karakter uzunluğunda olarak gönderilecek dizenin içeriğini sınırlandırır.

ATLTRACE ve ATLTRACE2 aynı davranışa sahiptir ve geriye dönük uyumluluk için ATLTRACE dahil edilmiştir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Larının](../../atl/reference/atl-macros.md)<br/>
[Hata Ayıklama ve Hata Raporlama Genel İşlevleri](../../atl/reference/debugging-and-error-reporting-global-functions.md)
