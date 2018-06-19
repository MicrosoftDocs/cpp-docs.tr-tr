---
title: Tanılama Hizmetleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- diagnosi [MFC]s, diagnostic services
- diagnostic macros [MFC], list of general MFC
- services [MFC], diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables [MFC]
- diagnostics [MFC], diagnostic functions and variables
- diagnostics [MFC], list of general MFC
- diagnosis [MFC], diagnostic functions and variables
- diagnosis [MFC], list of general MFC
- general diagnostic macros in MFC
- diagnostic macros [MFC]
- diagnostic services [MFC]
- object diagnostic functions in MFC
- diagnostics [MFC], diagnostic services
- diagnostic functions and variables [MFC]
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2332090032a93152b6c841336538bf9d45984300
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377327"
---
# <a name="diagnostic-services"></a>Tanı Hizmetleri
Microsoft Foundation Class Kitaplığı programlarınızı daha kolay hata ayıklama birçok tanılama hizmetler sağlar. Bu tanılama hizmetler makrolar ve ayırma, çalışma zamanı sırasında nesnelerin içeriğini dökümü ve çalışma zamanında hata ayıklama iletilerini yazdırma programınızın bellek izlemenize olanak sağlayan genel işlevler içerir. Makrolar ve genel işlevler tanı Hizmetleri için aşağıdaki kategorilerde gruplanır:  
  
-   Genel tanılama makroları  
  
-   Genel Tanılama işlevleri ve değişkenler  
  
-   Nesne Tanılama işlevleri  
  
 Bu makrolar ve İşlevler türetilmiş tüm sınıflar için kullanılabilir, `CObject` MFC hata ayıklama ve yayın sürümlerinde. Ancak, tüm dışındaki `DEBUG_NEW` ve **doğrula** yayın sürümü, hiçbir şey yapma.  
  
 Hata ayıklama Kitaplığı'nda tüm ayrılmış bellek blokları "koruyucusu bayt sayısı." bir dizi köşeli parantez içindeki Bu bayt yalıtılarak bellek yazma tarafından etkilenir, tanılama yordamları bir sorun bildirebilirsiniz. Satır içeriyorsa:  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 tüm uygulama dosyanızda çağrılar **yeni** burada bellek ayırma sürdü yer filename ve satır numarası depolar. İşlev [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) bellek sızıntıları tanımlamanıza izin vererek bu ek bilgiler görüntülenir. Ayrıca sınıfına başvuru [CDumpContext](../../mfc/reference/cdumpcontext-class.md) tanılama çıktıları hakkında ek bilgi için.  
  
 Ayrıca, C çalışma zamanı kitaplığı da uygulamalarınızda hata ayıklamak için kullanabileceğiniz tanılama işlevleri, bir kümesini destekler. Daha fazla bilgi için bkz: [hata ayıklama yordamları](../../c-runtime-library/debug-routines.md) çalışma zamanı kitaplığı başvurusu.  
  
### <a name="mfc-general-diagnostic-macros"></a>MFC genel tanılama makroları  
  
