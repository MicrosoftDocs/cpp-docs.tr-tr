---
title: Tanı Hizmetleri | Microsoft Docs
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
ms.openlocfilehash: 7b572af3bdfd444687af98172da9ada0736dac25
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429519"
---
# <a name="diagnostic-services"></a>Tanı Hizmetleri

Microsoft Foundation Class Kitaplığı programlarınızın daha kolay hata ayıklaması yapmak çok sayıda tanı hizmetleri sağlar. Bu tanılama Hizmetleri makroları ve programınızın bellek ayırmaları, çalışma zamanı sırasında nesnelerin içeriğini dökümü ve çalışma zamanı sırasında hata ayıklama iletilerini yazdırma izlemenize olanak tanıyan genel işlevleri içerir. Makrolar ve genel işlevler için tanı Hizmetleri aşağıdaki kategorilere ayrılır:

- Genel tanılama makroları

- Genel Tanılama işlevleri ve değişkenler

- Nesne Tanılama işlevleri

Bu makrolar ve İşlevler tüm sınıflarından türetilen sınıflar için kullanılabilir, `CObject` MFC hata ayıklama ve yayın sürümlerinde. Ancak, DEBUG_NEW ve Doğrula hariç tüm yayın sürümünde bir şey yapın.

Hata ayıklama Kitaplığı'nda, tüm ayrılan bellek blokları "guard bayt sayısı." bir dizi köşeli parantez içindeki Ardından bu bayt bir yalıtılarak bellek yazma tarafından etkilenir, tanılama yordamlarını sorun bildirebilir. Satırı içeriyorsa:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

tüm uygulama dosyanızda çağrılar **yeni** burada yer aldı bellek ayırma dosya adı ve satır numarasını depolar. İşlev [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) bellek sızıntılarını tanımlamanıza izin vererek bu ek bilgiler görüntülenir. Ayrıca sınıfına başvuru [CDumpContext](../../mfc/reference/cdumpcontext-class.md) tanılama çıkışı hakkında daha fazla bilgi için.

Ayrıca, C çalışma zamanı kitaplığı, Tanılama işlevleri, uygulamalarınızda hata ayıklamak için kullanabileceğiniz bir dizi da destekler. Daha fazla bilgi için [yordamları Debug](../../c-runtime-library/debug-routines.md) çalışma zamanı kitaplığı başvurusu.

### <a name="mfc-general-diagnostic-macros"></a>MFC genel tanılama makroları

