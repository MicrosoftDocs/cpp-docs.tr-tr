---
title: Tanı Hizmetleri
ms.date: 11/04/2016
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
ms.openlocfilehash: f952044f4320aea1a757559b3c9c51e8ffb7c3a6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751647"
---
# <a name="diagnostic-services"></a>Tanı Hizmetleri

Microsoft Hazırlık Sınıfı Kitaplığı, programlarınızın hata ayıklamasını kolaylaştıran birçok tanılama hizmeti sağlar. Bu tanılama hizmetleri, programınızın bellek ayırmalarını izlemenize, çalışma süresi sırasında nesnelerin içeriğini boşaltmanıza ve çalışma süresi boyunca hata ayıklama iletilerini yazdırmanıza olanak tanıyan makrolar ve genel işlevler içerir. Tanılama hizmetlerine yönelik makrolar ve genel işlevler aşağıdaki kategorilerde gruplandırılır:

- Genel tanı makroları

- Genel tanı fonksiyonları ve değişkenler

- Nesne tanılama işlevleri

Bu makrolar ve işlevler, MFC'nin Hata Ayıklama ve Sürüm sürümlerinden `CObject` türetilen tüm sınıflar için kullanılabilir. Ancak, DEBUG_NEW ve VERIFY dışındaki tüm sürümde hiçbir şey yapmaz.

Hata Ayıklama kitaplığında, ayrılan tüm bellek blokları bir dizi "koruma baytı" ile parantez içinde dir. Bu baytlar hatalı bir bellek yazmak tarafından rahatsız edilirse, tanı yordamları bir sorunu bildirebilirsiniz. Satırı eklerseniz:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

uygulama dosyanızda, **yeni** yapılan tüm aramalarda dosya adı ve bellek ayırmanın gerçekleştiği satır numarası depolanır. [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) işlevi bu ekstra bilgileri görüntüleyerek bellek sızıntılarını belirlemenize olanak sağlar. Tanılama çıktısı hakkında ek bilgi için [CDumpContext](../../mfc/reference/cdumpcontext-class.md) sınıfına da bakın.

Buna ek olarak, C çalışma zamanı kitaplığı, uygulamalarınızı hata ayıklamak için kullanabileceğiniz bir dizi tanılama işlevlerini de destekler. Daha fazla bilgi için, Çalışma Zamanı Kitaplığı Başvurusu'nda [Hata Ayıklama Yordamları'na](../../c-runtime-library/debug-routines.md) bakın.

### <a name="mfc-general-diagnostic-macros"></a>MFC Genel Tanı makroları

