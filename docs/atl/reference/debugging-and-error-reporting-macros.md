---
title: Hata ayıklama ve hata raporlama makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
dev_langs:
- C++
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b99147c9eb9a331d7cc0f9064b858979d00e2804
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="debugging-and-error-reporting-macros"></a>Hata ayıklama ve hata raporlama makroları
Bu makroları yararlı hata ayıklama ve izleme olanakları sağlar.  
  
|||  
|-|-|  
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|, Herhangi bir arabirim sızdırıyor çıkış penceresine yazar zaman algılanır `_Module.Term` olarak adlandırılır.|  
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Tüm çağrıları Yazar `QueryInterface` çıkış penceresine.|  
|[ATLASSERT](#atlassert)|Aynı işlevi gerçekleştirir [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrosu C Çalışma Zamanı Kitaplığı'nda bulundu.|  
|[ATLENSURE](#atlensure)|Parametre doğrulaması gerçekleştirir. Çağrı `AtlThrow` gerekirse|  
|[ATLTRACENOTIMPL](#atltracenotimpl)|Belirtilen işlev uygulanmadı döküm cihaza bir ileti gönderir.|  
|[ATLTRACE](#alttrace)|Uyarı düzeyleri ve belirtilen bayrakları göre hata ayıklayıcı penceresini gibi bir çıktı cihazına bildirir. Geriye dönük uyumluluk için dahil.|  
|[ATLTRACE2](#atltrace2)|Uyarı düzeyleri ve belirtilen bayrakları göre hata ayıklayıcı penceresini gibi bir çıktı cihazına bildirir.|  
  
##  <a name="_atl_debug_interfaces"></a>  _ATL_DEBUG_INTERFACES  
 ATL üstbilgi dosyalarının tüm izleme eklemeden önce bu makrosu tanımlama `AddRef` ve **sürüm** çıkış penceresine, bileşenlerinizin arabirimlerindeki çağırır.  
  
```
#define _ATL_DEBUG_INTERFACES
```  
  
### <a name="remarks"></a>Açıklamalar  
 İzleme çıktısı, aşağıda gösterildiği gibi görünür:  
  
 `ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`  
  
 Her izleme ilk kısmı her zaman olacaktır `ATL: QIThunk`. Sonraki belirli tanımlayan bir değerdir *dönüştürücü arabirim* kullanılan. Bir arabirim dönüştürücü başvuru sayısı korumak ve burada kullanılan izleme yeteneği sağlamak için kullanılan bir nesnedir. Yeni bir arabirim dönüştürücü her çağrı için oluşturulan `QueryInterface` isteklerinde dışında **IUnknown** arabirimi (Bu durumda, aynı dönüştürücü her zaman COM'ın kimlik kurallarıyla uyumlu döndürülür).  
  
 Sonraki göreceğiniz `AddRef` veya **sürüm** belirten hangi yöntemi çağrıldı. Olan arabirimi başvuru sayısı değiştirildi nesnesini belirten bir değer görürsünüz. İzlenen değer **bu** nesne işaretçisi.  
  
 Sonra Bu dönüştürücü başvuru sayısına izlenen başvuru sayısı: `AddRef` veya **sürüm** çağrıldı. Bu başvuru sayısı nesne başvuru sayısı eşleşmeyebilir unutmayın. Her dönüştürücü tam COM'in başvuru sayımı kurallarıyla uyumlu yardımcı olmak için kendi başvuru sayımı tutar.  
  
 Son izlenen nesne ve tarafından etkilenen arabirimi adı bilgidir `AddRef` veya **sürüm** çağırın.  
  
 Herhangi bir arabirim sunucu kapatıldığında, algılanan sızıntıları ve `_Module.Term` çağrıldığında oturum açmış olmanız şuna benzer:  
  
 `ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`  
  
 Bilgileri doğrudan önceki izleme deyimleri sağlanan bilgilere eşlemeleri burada sağlanan, inceleyebilirsiniz için bir arabirim dönüştürücü tam yaşam süresi başvuru sayar. Ayrıca, bu arabirimi dönüştürücü göstergesidir maksimum başvuru sayısı alın.  
  
> [!NOTE]
> `_ATL_DEBUG_INTERFACES` perakende yapılarında kullanılır.  
  
##  <a name="_atl_debug_qi"></a>  _ATL_DEBUG_QI  
 Tüm çağrıları Yazar `QueryInterface` çıkış penceresine.  
  
```
#define _ATL_DEBUG_QI
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı, `QueryInterface` başarısız oldu, çıktı penceresi görüntülenir:  
  
 *Arabirim adı* - `failed`  
  
##  <a name="atlassert"></a>  ATLASSERT  
 `ATLASSERT` Makrosu aynı işlevi gerçekleştirir [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrosu C Çalışma Zamanı Kitaplığı'nda bulundu.  
  
```
ATLASSERT(booleanExpression);
```  
  
### <a name="parameters"></a>Parametreler  
 `booleanExpression`  
 Sıfır olmayan bir değer veya 0 (işaretçileri dahil) ifadesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, `ATLASSERT` değerlendirir `booleanExpression` ve sonucu false olduğunda hata ayıklama raporunu oluşturur.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldef.h  
    
##  <a name="atlensure"></a>  ATLENSURE  
 Bu makrosu bir işleve parametreleri doğrulamak için kullanılır.  
  
```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```  
  
### <a name="parameters"></a>Parametreler  
 `booleanExpression`  
 Sınanacak bir Boole ifadesini belirtir.  
  
 `hr`  
 Döndürülecek bir hata kodu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makroları algılamak ve hatalı parametre kullanım kullanıcıya bildirmek için bir mekanizma sağlar.  
  
 Makro çağrıları `ATLASSERT` ve koşul çağrıları başarısız olursa `AtlThrow`.  
  
 İçinde **ATLENSURE** durumda `AtlThrow` E_FAIL ile adlandırılır.  
  
 İçinde **ATLENSURE_THROW** durumda `AtlThrow` belirtilen HRESULT olarak adlandırılır.  
  
 Arasındaki farkı **ATLENSURE** ve `ATLASSERT` olan **ATLENSURE** sürümdeki bir özel durum oluşturur de olduğu gibi hata ayıklama yapıları atar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  

##  <a name="atltracenotimpl"></a>  ATLTRACENOTIMPL  
 ATL hata ayıklama derlemelerinde dizesi gönderir " `funcname` uygulanmadı" döndürür ve döküm cihaz için **E_NOTIMPL**.  
  
```
ATLTRACENOTIMPL(funcname);
```  
  
### <a name="parameters"></a>Parametreler  
 `funcname`  
 [in] Uygulanmadı işlevin adını içeren dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Yayın derlemelerde yalnızca döndürür **E_NOTIMPL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltrace.h 

##  <a name="atltrace"></a>  ATLTRACE
 Uyarı düzeyleri ve belirtilen bayrakları göre hata ayıklayıcı penceresini gibi bir çıktı cihazına bildirir. Geriye dönük uyumluluk için dahil.  
  
```
ATLTRACE(exp);

ATLTRACE(  
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `exp`  
 [in] Visual C++ çıktı penceresi veya bu iletiler yakalar herhangi bir uygulama göndermek için değişkenleri ve dizesi.  
  
 `category`  
 [in] Olay ya da rapor üretileceği yönteme türü. Açıklamalar kategorileri listesi için bkz.  
  
 `level`  
 [in] Rapor için izleme düzeyi. Açıklamalar Ayrıntılar için bkz.  
  
 `lpszFormat`  
 [in] Döküm aygıta göndermek için biçimlendirilmiş dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ATLTRACE2](#atltrace2) bir açıklaması için **ATLTRACE**. **ATLTRACE** ve `ATLTRACE2` aynı davranışı **ATLTRACE** geriye dönük uyumluluk için bulunmaktadır.  
  
##  <a name="atltrace2"></a>  ATLTRACE2  
 Uyarı düzeyleri ve belirtilen bayrakları göre hata ayıklayıcı penceresini gibi bir çıktı cihazına bildirir.  
  
```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `exp`  
 [in] Visual C++ çıktı penceresi veya bu iletiler yakalar herhangi bir uygulama göndermek için dize.  
  
 `category`  
 [in] Olay ya da rapor üretileceği yönteme türü. Açıklamalar kategorileri listesi için bkz.  
  
 `level`  
 [in] Rapor için izleme düzeyi. Açıklamalar Ayrıntılar için bkz.  
  
 `lpszFormat`  
 [in] `printf`-Stil döküm aygıta göndermek için bir dize oluşturmak için kullanılacak biçim dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kısa formunu `ATLTRACE2` hata ayıklayıcı dizeye animasyonun çıktı penceresi yazar. İkinci biçiminde `ATLTRACE2` de çıktı Hata Ayıklayıcı'nın çıkış penceresine yazar, ancak ATL/MFC izleme aracı ayarları tabi (bkz [ATLTraceTool örnek](../../visual-cpp-samples.md)). Örneğin, ayarlarsanız `level` 4 ve düzey 0 ATL/MFC izleme aracı için ileti görüntülenmez. *düzey* 0, 1, 2, 3 veya 4 olabilir. Varsayılan değer, 0, yalnızca en ciddi sorunlar bildirir.  
  
 `category` Parametresi ayarlamak için izleme bayrakları listeler. Bu bayrakların raporlamak istediğiniz yöntemleri türlerini karşılık gelir. Aşağıdaki tablolarda listelemek için kullanabileceğiniz geçerli izleme bayrakları `category` parametresi.  
  
### <a name="atl-trace-flags"></a>ATL İzleme Bayrakları  
  
|ATL kategorisi|Açıklama|  
|------------------|-----------------|  
|`atlTraceGeneral`|Tüm ATL uygulamaları raporları. Varsayılan.|  
|`atlTraceCOM`|COM yöntemleri raporlarda.|  
|`atlTraceQI`|QueryInterface çağrılarını raporları.|  
|`atlTraceRegistrar`|Kayıt nesnelerin raporları.|  
|`atlTraceRefcount`|Başvuru sayısı değiştirme hakkında raporlar.|  
|`atlTraceWindowing`|Windows yöntemleri raporlarda; Örneğin, bir geçersiz ileti eşleme kimliği raporları|  
|`atlTraceControls`|Denetimleri raporlarda; Örneğin, bir denetim veya onun penceresi bozulduğunda bildirir.|  
|`atlTraceHosting`|Raporlar; iletileri barındırma Örneğin, bir istemci bir kapsayıcıda etkinleştirildiğinde bildirir.|  
|`atlTraceDBClient`|OLE DB tüketici şablonu raporlarda; Örneğin, bir çağrı, GetData başarısız için çıktı HRESULT içerebilir.|  
|`atlTraceDBProvider`|OLE DB sağlayıcı şablonu raporlarda; Örneğin, bir sütun oluşturulamadı, raporlar.|  
|`atlTraceSnapin`|MMC ek bileşeni uygulama raporları.|  
|`atlTraceNotImpl`|Rapor, belirtilen işlevi uygulanmadı.|  
|**atlTraceAllocation**|Hata ayıklama araçları atldbgmem.h içinde bellek tarafından yazdırılan iletileri bildirir.|  
  
### <a name="mfc-trace-flags"></a>MFC İzleme Bayrakları  
  
|MFC kategorisi|Açıklama|  
|------------------|-----------------|  
|**traceAppMsg**|Genel amaçlı, MFC iletileri. Her zaman önerilir.|  
|**traceDumpContext**|Gelen iletileri [CDumpContext](../../mfc/reference/cdumpcontext-class.md).|  
|**traceWinMsg**|İletileri işleme kodunu MFC'nin iletisi.|  
|**traceMemory**|MFC'nin bellek yönetimi kodundan iletileri.|  
|**traceCmdRouting**|Komut yönlendirme kod MFC'nin Windows iletileri.|  
|**traceHtml**|MFC'nin DHTML iletişim destek gelen iletileri.|  
|**traceSocket**|MFC'nin yuva destek gelen iletileri.|  
|**traceOle**|MFC'nin OLE desteği gelen iletileri.|  
|**traceDatabase**|MFC'nin veritabanı desteği gelen iletileri.|  
|**traceInternet**|MFC'nin Internet gelen iletileri destekler.|  
  
 Özel İzleme kategorisi bildirmek için genel bir örneğini bildirme `CTraceCategory` gibi sınıfı:  
  
 [!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]  
  
 Kategori adı `MY_CATEGORY` Bu örnekte, belirttiğiniz addır `category` parametresi. ATL/MFC izleme aracı görünür kategori adı ilk parametresidir. İkinci parametre varsayılan izleme düzeydir. Bu parametre isteğe bağlıdır ve varsayılan izleme düzeyi 0'dır.  
  
 Kullanıcı tanımlı bir kategori kullanmak için:  
  
 [!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]  
  
 İzleme İletileri Filtrele istediğinizi belirtmek için bu makro tanımlarında Stdafx.h önce takın `#include <atlbase.h>` deyimi.  
  
 Önişlemci yönergeleri içinde filtre alternatif olarak, ayarlayabilirsiniz **özellik sayfaları** iletişim kutusu. Tıklatın **önişlemci** sekmesini ve sonra genel içine ekleyin **önişlemci tanımları** düzenleme kutusu.  
  
 Atlbase.h varsayılan tanımları içeren `ATLTRACE2` makrolar ve bu tanımları kullanılacak atlbase.h işlenmeden önce bu simgeleri yok tanımlarsanız.  
  
 Yayın derlemelerde `ATLTRACE2` için derler `(void) 0`.  
  
 `ATLTRACE2` en fazla 1023 karakter döküm aygıta biçimlendirme sonra gönderilecek dize içeriklerini sınırlar.  
  
 **ATLTRACE** ve `ATLTRACE2` aynı davranışı **ATLTRACE** geriye dönük uyumluluk için bulunmaktadır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)   
 [Hata Ayıklama ve Hata Raporlama Genel İşlevleri](../../atl/reference/debugging-and-error-reporting-global-functions.md)
