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
ms.openlocfilehash: 4e57e0ec175abca5453c6f2ad1c05ab5a53f125e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222855"
---
# <a name="diagnostic-services"></a>Tanı Hizmetleri

Microsoft Foundation Class Kitaplığı, programlarınızda hata ayıklamanın daha kolay olmasını sağlayan birçok tanılama hizmeti sağlar. Bu tanılama Hizmetleri, programınızın bellek ayırmalarını izlemenize, çalışma zamanında nesnelerin içeriğinin dökümünü yapmanıza ve çalışma zamanında hata ayıklama iletilerini yazdırmanıza olanak sağlayan makrolar ve genel işlevler içerir. Tanılama Hizmetleri için makrolar ve genel işlevler aşağıdaki kategorilerde gruplandırılır:

- Genel Tanılama makroları

- Genel Tanılama işlevleri ve değişkenleri

- Nesne Tanılama işlevleri

Bu makrolar ve işlevler, `CObject` MFC 'Nin hata ayıklama ve yayın sürümlerindeki sınıfından türetilmiş tüm sınıflar için kullanılabilir. Ancak, DEBUG_NEW ve doğrulama hariç hepsi yayın sürümünde hiçbir şey yapmaz.

Hata ayıklama kitaplığında, ayrılan tüm bellek blokları "Guard bayt" serisiyle birlikte eklenir. Bu baytlar bir errant belleği yazma tarafından rahatsız edici ise, tanılama yordamları bir sorunu bildirebilir. Satırı eklerseniz:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

Uygulama dosyanızda, ' a yapılan tüm çağrılar, **`new`** bellek ayırmanın gerçekleştiği dosya adını ve satır numarasını depolayacaktır. [CMemoryState::D umpallobjectssince](cmemorystate-structure.md#dumpallobjectssince) işlevi bu ek bilgileri görüntüleyecek ve bellek sızıntılarını tanımlamanızı sağlar. Tanılama çıkışı hakkında daha fazla bilgi için [CDumpContext](../../mfc/reference/cdumpcontext-class.md) sınıfına da bakın.

Ayrıca, C çalışma zamanı kitaplığı, uygulamalarınızda hata ayıklamak için kullanabileceğiniz bir tanılama işlevleri kümesini destekler. Daha fazla bilgi için bkz. çalışma zamanı kitaplık başvurusunda [hata ayıklama yordamları](../../c-runtime-library/debug-routines.md) .

### <a name="mfc-general-diagnostic-macros"></a>MFC genel tanılama makroları