|||
|-|-|
|[Assert](#assert)|Bir ileti yazdırır ve belirtilen ifade kitaplığın Hata Ayıklama sürümünde FALSE olarak değerlendirirse programı iptal eder.|
|[ASSERT_KINDOF](#assert_kindof)|Bir nesnenin belirtilen sınıfın veya belirtilen sınıftan türetilen bir sınıfın nesnesi olduğunu sınar.|
|[ASSERT_VALID](#assert_valid)|`AssertValid` Bir nesnenin iç geçerliliğini üye işlevini çağırarak sınar; genellikle `CObject`geçersiz kılınmış.|
|[DEBUG_NEW](#debug_new)|Hata ayıklama modundaki tüm nesne ayırmaları için bellek sızıntılarını bulmaya yardımcı olmak için bir dosya adı ve satır numarası sağlar.|
|[DEBUG_ONLY](#debug_only)|Assert'a benzer ancak ifadenin değerini sınamaz; yalnızca Hata Ayıklama modunda yürütülmesi gereken kod için yararlıdır.|
|[ENSURE ve ENSURE_VALID](#ensure)|Veri doğruluğunu doğrulamak için kullanın.|
|[THIS_FILE](#this_file)|Derlenen dosyanın adını genişletir.|
|[Izleme](#trace)|Kitaplığın Hata Ayıklama sürümünde -benzer yetenek sağlar. `printf`|
|[Doğrulamak](#verify)|Assert'a benzer, ancak kitaplığın Sürüm sürümündeki ve Hata Ayıklama sürümündeki ifadeyi değerlendirir.|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC Genel Tanı Değişkenleri ve Fonksiyonları

|||
|-|-|
|[afxDump](#afxdump)|[CDumpContext](../../mfc/reference/cdumpcontext-class.md) bilgilerini hata ayıklama çıkış penceresine veya hata ayıklama terminaline gönderen genel değişken.|
|[afxMemDF](#afxmemdf)|Hata ayıklama bellek ayırıcısının davranışını kontrol eden genel değişken.|
|[AfxCheckError](#afxcheckerror)|Genel değişken bir hata olup olmadığını görmek için geçirilen SCODE test etmek için kullanılır ve eğer öyleyse, uygun hata atar.|
|[AfxCheckMemory](#afxcheckmemory)|Şu anda ayrılan tüm belleğin bütünlüğünü denetler.|
|[AfxDebugBreak](#afxdebugbreak)|Yürütmede bir mola neden olur.|
|[AfxDump](#cdumpcontext_in_mfc)|Hata ayıklama sırasında çağrılırsa, hata ayıklama sırasında bir nesnenin durumunu döker.|
|[AfxDump](#afxdump)|Hata ayıklama sırasında bir nesnenin durumunu boşaltan iç işlev.|
|[AfxDumpStack](#afxdumpstack)|Geçerli yığının görüntüsünü oluşturun. Bu işlev her zaman statik olarak bağlanır.|
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|Bellek sızıntısı dökümünün etkin olmasını sağlar.|
|[AfxEnableMemoryTracking](#afxenablememorytracking)|Bellek izlemeyi açar ve kapatır.|
|[AfxIsMemoryBlock](#afxismemoryblock)|Bellek bloğunun düzgün şekilde tahsis edildiğini doğrular.|
|[AfxIsValidAddress](#afxisvalidaddress)|Bellek adresi aralığının programın sınırları içinde olduğunu doğrular.|
|[AfxIsValidString](#afxisvalidstring)|Dize işaretçisi geçerli olup olmadığını belirler.|
|[AfxSetAllocHook](#afxsetallochook)|Her bellek ayırma da bir işlevin çağrılmasını sağlar.|

### <a name="mfc-object-diagnostic-functions"></a>MFC Nesne Tanılama Fonksiyonları

|||
|-|-|
|[AfxDoForAllClasses](#afxdoforallclasses)|Çalışma zamanı türü `CObject`denetimini destekleyen tüm türemiş sınıflarda belirli bir işlev gerçekleştirir.|
|[AfxDoForAllObjects](#afxdoforallobjects)|Yeni ile ayrılan `CObject`tüm türetilmiş nesnelerde **new**belirli bir işlev gerçekleştirir.|

### <a name="mfc-compilation-macros"></a>MFC Derleme Makroları

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Amortismana uymulan MFC işlevlerinin kullanımı için derleyici uyarılarını bastırır.|

## <a name="_afx_secure_no_warnings"></a><a name="afx_secure_no_warnings"></a>_AFX_SECURE_NO_WARNINGS

Amortismana uymulan MFC işlevlerinin kullanımı için derleyici uyarılarını bastırır.

### <a name="syntax"></a>Sözdizimi

```
_AFX_SECURE_NO_WARNINGS
```

### <a name="example"></a>Örnek

Bu kod örneği, _AFX_SECURE_NO_WARNINGS tanımlanmamışsa derleyici uyarısına neden olur.

```cpp
// define this before including any afx files in *pch.h* (*stdafx.h* in Visual Studio 2017 and earlier)
#define _AFX_SECURE_NO_WARNINGS
```

```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a><a name="afxdebugbreak"></a>AfxDebugBreak

MFC uygulamanızın hata ayıklama sürümünün yürütülmesinde bir ara (çağrının bulunduğu yerde) neden olmak için `AfxDebugBreak`bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AfxDebugBreak( );
```

### <a name="remarks"></a>Açıklamalar

`AfxDebugBreak`bir MFC uygulamasının sürüm sürümlerinde hiçbir etkisi yoktur ve kaldırılmalıdır. Bu işlev yalnızca MFC uygulamalarında kullanılmalıdır. MFC olmayan uygulamalarda bir `DebugBreak`mola vermek için Win32 API sürümünü kullanın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxver_.h

## <a name="assert"></a><a name="assert"></a>Assert

Bağımsız değişkenini değerlendirir.

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>Parametreler

*booleanExpression*<br/>
Sıfır olmayan veya 0 olarak değerlendiren bir ifade (işaretçi değerleri dahil) belirtir.

### <a name="remarks"></a>Açıklamalar

Sonuç 0 ise, makro bir tanılama iletisi yazdırır ve programı iptal eder. Koşul sıfır değilse, hiçbir şey yapmaz.

Tanılama iletisi şu formdadır:

`assertion failed in file <name> in line <num>`

*burada ad* kaynak dosyanın adıdır ve *num* kaynak dosyada başarısız olan iddianın satır numarasıdır.

MFC'nin Sürüm sürümünde, ASSERT ifadeyi değerlendirmez ve bu nedenle programı kesintiye uğratmaz. İfadenin ortama bakılmaksızın değerlendirilmesi gerekiyorsa, ASSERT yerine DOĞRULA makroyu kullanın.

> [!NOTE]
> Bu işlev yalnızca MFC'nin Hata Ayıklama sürümünde kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="assert_kindof"></a><a name="assert_kindof"></a>ASSERT_KINDOF

Bu makro, işaret edilen nesnenin belirtilen sınıfın bir nesnesi olduğunu veya belirtilen sınıftan türetilen bir sınıfın nesnesi olduğunu ileri sürtürü.

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
Türetilmiş `CObject`sınıfın adı.

*Pobject*<br/>
Sınıf nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

*Pobject* parametresi bir nesneye işaretçi olmalıdır ve **const**olabilir. Nesne işaret ve sınıf çalışma `CObject` zamanı sınıf bilgilerini desteklemesi gerekir. Örnek olarak, `pDocument` `CMyDoc` sınıfın veya türevlerinin herhangi birinin nesnesine işaretçi olduğundan emin olmak için şu şekilde kodlayabilirsiniz:

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

Makroyu `ASSERT_KINDOF` kullanmak kodlama ile tamamen aynıdır:

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

Bu işlev yalnızca [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic veya [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makrosuyla bildirilen sınıflar için çalışır.

> [!NOTE]
> Bu işlev yalnızca MFC'nin Hata Ayıklama sürümünde kullanılabilir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="assert_valid"></a><a name="assert_valid"></a>ASSERT_VALID

Bir nesnenin iç durumunun geçerliliği hakkındaki varsayımlarınızı sınamak için kullanın.

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>Parametreler

*Pobject*<br/>
Üye işlevin geçersiz bir sürümü `CObject` olan bir sınıfın nesnesini belirtir. `AssertValid`

### <a name="remarks"></a>Açıklamalar

ASSERT_VALID, `AssertValid` bağımsız değişken olarak geçirilen nesnenin üye işlevini çağırır.

MFC'nin Sürüm sürümünde, ASSERT_VALID hiçbir şey yapmaz. Hata Ayıklama sürümünde işaretçiyi doğrular, NULL'a karşı denetler ve nesnenin kendi `AssertValid` üye işlevlerini çağırır. Bu sınamalardan herhangi biri başarısız olursa, bir uyarı [iletisi ASSERT](#assert)ile aynı şekilde görüntülenir.

> [!NOTE]
> Bu işlev yalnızca MFC'nin Hata Ayıklama sürümünde kullanılabilir.

Daha fazla bilgi ve örnekler için, [Hata Ayıklama MFC Uygulamaları'na](/visualstudio/debugger/mfc-debugging-techniques)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="debug_new"></a><a name="debug_new"></a>DEBUG_NEW

Hafıza sızıntılarını bulmada yardımcı olur.

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>Açıklamalar

Programınızda, yığın depolama alanı ayırmak için **normalde yeni** işleci kullanacağınız her yerde DEBUG_NEW kullanabilirsiniz.

Hata ayıklama modunda **(_DEBUG** simgesi tanımlandığında), DEBUG_NEW ayırdığı her nesne için dosya adını ve satır numarasını izler. Daha sonra, [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) üye işlevi kullandığınızda, DEBUG_NEW ile ayrılan her nesne, tahsis edildiği dosya adı ve satır numarasıyla gösterilir.

DEBUG_NEW kullanmak için kaynak dosyalarınıza aşağıdaki yönergeyi ekleyin:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

Bu yönergeyi ekledikten sonra, önişlemci **yeni**kullandığınız her yere DEBUG_NEW ekler ve gerisini MFC yapar. Programınızın sürüm sürümünü derlediğinizde, DEBUG_NEW basit bir **yeni** işlemle çözülür ve dosya adı ve satır numarası bilgileri oluşturulmaz.

> [!NOTE]
> MFC'nin önceki sürümlerinde (4.1 ve daha `#define` önceki) IMPLEMENT_DYNCREATE veya IMPLEMENT_SERIAL makroları olarak adlandırılan tüm ifadelerden sonra deyimi koymanız gerekir. Buna artık gerek yok.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="debug_only"></a><a name="debug_only"></a>DEBUG_ONLY

Hata ayıklama modunda **(_DEBUG** sembolü tanımlandığında), DEBUG_ONLY bağımsız değişkenini değerlendirir.

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>Açıklamalar

Sürüm yapısında, DEBUG_ONLY bağımsız değişkenini değerlendirmez. Bu, yalnızca hata ayıklama yapılarında yürütülmesi gereken kodunuz olduğunda yararlıdır.

DEBUG_ONLY makrosu ile `#ifdef _DEBUG` çevreleyen *ifadeye* eşdeğerdir. `#endif`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

### <a name="ensure-and-ensure_valid"></a><a name="ensure"></a>ENSURE ve ENSURE_VALID

Veri doğruluğunu doğrulamak için kullanın.

### <a name="syntax"></a>Sözdizimi

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```

### <a name="parameters"></a>Parametreler

*booleanExpression*<br/>
Test edilecek bir boolean ifadesini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makroların amacı parametrelerin doğrulanmasını geliştirmektir. Makrolar, kodunuzdaki yanlış parametrelerin daha fazla işlenmesini engeller. ASSERT makrolarının aksine, ENSURE makroları bir iddia oluşturmaya ek olarak bir özel durum oluşturur.

Makrolar, proje yapılandırmasına göre iki şekilde birden etkilidir. Makrolar ASSERT'ı çağırır ve iddia başarısız olursa bir özel durum oluşturur. Bu nedenle, Hata Ayıklama yapılandırmalarında (yani _DEBUG tanımlandığı yerde) makrolar bir öneetme ve özel durum üretirken, Sürüm yapılandırmalarında makrolar yalnızca özel durum üretir (Assert, Release yapılandırmalarında ifadeyi değerlendirmez).

Makro ENSURE_ARG ENSURE makrosu gibi davranır.

ENSURE_VALID ASSERT_VALID makro (yalnızca Hata Ayıklama oluşturur bir etkisi vardır) çağırır. Ayrıca, işaretçi NULL ise ENSURE_VALID bir özel durum atar. NULL testi hem Hata Ayıklama hem de Sürüm yapılandırmalarında gerçekleştirilir.

Bu sınamalardan herhangi biri başarısız olursa, bir uyarı iletisi ASSERT ile aynı şekilde görüntülenir. Makro gerekirse geçersiz bir bağımsız değişken özel durum atar.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="this_file"></a><a name="this_file"></a>THIS_FILE

Derlenen dosyanın adını genişletir.

### <a name="syntax"></a>Sözdizimi

```
THIS_FILE
```

### <a name="remarks"></a>Açıklamalar

Bilgiler, ASSERT ve VERIFY makroları tarafından kullanılır. Uygulama Sihirbazı ve kod sihirbazları makroyu oluşturdukları kaynak kod dosyalarına yer.

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

**Üstbilgi:** afx.h

## <a name="trace"></a><a name="trace"></a>Izleme

Belirtilen dizeyi geçerli uygulamanın hata ayıkıcısına gönderir.

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>Açıklamalar

TRACE'in açıklaması için [ATLTRACE2'ye](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) bakın. TRACE ve ATLTRACE2 aynı davranışa sahiptir.

MFC hata ayıklama sürümünde, bu makro geçerli uygulamanın hata ayıklayıcı belirtilen dize gönderir. Bir sürüm yapısında, bu makro hiçbir şey için derler (hiçbir kod hiç oluşturulur).

Daha fazla bilgi için, [Hata Ayıklama MFC Uygulamaları'na](/visualstudio/debugger/mfc-debugging-techniques)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="verify"></a><a name="verify"></a>Doğrulamak

MFC'nin Hata Ayıklama sürümünde, bağımsız değişkenini değerlendirir.

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>Parametreler

*booleanExpression*<br/>
Sıfır olmayan veya 0 olarak değerlendiren bir ifade (işaretçi değerleri dahil) belirtir.

### <a name="remarks"></a>Açıklamalar

Sonuç 0 ise, makro bir tanılama iletisi yazdırır ve programı durdurur. Koşul sıfır değilse, hiçbir şey yapmaz.

Tanılama iletisi şu formdadır:

`assertion failed in file <name> in line <num>`

*adı* kaynak dosyanın adı ve *num* kaynak dosyasında başarısız olan iddianın satır numarasıdır.

MFC'nin Sürüm sürümünde, VERIFY ifadeyi değerlendirir, ancak programı yazdırmaz veya kesintiye uğratmaz. Örneğin, ifade bir işlev çağrısıysa, arama yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxdump-cdumpcontext-in-mfc"></a><a name="cdumpcontext_in_mfc"></a>afxDump (MFC'de CDumpContext)

Uygulamanızda temel nesne damping özelliği sağlar.

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>Açıklamalar

`afxDump`hata ayıklama çıkış penceresine veya hata `CDumpContext` ayıklama terminaline bilgi göndermenize olanak tanıyan önceden tanımlanmış bir [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesidir. Genellikle, bir `afxDump` parametre olarak `CObject::Dump`kaynağı.

Windows NT ve Windows'un `afxDump` tüm sürümleri altında, uygulamanızı hata ayıklama yaptığınızda çıktı Visual C++'ın Çıktı Hata Ayıklama penceresine gönderilir.

Bu değişken yalnızca MFC'nin Hata Ayıklama sürümünde tanımlanır. Daha fazla `afxDump`bilgi için, [Hata Ayıklama MFC Uygulamaları'na](/visualstudio/debugger/mfc-debugging-techniques)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxdump-internal"></a><a name="afxdump"></a>AfxDump (Dahili)

MFC'nin hata ayıklama sırasında nesnenin durumunu boşaltmak için kullandığı iç işlev.

### <a name="syntax"></a>Sözdizimi

```cpp
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*Pob*<br/>
Bir sınıfın nesnesine `CObject`işaretçi.

### <a name="remarks"></a>Açıklamalar

`AfxDump`nesnenin `Dump` üye işlevini çağırır ve bilgileri `afxDump` değişken tarafından belirtilen konuma gönderir. `AfxDump`yalnızca MFC'nin Hata Ayıklama sürümünde kullanılabilir.

Program kodunuz aramamalı, `AfxDump`bunun yerine `Dump` uygun nesnenin üye işlevini aramalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxmemdf"></a><a name="afxmemdf"></a>afxMemDF

Bu değişkene bir hata ayıklayıcıdan veya programınızdan erişilebilir ve ayırma tanılamalarını ayarlamanızı sağlar.

```
int  afxMemDF;
```

### <a name="remarks"></a>Açıklamalar

`afxMemDF`numaralandırmada `afxMemDF`belirtildiği gibi aşağıdaki değerlere sahip olabilir:

- `allocMemDF`Hata ayıklama ayırıcıyı (Hata Ayıklama kitaplığında varsayılan ayar) açar.

- `delayFreeMemDF`Hafızanın serbest silmesinde gecikmeler. Programınız bir bellek bloğunu boşaltırken, ayırıcı bu belleği temel işletim sistemine döndürmez. Bu, programınıza maksimum bellek stresi yerleştirecektir.

- `checkAlwaysMemDF`Bellek `AfxCheckMemory` her zaman tahsis veya serbest çağrılar. Bu önemli ölçüde bellek ayırmaları ve anlaşma yerleri yavaşlayacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxcheckerror"></a><a name="afxcheckerror"></a>AfxCheckError

Bu işlev, bir hata olup olmadığını görmek için geçirilen SCODE'u sınar.

```cpp
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>Açıklamalar

Bu bir hataysa, işlev bir özel durum atar. Geçirilen SCODE E_OUTOFMEMORY ise, işlev [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)çağırarak bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) atar. Aksi takdirde, işlev [AfxThrowOleException](exception-processing.md#afxthrowoleexception)çağırarak bir [COleException](../../mfc/reference/coleexception-class.md) atar.

Bu işlev, uygulamanızdaki OLE işlevlerine yapılan çağrıların dönüş değerlerini denetlemek için kullanılabilir. Uygulamanızdaki bu işlevle iade değerini sınayarak, hata koşullarına en az miktarda kodla düzgün bir şekilde tepki verebilirsiniz.

> [!NOTE]
> Bu işlev hata ayıklama ve hata ayıklama olmayan yapılarda aynı etkiye sahiptir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxcheckmemory"></a><a name="afxcheckmemory"></a>AfxCheckMemory

Bu işlev, boş bellek havuzunu doğrular ve gerektiğinde hata iletilerini yazdırır.

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan bellek hataları yoksa; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlev bellek bozulması algılamazsa, hiçbir şey yazdıramaz.

Şu anda yığında ayrılan tüm bellek blokları, **malloc** işlevi veya `GlobalAlloc` Windows işlevi gibi altta yatan bellek ayırıcılarına doğrudan çağrılarla ayrılanlar da dahil olmak **üzere, yeni** tarafından ayrılanlar da dahil olmak üzere denetlenir. Herhangi bir bloğun bozuk olduğu tespit edilirse, hata ayıklama çıkışına bir ileti yazdırılır.

Satırı eklerseniz

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

bir program modülünde, daha `AfxCheckMemory` sonra bellek tahsis edildi dosya adı ve satır numarasını göstermek için sonraki aramalar.

> [!NOTE]
> Modülünüzün serileştirilebilir sınıfların bir veya daha fazla uygulaması `#define` varsa, son IMPLEMENT_SERIAL makro çağrısından sonra satırı koymanız gerekir.

Bu işlev yalnızca MFC'nin Hata Ayıklama sürümünde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxdump-mfc"></a><a name="afxdump"></a>AfxDump (MFC)

Hata ayıklama sırasında bir nesnenin durumunu dökümü için hata ayıklama sırasında bu işlevi çağırın.

```cpp
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*Pob*<br/>
Bir sınıfın nesnesine `CObject`işaretçi.

### <a name="remarks"></a>Açıklamalar

`AfxDump`nesnenin `Dump` üye işlevini çağırır ve bilgileri `afxDump` değişken tarafından belirtilen konuma gönderir. `AfxDump`yalnızca MFC'nin Hata Ayıklama sürümünde kullanılabilir.

Program kodunuz aramamalı, `AfxDump`bunun yerine `Dump` uygun nesnenin üye işlevini aramalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxdumpstack"></a><a name="afxdumpstack"></a>AfxDumpStack

Bu genel işlev, geçerli yığının görüntüsünü oluşturmak için kullanılabilir.

```cpp
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>Parametreler

*dwTarget*<br/>
Döküm çıktısının hedefini gösterir. Bitwise-OR ( **&#124;**) işleci kullanılarak birleştirilebilen olası değerler aşağıdaki gibidir:

- AFX_STACK_DUMP_TARGET_TRACE [TRACE](#trace) makrosu ile çıktı gönderir. TRACE makrosu yalnızca hata ayıklama oluşturur çıktı üretir; sürüm yapılarında hiçbir çıktı üretmez. Ayrıca, TRACE hata ayıklama nın yanı sıra diğer hedeflere de yönlendirilebilir.

- AFX_STACK_DUMP_TARGET_DEFAULT Dump output'u varsayılan hedefe gönderir. Hata ayıklama yapısı için çıktı TRACE makrosu gider. Sürüm yapısında, çıktı Pano'ya gider.

- AFX_STACK_DUMP_TARGET_CLIPBOARD Çıktıyı yalnızca Panoya Gönderir. Veriler, pano CF_TEXT biçimini kullanarak düz metin olarak Pano'ya yerleştirilir.

- AFX_STACK_DUMP_TARGET_BOTH Çıktıyı Panoya ve TRACE makrosuna aynı anda gönderir.

- AFX_STACK_DUMP_TARGET_ODS Win32 fonksiyonu `OutputDebugString()`ile çıktıyı doğrudan hata ayıklayana gönderir. Bu seçenek, bir hata ayıklama işlemine bağlı olduğunda hem hata ayıklama hem de sürüm yapılarında hata ayıklama çıktısı oluşturur. AFX_STACK_DUMP_TARGET_ODS her zaman hata ayıklama (bağlıise) ulaşır ve yeniden yönlendirilemez.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek, Bir MFC iletişim uygulamasında `AfxDumpStack` bir düğme işleyicisinden çağrılarak oluşturulan çıktının tek bir satırını yansıtır:

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

Yukarıdaki çıktıdaki her satır, son işlev çağrısının adresini, işlev çağrısını içeren modülün tam yol adını ve çağrılan işlev prototipini gösterir. Yığındaki işlev çağrısı işlevin tam adresinde gerçekleşmezse, bayt ların mahsup edilir.

Örneğin, aşağıdaki tabloyukarıdaki çıktının ilk satırını açıklar:

|Çıktı|Açıklama|
|------------|-----------------|
|`00427D55:`|Son işlev çağrısının dönüş adresi.|
|`DUMP2\DEBUG\DUMP2.EXE!`|İşlev çağrısını içeren modülün tam yol adı.|
|`void AfxDumpStack(unsigned long)`|Fonksiyon prototipi denir.|
|`+ 181 bytes`|İşlev prototipinin adresinden (bu durumda) `void AfxDumpStack(unsigned long)`iade adresine (bu durumda) `00427D55`bayt lık mahsup.|

`AfxDumpStack`MFC kitaplıklarının hata ayıklama ve nondebug sürümlerinde kullanılabilir; ancak, yürütülebilir dosyanız paylaşılan bir DLL'de MFC kullansa bile işlev her zaman statik olarak bağlanır. Ortak kitaplık uygulamalarında işlev MFCS42'de bulunur. LIB kitaplığı (ve türevleri).

Bu işlevi başarıyla kullanmak için:

- ImageHLP dosyası. DLL senin yolunda olmalı. Bu DLL yoksa, işlev bir hata iletisi görüntüler. IMAGEHLP tarafından sağlanan işlev kümesi hakkında bilgi için [Resim Yardım Kitaplığı'na](/windows/win32/Debug/image-help-library) bakın.

- Yığında çerçeveleri olan modüller hata ayıklama bilgilerini içermelidir. Hata ayıklama bilgileri içermiyorsa, işlev yine bir yığın izleme oluşturur, ancak izleme daha az ayrıntılı olacaktır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxenablememoryleakdump"></a><a name="afxenablememoryleakdump"></a>AfxEnableMemoryLeakDump

AFX_DEBUG_STATE yıkıcıdaki bellek sızıntısı dökümünün etkin ve devre dışı bırakılmasını sağlar.

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>Parametreler

*bDump*<br/>
[içinde] TRUE, bellek kaçağı dökümünün etkin olduğunu gösterir; FALSE, bellek sızıntısı dökümünün devre dışı bırakıldığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Bu bayrak için önceki değer.

### <a name="remarks"></a>Açıklamalar

Bir uygulama MFC kitaplığını boşalttığında, MFC kitaplığı bellek sızıntılarını denetler. Bu noktada, herhangi bir bellek sızıntısı Visual Studio **Hata Ayıklama** penceresi üzerinden kullanıcıya bildirilir.

Uygulamanız MFC kitaplığından önce başka bir kitaplık yüklerse, bu kitaplıktaki bazı bellek ayırmaları bellek sızıntısı olarak yanlış olarak bildirilir. MFC kitaplığı bunları bildirdiği gibi yanlış bellek sızıntıları uygulamanızın yavaş kapanmasına neden olabilir. Bu durumda, `AfxEnableMemoryLeakDump` bellek sızıntısı dökümünün devre dışı bırakılmasını devre dışı bırak.

> [!NOTE]
> Bellek sızıntısı dökümünün sağlanmasını sağlamak için bu yöntemi kullanırsanız, uygulamanızda geçerli bellek sızıntıları raporları almazsınız. Bu yöntemi yalnızca bellek sızıntısı raporunun yanlış bellek sızıntıları içerdiğinden eminseniz kullanmalısınız.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxenablememorytracking"></a><a name="afxenablememorytracking"></a>AfxEnableMemoryTracking

Tanılama bellek izleme normalde MFC Hata Ayıklama sürümünde etkindir.

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>Parametreler

*bTrack*<br/>
Bu değeri TRUE'ya ayarlama bellek takibinde; FALSE kapatır.

### <a name="return-value"></a>Dönüş Değeri

İzleme etkinleştir bayrağının önceki ayarı.

### <a name="remarks"></a>Açıklamalar

Kodunuzu blokları doğru ayırdığını bildiğiniz bölümlerdeki izlemeyi devre dışı kayırmak için bu işlevi kullanın.

Daha fazla `AfxEnableMemoryTracking`bilgi için, [Hata Ayıklama MFC Uygulamaları'na](/visualstudio/debugger/mfc-debugging-techniques)bakın.

> [!NOTE]
> Bu işlev yalnızca MFC'nin Hata Ayıklama sürümünde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxismemoryblock"></a><a name="afxismemoryblock"></a>AfxIsMemoryBlock

**Yeni**tanılama sürümü tarafından ayrılmış olan şu anda etkin leştirilmiş bir bellek bloğunu temsil ettiğinden emin olmak için bir bellek adresini sınamak için bir bellek adresini sınamak.

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Test edilecek bellek bloğuna işaret eden.

*nBayt*<br/>
Baytlar bellek bloğu uzunluğunu içerir.

*plRequestNumber*<br/>
Bellek bloğunun ayırma sıra numarasıyla doldurulacak **uzun** bir tamsayıya veya şu anda etkin bir bellek bloğunu temsil etmiyorsa sıfıra işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Bellek bloğu şu anda ayrılmışsa ve uzunluk doğruysa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, belirtilen boyutu özgün ayrılan boyuta göre denetler. İşlev sıfırsız dönerse, ayırma sırası numarası *plRequestNumber'ta*döndürülür. Bu sayı, bloğun diğer tüm **yeni** ayırmalara göre tahsis edildiği sırayı temsil eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxisvalidaddress"></a><a name="afxisvalidaddress"></a>AfxIsValidAddress

Programın bellek alanı içinde tamamen içerdiğinden emin olmak için herhangi bir bellek adresini sınar.

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>Parametreler

*Lp*<br/>
Test edilecek bellek adresini işaret edin.

*nBayt*<br/>
Test edilecek bellek baytlarının sayısını içerir.

*bReadWrite*<br/>
Belleğin hem okuma hem de yazma (TRUE) veya sadece okuma (FALSE) olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama oluştururda, belirtilen bellek bloğu tamamen programın bellek alanı içinde bulunursa sıfırolmayan; aksi takdirde 0.

Hata ayıklama yapılarında, *lp* NULL değilse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Adres, **yeni**tarafından ayrılan bloklarla sınırlı değildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxisvalidstring"></a><a name="afxisvalidstring"></a>AfxIsValidString

Dize işaretçisi geçerli olup olmadığını belirlemek için bu işlevi kullanın.

```
BOOL  AfxIsValidString(
    LPCSTR lpsz,
    int nLength = -1);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Test etmek için işaretçi.

*nUzunluk*<br/>
Test edilecek dize uzunluğunu baytlar halinde belirtir. -1 değeri dize geçersiz sonlandırılacak gösterir.

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama oluştururda, belirtilen işaretçi belirtilen boyuttaki bir dize işaret ederse sıfır olmayan; aksi takdirde 0.

Hata ayıklama yapılarında, *lpsz* NULL değilse sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxsetallochook"></a><a name="afxsetallochook"></a>AfxSetAllocHook

Her bellek bloğu ayrılmadan önce belirtilen işlevin çağrılmasını sağlayan bir kanca ayarlar.

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>Parametreler

*pfnAllocHook*<br/>
Adlı adı arayışını belirtir. Bir ayırma işlevinin prototipi için Açıklamalar'a bakın.

### <a name="return-value"></a>Dönüş Değeri

Tahsise izin vermek istiyorsanız sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Microsoft Hazırlık Sınıfı Kitaplığı hata ayıklayıcı bellek ayırıcısı, kullanıcının bir bellek ayırmasını izlemesine ve ayırmaya izin verilip verilmeyeceğini denetlemesine olanak sağlamak için kullanıcı tanımlı bir bağlantı işlevi çağırabilir. Ayırma kancası işlevleri aşağıdaki gibi prototiplenir:

**BOOL AFXAPI AllocHook( size_t** `nSize` **, BOOL** `bObject` **, UZUN** `lRequestNumber` **);**

*nSize*<br/>
Önerilen bellek ayırmanın boyutu.

*bNesne*<br/>
Ayırma türetilmiş bir `CObject`nesne içinse DOĞRU; aksi takdirde YANLIŞ.

*lRequestNumber*<br/>
Bellek ayırmanın sıra numarası.

AFXAPI arama kuralının, callee'nin parametreleri yığından kaldırması gerektiği anlamına geldiğini unutmayın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxdoforallclasses"></a><a name="afxdoforallclasses"></a>AfxDoForAllClasses

Uygulamanın bellek alanındaki tüm serileştirilebilir `CObject`türetilmiş sınıflar için belirtilen yineleme işlevini çağırır.

```cpp
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parametreler

*Pfn*<br/>
Her sınıf için çağrılacak bir yineleme işlevine işaret eder. İşlev bağımsız değişkenleri, `CRuntimeClass` bir nesneye işaretçi ve arayan kişinin işleve sağladığı ek verileri gösteren geçersiz bir işaretçidir.

*Pcontext*<br/>
Arayanın yineleme işlevine sağlayabileceği isteğe bağlı verilere işaret eder. Bu işaretçi NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Serializable `CObject`-türetilmiş sınıflar DECLARE_SERIAL makro kullanılarak türetilen sınıflardır. `AfxDoForAllClasses` *pContext'de* geçirilen işaretçi, her çağrıldığında belirtilen yineleme işlevine geçirilir.

> [!NOTE]
> Bu işlev yalnızca MFC'nin Hata Ayıklama sürümünde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="afxdoforallobjects"></a><a name="afxdoforallobjects"></a>AfxDoForAllObjects

`CObject` **Yeni**ile ayrılan tüm nesneler için belirtilen yineleme işlevini yürütür.

```cpp
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parametreler

*Pfn*<br/>
Her nesne için yürütmek için bir yineleme işlevine işaret eder. İşlev bağımsız değişkenleri, `CObject` arayanın işleve sağladığı ek verilere işaretçi ve geçersiz bir işaretçidir.

*Pcontext*<br/>
Arayanın yineleme işlevine sağlayabileceği isteğe bağlı verilere işaret eder. Bu işaretçi NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Yığın, genel veya katıştırılmış nesneler numaralandırılmaz. `AfxDoForAllObjects` *pContext'de* geçirilen işaretçi, her çağrıldığında belirtilen yineleme işlevine geçirilir.

> [!NOTE]
> Bu işlev yalnızca MFC'nin Hata Ayıklama sürümünde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[CObject::Dump](cobject-class.md#dump)
