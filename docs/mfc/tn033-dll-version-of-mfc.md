---
title: "TN033: MFC'nin DLL sürümü | Microsoft Docs"
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dll
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23b92b0bf8c71a9038a8c8b2b77bfac8feac8822
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417754"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC'nin DLL Sürümü

Bu Not MFCxx.DLL kullanabilirsiniz ve (burada x MFC sürüm numarasıdır) paylaşılan dinamik bağlantı kitaplıkları paylaşılan MFC uygulamaları ve MFC uzantısı DLL'leri ile nasıl açıklanmaktadır. Normal MFC DLL'leri hakkında daha fazla bilgi için bkz: [bir DLL'in bir parçası olarak MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md).

Bu teknik Not DLL'leri üç yönlerini kapsar. Daha gelişmiş kullanıcılar için son iki şunlardır:

- [MFC uzantısı DLL nasıl oluşturacağınız](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC'nin DLL sürümü kullanan bir MFC uygulamasını nasıl oluşturacağınız](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC dinamik bağlantı kitaplıklarını nasıl paylaşılacağını uygulanır](#_mfcnotes_how_the_mfc30.dll_is_implemented)

Bir DLL ile MFC olmayan uygulamalar (Bu çağrılır Normal MFC DLL'SİNİN) kullanılabilir MFC kullanarak oluşturmak istiyorsanız, bakın [Teknik Not 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md).

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL desteğine genel bakış: terminoloji ve dosyaları

**Normal MFC DLL'SİNİN**: bazı MFC sınıflarını kullanarak tek başına bir DLL yapılandırmak için Normal MFC DLL'SİNİN kullanın. Arabirimleri arasında uygulama/DLL sınır "C" arabirimdir ve istemci uygulama bir MFC uygulaması yok.

DLL desteği MFC 1.0 desteklenen sürümüdür. İçinde açıklanan [Teknik Not 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) ve MFC Gelişmiş kavramlar örneği [ile ilgili](../visual-cpp-samples.md).

> [!NOTE]
> Visual C++ sürüm 4.0 itibariyle terimi **USRDLL** kullanımdan kalkmıştır ve statik olarak MFC'ye bağlanan normal bir MFC DLL ile değiştirilmiştir. Ayrıca, bir normal dinamik olarak MFC'ye bağlanan MFC DLL da oluşturabilirsiniz.

MFC 3.0 (ve üstü) Normal MFC DLL'leri OLE ve veritabanı sınıfları da dahil olmak üzere tüm yeni işlevlerle destekler.

**AFXDLL**: Bu aynı zamanda paylaşılan MFC kitaplıklarını sürümü adlandırılır. MFC 2.0 sürümünde yeni DLL desteği budur. DLL'ler (aşağıda açıklanmıştır) çeşitli MFC kitaplığı olan ve bir istemci uygulaması veya DLL gerekli DLL'lerin dinamik olarak bağlar. Uygulama/DLL sınırı arasında arabirimdir C + +/ MFC sınıfı arabirimleri. İstemci uygulaması, bir MFC uygulaması olmalıdır. Bu, tüm MFC 3.0 işlevselliği destekler (özel durum: UNICODE veritabanı sınıfları için desteklenmez).

> [!NOTE]
> Visual C++ sürüm 4.0 itibariyle bu tür bir DLL "Uzantı olarak DLL." başvuruda bulunulur

Bu Not, MFCxx.DLL, içeren MFC DLL ayarlanırsa, tüm başvurmak için kullanacağınız:

- Hata ayıklama: paylaşılan (toplam) ve MFCSxxD.LIB (statik).

- Sürüm: (toplam) MFCxx.DLL ve MFCSxx.LIB (statik).

- Unicode hata ayıklama: MFCxxUD.DLL (toplam) ve MFCSxxD.LIB (statik).

- Unicode sürüm: (toplam) MFCxxU.DLL ve MFCSxxU.LIB (statik).

> [!NOTE]
> MFCSxx [U] [D]. LIB kitaplıkları kullanıldığı MFC ile birlikte paylaşılan DLL'er. Bu kitaplıklar için uygulama veya DLL statik olarak bağlanmalıdır kodunu içerir.

Karşılık gelen bir uygulama bağlantı kitaplıklarını içeri aktarın:

- Hata ayıklama: MFCxxD.LIB

- Yayın: MFCxx.LIB

- Unicode hata ayıklama: MFCxxUD.LIB

- Unicode sürümü: MFCxxU.LIB

Bir "MFC uzantısı DLL" MFCxx.DLL üzerinde derlenmiş bir DLL'dir (ve/veya diğer MFC DLL'leri paylaşılan). MFC bileşeni mimarisi burada devreye girer. Kitaplığından bir MFC sınıfı yararlı bir sınıf türetmek veya başka bir MFC benzeri araç setini oluşturun, bir DLL içinde yerleştirebilirsiniz. DLL olarak MFCxx.DLL, kullanan ultimate istemci uygulamasını desteklemez. Bu, yeniden kullanılabilir yaprak sınıfları, yeniden kullanılabilir temel sınıflar ve yeniden kullanılabilir görünüm/belge sınıfları sağlar.

## <a name="pros-and-cons"></a>Avantajları ve dezavantajları

MFC'nin paylaşılan sürümünden neden kullanmalısınız

- Paylaşılan bir kitaplık kullanan, daha küçük uygulamalar (küçüktür 10 bin çoğu MFC kitaplığını kullanan en az bir uygulama olduğu) neden olabilir.

- MFC uzantı DLL'leri ve Normal MFC DLL'leri MFC'nin paylaşılan sürümünden destekler.

- Paylaşılan MFC kitaplıkları kullanan bir uygulama oluşturmak, MFC'nin kendisine bağlamak gerekli olduğundan, statik olarak bağlı bir MFC uygulaması oluşturma daha hızlıdır. Bu durum, özellikle de **hata ayıklama** derlemeler burada bağlayıcı gerekir compact hata ayıklama bilgileri — zaten hata ayıklama bilgilerini içeren bir DLL'ye, uygulamanızın içinde sıkıştırmak için daha az hata ayıklama bilgileri yoktur.

Neden MFC'nin paylaşılan sürümünden kullanmamanız gerekir:

- Paylaşılan kitaplığı kullanan bir uygulamayı sevkiyat gerektirir MFCxx.DLL (ve diğerleri) sevk programınızla kitaplığı. MFCxx.DLL gibi birçok DLL'leri ücretsiz olarak yeniden dağıtılabilir, ancak DLL hala Kurulum programınıza yüklemeniz gerekir. Ayrıca, programınız ve MFC DLL'lerinin kendilerinin kullanılan C çalışma zamanı kitaplığı içeren MSVCRTxx.DLL hazırlamalısınız.

##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> Bir MFC uzantılı DLL yazma

MFC uzantısı DLL, sınıfları ve işlevleri MFC sınıflarını işlevselliğini süslemek için yazılan içeren bir DLL'dir. MFC uzantısı DLL paylaşılan MFC DLL ile bazı ek hususlar, bir uygulamanın kullandığı aynı şekilde kullanır:

- Derleme işlemi, bazı ek derleyici ve bağlayıcı seçenekleri ile paylaşılan MFC kitaplıkları kullanan bir uygulama oluşturmak için benzer.

- MFC uzantısı DLL olmayan bir `CWinApp`-türetilmiş sınıf.

- MFC uzantısı DLL, özel bir sağlamalısınız `DllMain`. AppWizard sağlayan bir `DllMain` değiştirebileceğiniz işlevi.

- MFC uzantısı DLL, genellikle oluşturmak için bir başlatma yordamı sağlayacak bir `CDynLinkLibrary` MFC uzantısı DLL dışarı aktarma isterse `CRuntimeClass`es veya kaynakları uygulama. Türetilmiş bir sınıf, `CDynLinkLibrary` uygulama başına veri MFC uzantısı DLL tutulması gereken varsa kullanılabilir.

Bu noktalar aşağıda daha ayrıntılı olarak açıklanmıştır. MFC Gelişmiş kavramlar örneği için ayrıca başvurmanız gerekir [DLLHUSK](../visual-cpp-samples.md) olduğundan bunu göstermektedir:

- Paylaşılan kitaplıklar kullanarak uygulama oluşturma. (DLLHUSK. EXE için MFC kitaplıkları sair DLL'lerin dinamik olarak bağlanan bir MFC uygulamasıdır.)

- Bir MFC uzantılı DLL oluşturma. (Not gibi özel bayrakları `_AFXEXT` bir MFC uzantılı DLL oluşturulmasında kullanılan)

- MFC uzantı DLL'leri iki örnekleri. Bir MFC uzantısı DLL ile sınırlı dışarı aktarmalar (TESTDLL1) ve bir sınıfın tamamı arabirim (TESTDLL2) dışarı aktarma diğer programları temel yapısını göstermektedir.

Hem istemci uygulaması hem de bir MFC uzantısı DLL'leri MFCxx.DLL aynı sürümünü kullanmanız gerekir. MFC DLL kuralı izleyin ve her iki bir hata ayıklama sağlamak ve perakende (/ release) MFC uzantısı DLL sürümü. Bu, istemci programları uygulamalarını hem hata ayıklama hem de perakende sürümlerini oluşturup bunları uygun hata ayıklama veya perakende sürümünü tüm DLL'ler ile bağlantı verir.

> [!NOTE]
>  C++ bozma adlandırın ve dışarı aktarma sorunlarını olduğundan, bir MFC uzantılı DLL dışarı aktarma listeden farklı platformlar için aynı DLL'nin hata ayıklama ve perakende sürümleri ve DLL'ler farklı olabilir. Perakende MFCxx.DLL yaklaşık 2000 giriş noktaları dışarı; hata ayıklama paylaşılan yaklaşık 3000 giriş noktaları dışarı.

### <a name="quick-note-on-memory-management"></a>Bellek yönetimi hızlı notu

Bu teknik Not sonuna yakın alan "bellek yönetimi" başlıklı bölüme MFC'nin paylaşılan sürümünden MFCxx.DLL uygulamasıyla açıklar. Yalnızca DLL burada açıklanan bir MFC uzantılı uygulamak için bilmeniz gereken bilgileri.

Aynı uygulamada değilmiş gibi MFCxx.DLL ve bir istemci uygulamanın adres alanına yüklenen tüm MFC uzantısı DLL'leri aynı bellek ayırıcısı, kaynak yükleme ve diğer MFC "Genel" durumlarını kullanır. MFC olmayan DLL kitaplıkları ve statik olarak MFC'ye bağlanan normal MFC DLL'leri tam tersi yapın ve her DLL, kendi bellek havuzunda yetersiz ayırma sahip olduğundan bu önemlidir.

Ardından bir MFC uzantılı DLL bellek ayırırsa, bellek diğer uygulama ayrılan nesneleri intermix serbestçe. Ayrıca, paylaşılan MFC kitaplıkları kullanan bir uygulama çökerse, işletim sisteminin koruma DLL paylaşımı başka bir MFC Uygulama bütünlüğünü korur.

Benzer şekilde, kaynakları yüklemek için geçerli yürütülebilir dosya gibi diğer "Genel" MFC durumları da istemci uygulaması ve tüm MFC uzantısı DLL'leri yanı sıra arasında MFCxx.DLL kendisini paylaşılır.

### <a name="building-an-mfc-extension-dll"></a>Bir MFC uzantılı DLL oluşturma

AppWizard bir MFC uzantısı DLL projesi oluşturmak için kullanabileceğiniz ve uygun derleyici ve bağlayıcı ayarları otomatik olarak oluşturur. Ayrıca olduğu bir `DllMain` değiştirebileceğiniz işlevi.

Projesinde varolan bir MFC uzantılı DLL dönüştürüyorsanız MFC'nin paylaşılan sürümünden kullanarak uygulama oluşturmaya yönelik standart kuralları ile başlayın, ardından aşağıdakileri yapın:

- Ekleme **/D_AFXEXT** derleyici bayraklarına. Proje Özellikleri iletişim kutusunda C/C++ düğümünü seçin. Ardından önişlemci kategorisini seçin. Ekleme `_AFXEXT` makroları tanımlama alanın öğelerin her biri noktalı virgül.

- Kaldırma **/Gy** derleyici anahtarı. Proje Özellikleri iletişim kutusunda C/C++ düğümünü seçin. Ardından kod oluşturma kategorisini seçin. "İşlev düzeyi bağlamayı etkinleştir" seçeneği etkinleştirilmediğinden emin olun. Bu bağlayıcı, başvurulmayan işlevleri kaldırmayacaktır çünkü sınıflarını dışarı aktarmak kolaylaştırır. Özgün proje normal oluşturmak için kullanılıyorsa, MFC DLL değişiklik MFC'ye statik olarak bağlanan **[d] / MT** derleyici seçeneği **/MD [d]**.

- Bir dışarı aktarma kitaplığı ile derleme **/dll** bağlantı seçeneği. Win32 dinamik bağlantı kitaplığı hedef türü olarak belirterek yeni bir hedef oluşturduğunuzda bu ayarlanır.

### <a name="changing-your-header-files"></a>Üst bilgi dosyalarınız değiştirme

Bir MFC uzantılı DLL amacı genellikle bu işlevi kullanabilmeniz için bir veya daha fazla uygulama için bazı ortak işlevselliği dışa aktarılmamasıdır. Sınıflar ve istemci uygulamalarınız için kullanılabilen genel işlevleri dışa bu boils.

Bunu yapmak için üye işlevlerin her biri içeri veya dışarı aktarma olarak uygun olarak işaretlenmiş Sigortası gerekir. Bu özel bildirimleri gerektirir: `__declspec(dllexport)` ve `__declspec(dllimport)`. Sınıfları istemci uygulamaları tarafından kullanıldığında bildirilmesini istediğiniz `__declspec(dllimport)`. MFC uzantısı DLL kendisini oluşturulmuştur, bunlar olarak bildirilmelidir `__declspec(dllexport)`. Yükleme zamanında istemci programları bağlayabilir, ayrıca, İşlevler aslında, dışarı aktarılmalıdır.

Sınıfın tamamı dışa aktarmak için kullanın `AFX_EXT_CLASS` sınıf tanımında. Bu makro framework tarafından tanımlanan `__declspec(dllexport)` olduğunda `_AFXDLL` ve `_AFXEXT` tanımlı, ancak olarak tanımlanan `__declspec(dllimport)` olduğunda `_AFXEXT` tanımlı değil. `_AFXEXT` MFC uzantısı DLL oluşturma sırasında yalnızca yukarıda açıklanan şekilde tanımlanır. Örneğin:

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>Sınıfın tamamı dışa aktarma değil

Bazen sınıfınıza yalnızca tek gerekli üyeleri vermek isteyebilirsiniz. Dışa aktarıyorsanız, örneğin, bir `CDialog`-türetilmiş sınıf, yalnızca Oluşturucu dışarı aktarmak gerekebilir ve `DoModal` çağırın. DLL'nin kullanarak bu üyelerin dışarı aktarabilirsiniz. DEF dosyası, ancak kullanabileceğiniz `AFX_EXT_CLASS` çok dışarı aktarmak için gereken tek tek üyelerin aynı şekilde.

Örneğin:

```cpp
class CExampleDialog : public CDialog
{
public:
    AFX_EXT_CLASS CExampleDialog();
    AFX_EXT_CLASS int DoModal();
    // rest of class definition
    // ...
};
```

Bunu yaptığınızda, sınıfın tüm üyeleri artık dışarı aktardığınız aktarmadığınızdan ek bir sorunla karşılaşabilirsiniz. Sorun, MFC makroları çalışma biçiminde olmasıdır. Birkaç MFC'nin yardımcı makroları gerçekten bildirmek veya veri üyeleri tanımlar. Bu nedenle, bu veri üyeleri, ayrıca, DLL'den dışarı aktarılmasına izin gerekir.

Örneğin, bir MFC uzantılı DLL oluşturma sırasında DECLARE_DYNAMIC makrosu şu şekilde tanımlanır:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \

```

Başlayan satırı "statik `AFX_DATA`" Sınıfınız içinde statik nesne bildirme. Bu sınıfı doğru olarak dışarı aktarın ve çalışma zamanı bilgileri, bir istemciden erişmek için. EXE, bu statik nesne dışarı aktarmanız gerekmez. Statik nesne değiştiriciyle bildirildiğinden `AFX_DATA`, tanımlamak yeterlidir `AFX_DATA` olmasını `__declspec(dllexport)` DLL dosyanızı oluştururken ve olarak tanımlayın `__declspec(dllimport)` istemcinizi yürütülebilir oluştururken.

Yukarıda açıklandığı gibi `AFX_EXT_CLASS` zaten bu şekilde tanımlanır. Yeniden tanımlamak yeterlidir `AFX_DATA` aynı olacak şekilde `AFX_EXT_CLASS` sınıf tanımına geçici bir çözüm.

Örneğin:

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS
class CExampleView : public CView
{
    DECLARE_DYNAMIC()
    // ... class definition ...
};
#undef  AFX_DATA
#define AFX_DATA
```

Her zaman bir MFC kullanmadığı `AFX_DATA` sembol veri öğelerinde gibi senaryolar için bu tekniği çalışacak şekilde kendi makrosunda tanımlar. Örneğin, DECLARE_MESSAGE_MAP çalışır.

> [!NOTE]
> Seçilen üyeleri sınıf yerine sınıfın tamamı dışa aktarıyorsanız, otomatik olarak statik veri üyeleri dışa aktarılır.

Otomatik olarak dışarı aktarmak için aynı tekniği kullanabilirsiniz `CArchive` declare_serıal ve ımplement_serıal makroları sınıflar için ayıklama işleci. Arşiv işleci, sınıf bildirimleri köşeli ayraç kullanarak dışarı aktarma (bulunur. H dosyası) aşağıdaki kod ile:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-afxext"></a>_AFXEXT Sınırlamaları

_ Kullanabilirsiniz**AFXEXT** MFC uzantısı DLL'leri çözümsüz MFC uzantısı DLL'leri olmayan sürece ön işlemci simgesi. MFC uzantı DLL'leri çağrı yapma veya kendi MFC uzantısı DLL'leri sonra MFC sınıflarından türetilen, sınıflar türetilen varsa belirsizlik önlemek için kendi önişlemci sembolü kullanmanız gerekir.

Sorunu söz konusu Win32, tüm veriler olarak açıkça belirtmesi gerekir `__declspec(dllexport)` bir DLL'den dışarı aktarılmasına izin olup olmadığını ve `__declspec(dllimport)` DLL'den içeri aktarılacak ise. Tanımladığınızda `_AFXEXT`, MFC üstbilgi emin `AFX_EXT_CLASS` doğru şekilde tanımlanır.

Olduğunda, birden fazla katman, bir simge gibi `AFX_EXT_CLASS` bir MFC uzantılı DLL yeni sınıfları dışarı aktarma hem de bu yana diğer sınıfları, başka bir MFC uzantı DLL'SİNDEN içeri aktarma yeterli değildir. Bu sorunları gidermek için DLL kullanan ve DLL kendisi oluşturduğunuzu gösteren özel bir önişlemci sembolü kullanın. Örneğin, iki MFC uzantısı DLL'leri ve A.DLL B.DLL düşünün. Her bazı sınıflar A.H ve B.H'taki sırasıyla verin. B.DLL a.DLL'den sınıfları kullanır. Üst bilgi dosyaları, şunun gibi görünür:

```cpp
/* A.H */
#ifdef A_IMPL
    #define CLASS_DECL_A   __declspec(dllexport)
#else
    #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ /* ... class definition ... */ };

/* B.H */
#ifdef B_IMPL
    #define CLASS_DECL_B   __declspec(dllexport)
#else
    #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ /* ... class definition ... */ };
```

A.dll oluşturulduğunda ile oluşturulmuştur **/DA_IMPL** ve B.DLL oluşturulduğunda ile oluşturulmuştur **/DB_IMPL**. Her DLL için ayrı bir sembol kullanarak CExampleB aktarılır ve CExampleA b.dll oluşturulduğunda alınır. CExampleA a.dll oluşturulurken dışarı ve B.DLL (veya başka bir istemci) kullanıldığında içeri aktarılır.

Bu tür katmanlama yerleşik kullanılırken gerçekleştirilemez `AFX_EXT_CLASS` ve `_AFXEXT` önişlemci sembolleri. Yukarıda açıklanan tekniği MFC'nin OLE, veritabanı ve ağ MFC uzantısı DLL'leri oluştururken kullandığı bir şekilde benzemeyen bu sorunu çözer.

### <a name="not-exporting-the-entire-class"></a>Sınıfın tamamı dışa aktarma değil

Bir sınıfın tamamı dışa aktarma değil, özel dikkatli gerekecektir. MFC makroları tarafından oluşturulan gerekli veri öğelerinin doğru bir şekilde dışarı aktarıldığından emin olmanız gerekir. Bu yeniden tanımlayarak yapılabilir `AFX_DATA` , belirli sınıf makro. Bu sınıfın tamamı dışa aktarma değil istediğiniz zaman yapılmalıdır.

Örneğin:

```cpp
// A.H
#ifdef A_IMPL
    #define CLASS_DECL_A  _declspec(dllexport)
#else
    #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
    DECLARE_DYNAMIC()
    CLASS_DECL_A int SomeFunction();
    // class definition
    // ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="dllmain"></a>DllMain

MFC uzantısı DLL için ana kaynak dosyanızı yerleştirmeniz gerekir tam kodu verilmiştir. Standartı sonra gelmelidir. AppWizard bir MFC uzantılı DLL için başlangıç dosyaları oluşturmak için kullandığınızda, bu kaynakları not bir `DllMain` sizin için.

```cpp
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      // MFC extension DLL one-time initialization
      if (!AfxInitExtensionModule(
             extensionDLL, hInstance))
         return 0;

      // TODO: perform other initialization tasks here
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      // MFC extension DLL per-process termination
      AfxTermExtensionModule(extensionDLL);

      // TODO: perform other cleanup tasks here
   }
   return 1;   // ok
}
```

Çağrı `AfxInitExtensionModule` modülü çalışma zamanı sınıfları yakalar (`CRuntimeClass` yapıları), nesne fabrikaları yanı sıra (`COleObjectFactory` nesneleri) kullanmak için sonraki olduğunda `CDynLinkLibrary` nesnesi oluşturulur. (İsteğe bağlı) çağrısı `AfxTermExtensionModule` her işlem ayırdığında MFC temizlemek için MFC uzantısı DLL izin verir. (işlem çıktığında veya DLL sonucu olarak kaldırıldığında gerçekleşir bir `FreeLibrary` çağrısı) MFC uzantı DLL. Çoğu MFC uzantısı DLL'leri dinamik olarak yüklenmediği beri (genellikle kullanıcılar, içeri aktarma kitaplıkları bağlı), çağrı `AfxTermExtensionModule` genellikle gerekli değildir.

Uygulamanızı yükler ve MFC uzantısı DLL'leri dinamik olarak boşaltır, çağırdığınızdan emin olun `AfxTermExtensionModule` yukarıda da gösterildiği gibi. Ayrıca kullandığınızdan emin olun `AfxLoadLibrary` ve `AfxFreeLibrary` (Win32 işlevlerini yerine `LoadLibrary` ve `FreeLibrary`) uygulamanız birden çok iş parçacığı kullanıyorsa veya dinamik olarak bir MFC uzantılı DLL yükler. Kullanarak `AfxLoadLibrary` ve `AfxFreeLibrary` MFC uzantısı DLL yüklendiğinde ve kaldırıldığında, yürütülen başlatma ve kapatma kod genel MFC durum bozuk değil oluşturmasını sağlar.

Üst bilgi dosyası AFXDLLX. H tanımı gibi MFC uzantısı DLL'leri içinde kullanılan yapılar için özel tanımları içerir `AFX_EXTENSION_MODULE` ve `CDynLinkLibrary`.

Genel *extensionDLL* gösterildiği şekilde bildirilmesi gerekir. MFC 16-bit sürümü, bellek ve MFCxx.DLL tam olarak başlatılmış olduğundan bu süre boyunca, çağrı MFC işlevleri, `DllMain` çağrılır.

### <a name="sharing-resources-and-classes"></a>Kaynakları ve sınıfları paylaşma

Basit MFC uzantısı DLL'leri yalnızca birkaç düşük bant genişliğine sahip işlevler istemci uygulaması ve hiçbir şey için daha fazla dışa aktarmanız gerekir. Daha fazla kullanıcı arabirimi yoğun DLL'leri, kaynakları ve C++ sınıfları istemci uygulamaya vermek isteyebilirsiniz.

Kaynakları dışarı aktarma, bir kaynak listesi üzerinden gerçekleştirilir. Her iki uygulamada tek bağlı listesidir `CDynLinkLibrary` nesneleri. Bir kaynak ararken kaynakları yükleme standart MFC uygulamalarının çoğunu geçerli kaynak modülüne bakın (`AfxGetResourceHandle`) ve Yürüme bulunamadı listesini `CDynLinkLibrary` nesneleri istenen kaynak yüklenmeye çalışılıyor.

Dinamik bir C++ sınıf adı verilen C++ nesnelerinin oluşturulması benzerdir. MFC nesne seri durumundan çıkarma mekanizması tüm olması gerekiyorsa `CRuntimeClass` nesneleri kayıtlı ne daha önce depolanan üzerinde bağlı olarak gerekli tür C++ nesne oluşturarak dinamik olarak yeniden oluşturabilir.

İstemci uygulaması olan sınıflar, MFC uzantısı DLL içinde kullanmak isterseniz `DECLARE_SERIAL`, sonra istemci uygulamasına görünür olmasını sınıfları dışarı aktarmanız gerekecektir. Bu yürüyen tarafından yapılır `CDynLinkLibrary` listesi.

MFC Gelişmiş kavramlar örneği söz konusu olduğunda [DLLHUSK](../visual-cpp-samples.md), liste şöyle görünür:

```Example
head ->   DLLHUSK.EXE   - or - DLLHUSK.EXE
               |                    |
          TESTDLL2.DLL         TESTDLL2.DLL
               |                    |
          TESTDLL1.DLL         TESTDLL1.DLL
               |                    |
               |                    |
           MFC90D.DLL           MFC90.DLL
```

Kaynak ve sınıf listesi genellikle son MFCxx.DLL. MFCxx.DLL tüm standart komut kimlikleri için komut istemi dizeleri dahil olmak üzere tüm standart MFC kaynakları içerir. Listenin kuyruğunu yerleştirme sağlar DLL'ler ve sahip değil istemci uygulamanın kendisi bir paylaşılan kaynaklar MFCxx.dll yerine dayanan şekilde ancak standart MFC kaynakları, kendilerine ait kopyasında.

Kaynaklar ve sınıf adları tüm DLL'leri, istemci uygulamanın adı alanına birleştirme, hangi kimlikleri dikkatli olmak zorunda olumsuz veya adları vardır. Tabii bu özellik ya da vererek olmayan kaynaklarınızı devre dışı bırakabilirsiniz veya `CDynLinkLibrary` istemci uygulamasına nesne. [DLLHUSK](../visual-cpp-samples.md) örnek paylaşılan kaynak ad alanı birden çok üstbilgi dosyasını kullanarak yönetir. Bkz: [Teknik Not 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) paylaşılan kaynak dosyalarını kullanma hakkında daha fazla ipucu için.

### <a name="initializing-the-dll"></a>DLL başlatma

Yukarıda belirtildiği gibi genellikle oluşturmak isteyeceksiniz bir `CDynLinkLibrary` istemci uygulaması için kaynak ve sınıflarını dışarı aktarmak için nesne. DLL başlatmak için dışarı aktarılan giriş noktası sağlamanız gerekir. En düşük düzeyde, bu, hiçbir bağımsız değişkeni alır ve hiçbir şey döndürür, void bir yordamdır, ancak istediğiniz herhangi bir şey olabilir.

DLL dosyanızı kullanmak istiyorsa her istemci uygulaması, bu yaklaşımı kullanırsanız bu başlatma yordamı çağırmanız gerekir. Bu ayrıca ayırabileceği `CDynLinkLibrary` nesnesine, `DllMain` çağırma hemen ardına `AfxInitExtensionModule`.

Başlatma yordamı oluşturmalısınız bir `CDynLinkLibrary` MFC uzantısı DLL bilgi kadar kablolu, geçerli uygulamanın yığın nesnesi. Bu aşağıdaki ile yapılabilir:

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

Rutin adı *InitXxxDLL* Bu örnekte, istediğiniz herhangi bir şey olabilir. Olması gerekmez **extern "C"**, ancak bunu yapar dışarı aktarma listesine korumak daha kolay yapmak.

> [!NOTE]
> Normal MFC DLL, MFC uzantı DLL kullanırsanız, bu başlatma işlevi dışarı aktarmanız gerekir. Bu işlev, herhangi bir MFC uzantısı DLL sınıfların veya kaynakları kullanmadan önce de Normal MFC DLL çağrılmalıdır.

### <a name="exporting-entries"></a>Girdileri dışarı aktarma

Sınıfları dışarı aktarmak için basit bir yolla kullanmaktır `__declspec(dllimport)` ve `__declspec(dllexport)` her bir sınıf ve dışarı aktarmak istediğiniz genel işlev. Bu, çok daha kolaylaştırır, ancak hangi işlevleri dışa daha az denetime sahip olursunuz ve sıralı olarak işlevleri dışarı aktaramazsınız beri (aşağıda açıklanmıştır) her bir giriş noktası adlandırma daha az verimlidir. TESTDLL1 ve TESTDLL2 bunların girişlerini dışarı aktarmak için bu yöntemi kullanın.

Daha verimli bir yöntem (ve MFCxx.DLL tarafından kullanılan yöntem) her giriş adlandırarak her giriş el ile dışa aktarılmamasıdır. DEF dosyası. Seçmeli dışarı aktarmalar sayfamızı DLL'den (diğer bir deyişle, her şey) verdiğiniz olduğundan, biz dışarı aktarmak için istediğimiz hangi belirli arabirimleri karar vermeniz gerekir. Bağlayıcı karıştırılmış adlar girişleri biçiminde belirtmeniz gerekir bu yana bu zordur. DEF dosyası. Sembolik bağlantı sağlamak gerçekten gerekli olmadıkça herhangi bir C++ sınıfları vermeyin.

Bunu denediyseniz C++ dışarı aktarma ile sınıfları bir. DEF dosyası bu listeye otomatik olarak oluşturmak için bir araç geliştirmek istiyorsanız önce. Bu yapılabilir iki aşamalı bağlama işlemini kullanma. DLL kez hiçbir dışarı aktarma ile bağlantısını ve bağlayıcı oluşturmak izin bir. Harita dosyası. . EŞLEME dosyası, bazı yeniden düzenleme ile bu dışarı aktarma girişlerinizi oluşturmak için kullanılacak şekilde verilmeli, İşlevler listesi oluşturmak için kullanılabilir. DEF dosyası. (Tamamen otomatik değildir ve her bir kez bir süredir ayarlama bazı el gerektirir ancak) dışarı aktarma listesine MFCxx.DLL ve OLE ve veritabanı MFC uzantısı DLL'leri, birkaç bin sayısı, bu tür bir işlem ile oluşturuldu.

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp vs. CDynLinkLibrary

MFC uzantısı DLL olmayan bir `CWinApp`-türetilmiş bir nesneye kendi; bunun yerine birlikte çalışmalıdır `CWinApp`-türetilmiş bir nesneye istemci uygulaması. Bu, istemci uygulama ana ileti pompası, boşta döngü vb. sahibi olduğu anlamına gelir.

MFC uzantısı DLL dosyanızı her uygulama için ek verileri tutması gerekiyorsa, yeni bir sınıf türetebilirsiniz `CDynLinkLibrary` ve yordamı açıklar yukarıda InitXxxDLL oluşturun. DLL çalıştırırken, geçerli uygulama listesini denetleyebilirsiniz `CDynLinkLibrary` o belirli MFC uzantısı DLL bulmak için nesneleri.

### <a name="using-resources-in-your-dll-implementation"></a>Kaynakları DLL uygulamanızda kullanma

Yukarıda belirtildiği gibi varsayılan kaynak yükü listesini yükselteceğinizi `CDynLinkLibrary` nesneleri ilk EXE veya DLL istenen kaynağa sahip olabilirsiniz. Tüm MFC API'lerine ek olarak tüm iç kod `AfxFindResourceHandle` burada bulunabilir ne olursa olsun tüm kaynak bulmak için kaynak listesini görmek için.

Yalnızca belirli bir konumdan kaynakları yüklemek istiyorsanız, API'leri kullanan `AfxGetResourceHandle` ve `AfxSetResourceHandle` eski tutamacı kaydedin ve yeni işleyici ayarlayın. İstemci uygulamaya döndüren önce eski kaynağı tanıtıcısı geri emin olun. Örnek TESTDLL2 menü açıkça yüklemek için bu yaklaşımı kullanır.

Listenin anlatarak biraz daha yavaş olması ve kaynak kimliği aralıklarını yönetmeyi gerektirir dezavantajları vardır. Bu, birkaç MFC uzantısı DLL'leri bağlanan istemci uygulaması herhangi bir DLL tarafından sağlanan kaynak DLL örneğinin tutamacını belirtmenize gerek kalmadan kullanabilirsiniz avantajına sahiptir. `AfxFindResourceHandle` bir API için belirli bir eşleşme aramak için kaynak listesinden walking için kullanılır. Bir kaynak türünü ve adını alır ve ilk bulunduğu kaynak tutamacının (veya NULL) döndürür.

##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> DLL sürümü kullanan bir uygulama yazma

### <a name="application-requirements"></a>Uygulama gereksinimleri

MFC'nin paylaşılan sürümünden kullanan bir uygulamayı birkaç basit kurallara uymalıdır:

- Olmalıdır bir `CWinApp` nesnesi ve standart bir ileti pompası kurallarını izleyin.

- Bir dizi gerekli derleyici bayraklarına (aşağıya bakın) ile derlenmelidir.

- Bu, MFCxx içeri aktarma kitaplıkları ile bağlanmanız gerekir. MFC üstbilgi gerekli derleyici bayraklarına ayarlayarak, uygulamanın bağlanması gereken hangi kitaplığı bağlantı zamanında belirleyin.

- Yürütülebilir dosyayı çalıştırmak için MFCxx.DLL yolu veya Windows Sistem dizini olmalıdır.

### <a name="building-with-the-development-environment"></a>Geliştirme ortamı oluşturma

Standart Varsayılanları en iç derleme görevleri dosyası kullanıyorsanız, DLL sürümünü oluşturmak için proje kolaylıkla değiştirebilirsiniz.

Aşağıdaki adım NAFXCWD ile bağlı olarak doğru şekilde çalıştığını bir MFC uygulaması olduğunu varsayar. LIB (için hata ayıklama) ve NAFXCW. LIB (Perakende için) ve paylaşılan MFC kitaplık sürümünü kullanacak şekilde dönüştürmek istiyorsanız. Visual C++ ortamında çalışan ve bir iç proje dosyası.

1. Üzerinde **projeleri** menüsünde tıklatın **özellikleri**. İçinde **genel** altındaki **Proje Varsayılanları**, Microsoft Foundation sınıfları Ayarla **MFC'yi bir ortak DLL'de** (MFCxx(d).dll).

### <a name="building-with-nmake"></a>NMAKE ile oluşturma

Visual C++'ın dış derleme görevleri dosyası özelliğini kullanarak ya da NMAKE doğrudan kullanıyorsanız, derleyici ve bağlayıcı seçenekleri desteklemek için derleme görevleri dosyası Düzenle gerekir

Derleyici bayraklarına gerekli:

- **/ D_AFXDLL /MD**
   **/D_AFXDLL**

Standart MFC üstbilgileri bu simge tanımlanması gerekir:

- **/ MD** uygulama C çalışma zamanı kitaplığının DLL sürümü kullanmanız gerekir

MFC varsayılan değerleri (örneğin, hata ayıklama için _DEBUG) diğer tüm derleyici bayraklarına izleyin.

Kitaplıkların bağlayıcı listesini düzenleyin. NAFXCWD değiştirin. İçin MFCxxD.LIB LIB ve NAFXCW değiştirin. LIB MFCxx.LIB için. LIBC değiştirin. İle MSVCRT LIB. LIB. Diğer MFC kitaplığı ile MFCxxD.LIB yerleştirilir önemli olduğu gibi **önce** tüm C çalışma zamanı kitaplıkları.

İsteğe bağlı olarak ekleyin **/D_AFXDLL** hem tekil hem de hata ayıklama kaynak derleyici seçenekleri (kaynaklarla derleyen bir **/R**). Bu son yürütülebilir dosyanızın MFC DLL'leri mevcut olan kaynakları paylaşarak küçültür.

Bu değişiklikler yapıldıktan sonra tam yeniden derleme gereklidir.

### <a name="building-the-samples"></a>Örnekleri derleme

MFC örnek programların çoğu, Visual C++ ya da komut satırından paylaşılan uyumlu NMAKE derleme görevleri oluşturulabilir.

MFCxx.DLL kullanılacak Bu örnek hiçbirini dönüştürmek için yükleyebilirsiniz. MAK, Visual C++'ta dosya ve proje seçeneklerinde yukarıda açıklanan şekilde ayarlayın. NMAKE derleme kullanıyorsanız, belirtebilmeniz için "AFXDLL = 1" üzerinde NMAKE komut satırı ve, paylaşılan MFC kitaplıklarını kullanarak örneği oluşturmak.

MFC Gelişmiş kavramlar örneği [DLLHUSK](../visual-cpp-samples.md) MFC'nin DLL sürümü ile oluşturulmuştur. Bu örnek yalnızca ile MFCxx.DLL bağlı bir uygulamanın nasıl oluşturulacağını gösterir, ancak aynı zamanda bir MFC DLL paketleme seçeneğinin MFC uzantı DLL'leri daha sonra bu Teknik Not açıklandığı gibi diğer özellikleri gösterilmektedir.

### <a name="packaging-notes"></a>Paketleme notları

Perakende sürümü ' % s'dll (MFCxx [U]. DLL) ücretsiz olarak yeniden dağıtılabilir. DLL'lerin hata ayıklama sürümünü ücretsiz olarak yeniden dağıtılabilir değildir ve yalnızca uygulamanızın geliştirilmesi sırasında kullanılmalıdır.

DLL'lerin hata ayıklama, hata ayıklama bilgileri ile sağlanır. Visual C++ hata ayıklayıcı kullanarak DLL'yi yanı sıra, uygulamanızın yürütülmesini izleyebilirsiniz. Yayın DLL'leri (MFCxx [U]. DLL) hata ayıklama bilgisi içermez.

Özelleştirme veya DLL'leri yeniden derleyin, ardından bunları bir şey MFCDLL MFC src = "MFCxx" dosya dışındaki çağırmalısınız. MAK, derleme seçenekleri açıklar ve DLL yeniden adlandırma mantığı içerir. Bu DLL'leri potansiyel olarak birçok MFC uygulamaları tarafından paylaşılan yeniden adlandırmayı gerekli olduğu. MFC DLL'leri Değiştir özel sürümünüz sahip olanlar için sistemde yüklü paylaşılan MFC DLL'leri kullanmanın başka bir MFC uygulaması kesilebilir.

MFC DLL'leri yeniden önerilmez.

##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> MFCxx.DLL nasıl uygulanır

Aşağıdaki bölümde, MFC DLL (MFCxx.DLL ve paylaşılan) nasıl uygulandığı açıklanmaktadır. Ayrıntıları buraya de olmayan anlamak, tüm yapmak istiyorsanız MFC DLL uygulamanızda kullandığınız önemlidir. Ayrıntıları Buraya bir MFC uzantılı DLL yazma anlamak için gerekli değildir, ancak bu uygulama anlama kendi DLL yazmanıza yardımcı.

### <a name="implementation-overview"></a>Uygulama genel bakış

MFC DLL gerçekten özel bir MFC uzantısı DLL, yukarıda açıklanan şekilde bir durumdur. Dışarı aktarımlar çok sayıda sınıfları için çok büyük bir sayı var. Normal MFC uzantısı DLL daha özel kılan MFC DLL'yi yaptığımız bazı ek noktalar vardır.

### <a name="win32-does-most-of-the-work"></a>Win32 işin çoğunu yapar.

MFC 16-bit sürümü, çeşitli uygulama başına veri yığını segmentine bazı 80 x 86 bütünleştirilmiş kodu, işlem başına özel durum bağlamı ve diğer teknikleri tarafından oluşturulan özel parçaları dahil olmak üzere özel teknikler gerekli. Win32 doğrudan işlem içi verilerin bir DLL içinde çoğu zaman, istediğiniz olduğu destekler. Çoğunlukla MFCxx.DLL yalnızca NAFXCW ' dir. Bir DLL içinde paketlenmiş LIB. MFC kaynak koda göz atmak, yapılması gereken özel durumlar çok az sayıda olduğundan çok az sayıda #ifdef _AFXDLL bulabilirsiniz. Vardır özellikle Win32 Windows 3.1 (Win32 da bilinir) üzerinde çalışılabilecek olan özel durumlar. MFC DLL iş parçacığı yerel deposu (TLS) işlem yerel verileri almak için Win32 API'ları kullanmanız gerekir böylece doğrudan Win32 değil destek işlem içi DLL verileri desteklemez.

### <a name="impact-on-library-sources-additional-files"></a>Kitaplık kaynaklarını ek dosyalar üzerindeki etki

Etkisini **_AFXDLL** normal MFC sınıf kitaplığı kaynakları ve üstbilgi sürümü, görece küçük. Özel sürüm dosyası (AFXV_DLL. H) yanı sıra bir ek üst bilgi dosyası (AFXDLL_. H) tarafından ana AFXWIN dahil. H üstbilgisi. AFXDLL_. H üst bilgisi `CDynLinkLibrary` sınıfı ve hem de diğer uygulama ayrıntılarını `_AFXDLL` uygulamaları ve MFC uzantısı DLL'leri. AFXDLLX. MFC uzantı DLL'leri (Ayrıntılar için yukarıya bakın) oluşturmak için H üst bilgisi sağlanır.

Bazı ek koşullu kod altında Normal MFC src MFC kitaplık kaynaklarına sahip `_AFXDLL` #ifdef. Bir ek kaynak dosyası (DLLINIT. Ek DLL başlatma kodunu ve MFC'nin paylaşılan sürümünden için diğer Birleştirici CPP) içerir.

MFC'nin paylaşılan sürümünden oluşturmak için ek dosyaları sağlanır. (Aşağıda DLL oluşturma hakkında ayrıntılar için bkz.)

- İki. DEF dosyaları, hata ayıklama (MFCxxD.DEF) için MFC DLL giriş noktalarını dışarı aktarmak için kullanılır ve DLL sürümlerini (MFCxx.DEF) bırakın.

- Bir. RC dosyası (MFCDLL. RC), DLL için tüm standart MFC kaynakları ve VERSIONINFO kaynak içerir.

- A. CLW dosyası (MFCDLL. MFC göz atma izni ClassWizard kullanarak sınıfları CLW) sağlanır. Not: Bu özellik belirli MFC'nin DLL sürümü değil.

### <a name="memory-management"></a>Bellek Yönetimi

MFCxx.DLL kullanarak uygulama paylaşılan C çalışma zamanı DLL MSVCRTxx.DLL tarafından sağlanan genel bellek ayırıcı kullanır. Uygulama, herhangi bir MFC uzantısı DLL'leri ve MFC DLL'lerinin kendilerinin yanı, bu paylaşılan bellek ayırıcısı kullanın. MFC DLL'leri paylaşılan DLL için bellek ayırmayı kullanarak daha sonra uygulama tarafından veya serbest bellek ayırabilirsiniz. Hem uygulama hem de DLL aynı ayırıcı kullanması gerektiğinden, genel C++'ı geçersiz kılmalıdır değil **new işleci** veya **delete işleci**. C çalışma zamanı bellek ayırma yordamlarını geri kalanı için aynı kuralları uygula (gibi **malloc**, **realloc**, **ücretsiz**ve diğerleri).

### <a name="ordinals-and-class-declspecdllexport-and-dll-naming"></a>Sıra sayıları ve sınıf __declspec(dllexport) ve DLL adlandırma

Biz kullanmayın `class` **__declspec(dllexport)** işlevselliğini C++ derleyicisi. Bunun yerine, sınıf kitaplık kaynakları (MFCxx.DEF ve MFCxxD.DEF) ile bir listesini dışarı aktarma dahildir. Yalnızca bu grup giriş noktaları (İşlevler ve veriler) izin verilir. MFC özel uygulama işlevler veya sınıflar gibi diğer simgeler verilmeyen tüm dışarı sıralı olmayan bir dize adı yerleşik veya yerleşik olmayan adı tablosundaki tarafından gerçekleştirilir.

Kullanarak `class` **__declspec(dllexport)** MFC, dışa aktarma mekanizması varsayılan gibi büyük bir DLL söz konusu olduğunda ancak daha küçük DLL'leri oluşturmak için uygun bir alternatif, verimlilik ve kapasite sahip olabilir sınırlar.

Tüm Bunun anlamı nedir işlevselliği, yalnızca kadar yürütme ödün veya yükleme hızını olmadan yaklaşık 800 KB MFCxx.DLL sürümde, büyük bir miktarını paketleyebilirsiniz. MFCxx.DLL olabilirdi 100 bin cinsinden daha büyük bu tekniği karşılanmadığını kullanılır. Bu ayrıca, sonunda ek giriş noktaları eklemek mümkün kılar. DEF dosyası, sıralı olarak verme hızı ve boyutu verimliliğini ödün vermeden basit sürüm oluşturma izni. MFC Sınıf Kitaplığı'ndaki ana sürüm düzeltmeler kitaplık adını değiştirir. Diğer bir deyişle, MFC30. DLL, MFC sınıf kitaplığı 3.0 sürümünü içeren yeniden dağıtılabilir DLL'dir. Bu DLL yükseltmesini varsayalım, kuramsal bir MFC 3.1 DLL MFC31 adlandırılması. DLL yerine. MFC DLL özel bir sürümünü oluşturmak için MFC kaynak kodunda değişiklik yaparsanız, yeniden, farklı bir ad (ve tercihen biri adında "MFC" olmadan) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