|||
|-|-|
|[VERMEDIĞINI](#assert)|Kitaplığın hata ayıklama sürümünde belirtilen ifade FALSE olarak değerlendirilirse, bir ileti yazdırır ve sonra programı iptal eder.|
|[ASSERT_KINDOF](#assert_kindof)|Bir nesnenin belirtilen sınıftan türetilmiş bir nesne veya belirtilen sınıftan türetilmiş bir sınıf olduğunu sınar.|
|[ASSERT_VALID](#assert_valid)|Bir nesnenin kendi üye işlevini çağırarak iç geçerliliğini sınar `AssertValid` ; genellikle öğesinden geçersiz kılınır `CObject` .|
|[DEBUG_NEW](#debug_new)|Bellek sızıntılarını bulmaya yardımcı olması için hata ayıklama modundaki tüm nesne ayırmaları için bir dosya adı ve satır numarası sağlar.|
|[DEBUG_ONLY](#debug_only)|ONAYLAMA işlemine benzer ancak ifadenin değerini test etmez; yalnızca hata ayıklama modunda yürütülmesi gereken kod için faydalıdır.|
|[EMIN olun ve ENSURE_VALID](#ensure)|Verilerin doğruluğunu doğrulamak için kullanın.|
|[THIS_FILE](#this_file)|Derlenmekte olan dosyanın adına genişletir.|
|[IZLEMESININ](#trace)|`printf`Kitaplığın hata ayıklama sürümünde benzeri yetenek sağlar.|
|[DOĞRU](#verify)|ONAYLAMA işlemine benzer ancak, hata ayıklama sürümünde ve, kitaplığın yayın sürümünde de ifadeyi değerlendirir.|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC genel tanılama değişkenleri ve Işlevleri

|||
|-|-|
|[afxDump](#afxdump)|Hata ayıklayıcı çıkış penceresine veya hata ayıklama terminaline [CDumpContext](../../mfc/reference/cdumpcontext-class.md) bilgilerini gönderen genel değişken.|
|[afxMemDF](#afxmemdf)|Hata ayıklama belleği ayırıcılarının davranışını denetleyen genel değişken.|
|[AfxCheckError](#afxcheckerror)|Bir hata olup olmadığını görmek için geçirilen SCODE 'u test etmek için kullanılan genel değişken, bu durumda uygun hatayı oluşturur.|
|[AfxCheckMemory](#afxcheckmemory)|Ayrılmış olan tüm belleğin bütünlüğünü denetler.|
|[AfxDebugBreak](#afxdebugbreak)|Yürütme sırasında kesintiye neden olur.|
|[AfxDump](#cdumpcontext_in_mfc)|Hata ayıklayıcıda çağrıldığında, hata ayıklama sırasında nesnenin durumunu döker.|
|[AfxDump](#afxdump)|Hata ayıklama sırasında bir nesnenin durumunu dökümünü yapan iç işlev.|
|[AfxDumpStack](#afxdumpstack)|Geçerli yığının bir görüntüsünü oluşturur. Bu işlev her zaman statik olarak bağlanır.|
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|Bellek sızıntısı dökümünü sunar.|
|[Afxenablememoryıtracking](#afxenablememorytracking)|Bellek izlemeyi açar ve kapatır.|
|[Afxısmemoryblock](#afxismemoryblock)|Bir bellek bloğunun düzgün şekilde ayrıldığını doğrular.|
|[Afxısvalidaddress](#afxisvalidaddress)|Bir bellek adres aralığının programın sınırları içinde olduğunu doğrular.|
|[Afxısvalidstring](#afxisvalidstring)|Bir dizeye yönelik işaretçinin geçerli olup olmadığını belirler.|
|[AfxSetAllocHook](#afxsetallochook)|Her bellek ayırmada bir işlevin çağrılmasını mümkün.|

### <a name="mfc-object-diagnostic-functions"></a>MFC nesne tanılama Işlevleri

|||
|-|-|
|[AfxDoForAllClasses](#afxdoforallclasses)|`CObject`Çalışma zamanı tür denetimini destekleyen, tüm türetilmiş sınıflarda belirtilen bir işlevi gerçekleştirir.|
|[Afxdoforallobeler](#afxdoforallobjects)|İle ayrılmış olan tüm türetilmiş nesnelerde belirtilen bir işlevi gerçekleştirir `CObject` **`new`** .|

### <a name="mfc-compilation-macros"></a>MFC derleme makroları

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Kullanım dışı bırakılan MFC işlevlerinin kullanılması için derleyici uyarılarını gizler.|

## <a name="_afx_secure_no_warnings"></a><a name="afx_secure_no_warnings"></a>_AFX_SECURE_NO_WARNINGS

Kullanım dışı bırakılan MFC işlevlerinin kullanılması için derleyici uyarılarını gizler.

### <a name="syntax"></a>Sözdizimi

```
_AFX_SECURE_NO_WARNINGS
```

### <a name="example"></a>Örnek

_AFX_SECURE_NO_WARNINGS tanımlanmamışsa, bu kod örneği bir derleyici uyarısına neden olur.

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

`AfxDebugBreak`MFC uygulamanızın hata ayıklama sürümünün yürütülmesi sırasında bir kesme (çağrının konumunda) sağlamak için bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AfxDebugBreak( );
```

### <a name="remarks"></a>Açıklamalar

`AfxDebugBreak`MFC uygulamasının yayın sürümlerinde hiçbir etkiye sahip değildir ve kaldırılmalıdır. Bu işlev yalnızca MFC uygulamalarında kullanılmalıdır. `DebugBreak`MFC olmayan uygulamalarda kesme sağlamak için Win32 API sürümünü kullanın.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxver_. h

## <a name="assert"></a><a name="assert"></a>VERMEDIĞINI

Bağımsız değişkenini değerlendirir.

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sıfır dışında veya 0 olarak değerlendirilen bir ifadeyi (işaretçi değerleri dahil) belirtir.

### <a name="remarks"></a>Açıklamalar

Sonuç 0 ise, makro bir tanılama iletisi yazdırır ve programı iptal eder. Koşul sıfır değilse, hiçbir şey yapmaz.

Tanılama iletisi şu formdadır:

`assertion failed in file <name> in line <num>`

Burada *ad* kaynak dosyanın adıdır ve *num* , kaynak dosyada başarısız olan onaylama işlemi satır numarasıdır.

MFC 'nin yayın sürümünde, onaylama ifadeyi değerlendirmez ve bu nedenle programı kesintiye uğramaz. İfade, ortamdan bağımsız olarak değerlendirilmelidir, onay yerine makroyu Doğrula ' yı kullanın.

> [!NOTE]
> Bu işlev yalnızca MFC 'nin hata ayıklama sürümünde kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="assert_kindof"></a><a name="assert_kindof"></a>ASSERT_KINDOF

Bu makro, işaret edilen nesnenin belirtilen sınıftan bir nesne olduğunu veya belirtilen sınıftan türetilmiş bir sınıfın nesnesi olduğunu onaylar.

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>Parametreler

*sınıf*<br/>
`CObject`Türetilmiş sınıfın adı.

*nesnesini*<br/>
Sınıf nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*Nesnesini* parametresi bir nesne işaretçisi olmalıdır ve olabilir **`const`** . İşaret edilen nesne ve sınıf, `CObject` çalışma zamanı sınıf bilgilerini desteklemelidir. Örnek olarak, `pDocument` sınıfın bir nesnesinin bir işaretçisi veya türevlerinden herhangi birinin bir işaretçisi olduğundan emin olmak için şu `CMyDoc` kodu kullanabilirsiniz:

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

Makro kullanımı, `ASSERT_KINDOF` kodlama ile tamamen aynıdır:

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

Bu işlev yalnızca [DECLARE_DYNAMIC] (Run-Time-Object-Model-Services. MD # declare_dynamic veya [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makrosu ile belirtilen sınıflar için çalışır.

> [!NOTE]
> Bu işlev yalnızca MFC 'nin hata ayıklama sürümünde kullanılabilir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="assert_valid"></a><a name="assert_valid"></a>ASSERT_VALID

Bir nesnenin iç durumunun geçerliliği hakkında varsayımlarınızı test etmek için kullanın.

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>Parametreler

*Nesnesini*<br/>
Öğesinden türetilmiş `CObject` , üye işlevin geçersiz kılan bir sürümüne sahip bir sınıfının nesnesini belirtir `AssertValid` .

### <a name="remarks"></a>Açıklamalar

ASSERT_VALID `AssertValid` bağımsız değişkeni olarak geçirilen nesnenin üye işlevini çağırır.

MFC 'nin yayın sürümünde ASSERT_VALID hiçbir şey yapmaz. Hata ayıklama sürümünde, işaretçiyi doğrular, NULL olarak denetler ve nesnenin kendi `AssertValid` üye işlevlerini çağırır. Bu testlerin herhangi biri başarısız olursa, [onaylama](#assert)ile aynı şekilde bir uyarı iletisi görüntülenir.

> [!NOTE]
> Bu işlev yalnızca MFC 'nin hata ayıklama sürümünde kullanılabilir.

Daha fazla bilgi ve örnek için bkz. [MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="debug_new"></a><a name="debug_new"></a>DEBUG_NEW

Bellek sızıntılarını bulmaya yardımcı olur.

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>Açıklamalar

Programınızdaki her yerde DEBUG_NEW kullanarak, genellikle **`new`** yığın depolama alanı ayırmak için işlecini kullanırsınız.

Hata ayıklama modunda ( **_DEBUG** sembol tanımlandığında) DEBUG_NEW, ayrılan her nesne için dosya adını ve satır numarasını izler. Ardından, [CMemoryState::D umpallobjectssince](cmemorystate-structure.md#dumpallobjectssince) üye işlevini kullandığınızda, DEBUG_NEW ile ayrılan her nesne, ayrıldığı dosya adı ve satır numarası ile gösterilir.

DEBUG_NEW kullanmak için aşağıdaki yönergeyi kaynak dosyalarınıza ekleyin:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

Bu yönergeyi ekledikten sonra Önişlemci, kullandığınız her yerde DEBUG_NEW ekler **`new`** ve MFC Rest 'i yapar. Programınızın bir yayın sürümünü derlerken DEBUG_NEW basit bir **`new`** işleme çözümlenir ve dosya adı ve satır numarası bilgileri oluşturulmaz.

> [!NOTE]
> MFC 'nin önceki sürümlerinde (4,1 ve önceki sürümlerde), `#define` deyimi IMPLEMENT_DYNCREATE veya IMPLEMENT_SERIAL makroları çağıran tüm deyimlerden sonra yerleştirmeniz gerekir. Bu artık gerekli değildir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="debug_only"></a><a name="debug_only"></a>DEBUG_ONLY

Hata ayıklama modunda ( **_DEBUG** sembol tanımlandığında), debug_only bağımsız değişkenini değerlendirir.

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>Açıklamalar

Bir yayın derlemesinde, DEBUG_ONLY bağımsız değişkenini değerlendirmez. Bu, yalnızca hata ayıklama yapılarında yürütülmesi gereken bir kodunuz olduğunda yararlıdır.

DEBUG_ONLY makrosu, ve ile çevreleyen *ifadeye* eşdeğerdir `#ifdef _DEBUG` `#endif` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

### <a name="ensure-and-ensure_valid"></a><a name="ensure"></a>EMIN olun ve ENSURE_VALID

Verilerin doğruluğunu doğrulamak için kullanın.

### <a name="syntax"></a>Söz dizimi

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sınanacak Boole ifadesini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makroların amacı parametrelerin doğrulanmasını geliştirmaktır. Makrolar, kodunuzda yanlış parametrelerin daha fazla işlenmesini önler. ONAYLAMA makrolarının aksine, makroların bir onaylama oluşturmaya ek olarak bir özel durum oluşturması gerekir.

Makrolar, proje yapılandırmasına göre iki şekilde davranır. Makrolar ONAYı çağırır ve onaylama başarısız olursa bir özel durum oluşturur. Bu nedenle, hata ayıklama yapılandırmalarında (yani _DEBUG tanımlanmıştır) makrolar yayın yapılandırmalarında bir onaylama ve özel durum üretir, makrolar yalnızca özel durumu oluşturur (onay, ifadeyi sürüm yapılandırmalarında değerlendirmez).

Makro ENSURE_ARG, makrosuz gibi davranır.

ENSURE_VALID, ASSERT_VALID makrosunu çağırır (yalnızca hata ayıklama yapılarında bir etkiye sahiptir). Ayrıca, işaretçi NULL ise ENSURE_VALID bir özel durum oluşturur. NULL test her iki hata ayıklama ve yayın yapılandırmasında gerçekleştirilir.

Bu testlerin herhangi biri başarısız olursa, onaylama ile aynı şekilde bir uyarı iletisi görüntülenir. Makro gerekirse geçersiz bir bağımsız değişken özel durumu oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="this_file"></a><a name="this_file"></a>THIS_FILE

Derlenmekte olan dosyanın adına genişletir.

### <a name="syntax"></a>Sözdizimi

```
THIS_FILE
```

### <a name="remarks"></a>Açıklamalar

Bilgiler onaylama ve makroları doğrulama tarafından kullanılır. Uygulama Sihirbazı ve kod sihirbazları, makroyu oluşturdukları kaynak kodu dosyalarına yerleştirir.

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

**Üstbilgi:** AFX. h

## <a name="trace"></a><a name="trace"></a>IZLEMESININ

Belirtilen dizeyi geçerli uygulamanın hata ayıklayıcısına gönderir.

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>Açıklamalar

Izleme açıklaması için bkz. [ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) . TRACE ve ATLTRACE2 aynı davranışa sahiptir.

MFC 'nin hata ayıklama sürümünde, bu makro belirtilen dizeyi geçerli uygulamanın hata ayıklayıcısına gönderir. Bir yayın derlemesinde, bu makro Nothing olarak derlenir (hiçbir kod üretilmez).

Daha fazla bilgi için bkz. [MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="verify"></a><a name="verify"></a>DOĞRU

MFC 'nin hata ayıklama sürümünde, bağımsız değişkenini değerlendirir.

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sıfır dışında veya 0 olarak değerlendirilen bir ifadeyi (işaretçi değerleri dahil) belirtir.

### <a name="remarks"></a>Açıklamalar

Sonuç 0 ise, makro bir tanılama iletisi yazdırır ve programı durdurur. Koşul sıfır değilse, hiçbir şey yapmaz.

Tanılama iletisi şu formdadır:

`assertion failed in file <name> in line <num>`

Burada *ad* kaynak dosyanın adıdır ve *num* kaynak dosyada başarısız olan onaylama işlemi satır numarasıdır.

MFC 'nin yayın sürümünde, ifadeyi değerlendirir, ancak programı yazdırmaz veya kesintiye uğratmaz. Örneğin, ifade bir işlev çağrısiyse, çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxdump-cdumpcontext-in-mfc"></a><a name="cdumpcontext_in_mfc"></a>afxDump (MFC 'de CDumpContext)

Uygulamanızda temel nesne dökümü özelliği sağlar.

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>Açıklamalar

`afxDump`, hata ayıklayıcı çıkış penceresine veya hata ayıklama terminaline bilgi göndermenizi sağlayan önceden tanımlanmış bir [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesidir `CDumpContext` . Genellikle, `afxDump` için bir parametre olarak sağlarsınız `CObject::Dump` .

Windows NT ve tüm Windows sürümleri `afxDump` için çıkış, uygulamanızda hata ayıkladığınızda Visual C++ çıktı-hata ayıklama penceresine gönderilir.

Bu değişken yalnızca MFC 'nin hata ayıklama sürümünde tanımlanmıştır. Hakkında daha fazla bilgi için `afxDump` bkz. [MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxdump-internal"></a><a name="afxdump"></a>AfxDump (Iç)

Hata ayıklama sırasında MFC 'nin bir nesne durumunun dökümünü almak için kullandığı iç işlev.

### <a name="syntax"></a>Söz dizimi

```cpp
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*pOb*<br/>
Sınıfından türetilmiş bir sınıfın nesnesine yönelik bir işaretçi `CObject` .

### <a name="remarks"></a>Açıklamalar

`AfxDump`bir nesnenin `Dump` üye işlevini çağırır ve bilgileri değişken tarafından belirtilen konuma gönderir `afxDump` . `AfxDump`yalnızca MFC 'nin hata ayıklama sürümünde kullanılabilir.

Program kodunuz çağırmamalıdır `AfxDump` , ancak bunun yerine `Dump` uygun nesnenin üye işlevini çağırmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxmemdf"></a><a name="afxmemdf"></a>afxMemDF

Bu değişkene bir hata ayıklayıcı veya programdan erişilebilir ve ayırma tanılamayı ayarlamanıza olanak sağlar.

```
int  afxMemDF;
```

### <a name="remarks"></a>Açıklamalar

`afxMemDF`, sabit listesi tarafından belirtilen aşağıdaki değerlere sahip olabilir `afxMemDF` :

- `allocMemDF`Hata ayıklama ayırıcısını etkinleştirir (hata ayıklama kitaplığındaki varsayılan ayar).

- `delayFreeMemDF`Belleği boşaltma gecikmeleri. Programınız bir bellek bloğunu serbest bırakırken, ayırıcı bu belleği temel işletim sistemine döndürmez. Bu işlem, programınıza maksimum bellek stres yerleştirir.

- `checkAlwaysMemDF``AfxCheckMemory`Bellek her ayrıldığında veya serbest bırakılmış her seferinde çağırır. Bu, bellek ayırmalarını ve ayırmayı önemli ölçüde yavaşlatır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxcheckerror"></a><a name="afxcheckerror"></a>AfxCheckError

Bu işlev, bir hata olup olmadığını görmek için geçirilen SCODE 'u sınar.

```cpp
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>Açıklamalar

Bir hata ise, işlev bir özel durum oluşturur. Geçirilen SCODE E_OUTOFMEMORY, işlev [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)çağırarak bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oluşturur. Aksi takdirde, işlev [AfxThrowOleException](exception-processing.md#afxthrowoleexception)çağırarak bir [copaexception](../../mfc/reference/coleexception-class.md) oluşturur.

Bu işlev, uygulamanızdaki OLE işlevlerine yapılan çağrıların dönüş değerlerini denetlemek için kullanılabilir. Dönüş değerini uygulamanızdaki Bu işlevle test ederek, en az miktarda kodla hata koşullarına doğru şekilde tepki verebilirsiniz.

> [!NOTE]
> Bu işlev hata ayıklama ve hata ayıklama olmayan derlemelerde aynı etkiye sahiptir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxcheckmemory"></a><a name="afxcheckmemory"></a>AfxCheckMemory

Bu işlev, boş bellek havuzunu doğrular ve hata iletilerini gerektiği gibi yazdırır.

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek hatası yoksa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlev bir bellek bozulması algılarsa, hiçbir şey yazdıramayabilir.

Yığında ayrılmış olan tüm bellek blokları, tarafından ayrılan, **`new`** ancak **malloc** işlevi veya Windows işlevi gibi temeldeki bellek ayırıcılarına doğrudan çağrılar tarafından ayrılanlar dahil olmak üzere denetlenir `GlobalAlloc` . Herhangi bir bloğun bozulmuş olduğu bulunursa, hata ayıklayıcı çıktısına bir ileti yazdırılır.

Satırı eklerseniz

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

bir program modülünde, daha sonra `AfxCheckMemory` belleğin ayrıldığı dosya adını ve satır numarasını göstermek için çağırır.

> [!NOTE]
> Modülünüzün bir veya daha fazla serileştirilebilir sınıf uygulaması varsa, `#define` satırı son IMPLEMENT_SERIAL makro çağrısından sonra koymanız gerekir.

Bu işlev yalnızca MFC 'nin hata ayıklama sürümünde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxdump-mfc"></a><a name="afxdump"></a>AfxDump (MFC)

Hata ayıklama sırasında bir nesnenin durumunun dökümünü almak için hata ayıklayıcı sırasında bu işlevi çağırın.

```cpp
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*pOb*<br/>
Sınıfından türetilmiş bir sınıfın nesnesine yönelik bir işaretçi `CObject` .

### <a name="remarks"></a>Açıklamalar

`AfxDump`bir nesnenin `Dump` üye işlevini çağırır ve bilgileri değişken tarafından belirtilen konuma gönderir `afxDump` . `AfxDump`yalnızca MFC 'nin hata ayıklama sürümünde kullanılabilir.

Program kodunuz çağırmamalıdır `AfxDump` , ancak bunun yerine `Dump` uygun nesnenin üye işlevini çağırmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxdumpstack"></a><a name="afxdumpstack"></a>AfxDumpStack

Bu genel işlev, geçerli yığının bir görüntüsünü oluşturmak için kullanılabilir.

```cpp
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>Parametreler

*dwTarget*<br/>
Döküm çıkışının hedefini gösterir. Bit düzeyinde OR ( **&#124;**) işleci kullanılarak birleştirilebilen olası değerler şunlardır:

- AFX_STACK_DUMP_TARGET_TRACE, [Trace](#trace) makrosu yoluyla çıkış gönderir. TRACE makrosu yalnızca hata ayıklama yapılarında çıktı oluşturur; Yayın yapılarında çıkış oluşturmaz. Ayrıca, Izleme hata ayıklayıcının yanı sıra diğer hedeflere yönlendirilebilir.

- AFX_STACK_DUMP_TARGET_DEFAULT, varsayılan hedefe döküm çıkışı gönderir. Hata ayıklama derlemesi için, çıkış Izleme makrosuna gider. Yayın derlemesinde çıkış panoya gider.

- AFX_STACK_DUMP_TARGET_CLIPBOARD çıktı yalnızca panoya gönderilir. Veriler panoya CF_TEXT Pano biçimi kullanılarak düz metin olarak yerleştirilir.

- AFX_STACK_DUMP_TARGET_BOTH, çıktıyı Pano 'ya ve Izleme makrosunu aynı anda gönderir.

- AFX_STACK_DUMP_TARGET_ODS, Win32 işlevi aracılığıyla hata ayıklayıcıya doğrudan çıktı gönderir `OutputDebugString()` . Bu seçenek, işleme bir hata ayıklayıcı eklendiğinde hata ayıklama ve sürüm yapılarında hata ayıklayıcı çıkışı oluşturur. AFX_STACK_DUMP_TARGET_ODS her zaman hata ayıklayıcıya ulaşır (iliştirilmişse) ve yeniden yönlendirilemez.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek, bir `AfxDumpStack` MFC iletişim uygulamasındaki düğme işleyicisinden çağrılmadan oluşturulan çıkışın tek bir satırını yansıtır:

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

Yukarıdaki çıktıda bulunan her satır, son işlev çağrısının adresini, işlev çağrısını içeren modülün tam yol adını ve çağrılan işlev prototipini belirtir. Yığında işlev çağrısı, işlevin tam adresinde gerçekleşmezse, bayt bir konum gösterilir.

Örneğin, aşağıdaki tabloda yukarıdaki çıktının ilk satırı açıklanmaktadır:

|Çıktı|Açıklama|
|------------|-----------------|
|`00427D55:`|Son işlev çağrısının dönüş adresi.|
|`DUMP2\DEBUG\DUMP2.EXE!`|İşlev çağrısını içeren modülün tam yol adı.|
|`void AfxDumpStack(unsigned long)`|İşlev prototipi çağrıldı.|
|`+ 181 bytes`|İşlev prototipinin adresinden (Bu durumda, `void AfxDumpStack(unsigned long)` ) dönüş adresine (Bu durumda) bayt cinsinden bir konum `00427D55` .|

`AfxDumpStack`MFC kitaplıklarının hata ayıklama ve hata ayıklama sürümlerinde kullanılabilir; Ancak, çalıştırılabilir dosyanız MFC 'yi paylaşılan bir DLL 'de kullandığında bile işlev her zaman statik olarak bağlanır. Paylaşılan kitaplık uygulamalarında, işlevi MFCS42 içinde bulunur. LIB kitaplığı (ve türevleri).

Bu işlevi başarıyla kullanmak için:

- Dosya IMAGEHLP.DLL yolunuzda olmalıdır. Bu DLL 'ye sahip değilseniz, işlev bir hata mesajı görüntüler. IMAGEHLP tarafından sağlanan işlev kümesi hakkında bilgi için bkz. [görüntü Yardım Kitaplığı](/windows/win32/Debug/image-help-library) .

- Yığındaki çerçevelere sahip modüller hata ayıklama bilgilerini içermelidir. Hata ayıklama bilgileri içermiyorsa, işlev yine de bir yığın izlemesi oluşturacaktır, ancak izleme daha az ayrıntılı olacaktır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxenablememoryleakdump"></a><a name="afxenablememoryleakdump"></a>AfxEnableMemoryLeakDump

AFX_DEBUG_STATE yıkıcısında bellek sızıntısı dökümünü etkinleştirilir ve devre dışı bırakır.

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>Parametreler

*bDump*<br/>
'ndaki DOĞRU, bellek sızıntısı dökümünü etkin olduğunu belirtir; FALSE, bellek sızıntısı dökümünü devre dışı olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Bu bayrak için önceki değer.

### <a name="remarks"></a>Açıklamalar

Bir uygulama MFC kitaplığını kaldırdığında, MFC kitaplığı bellek sızıntılarını denetler. Bu noktada, Visual Studio 'nun **hata ayıklama** penceresi aracılığıyla kullanıcıya herhangi bir bellek sızıntıları bildirilir.

Uygulamanız MFC kitaplığından önce başka bir kitaplık yüklerse, bu kitaplıktaki bazı bellek ayırmaları hatalı olarak bellek sızıntısı olarak bildirilir. Hatalı bellek sızıntıları, MFC kitaplığı tarafından rapor olduğundan, uygulamanızın yavaş kapanmasına neden olabilir. Bu durumda, `AfxEnableMemoryLeakDump` bellek sızıntısı dökümünü devre dışı bırakmak için kullanın.

> [!NOTE]
> Bellek sızıntısı dökümünü devre dışı bırakmak için bu yöntemi kullanırsanız, uygulamanızda geçerli bellek sızıntılarını rapor almazsınız. Bu yöntemi yalnızca bellek sızıntısı raporunun yanlış bellek sızıntılarını içerdiğinden emin olmanız durumunda kullanmanız gerekir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxenablememorytracking"></a><a name="afxenablememorytracking"></a>Afxenablememoryıtracking

Tanılama belleği izleme, normalde MFC 'nin hata ayıklama sürümünde etkinleştirilir.

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>Parametreler

*bTrack*<br/>
Bu değerin TRUE olarak ayarlanması bellek izlemeyi açar; FALSE, devre dışı bırakır.

### <a name="return-value"></a>Dönüş Değeri

İzleme-etkinleştirme bayrağının önceki ayarı.

### <a name="remarks"></a>Açıklamalar

Hangi bloklarında doğru şekilde ayırdığınıza bildiğiniz kodunuzun bölümlerinde izlemeyi devre dışı bırakmak için bu işlevi kullanın.

Hakkında daha fazla bilgi için `AfxEnableMemoryTracking` bkz. [MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
> Bu işlev yalnızca MFC 'nin hata ayıklama sürümünde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxismemoryblock"></a><a name="afxismemoryblock"></a>Afxısmemoryblock

' Nin tanılama sürümü tarafından ayrılan etkin bir bellek bloğunu temsil ettiğinden emin olmak için bir bellek adresini sınar **`new`** .

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Sınanacak bellek bloğunu işaret eder.

*nBytes*<br/>
Bayt cinsinden bellek bloğunun uzunluğunu içerir.

*plRequestNumber*<br/>
**`long`** Bellek bloğunun ayırma sıra numarasıyla doldurulacak bir tamsayıya işaret eder veya şu anda etkin olan bir bellek bloğunu temsil ediyorsa sıfır olur.

### <a name="return-value"></a>Dönüş Değeri

Bellek bloğu Şu anda ayrıldıysanız ve uzunluk doğruysa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, belirtilen boyutu özgün ayrılan boyuta göre denetler. İşlev sıfır dışında bir değer döndürürse, ayırma sıra numarası *plRequestNumber*içinde döndürülür. Bu sayı, bloğun diğer tüm ayırmalara göre ayrıldığı sırayı temsil eder **`new`** .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxisvalidaddress"></a><a name="afxisvalidaddress"></a>Afxısvalidaddress

Tamamen programın bellek alanında bulunduğundan emin olmak için herhangi bir bellek adresini sınar.

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>Parametreler

*'nin*<br/>
Sınanacak bellek adresine işaret eder.

*nBytes*<br/>
Sınanacak belleğin bayt sayısını içerir.

*Enine yazma*<br/>
Belleğin hem okuma hem de yazma (TRUE) veya yalnızca okuma (FALSE) için olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, belirtilen bellek bloğu tamamen programın bellek alanı içinde içerilse, sıfır dışında; Aksi takdirde 0.

Hata ayıklama olmayan derlemelerde, *LP* null değilse sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Adres tarafından ayrılan bloklarla sınırlı değildir **`new`** .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxisvalidstring"></a><a name="afxisvalidstring"></a>Afxısvalidstring

Bir dizeye yönelik işaretçinin geçerli olup olmadığını anlamak için bu işlevi kullanın.

```
BOOL  AfxIsValidString(
    LPCSTR lpsz,
    int nLength = -1);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Sınanacak işaretçi.

*nLength*<br/>
Sınanacak dizenin uzunluğunu bayt cinsinden belirtir. -1 değeri, dizenin null olarak sonlandırıldığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, belirtilen işaretçi belirtilen boyuttaki bir dizeye işaret ediyorsa sıfır dışında; Aksi takdirde 0.

Hata ayıklama olmayan derlemelerde, *lpsz* null değilse sıfır değil; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxsetallochook"></a><a name="afxsetallochook"></a>AfxSetAllocHook

Her bellek bloğu ayrılmadan önce belirtilen işlevin çağrılmasını sağlayan bir kanca ayarlar.

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>Parametreler

*pfnAllocHook*<br/>
Çağrılacak işlevin adını belirtir. Bir ayırma işlevinin prototipine ilişkin açıklamalara bakın.

### <a name="return-value"></a>Dönüş Değeri

Ayırmaya izin vermek istiyorsanız sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı hata ayıklama-bellek ayırıcısı, kullanıcının bir bellek ayırmayı izlemesine ve ayırmaya izin verilip verilmeyeceğini denetlemesine izin vermek için Kullanıcı tanımlı bir kanca işlevi çağırabilir. Ayırma kanca işlevleri prototipsiz aşağıdaki gibidir:

**Bool AFXAPI allocHook (size_t** `nSize` **, bool** `bObject` **, Long** `lRequestNumber` **);**

*nSize*<br/>
Önerilen bellek ayırmasının boyutu.

*bObject*<br/>
Ayırma, `CObject` türetilmiş bir nesne IÇINSE true; Aksi takdirde false.

*lRequestNumber*<br/>
Bellek ayırmasının sıra numarası.

AFXAPı çağırma kuralının, çağrılan parametrelerin yığından kaldırılması gerektiğini belirtir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxdoforallclasses"></a><a name="afxdoforallclasses"></a>AfxDoForAllClasses

Uygulamanın bellek alanındaki tüm seri hale getirilebilir türetilmiş sınıflar için belirtilen yineleme işlevini çağırır `CObject` .

```cpp
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parametreler

*PFN*<br/>
Her sınıf için çağrılacak yineleme işlevine işaret eder. İşlev bağımsız değişkenleri, `CRuntimeClass` çağıran işlevin işlevine sağladığı ek verilere yönelik bir işaretçi ve void işaretçisi.

*pContext*<br/>
Çağıran tarafından yineleme işlevine sağlayabileceğinizden isteğe bağlı verileri gösterir. Bu işaretçi NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Seri hale getirilebilir `CObject` türetilmiş sınıflar, DECLARE_SERIAL makrosu kullanılarak türetilmiş sınıflardır. `AfxDoForAllClasses` *PContext* içinde öğesine geçirilen işaretçi, her çağrıldığında belirtilen yineleme işlevine geçirilir.

> [!NOTE]
> Bu işlev yalnızca MFC 'nin hata ayıklama sürümünde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="afxdoforallobjects"></a><a name="afxdoforallobjects"></a>Afxdoforallobeler

, İle ayrılmış olan öğesinden türetilmiş tüm nesneler için belirtilen yineleme işlevini yürütür `CObject` **`new`** .

```cpp
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parametreler

*PFN*<br/>
Her nesne için yürütülecek yineleme işlevine işaret eder. İşlev bağımsız değişkenleri, `CObject` çağıranın işlevine sağladığı ek verilere ve void işaretçisine bir işaretçisidir.

*pContext*<br/>
Çağıran tarafından yineleme işlevine sağlayabileceğinizden isteğe bağlı verileri gösterir. Bu işaretçi NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Yığın, genel veya katıştırılmış nesneler numaralandırılmadı. `AfxDoForAllObjects` *PContext* içinde öğesine geçirilen işaretçi, her çağrıldığında belirtilen yineleme işlevine geçirilir.

> [!NOTE]
> Bu işlev yalnızca MFC 'nin hata ayıklama sürümünde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[CObject::D UMP](cobject-class.md#dump)