|||  
|-|-|  
|[ASSERT](#assert)|Bir ileti yazdırır ve için belirtilen ifadeyi hesaplar, programı durdurur **FALSE** kitaplığı hata ayıklama sürümünde.|  
|[ASSERT_KINDOF](#assert_kindof)|Bir nesneyi belirtilen sınıf veya belirtilen sınıfından türetilmiş bir sınıf bir nesnedir testleri.|  
|[ASSERT_VALID](#assert_valid)|Çağırarak bir nesnenin iç geçerlilik testleri kendi `AssertValid` üye işlev; öğesinden tipik olarak geçersiz kılınan `CObject`.|
|[DEBUG_NEW](#debug_new)|Bellek sızıntıları bulmak için bir dosya adı ve satır numarası için hata ayıklama modunda tüm nesne ayırmaları sağlar.|  
|[DEBUG_ONLY](#debug_only)|Benzer şekilde **ASSERT** ; ifadesinin değerini test değil ancak yalnızca hata ayıklama modunda yürütülecek kod için kullanışlıdır.|  
|[Emin olun ve ENSURE_VALID](#ensure)|Veri doğruluk doğrulamak için kullanın.|
|[THIS_FILE](#this_file)|Derleniyor dosya adı için genişletir.|
|[İZLEME](#trace)|Sağlar `printf`-yeteneği kitaplığının hata ayıklama sürümü, ister.|  
|[DOĞRULAYIN](#verify)|Benzer şekilde **ASSERT** ancak kitaplığı de hata ayıklama sürümü olduğu gibi sürümünü ifadeyi değerlendirir.|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC genel tanılama değişkenleri ve işlevleri  
  
|||  
|-|-|  
|[afxDump](#afxdump)|Gönderir genel değişkeni [CDumpContext](../../mfc/reference/cdumpcontext-class.md) hata ayıklayıcı çıktı penceresi veya hata ayıklama terminal bilgi.|  
|[afxMemDF](#afxmemdf)|Hata ayıklama bellek ayırıcısı davranışını denetleyen genel değişkeni.|  
|[AfxCheckError](#afxcheckerror)|Geçirilen test etmek için kullanılan genel değişkeni **SCODE** bunu bir hatadır ve Öyleyse, uygun hata oluşturur, görmek için.|  
|[AfxCheckMemory](#afxcheckmemory)|Tüm bütünlüğünü bellek ayrılmış denetler.|  
|[AfxDebugBreak](#afxdebugbreak)|Bir sonu yürütülmesine neden olur.|
|[AfxDump](#cdumpcontext_in_mfc)|Hata ayıklayıcısında sırada çağırdıysanız, hata ayıklama sırasında bir nesnenin durumu dökümünü yapar.|  
|[AfxDump](#afxdump)|Bir nesnenin durumu hata ayıklama sırasında dökümleri iç işlev.|
|[AfxDumpStack](#afxdumpstack)|Geçerli yığın görüntüsü oluşturur. Bu işlev her zaman statik olarak bağlanır.|  
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|Bellek sızıntısı dökümü sağlar.|  
|[AfxEnableMemoryTracking](#afxenablememorytracking)|İzleme üzerinde ve bellek etkinleştirir.|  
|[Afxısmemoryblock](#afxismemoryblock)|Bir bellek bloğu düzgün ayrıldı doğrular.|  
|[Afxısvalidaddress](#afxisvalidaddress)|Bir bellek adresi aralığı programın sınırları içinde olduğunu doğrular.|  
|[Afxısvalidstring](#afxisvalidstring)|Bir dize için bir işaretçi geçerli olup olmadığını belirler.|  
|[AfxSetAllocHook](#afxsetallochook)|Her bellek ayırma üzerinde bir işlevi çağırmak sağlar.|  
  
### <a name="mfc-object-diagnostic-functions"></a>MFC nesne Tanılama işlevleri  
  
|||  
|-|-|  
|[AfxDoForAllClasses](#afxdoforallclasses)|Tüm belirtilen bir işlevi gerçekleştiren `CObject`-çalışma zamanı tür denetimi destekleyen sınıfları türetilmiş.|  
|[AfxDoForAllObjects](#afxdoforallobjects)|Tüm belirtilen bir işlevi gerçekleştiren `CObject`-türetilmiş ile ayrılmış nesneleri **yeni**.|  

### <a name="mfc-compilation-macros"></a>MFC derleme makroları
|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Kullanım dışı MFC işlevleri kullanmak için derleyici uyarıları bastırır.|  


## <a name="afx_secure_no_warnings"></a> _AFX_SECURE_NO_WARNINGS
Kullanım dışı MFC işlevleri kullanmak için derleyici uyarıları bastırır.  
   
### <a name="syntax"></a>Sözdizimi   
```  
_AFX_SECURE_NO_WARNINGS  
```     
### <a name="example"></a>Örnek  
 Bu kod örneği, _AFX_SECURE_NO_WARNINGS tanımlanmamış varsa derleyici uyarısı neden olur.  
  
 ```cpp
// define this before including any afx files in stdafx.h
#define _AFX_SECURE_NO_WARNINGS
```
```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a> AfxDebugBreak
Bir sonu neden bu işlev çağrısı (çağrısı konumda `AfxDebugBreak`), MFC Uygulama hata ayıklama sürümü yürütülmesi.  

### <a name="syntax"></a>Sözdizimi    
```
void AfxDebugBreak( );    
```  
   
### <a name="remarks"></a>Açıklamalar  
 `AfxDebugBreak` MFC uygulaması sürüm sürümlerinde hiçbir etkisi olmaz ve kaldırılması gerekiyor. Bu işlev yalnızca MFC uygulamalarında kullanılmalıdır. Win32 API sürümü kullanmak **DebugBreak**, bir kesme MFC dışı uygulamalarda neden olacak.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxver_.h   

##  <a name="assert"></a>  ASSERT
 Bağımsız değişken olarak değerlendirilir.  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>Parametreler  
 `booleanExpression`  
 Sıfır olmayan bir değer veya 0 (kayan nokta değerlerini dahil) bir ifade belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuç 0 ise, makrosu bir tanılama iletisi yazdırır ve programı durdurur. Koşul sıfır değilse, hiçbir şey yapmaz.  
  
 Tanılama iletisi şu formdadır:  
  
 `assertion failed in file <name> in line <num>`  
  
 Burada *adı* kaynak dosyasının adıdır ve *num* kaynak dosyasına başarısız onaylama satır sayısı.  
  
 MFC, yayın sürümünde **ASSERT** ifade değerlendirmez ve böylece programın durdurmaz. İfade ortam bağımsız olarak değerlendirilmesi gereken kullanırsanız **doğrula** makrosu yerine **ASSERT**.  
  
> [!NOTE]
>  Bu işlev yalnızca MFC hata ayıklama sürümü kullanılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="assert_kindof"></a>  ASSERT_KINDOF  
 Bu makrosu işaret belirtilen sınıfın bir nesnesi nesnedir veya bir sınıfın bir nesnesi belirtilen sınıfından türetilir onaylar.  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>Parametreler  
 *ClassName*  
 Adı bir `CObject`-türetilmiş sınıf.  
  
 *pobject*  
 Bir sınıf nesnesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 *Pobject* parametresi bir nesne için bir işaretçi olmalıdır ve olabilir **const**. Nesne işaret ve sınıf desteklemelidir `CObject` çalışma zamanı sınıf bilgileri. Emin olmak için bir örnek olarak `pDocument` gösteren bir işaretçidir bir nesnenin `CMyDoc` sınıfı ya da kendi türevleri hiçbirini kodu yazabilirsiniz:  
  
 [!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 Kullanarak `ASSERT_KINDOF` makrosu tam olarak aynı olup kodlama:  
  
 [!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 Bu işlev yalnızca ile bildirilen sınıfları için çalışır [DECLARE_DYNAMIC] (çalıştırma-saat-nesnesi-model-services.md #DECLARE_DYNAMIC veya [declare_serıal](run-time-object-model-services.md#declare_serial) makrosu.  
  
> [!NOTE]
>  Bu işlev yalnızca MFC hata ayıklama sürümü kullanılabilir.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="assert_valid"></a>  ASSERT_VALID  
 Bir nesnenin iç durum geçerliliğini hakkında varsayımları sınamak için kullanın.  
  
```   
ASSERT_VALID(pObject)   
```  
  
### <a name="parameters"></a>Parametreler  
 `pObject`  
 Türetilen bir sınıftan bir nesneyi belirtir `CObject` geçersiz kılan bir sürümünün yüklü `AssertValid` üye işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 `ASSERT_VALID` çağrıları `AssertValid` nesnenin üye işlevi bağımsız değişken olarak geçirilen.  
  
 MFC, yayın sürümünde `ASSERT_VALID` hiçbir şey yapmaz. Hata ayıklama sürümünde bu işaretçinin doğrular, karşı denetler **NULL**ve kendi çağıran `AssertValid` üye işlevleri. Bunlardan birine sınar, başarısız bir uyarı iletisi ile aynı şekilde görüntülenir [ASSERT](#assert).  
  
> [!NOTE]
>  Bu işlev yalnızca MFC hata ayıklama sürümü kullanılabilir.  
  
 Daha fazla bilgi ve örnekler için bkz: [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h

##  <a name="debug_new"></a>  DEBUG_NEW  
 Bellek sızıntılarını bulma yardımcı olur.  
  
```   
#define  new DEBUG_NEW   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `DEBUG_NEW` her yerde normalde kullanacağı programınızın **yeni** yığın depolama alanı ayırmak için işleci.  
  
 Hata ayıklama modunda (zaman **_DEBUG** simgesiyle tanımlanır), `DEBUG_NEW` ayırdığı her nesne için dosya adı ve satır numarası izler. Ardından, kullandığınızda, [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) üye işlevi, her bir nesne ile ayrılmış `DEBUG_NEW` burada ayrıldı filename ve satır numarası ile gösterilir.  
  
 Kullanılacak `DEBUG_NEW`, aşağıdaki yönergesi Kaynak dosyalarınız ekleyin:  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 Bu yönerge ekledikten sonra önişlemci ekleyecektir `DEBUG_NEW` yerde kullandığınız **yeni**, ve MFC rest yapar. Program sürümünü derlediğinizde `DEBUG_NEW` basit bir çözümler **yeni** işlem ve dosya adı ve satır numarası bilgilerini oluşturulmaz.  
  
> [!NOTE]
>  MFC (4.1 ve önceki) önceki sürümlerinde yerleştirmek için gereken `#define` adlı tüm deyimleri sonra deyimi `IMPLEMENT_DYNCREATE` veya `IMPLEMENT_SERIAL` makroları. Bu artık gerekli değildir.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h

##  <a name="debug_only"></a>  DEBUG_ONLY  
 Hata ayıklama modunda (zaman **_DEBUG** simgesiyle tanımlanır), `DEBUG_ONLY` bağımsız değişkeni olarak değerlendirilir.  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yayın derlemesi içinde **DEBUG_ONLY** bağımsız değişkeni değerlendirmez. Yalnızca hata ayıklama derlemelerinde yürütülmesi gereken kodu varsa, bu yararlıdır.  
  
 `DEBUG_ONLY` Makrosu çevredeki eşdeğerdir *ifade* ile **#ifdef _DEBUG** ve `#endif`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h

 ### <a name="ensure"></a>  Emin olun ve ENSURE_VALID
Veri doğruluk doğrulamak için kullanın.  
   
### <a name="syntax"></a>Sözdizimi    
```
ENSURE(  booleanExpression )  
ENSURE_VALID( booleanExpression  )  
```
### <a name="parameters"></a>Parametreler  
 `booleanExpression`  
 Sınanacak bir Boole ifadesini belirtir.  
   
### <a name="remarks"></a>Açıklamalar  
 Doğrulama parametrelerinin artırmak için bu makroları amacı budur. Makrolar, kodunuzda yanlış parametrelerinin daha fazla işleme engeller. Farklı **ASSERT** makroları **emin olun** makroları onayı ifade oluşturma yanı sıra bir özel durum atar.  
  
 Makrolar proje yapılandırmasına göre iki şekilde davranır. Makrolar çağrısı **ASSERT** ve onaylama başarısız olursa bir özel durum. Hata ayıklama yapılandırmaları, bu nedenle, (burada, diğer bir deyişle, **_DEBUG** tanımlanır) bir onaylama ve dağıtım yapılandırmalarını sırasında özel durum makroları oluşturmak, yalnızca özel durum makroları üretmek (**ASSERT** yok Yayın yapılandırmaları ifade değerlendirme).  
  
 Makro **ENSURE_ARG** gibi davranır **olun** makrosu.  
  
 **ENSURE_VALID** çağrıları `ASSERT_VALID` makrosu (hangi yalnızca hata ayıklama derlemelerinde bir etkisi yoktur). Ayrıca, **ENSURE_VALID** işaretçi NULL ise bir özel durum oluşturur. NULL test hata ayıklama ve yayın yapılandırmalarını gerçekleştirilir.  
  
 Bunlardan birine sınar, başarısız bir uyarı iletisi ile aynı şekilde görüntülenir **ASSERT**. Makro gerekirse geçersiz bağımsız değişken özel durum oluşturur.  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [DOĞRULAYIN](#verify)   
 [ATLENSURE](#altensure)

## <a name="this_file"></a> THIS_FILE
Derleniyor dosya adı için genişletir.  
   
### <a name="syntax"></a>Sözdizimi    
```
THIS_FILE    
```  
   
### <a name="remarks"></a>Açıklamalar  
 Tarafından kullanılan bilgileri **ASSERT** ve **doğrula** makroları. Uygulama Sihirbazı'nı ve kod sihirbazları makrosu kaynak kodu dosyaları oluşturdukları yerleştirin.  
   
### <a name="example"></a>Örnek  
```cpp
#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif

// __FILE__ is one of the six predefined ANSI C macros that the 
// compiler recognizes. 
```
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [ASSERT](#assert)   
 [DOĞRULAYIN](#verify)


##  <a name="trace"></a>  İZLEME  
 Belirtilen dize geçerli uygulama hata ayıklayıcı için gönderir.  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) bir açıklaması için **izleme**. **İzleme** ve `ATLTRACE2` aynı davranışı sahiptir.  
  
 MFC hata ayıklama sürümü, bu makrosu geçerli uygulama hata ayıklayıcı için belirtilen dize gönderir. Bir yayın derleme bu makrosu (kod hiç oluşturulur) bir şey derler.  
  
 Daha fazla bilgi için bkz: [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h

##  <a name="verify"></a>  DOĞRULAYIN  
 MFC hata ayıklama sürümü, bağımsız değişkeni olarak değerlendirilir.  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>Parametreler  
 `booleanExpression`  
 Sıfır olmayan bir değer veya 0 (kayan nokta değerlerini dahil) bir ifade belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuç 0 ise, makrosu bir tanılama iletisi yazdırır ve programı durdurur. Koşul sıfır değilse, hiçbir şey yapmaz.  
  
 Tanılama iletisi şu formdadır:  
  
 `assertion failed in file <name> in line <num>`  
  
 Burada *adı* kaynak dosyasının adıdır ve *num* kaynak dosyasına başarısız onaylama satır sayısı.  
  
 MFC, yayın sürümünde **doğrula** ifadeyi hesaplar ancak yazdırma veya bir programı kesmez. İfade bir işlev çağrısı ise, örneğin, çağrı yapılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>  afxDump (MFC'de CDumpContext)  
 Temel nesne döküm alma özelliği, uygulamanızdaki sağlar.  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>Açıklamalar  
 `afxDump` önceden tanımlanmış olan [CDumpContext](../../mfc/reference/cdumpcontext-class.md) göndermenize olanak sağlayan nesne `CDumpContext` hata ayıklayıcı çıktı penceresi veya hata ayıklama terminal bilgi. Genellikle, sağladığınız `afxDump` bir parametre olarak `CObject::Dump`.  
  
 Windows NT ve Windows, tüm sürümleri altındaki `afxDump` çıktı, Visual C++ hata ayıklama çıktı penceresine gönderilir, uygulamanızda hata ayıklama olduğunda.  
  
 Bu değişken, yalnızca MFC hata ayıklama sürümü tanımlanır. Daha fazla bilgi için `afxDump`, bkz: [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h


## <a name="afxdump"></a> AfxDump (iç)
MFC hata ayıklama sırasında bir nesnenin durumu dökümü kullanan bir iç işlev.  

### <a name="syntax"></a>Sözdizimi    
```
void AfxDump(const CObject* pOb);   
```
### <a name="parameters"></a>Parametreler  
 `pOb`  
 Bir sınıfın bir nesnesi için bir işaretçi türetilmiş `CObject`.  
   
### <a name="remarks"></a>Açıklamalar  
 **AfxDump** nesnenin çağırır `Dump` üye fonksiyonu ve tarafından belirtilen konuma bilgi gönderir `afxDump` değişkeni. **AfxDump** yalnızca MFC hata ayıklama sürümü kullanılabilir.  
  
 Program kodunuzu değil çağırmalıdır **AfxDump**, ancak bunun yerine çağırmalıdır `Dump` uygun nesnesinin üye işlevi.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [CObject::Dump](cobject-class.md#dump)   



##  <a name="afxmemdf"></a>  afxMemDF  
 Bu değişkeni bir hata ayıklayıcısı veya programınızı erişilebilir ve ayırma tanılama ince ayar olanak tanır.  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `afxMemDF` Numaralandırma belirtildiği gibi aşağıdaki değerlere sahip olabilir `afxMemDF`:  
  
- **allocMemDF** hata ayıklama ayırıcısı (hata ayıklama Kitaplığı'nda varsayılan ayar) açar.  
  
- **delayFreeMemDF** gecikmeler bellek boşaltma. Bir bellek bloğu programınızı boşaltır olsa da, ayırıcı temel işletim sistemi, bellek döndürmez. Bu en fazla bellek stres programınızın yerleştirin.  
  
- **checkAlwaysMemDF** çağrıları `AfxCheckMemory` bellek tahsis veya serbest her zaman. Bu önemli ölçüde bellek ayırma ve ayırma kaldırma işlemleri yavaşlatır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h

##  <a name="afxcheckerror"></a>  AfxCheckError  
 Bu işlev geçirilen testleri **SCODE** bir hata olup olmadığını görmek için.  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir hata varsa, işlev özel durum oluşturur. Varsa geçirilen `SCODE` olan **E_OUTOFMEMORY**, işlev oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) çağırarak [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Aksi takdirde, işlev oluşturur bir [COleException](../../mfc/reference/coleexception-class.md) çağırarak [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Bu işlevi dönüş değerleri, uygulamanızda OLE işlevlerini yapılan çağrıların denetlemek için kullanılabilir. Dönüş değeri bu işlev ile uygulamanızı test ederek, düzgün şekilde kodu en az miktarda içeren hata koşulları tepki.  
  
> [!NOTE]
>  Bu işlev, hata ayıklama modunda aynı etkiye sahiptir ve hata ayıklama olmayan oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h

##  <a name="afxcheckmemory"></a>  AfxCheckMemory  
 Bu işlev boş bellek havuzu doğrular ve gerektiği gibi hata iletilerini yazdırır.  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hiçbir bellek hatası durumunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev bellek bozulma algılarsa, hiçbir şey yazdırır.  
  
 Tarafından ayrılan dahil olmak üzere tüm bellek blokları yığında ayrılmış denetlenir **yeni** ancak değil olanlar gibi temel alınan bellek allocators yapılan doğrudan çağrılar tarafından ayrılan `malloc` işlevi veya  **GlobalAlloc** Windows işlevi. Herhangi bir bloğuna bozuk olduğu bulunursa, bir ileti hata ayıklayıcı çıkış yazdırılır.  
  
 Satır eklerseniz  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 bir program modülünde sonra yapılan sonraki çağrılar `AfxCheckMemory` burada belleği ayrıldı filename ve satır numarası göster.  
  
> [!NOTE]
>  Serileştirilebilir sınıflar, bir veya daha fazla uygulamalarını modülünüzün içeren sonra konulmalıdır `#define` son satırdan `IMPLEMENT_SERIAL` makrosu çağrısı.  
  
 Bu işlev yalnızca MFC hata ayıklama sürümü çalışır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
 
##  <a name="afxdump"></a>  AfxDump (MFC)  
 Hata ayıklama sırasında bir nesnenin durumu dökümü hata ayıklayıcı sırada bu işlevini çağırın.  
  
```   
void AfxDump(const CObject* pOb); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pOb`  
 Bir sınıfın bir nesnesi için bir işaretçi türetilmiş `CObject`.  
  
### <a name="remarks"></a>Açıklamalar  
 **AfxDump** nesnenin çağırır `Dump` üye fonksiyonu ve tarafından belirtilen konuma bilgi gönderir `afxDump` değişkeni. **AfxDump** yalnızca MFC hata ayıklama sürümü kullanılabilir.  
  
 Program kodunuzu değil çağırmalıdır **AfxDump**, ancak bunun yerine çağırmalıdır `Dump` uygun nesnesinin üye işlevi.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  

### <a name="see-also"></a>Ayrıca Bkz.  
 [CObject::Dump](cobject-class.md#dump)   


  
##  <a name="afxdumpstack"></a>  AfxDumpStack  
 Bu genel işlevi, geçerli yığın görüntüsü oluşturmak için kullanılabilir.  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>Parametreler  
 *dwTarget*  
 Döküm çıktı hedefinin gösterir. Bit düzeyinde-OR kullanılarak birleştirilebilir olası değerler ( **&#124;**) işleci, aşağıdaki gibidir:  
  
- **AFX_STACK_DUMP_TARGET_TRACE** yoluyla çıkış gönderir [izleme](#trace) makrosu. **İzleme** makrosu yalnızca hata ayıklama derlemelerinde çıktı oluşturur; sürüm derlemelerde herhangi bir çıktı üretir. Ayrıca, **izleme** hata ayıklayıcı yanı sıra diğer hedefler yönlendirilebilir.  
  
- **AFX_STACK_DUMP_TARGET_DEFAULT** varsayılan hedefe çıkış gönderir dökümü. Hata ayıklama derlemesi için çıktı gider **izleme** makrosu. Bir yayın derleme çıktı panoya gider.  
  
- **AFX_STACK_DUMP_TARGET_CLIPBOARD** yalnızca panoya çıkış gönderir. Düz metin olarak Pano verileri yerleştirildiği **CF_TEXT** Pano biçimi.  
  
- **AFX_STACK_DUMP_TARGET_BOTH** gönderir çıkış Pano ve çok **izleme** makrosu, aynı anda.  
  
- **AFX_STACK_DUMP_TARGET_ODS** gönderir çıkış doğrudan hata ayıklayıcı Win32 işlevi yoluyla **OutputDebugString()**. Bu seçenek, hata ayıklayıcı çıkış hem hata ayıklama modunda oluşturmak ve yayın derlemeleri işleme bir hata ayıklayıcısı ekli. **AFX_STACK_DUMP_TARGET_ODS** (bağlıysa) her zaman hata ayıklayıcı ulaşana ve yönlendirilemez.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki örnek tek satırlık bir arama gelen oluşturulan çıktı yansıtır `AfxDumpStack` düğmesi işleyicisinden bir MFC iletişim uygulamasında:  
  
 `=== begin AfxDumpStack output ===`  
  
 `00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes`  
  
 `0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes`  
  
 `0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,`  
  
 `unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct AFX_CMDHANDLE`  
  
 `0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes`  
  
 `00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes`  
  
 `00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned`  
  
 `int,long) + 312 bytes`  
  
 `00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned`  
  
 `int,unsigned int,long,long *) + 83 bytes`  
  
 `00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned`  
  
 `int,unsigned int,long) + 46 bytes`  
  
 `004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct`  
  
 `HWND__ *,unsigned int,unsigned int,long) + 237 bytes`  
  
 `00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned`  
  
 `int,unsigned int,long) + 129 bytes`  
  
 `BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes`  
  
 `BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes`  
  
 `=== end AfxDumpStack() output ===`  
  
 Yukarıdaki çıktıya her satırda son işlev çağrısı işlev çağrısı ve adlı işlev prototipi içeren modülü tam yol adını adresini belirtir. İşlev çağrısı yığında işlevi tam adresinde görünmezse bayt uzaklığı gösterilir.  
  
 Örneğin, aşağıdaki tabloda yukarıdaki çıktı ilk satırının açıklanmaktadır:  
  
|Çıkış|Açıklama|  
|------------|-----------------|  
|`00427D55:`|Son işlev çağrısının dönüş adresi.|  
|`DUMP2\DEBUG\DUMP2.EXE!`|İşlev çağrısı içeren modülü tam yol adı.|  
|`void AfxDumpStack(unsigned long)`|İşlev prototipi çağrılır.|  
|`+ 181 bytes`|İşlev prototipi adresinden bayt cinsinden uzaklık (Bu durumda, `void AfxDumpStack(unsigned long)`) dönüş adresi için (Bu durumda, `00427D55`).|  
  
 `AfxDumpStack` MFC kitaplıkları, hata ayıklama ve nondebug sürümlerinde kullanılabilir; hatta yürütülebilir dosyanızı paylaşılan DLL'de MFC kullandığında ancak, işlevi her zaman statik olarak, bağlı. Paylaşılan kitaplık uygulamalarında MFCS42 işlevi bulunamadı. LIB kitaplığı (ve türevleri).  
  
 Bu işlevi kullanabilmek için:  
  
-   Dosya IMAGEHLP. DLL, yolunuza bağlı olması gerekir. Bu DLL yoksa işlevi bir hata iletisi görüntüler. Bkz: [görüntü Yardım Kitaplığı](http://msdn.microsoft.com/library/windows/desktop/ms680321) IMAGEHLP tarafından sağlanan işlev kümesi hakkında bilgi için.  
  
-   Yığında çerçeve olan modülleri hata ayıklama bilgisi eklemeniz gerekir. Hata ayıklama bilgisi içermeyen, işlevi hala yığın izlemesi oluşturur, ancak izleme daha az ayrıntılı.  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="afxenablememoryleakdump"></a>  AfxEnableMemoryLeakDump  
 Sağlar ve bellek sızıntısı dökümü devre dışı bırakır `AFX_DEBUG_STATE` yıkıcı.  
  
```  
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bDump`  
 `TRUE` bellek sızıntısı dökümü etkinleştirildiğini gösterir; `FALSE` bellek sızıntısı dökümü devre dışıysa gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu bayrak önceki değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 MFC kitaplığını uygulama bellekten kaldırıldığında MFC Kitaplığı için bellek sızıntıları denetler. Bu noktada kullanıcının üzerinden tüm bellek sızıntıları bildirilen **hata ayıklama** pencerenin [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  
  
 MFC kitaplığını önce başka bir kitaplıkla uygulamanızı yüklenirse, bazı bellek ayırmaları bu kitaplıktaki yanlış bellek sızıntıları raporlanır. Yanlış bellek sızıntıları MFC kitaplığını bunları raporları gibi yavaş kapatmak, uygulamanızın neden olabilir. Bu durumda, kullanarak `AfxEnableMemoryLeakDump` bellek sızıntısı dökümü devre dışı bırakmak için.  
  
> [!NOTE]
>  Bellek sızıntısı dökümü devre dışı bırakma bu yöntemi kullanırsanız, geçerli bellek sızıntıları raporları uygulamanızda almaz. Bellek sızıntısı raporu false bellek sızıntıları içerdiğini eminseniz bu yöntem yalnızca kullanmanız gerekir.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="afxenablememorytracking"></a>  AfxEnableMemoryTracking  
 İzleme tanılama bellek normalde MFC hata ayıklama sürümü etkinleştirilir.  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>Parametreler  
 *bTrack*  
 Bu değeri ayarlamak **TRUE** izleme; bellek kapatır **FALSE** devre dışı bırakır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İzlemeyi etkinleştirme bayrağını önceki ayar.  
  
### <a name="remarks"></a>Açıklamalar  
 Blok düzgün ayırma bildiğiniz kodunuzu bölümlerini izlemeyi devre dışı bırakmak için bu işlevi kullanın.  
  
 Daha fazla bilgi için `AfxEnableMemoryTracking`, bkz: [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Bu işlev yalnızca MFC hata ayıklama sürümü çalışır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="afxismemoryblock"></a>  Afxısmemoryblock  
 Tanılama sürümü tarafından ayrıldı şu anda etkin bellek bloğu temsil ettiği emin olmak için bir bellek adresi testleri **yeni**.  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Sınanacak bellek bloğu noktalarına.  
  
 `nBytes`  
 Bellek bloğu bayt cinsinden uzunluğu içerir.  
  
 `plRequestNumber`  
 İşaret eden bir **uzun** bellek bloğun ayırma sıra numarası ile doldurulacaktır ya da şu anda etkin bellek bloğu temsil etmez, sıfır tamsayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek bloğu geçerli olarak ayrılmış ve uzunluğu doğru ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrıca, belirtilen boyut özgün ayrılmış boyutu karşı denetler. İşlevi sıfır olmayan bir değer döndürürse, ayırma sıra numarası döndürülür `plRequestNumber`. Bu sayı, blok tahsis edildiğinde göre diğer tüm sırasını temsil eden **yeni** ayırma.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="afxisvalidaddress"></a>  Afxısvalidaddress  
 Tamamen programın bellek alanı içinde yer emin olmak için herhangi bir bellek adresi sınar.  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lp`  
 Sınanacak bellek adresi noktalarına.  
  
 `nBytes`  
 Sınanacak belleğin bayt sayısını içerir.  
  
 *bReadWrite*  
 Bellek hem okumak ve yazmak için olup olmadığını belirtir ( **TRUE**) veya yalnızca okuma ( **FALSE**).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata ayıklama derlemelerinde belirtilen bellek engellerseniz sıfır olmayan tamamen programın bellek alanı içinde yer alır; Aksi takdirde 0.  
  
 Olmayan hata ayıklama derlemelerinde, sıfır olmayan IF `lp` NULL; Aksi halde 0 değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Adres blokları tarafından ayrılmış. kısıtlanmış değil **yeni**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="afxisvalidstring"></a>  Afxısvalidstring  
 Bu işlev bir dize için bir işaretçi geçerli olup olmadığını belirlemek için kullanın.  
  
```   
BOOL  AfxIsValidString(
    LPCSTR lpsz,  
    int nLength = -1); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lpsz`  
 Test etmek için işaretçi.  
  
 `nLength`  
 Bayt cinsinden test dize uzunluğunu belirtir. -1 değeri dize null ile sonlandırılmış olacağını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hata ayıklama derlemelerinde, belirtilen boyutta bir dizeyi belirtilen işaretçi işaret ediyorsa sıfır olmayan; Aksi takdirde 0.  
  
 Olmayan hata ayıklama derlemelerinde, sıfır olmayan IF `lpsz` NULL; Aksi halde 0 değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="afxsetallochook"></a>  AfxSetAllocHook  
 Belirtilen işlev çağırma her bellek bloğu ayrılmış önce sağlayan bir kanca ayarlar.  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>Parametreler  
 *pfnAllocHook*  
 Çağrılacak işlevin adını belirtir. Bir ayırma işlevi prototip açıklamalar bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayırma izin vermek istiyorsanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Microsoft Foundation Class Kitaplığı hata ayıklama bellek ayırıcısı bir bellek ayırma izlemek ve ayırma izin verilip verilmediğini denetlemek için izin vermek için bir kullanıcı tarafından tanımlanan kanca işlevini çağırabilirsiniz. Atama kanca işlevleri örneklenmiş aşağıdaki gibidir:  
  
 **BOOL AFXAPI AllocHook (size_t** `nSize` **, BOOL** `bObject` **, uzun** `lRequestNumber` **);**  
  
 `nSize`  
 Önerilen bellek ayırma boyutu.  
  
 `bObject`  
 **DOĞRU** ayırma için ise bir `CObject`-türetilen nesnesini; Aksi halde **FALSE**.  
  
 `lRequestNumber`  
 Bellek ayırma 's sıra numarası.  
  
 Unutmayın **AFXAPI** çağırma olduğu anlamına gelir Aranan yığından parametreleri kaldırmanız gerekir.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="afxdoforallclasses"></a>  AfxDoForAllClasses  
 Belirtilen yineleme işlevi için tüm serileştirilebilir çağırır `CObject`-türetilmiş sınıfları uygulamanın bellek alanında.  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pfn`  
 Her sınıf için çağrılacak bir yineleme işlev noktalarına. Bir işaretçi işlevi bağımsız değişkenler bir `CRuntimeClass` nesne ve void işaretçi çağıran işleve sağladığı ek veriler.  
  
 `pContext`  
 Yineleme işlevi çağıran sağladığınız isteğe bağlı veri noktalarına. Bu işaretçinin olabilir **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Seri hale getirilebilir `CObject`-türetilen sınıflardır kullanarak türetilmiş sınıfları `DECLARE_SERIAL` makrosu. Geçirilen işaretçiyi `AfxDoForAllClasses` içinde `pContext` belirtilen yineleme işlevi çağırıldığında her zaman geçirilir.  
  
> [!NOTE]
>  Bu işlev yalnızca MFC hata ayıklama sürümü çalışır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="afxdoforallobjects"></a>  AfxDoForAllObjects  
 Türetilen tüm nesneler için belirtilen yineleme işlevi yürütür `CObject` , ayrıldığı ile **yeni**.  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pfn`  
 Her nesne için yürütmek için bir yineleme işlevi noktalarına. Bir işaretçi işlevi bağımsız değişkenler bir `CObject` ve çağıran işleve sağladığı ek veriler için geçersiz bir işaretçi.  
  
 `pContext`  
 Yineleme işlevi çağıran sağladığınız isteğe bağlı veri noktalarına. Bu işaretçinin olabilir **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Yığın, genel veya katıştırılmış nesneler numaralandırılan değil. İşaretçinin geçirilen `AfxDoForAllObjects` içinde `pContext` belirtilen yineleme işlevi çağırıldığında her zaman geçirilir.  
  
> [!NOTE]
>  Bu işlev yalnızca MFC hata ayıklama sürümü çalışır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)