|||
|-|-|
|[ASSERT](#assert)|Bir ileti yazdırır ve belirtilen ifade kitaplığı hata ayıklama sürümünde false değerlendirilirse programı iptal eder.|
|[ASSERT_KINDOF](#assert_kindof)|Belirtilen sınıfın veya belirtilen sınıftan türetilmiş bir sınıfın bir nesnesi bir nesnedir sınar.|
|[ASSERT_VALID](#assert_valid)|Çağırarak bir nesnenin iç geçerlilik testleri kendi `AssertValid` üye işlev; öğesinden genellikle geçersiz kılınan `CObject`.|
|[DEBUG_NEW](#debug_new)|Bellek sızıntılarını bulmak için bir dosya adı ve satır numarası için hata ayıklama modunda tüm nesne ayırmalarını sağlar.|
|[DEBUG_ONLY](#debug_only)|ASSERT benzer; ifadenin değerini test değil ancak yalnızca hata ayıklama modunda yürütün kod için kullanışlıdır.|
|[Emin olun ve ENSURE_VALID](#ensure)|Veri doğruluğunu doğrulamak için kullanın.|
|[THIS_FILE](#this_file)|Derleniyor dosyasının adına genişletir.|
|[İZLEME](#trace)|Sağlar `printf`-kitaplığı hata ayıklama sürümünü özelliği ister.|
|[DOĞRULAYIN](#verify)|ASSERT benzer, ancak kitaplığı hata ayıklama sürümü olduğu gibi de yayın sürümünde ifade değerlendirir.|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC genel tanılama değişkenlerin ve işlevlerin

|||
|-|-|
|[afxDump](#afxdump)|Gönderen genel değişkeni [CDumpContext](../../mfc/reference/cdumpcontext-class.md) hata ayıklayıcı çıkış penceresine veya hata ayıklama terminale bilgileri.|
|[afxMemDF](#afxmemdf)|Hata ayıklama bellek ayırıcısı davranışını denetleyen genel değişkeni.|
|[AfxCheckError](#afxcheckerror)|Bir hata olup olmadığını ve bu durumda görmek için geçirilen SCODE test etmek için kullanılan genel değişkeni uygun hata oluşturur.|
|[AfxCheckMemory](#afxcheckmemory)|Şu anda ayrılan bellek tüm bütünlüğünü denetler.|
|[AfxDebugBreak](#afxdebugbreak)|Bir kesme yürütülmesine neden olur.|
|[afxDump](#cdumpcontext_in_mfc)|Hata ayıklayıcısı olsa çağrılırsa, hata ayıklama sırasında bir nesnenin durumu dökümünü yapar.|
|[afxDump](#afxdump)|Hata ayıklama sırasında bir nesnenin durumu dökümleri iç işlev.|
|[AfxDumpStack](#afxdumpstack)|Geçerli yığın görüntüsü oluşturur. Bu işlev her zaman statik olarak bağlanır.|
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|Bellek sızıntısı dökümü sağlar.|
|[AfxEnableMemoryTracking](#afxenablememorytracking)|Açma ve kapatma izleme bellek kapatır.|
|[Afxısmemoryblock](#afxismemoryblock)|Bir bellek bloğunu düzgün şekilde ayrıldığını doğrular.|
|[Afxısvalidaddress](#afxisvalidaddress)|Bir bellek adresi aralığı programın sınırları içinde olduğunu doğrular.|
|[Afxısvalidstring](#afxisvalidstring)|Bir dizeye bir işaretçi geçerli olup olmadığını belirler.|
|[AfxSetAllocHook](#afxsetallochook)|Arama her bellek ayırmada bir işlevin sağlar.|

### <a name="mfc-object-diagnostic-functions"></a>MFC nesne Tanılama işlevleri

|||
|-|-|
|[AfxDoForAllClasses](#afxdoforallclasses)|Tüm belirtilen bir işlevi gerçekleştiren `CObject`-çalışma zamanı tür denetimi destekleyen sınıflar türetilmiş.|
|[AfxDoForAllObjects](#afxdoforallobjects)|Tüm belirtilen bir işlevi gerçekleştiren `CObject`-türetilmiş ile ayrılmış nesneleri **yeni**.|

### <a name="mfc-compilation-macros"></a>MFC derleme makroları

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Kullanım dışı bırakılan MFC işlevlerin kullanılması için derleyici uyarıları bastırır.|


## <a name="afx_secure_no_warnings"></a> _AFX_SECURE_NO_WARNINGS

Kullanım dışı bırakılan MFC işlevlerin kullanılması için derleyici uyarıları bastırır.

### <a name="syntax"></a>Sözdizimi

```
_AFX_SECURE_NO_WARNINGS
```
### <a name="example"></a>Örnek

Bu kod örneği, bir derleyici uyarısı _afx_secure_no_warnıngs değil tanımlanırsa neden olur.

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

Bir kesintiye neden olmak için bu işlevi çağırın (yapılan çağrının konumda `AfxDebugBreak`) MFC uygulamanızı hata ayıklama sürümünü yürütülmesi.

### <a name="syntax"></a>Sözdizimi

```
void AfxDebugBreak( );
```

### <a name="remarks"></a>Açıklamalar

`AfxDebugBreak` bir MFC uygulaması yayın sürümlerinde etkiye sahip değildir ve kaldırılması gerekiyor. Bu işlev yalnızca MFC uygulamalarında kullanılması gerekir. Win32 API sürümünü kullanın `DebugBreak`, MFC olmayan uygulamalarda bir kesintiye neden olacak.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxver_.h

##  <a name="assert"></a>  ASSERT

Bağımsız değişkeni değerlendirir.

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>Parametreler

*booleanDeyimi*<br/>
Sıfır olmayan veya 0 için değerlendirilen bir ifade (işaretçi değerleri dahil) belirtir.

### <a name="remarks"></a>Açıklamalar

Sonucu 0 ise, makro bir tanılama iletisi yazdırır ve programı durdurur. Koşul sıfır ise, hiçbir şey yapmaz.

Tanılama iletisi şu formdadır:

`assertion failed in file <name> in line <num>`

Burada *adı* kaynak dosyasının adıdır ve *num* kaynak dosyada başarısız onaylama satır sayısıdır.

MFC yayın sürümünde, onay ifadeyi değerlendirmez ve dolayısıyla program yarıda kesmez. Ortam bağımsız olarak ifadenin değerlendirilmesi gereken ASSERT yerine VERIFY makrosu kullanın.

> [!NOTE]
>  Bu işlev, yalnızca MFC hata ayıklama sürümü kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="assert_kindof"></a>  ASSERT_KINDOF

Bu makro, işaret edilen nesnenin belirtilen sınıfın bir nesnesi olduğundan veya belirtilen sınıftan türetilmiş bir sınıfın bir nesnesi onaylar.

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>Parametreler

*ClassName*<br/>
Adı bir `CObject`-türetilmiş sınıf.

*pobject*<br/>
Bir sınıf nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*Pobject* parametresi bir nesneye bir işaretçi olmalıdır ve olabilir **const**. İşaret edilen nesne ve sınıf desteklemelidir `CObject` çalışma zamanı sınıf bilgileri. Emin olmak için örnek olarak `pDocument` bir nesne işaretçisidir `CMyDoc` sınıfı veya türevleri, biri kodu yazabilirsiniz:

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

Kullanarak `ASSERT_KINDOF` makrosu tam olarak aynı olup kodlama:

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

Bu işlev yalnızca sınıfları ile bildirilen çalışır [DECLARE_DYNAMIC] (#DECLARE_DYNAMIC Çalıştır-zaman-nesne-model-services.md veya [declare_serıal](run-time-object-model-services.md#declare_serial) makrosu.

> [!NOTE]
>  Bu işlev, yalnızca MFC hata ayıklama sürümü kullanılabilir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="assert_valid"></a>  ASSERT_VALID

Bir nesnenin iç durum geçerliliğini hakkında önemlisi test amacıyla kullanın.

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>Parametreler

*pObject*<br/>
Türetilen bir sınıfın bir nesnesi belirtir `CObject` geçersiz kılan bir sürümü olan `AssertValid` üye işlevi.

### <a name="remarks"></a>Açıklamalar

Assert_valıd çağrıları `AssertValid` nesnesinin üye işlevi, kendi bağımsız değişkeni olarak geçirilir.

MFC yayın sürümünde assert_valıd hiçbir şey yapmaz. Hata ayıklama sürümünde, işaretçi doğrular, NULL karşı denetler ve kendi çağıran `AssertValid` üye işlevleri. Bunlardan birine sınar, başarısız bir uyarı iletisi ile aynı şekilde görüntülenir [ASSERT](#assert).

> [!NOTE]
>  Bu işlev, yalnızca MFC hata ayıklama sürümü kullanılabilir.

Daha fazla bilgi ve örnekler için bkz. [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="debug_new"></a>  DEBUG_NEW

Bellek sızıntılarını bulmanın yardımcı olur.

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>Açıklamalar

DEBUG_NEW programınızda, normalde kullanacağınız her yerde kullanabilirsiniz **yeni** yığın ayrılacak işleci.

Hata ayıklama modunda (zaman **_DEBUG** sembol tanımlanır), dosya adı ve satır numarası ayırdığı her nesne için DEBUG_NEW izler. Ardından kullandığınızda [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) üye işlevini DEBUG_NEW ile ayrılan her nesne gösterilir dosya adı ve satır numarasıyla burada ayrıldı.

DEBUG_NEW kullanmak için kaynak dosyalarınızda aşağıdaki yönerge ekleyin:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

Bu yönerge ekledikten sonra kullandığınız her yerde önişlemci DEBUG_NEW ekleyecek **yeni**, ve MFC geri kalanını yapar. Programınızın bir yayım sürümünü derlediğinizde, bir basit DEBUG_NEW çözümler **yeni** işlem ve dosya adı ve satır numarası bilgileri oluşturulmaz.

> [!NOTE]
>  MFC (4.1 ve öncesi) önceki sürümlerinde yerleştirmek için gereken `#define` deyiminden sonra IMPLEMENT_DYNCREATE veya ımplement_serıal makroları adlı tüm deyimler. Bu artık gerekli değildir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="debug_only"></a>  DEBUG_ONLY

Hata ayıklama modunda (zaman **_DEBUG** sembol tanımlanır), DEBUG_ONLY bağımsız değişkeni değerlendirir.

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>Açıklamalar

Bir yayın yapıda DEBUG_ONLY argüman değerlendirmez. Bu, yalnızca hata ayıklama yapılarında yürütülmesi gereken kod olduğunda yararlıdır.

DEBUG_ONLY makrosu çevredeki eşdeğerdir *ifade* ile `#ifdef _DEBUG` ve `#endif`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

### <a name="ensure"></a>  Emin olun ve ENSURE_VALID

Veri doğruluğunu doğrulamak için kullanın.

### <a name="syntax"></a>Sözdizimi

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```
### <a name="parameters"></a>Parametreler

*booleanDeyimi*<br/>
Test edilecek bir Boole ifadesini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makrolar amacı doğrulama parametrelerinin artırmaktır. Makroları yanlış parametreler kodunuza daha fazla işlenmesini önler. ASSERT makroları olun makroları onaylama oluşturma ek olarak bir özel durum.

Makroları proje yapılandırmasına göre iki şekilde davranır. Makrolar, onay çağırın ve onaylama başarısız olursa, ardından bir özel durum. (Diğer bir deyişle, _DEBUG tanımlı olduğu yerlerde) bu nedenle, hata ayıklama yapılandırmasında makroları bir onaylama işlemi ve yayın yapılandırmaları, makroları üretmek özel durum oluştu (onay yayın yapılandırmaları ifadesinde değerlendirmez) yalnızca özel durum oluşturur.

Makro ENSURE_ARG olun makrosu gibi davranır.

(Bu yalnızca hata ayıklama yapılarında etkisi) assert_valıd makrosu ENSURE_VALID çağırır. Ayrıca, NULL işaretçi ise ENSURE_VALID özel durum oluşturur. NULL test hem hata ayıklama ve yayın yapılandırmaları gerçekleştirilir.

Şu testlerden herhangi birini başarısız olursa bir uyarı mesajı onay ile aynı şekilde görüntülenir. Makro, gerekirse geçersiz bağımsız değişken özel durum oluşturur.
### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

### <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[DOĞRULAYIN](#verify)<br/>
[ATLENSURE](#altensure)

## <a name="this_file"></a> THIS_FILE

Derleniyor dosyasının adına genişletir.

### <a name="syntax"></a>Sözdizimi

```
THIS_FILE
```

### <a name="remarks"></a>Açıklamalar

Bilgiler onay ve Doğrula makroları tarafından kullanılır. Uygulama Sihirbazı ve kod sihirbazları, kaynak kodu dosyalarını oluşturdukları makrosu yerleştirin.

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

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[ASSERT](#assert)<br/>
[DOĞRULAYIN](#verify)


##  <a name="trace"></a>  İZLEME

Belirtilen dize geçerli uygulamanın hata ayıklayıcıya gönderir.

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>Açıklamalar

Bkz: [ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) izleme açıklaması. İzleme ve ATLTRACE2 aynı davranışa sahip.

MFC hata ayıklama sürümünde bu makroyu belirtilen dize geçerli uygulamanın hata ayıklayıcıya gönderir. Bir yayın yapıda Bu makroyu (hiçbir kod hiç oluşturulur) bir şey derler.

Daha fazla bilgi için [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="verify"></a>  DOĞRULAYIN

MFC hata ayıklama sürümünde bağımsız değişkeni değerlendirir.

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>Parametreler

*booleanDeyimi*<br/>
Sıfır olmayan veya 0 için değerlendirilen bir ifade (işaretçi değerleri dahil) belirtir.

### <a name="remarks"></a>Açıklamalar

Sonucu 0 ise, makro bir tanılama iletisi yazdırır ve programı durdurur. Koşul sıfır ise, hiçbir şey yapmaz.

Tanılama iletisi şu formdadır:

`assertion failed in file <name> in line <num>`

Burada *adı* kaynak dosyasının adıdır ve *num* kaynak dosyada başarısız onaylama satır sayısıdır.

MFC yayın sürümünde DOĞRULAYIN ifade değerlendirilir ancak yazdırma veya programı kesmez. Örneğin, ifade bir işlev çağrısı ise, çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>  afxDump (MFC'de CDumpContext)

Uygulamanızdaki temel nesne dökme yeteneği sağlar.

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>Açıklamalar

`afxDump` önceden tanımlanmış olan [CDumpContext](../../mfc/reference/cdumpcontext-class.md) göndermek izin veren nesnesi `CDumpContext` hata ayıklayıcı çıkış penceresine veya hata ayıklama terminale bilgileri. Genelde, girdiğiniz `afxDump` bir parametre olarak `CObject::Dump`.

Windows NT ve tüm sürümleri, Windows altında `afxDump` uygulamanızın hata ayıklaması yaparken, çıktı Visual C++ hata ayıklama çıktı penceresine gönderilir.

Bu değişken, yalnızca MFC hata ayıklama sürümü tanımlanır. Daha fazla bilgi için `afxDump`, bkz: [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h


## <a name="afxdump"></a> AfxDump (iç)

MFC hata ayıklama sırasında bir nesnenin durumu dökümünü almak için kullandığı iç işlev.

### <a name="syntax"></a>Sözdizimi

```
void AfxDump(const CObject* pOb);
```
### <a name="parameters"></a>Parametreler

*posta kutusu*<br/>
Türetilen bir sınıfın bir nesnesi için bir işaretçi `CObject`.

### <a name="remarks"></a>Açıklamalar

`AfxDump` bir nesnenin çağırır `Dump` üye işlevine ve konum bilgileri tarafından belirtilen gönderen `afxDump` değişkeni. `AfxDump` yalnızca MFC hata ayıklama sürümü kullanıma sunulmuştur.

Program kodunuza çağırmamalıdır `AfxDump`, ancak bunun yerine çağırmalıdır `Dump` uygun nesnesinin üye işlevi.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

### <a name="see-also"></a>Ayrıca Bkz.

[CObject::Dump](cobject-class.md#dump)



##  <a name="afxmemdf"></a>  afxMemDF

Bu değişken, bir hata ayıklayıcı veya programınızın erişilebilir olduğundan ve ayırma tanılama ayarlamanıza olanak tanır.

```
int  afxMemDF;
```

### <a name="remarks"></a>Açıklamalar

`afxMemDF` numaralandırması tarafından belirtilen aşağıdaki değerlere sahip olabilir `afxMemDF`:

- `allocMemDF` Hata ayıklama ayırıcı (hata ayıklama Kitaplığı'nda varsayılan ayar) açar.

- `delayFreeMemDF` Bellek boşaltma bir gecikme olabilir. Ayırıcı, programınız bir bellek bloğunu serbest bırakır, ancak bu bellek temel işletim sistemi döndürmez. Bu maksimum bellek yoğun programınızın yerleştirmeniz gerekir.

- `checkAlwaysMemDF` Çağrıları `AfxCheckMemory` bellek tahsis veya serbest her zaman. Bu önemli ölçüde bellek ayırmaları ve deallocations yavaşlatır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxcheckerror"></a>  AfxCheckError

Bu işlev, geçirilen SCODE bir hata olup olmadığını görmek için sınar.

```
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>Açıklamalar

Bir hata ise, işlev bir özel durum oluşturur. Geçirilen SCODE E_OUTOFMEMORY ise, işlev oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) çağırarak [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Aksi halde, işlev oluşturur bir [COleException](../../mfc/reference/coleexception-class.md) çağırarak [AfxThrowOleException](exception-processing.md#afxthrowoleexception).

Bu işlev, uygulamanızdaki OLE işlevlere çağrılarının dönüş değerlerini denetlemek için kullanılabilir. Bu işlev dönüş değeriyle uygulamanızı test ederek, düzgün bir şekilde en az miktarda kodu içeren hata koşulları için tepki verebilir.

> [!NOTE]
>  Bu işlev, hata ayıklama aynı etkiye sahiptir ve hata ayıklama olmayan oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxcheckmemory"></a>  AfxCheckMemory

Bu işlev boş bellek havuzunda doğrular ve gerektiği gibi hata iletilerini yazdırır.

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek hata olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İşlev bellek bozulma algılarsa, hiçbir şey yazdırır.

Tarafından ayrılan dahil olmak üzere, şu anda yığın üzerinde ayrılan tüm bellek blokları denetlenir **yeni** ancak değil olanlar gibi temel alınan bellek ayırıcılar doğrudan çağrılar tarafından ayrılan **malloc** işlevi veya `GlobalAlloc` Windows işlevi. Tüm blok bozuk olduğu için bulunursa, bir ileti için hata ayıklayıcı çıkış yazdırılır.

Satır içeriyorsa

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

ardından sonraki çağrılar için bir program modülünde `AfxCheckMemory` bellek ayrıldığı dosya adı ve satır numarasını göster.

> [!NOTE]
>  Modülünüzün seri hale getirilebilir sınıflar, bir veya daha fazla uygulamalarını içeren sonra yerleştirmelisiniz `#define` son ımplement_serıal makrosu çağrısından sonra satır.

Bu işlev, yalnızca MFC hata ayıklama sürümü çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxdump"></a>  AfxDump (MFC)

Hata ayıklama sırasında bir nesnenin durumu dökümünü almak için hata ayıklayıcı sırada bu işlevi çağırın.

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*posta kutusu*<br/>
Türetilen bir sınıfın bir nesnesi için bir işaretçi `CObject`.

### <a name="remarks"></a>Açıklamalar

`AfxDump` bir nesnenin çağırır `Dump` üye işlevine ve konum bilgileri tarafından belirtilen gönderen `afxDump` değişkeni. `AfxDump` yalnızca MFC hata ayıklama sürümü kullanıma sunulmuştur.

Program kodunuza çağırmamalıdır `AfxDump`, ancak bunun yerine çağırmalıdır `Dump` uygun nesnesinin üye işlevi.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

### <a name="see-also"></a>Ayrıca Bkz.

[CObject::Dump](cobject-class.md#dump)



##  <a name="afxdumpstack"></a>  AfxDumpStack

Bu genel işlevi, geçerli yığının bir görüntü oluşturmak için kullanılabilir.

```
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>Parametreler

*dwTarget*<br/>
Döküm çıkış hedefinin gösterir. Bit düzeyinde OR kullanan birleştirileceğini olası değerler ( **&#124;**) işleci, aşağıdaki gibidir:

- Çıkış AFX_STACK_DUMP_TARGET_TRACE gönderir yoluyla [izleme](#trace) makrosu. TRACE makrosu, yalnızca hata ayıklama yapılarında çıktı üretir; Bunu, sürüm yapılarında hiçbir çıktı oluşturur. Ayrıca, izleme, hata ayıklayıcı yanı sıra diğer hedeflere yönlendirilebilir.

- AFX_STACK_DUMP_TARGET_DEFAULT gönderir dökümünün çıkışını varsayılan hedef. Bir hata ayıklama derlemesi için çıkış izleme makro gider. Bir yayın yapı içinde çıktısı panoya gider.

- AFX_STACK_DUMP_TARGET_CLIPBOARD yalnızca panoya çıktı gönderir. Veriler panoya CF_TEXT Pano biçimi kullanarak düz metin olarak yerleştirilir.

- Pano ve izleme makro için aynı anda çıkış AFX_STACK_DUMP_TARGET_BOTH gönderir.

- Win32 işlevini kullanarak hata ayıklayıcı için doğrudan çıkış AFX_STACK_DUMP_TARGET_ODS gönderir `OutputDebugString()`. Bu seçenek, hata ayıklayıcı çıktı üretmek her iki hata ayıklama ve yayın derlemeleri bir hata ayıklayıcı işleme iliştirildiğinde. AFX_STACK_DUMP_TARGET_ODS (bağlıysa) hata ayıklayıcı her zaman ulaşır ve yönlendirilemiyor.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki örnekte, tek satırlık bir arama öğesinden oluşturulan çıktı yansıtır `AfxDumpStack` MFC iletişim uygulamasında bir düğme işleyicisinden:

```Output
=== begin AfxDumpStack output ===
00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes
0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes
0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,
unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct
AFX_CMDHANDLE
0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes
00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes
00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned
int,long) + 312 bytes
00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned
int,unsigned int,long,long *) + 83 bytes
00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned
int,unsigned int,long) + 46 bytes
004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct
HWND__ *,unsigned int,unsigned int,long) + 237 bytes
00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned
int,unsigned int,long) + 129 bytes
BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes
BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes
=== end AfxDumpStack() output ===
```

Yukarıdaki çıktıda her satır son işlev çağrısı, işlev çağrısı ve adlı işlev prototipi içeren modül tam yol adını adresini belirtir. İşlev çağrısının yığın üzerinde işlev tam adresinde gerçekleşmezse, bayt uzaklığı gösterilir.

Örneğin, aşağıdaki tabloda yukarıdaki çıkış ilk satırını açıklanmaktadır:

|Çıkış|Açıklama|
|------------|-----------------|
|`00427D55:`|Son işlev çağrısının dönüş adresi.|
|`DUMP2\DEBUG\DUMP2.EXE!`|İşlev çağrısı içeren modül tam yol adı.|
|`void AfxDumpStack(unsigned long)`|İşlev prototipi çağrılır.|
|`+ 181 bytes`|İşlev prototipi adresini bayt uzaklığı (Bu durumda, `void AfxDumpStack(unsigned long)`) dönüş adresi (Bu durumda, `00427D55`).|

`AfxDumpStack` MFC kitaplıkları, hata ayıklama ve nondebug sürümlerinde kullanıma sunulmuştur; bile yürütülebilir dosyanızı paylaşılan DLL'de MFC kullandığında ancak işlev her zaman statik olarak, bağlı. Paylaşılan kitaplık uygulamalarında, işlev MFCS42 içinde bulunur. LIB kitaplığı (ve çeşitlerinin).

Bu işlev başarıyla kullanmak için:

- Dosya IMAGEHLP. DLL, yolda olmalıdır. Bu DLL yoksa işlev bir hata iletisi görüntüler. Bkz: [görüntü kitaplığı Yardım](/windows/desktop/Debug/image-help-library) IMAGEHLP tarafından sağlanan işlev kümesi hakkında bilgi için.

- Çerçeve yığında olan modülleri, hata ayıklama bilgileri içermelidir. Hata ayıklama bilgisi içermez, işlev hala bir yığın izleme oluşturur, ancak izlemeyi daha az ayrıntılı olur.
### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxenablememoryleakdump"></a>  AfxEnableMemoryLeakDump

Etkinleştirir ve bellek sızıntısı dökümü AFX_DEBUG_STATE yok Edicisi de devre dışı bırakır.

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>Parametreler

*bDump*<br/>
[in] TRUE, bellek sızıntısı dökümü etkinleştirildiğini belirtir; FALSE, bellek sızıntısı dökümü devre dışı gösterir.

### <a name="return-value"></a>Dönüş Değeri

Bu bayrak önceki değeri.

### <a name="remarks"></a>Açıklamalar

Bir uygulama MFC Kitaplığı kaldırdığında, MFC Kitaplığı için bellek sızıntılarını denetler. Bu noktada, bellek sızıntıları kullanıcının üzerinden raporlanır **hata ayıklama** Visual Studio'nun penceresi.

Uygulamanız MFC Kitaplığı önce başka bir kitaplık yüklerse, bu Kitaplığı'ndaki bazı bellek ayırmaları yanlış bellek sızıntısı bildirilir. Uygulamanız yavaş bunları raporlar MFC Kitaplığı olarak kapatmak false bellek sızıntılarının neden olabilir. Bu durumda, `AfxEnableMemoryLeakDump` bellek sızıntısı dökümü devre dışı bırakmak için.

> [!NOTE]
>  Bellek sızıntısı dökümü etkinleştirmek için bu yöntemi kullanırsanız, uygulamanızda raporları geçerli bellek sızıntılarının almazsınız. Bellek sızıntısı raporunda false bellek sızıntılarını içerdiğini eminseniz bu yöntem yalnızca kullanmanız gerekir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxenablememorytracking"></a>  AfxEnableMemoryTracking

İzleme, tanılama bellek Normal MFC hata ayıklama sürümünde etkinleştirilir.

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>Parametreler

*bTrack*<br/>
Bu değer için doğru sırayla izleme bellek ayarı; FALSE kapanır.

### <a name="return-value"></a>Dönüş Değeri

Önceki ayar izleme etkin bayrağı.

### <a name="remarks"></a>Açıklamalar

Blokları doğru şekilde ayırma bildiğiniz kod bölümlerini izlemeyi devre dışı bırakmak için bu işlevi kullanın.

Daha fazla bilgi için `AfxEnableMemoryTracking`, bkz: [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
>  Bu işlev, yalnızca MFC hata ayıklama sürümü çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxismemoryblock"></a>  Afxısmemoryblock

Tanılama sürümü tarafından ayrılan bir etkin bir bellek bloğunu temsil ettiğinden emin olmak için bir bellek adresi testleri **yeni**.

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Test edilecek bellek bloğuna işaret eder.

*nBytes*<br/>
Bayt cinsinden bellek bloğu uzunluğu içerir.

*plRequestNumber*<br/>
İşaret eden bir **uzun** bellek bloğun ayırma sıra numarası ile doldurulur ve etkin bellek bloğu temsil etmiyorsa sıfır tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Şu anda ayrılmış bellek bloğu ve uzunluğu doğru olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, belirtilen boyut özgün ayrılan boyut karşı denetler. İşlev sıfır dışı döndürürse, ayırma sıra numarası iade *plRequestNumber*. Bu sayı, blok tahsis edildiğinde tüm diğer göreli sırasını gösterir **yeni** ayırmalar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxisvalidaddress"></a>  Afxısvalidaddress

Herhangi bir bellek adresi tamamen programın bellek alanı içinde yer emin olmak için test eder.

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>Parametreler

*LP*<br/>
Test edilecek bellek adresi işaret eder.

*nBytes*<br/>
Test edilecek belleğin bayt sayısını içerir.

*bReadWrite*<br/>
Bellek için okuma ve yazma (TRUE) veya (FALSE) yalnızca okuma hem de olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, belirtilen bellek engellerseniz sıfır olmayan tamamen programın bellek alanı içinde yer alır; Aksi durumda 0.

Hata ayıklama olmayan yapılarında gösterimiyse *lp* NULL; Aksi durumda 0 değildir.

### <a name="remarks"></a>Açıklamalar

Adres blokları tarafından ayrılan sınırlı değil **yeni**.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxisvalidstring"></a>  Afxısvalidstring

Bir dizeye bir işaretçi geçerli olup olmadığını belirlemek için bu işlevi kullanın.

```
BOOL  AfxIsValidString(
    LPCSTR lpsz,
    int nLength = -1);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Test için işaretçi.

*nLength*<br/>
Bayt olarak test edilecek dize uzunluğunu belirtir. -1 değeri, null ile sonlandırılmış dize olacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, belirtilen boyutta bir dizeyi belirtilen işaretçi işaret ediyorsa sıfır; Aksi durumda 0.

Hata ayıklama olmayan yapılarında gösterimiyse *lpsz* NULL; Aksi durumda 0 değildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxsetallochook"></a>  AfxSetAllocHook

Belirtilen işlevi çağırmadan önce her bellek bloğu ayrılan sağlayan bir kanca ayarlar.

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>Parametreler

*pfnAllocHook*<br/>
Çağrılacak işlevin adını belirtir. İçin bir ayırma işlevinin prototipi açıklamalara bakın.

### <a name="return-value"></a>Dönüş Değeri

Ayırma izin vermek istediğiniz olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı hata ayıklama bellek ayırıcısı, kullanıcı bir bellek ayırma izleme ve ayırma izin verilip verilmediğini denetlemek için bir kullanıcı tanımlı kanca işlevini çağırabilir. Atama kanca işlevleri prototipli aşağıdaki gibidir:

**BOOL AFXAPI AllocHook (size_t** `nSize` **, BOOL** `bObject` **, uzun** `lRequestNumber` **);**

*nSize*<br/>
Önerilen bellek ayırma boyutu.

*bNesne*<br/>
Ayırma için ise TRUE bir `CObject`-türetilmiş nesne; Aksi takdirde FALSE.

*lRequestNumber*<br/>
Bellek ayırma'nın sıra numarası.

Çağırma kuralı AFXAPI çağrılan parametrelerin yığından kaldırmalısınız gelir unutmayın.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxdoforallclasses"></a>  AfxDoForAllClasses

Tüm serileştirilebilir belirtilen yineleme işlevi çağıran `CObject`-türetilmiş sınıflar içinde uygulamanın bellek alanı.

```
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parametreler

*pfn*<br/>
Her sınıf için çağrılacak bir yineleme işlev işaret eder. İşlev bağımsız değişkenleri olan bir işaretçi bir `CRuntimeClass` nesne ve çağıran işlevin sağlayan ek veriler void bir işaretçi.

*pContext*<br/>
Yineleme işlevine çağrıyı sağlayan isteğe bağlı verileri işaret eder. This işaretçisi, NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Seri hale getirilebilir `CObject`-türetilmiş sınıflardır declare_serıal makrosu kullanarak türetilmiş sınıflar. Geçirilen işaretçi `AfxDoForAllClasses` içinde *pContext* çağırıldığında her zaman belirtilen yineleme işleve geçirilir.

> [!NOTE]
>  Bu işlev, yalnızca MFC hata ayıklama sürümü çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="afxdoforallobjects"></a>  AfxDoForAllObjects

Türetilen tüm nesneleri için belirtilen yineleme işlevi yürütür `CObject` , ayrılmış ile **yeni**.

```
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parametreler

*pfn*<br/>
Her nesne için yürütülecek bir yineleme işlevi işaret eder. İşlev bağımsız değişkenleri olan bir işaretçi bir `CObject` ve çağıran işlevin sağlayan ek veriler void bir işaretçi.

*pContext*<br/>
Yineleme işlevine çağrıyı sağlayan isteğe bağlı verileri işaret eder. This işaretçisi, NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Yığın, genel veya katıştırılmış nesneleri listelenmiş değil. İşaretçi geçirilen `AfxDoForAllObjects` içinde *pContext* çağırıldığında her zaman belirtilen yineleme işleve geçirilir.

> [!NOTE]
>  Bu işlev, yalnızca MFC hata ayıklama sürümü çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)