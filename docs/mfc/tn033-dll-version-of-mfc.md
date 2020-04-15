---
title: "TN033: MFC'nin DLL Sürümü"
ms.date: 06/28/2018
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
ms.openlocfilehash: ad4cb883cfe7e397cf599d659afb02b23501dc5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370319"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC'nin DLL Sürümü

Bu not, MFc uygulamaları ve MFC uzantılı DL'lerle paylaşılan dinamik bağlantı kitaplıklarını MFCxx.DLL ve MFCxxD.DLL'yi (x'in MFC sürüm numarası olduğu) nasıl kullanabileceğinizi açıklar. Normal MFC DLL'leri hakkında daha fazla bilgi için, [MFC'yi Bir DLL'nin Parçası olarak kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)bölümüne bakın.

Bu teknik not DLs üç yönünü kapsar. Son iki daha gelişmiş kullanıcılar içindir:

- [Nasıl bir MFC Uzantısı DLL oluşturmak](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC'nin DLL sürümünü kullanan bir MFC uygulamasını nasıl oluşturursunuz?](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC paylaşılan dinamik bağlantı kitaplıkları nasıl uygulanır?](#_mfcnotes_how_the_mfc30.dll_is_implemented)

MFC olmayan uygulamalarda kullanılabilen (buna normal MFC DLL denir) MFC kullanarak bir DLL oluşturmak istiyorsanız, [Teknik Not 11'e](../mfc/tn011-using-mfc-as-part-of-a-dll.md)bakın.

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL Desteğine Genel Bakış: Terminoloji ve Dosyalar

**Normal MFC DLL**: Bazı MFC sınıflarını kullanarak tek başına bir DLL oluşturmak için normal bir MFC DLL kullanırsınız. App/DLL sınırındaki arabirimler "C" arabirimleridir ve istemci uygulamasının bir MFC uygulaması olması gerekmez.

Bu, MFC 1.0'da desteklenen DLL desteğinin sürümüdür. Bu Teknik [Not 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) ve MFC Gelişmiş Kavramlar örnek [DLLScreenCap](../overview/visual-cpp-samples.md)açıklanmıştır.

> [!NOTE]
> Visual C++ sürüm 4.0 **itibariyle, USRDLL** terimi eskidir ve yerine statik olarak MFC'ye bağlanan normal bir MFC DLL kullanılmıştır. Ayrıca, MFC'ye dinamik olarak bağlanan normal bir MFC DLL de oluşturabilirsiniz.

MFC 3.0 (ve üzeri) Normal MFC DL'leri OLE ve Veritabanı sınıfları da dahil olmak üzere tüm yeni işlevlerle destekler.

**AFXDLL**: Bu, MFC kitaplıklarının paylaşılan sürümü olarak da adlandırılır. Bu, MFC 2.0'a eklenen yeni DLL desteğidir. MFC kitaplığı kendisi DLs bir dizi (aşağıda açıklanan) ve bir istemci uygulaması veya DLL dinamik olarak gerekli DLs bağlanır. Uygulama/DLL sınırındaki arabirimler C++/MFC sınıfı arabirimlerdir. İstemci uygulaması bir MFC uygulaması olmalıdır. Bu, tüm MFC 3.0 işlevlerini destekler (özel durum: UNICODE veritabanı sınıfları için desteklenmez).

> [!NOTE]
> Visual C++ sürüm 4.0 itibariyle, bu dll türüne "Uzantı DLL" adı verilir.

Bu not, aşağıdakileri içeren tüm MFC DLL kümesini ifade etmek için MFCxx.DLL'yi kullanır:

- Hata Ayıklama: MFCxxD.DLL (kombine) ve MFCSxxD.LIB (statik).

- Yayın: MFCxx.DLL (kombine) ve MFCSxx.LIB (statik).

- Unicode Hata Ayıklama: MFCxxUD.DLL (kombine) ve MFCSxxD.LIB (statik).

- Unicode Release: MFCxxU.DLL (kombine) ve MFCSxxU.LIB (statik).

> [!NOTE]
> The MFCSxx[U][D]. LIB kitaplıkları, MFC paylaşılan DL'leri ile birlikte kullanılır. Bu kitaplıklar, uygulama veya DLL'ye statik olarak bağlanması gereken kodlar içerir.

İlgili alma kitaplıklarına bir uygulama bağlantıları:

- Hata Ayıklama: MFCxxD.LIB

- Yayın: MFCxx.LIB

- Unicode Hata Ayıklama: MFCxxUD.LIB

- Unicode Yayın: MFCxxU.LIB

"MFC Extension DLL", MFCxx.DLL (ve/veya diğer MFC paylaşılan DL'ler) üzerine kurulu bir DLL'dir. Burada MFC bileşen mimarisi devreye sayılsA. MFC sınıfından yararlı bir sınıf türetin veya Başka bir MFC benzeri araç seti oluşturuyorsanız, bunu bir DLL'ye yerleştirebilirsiniz. Bu DLL mfcxx.DLL kullanır, nihai istemci uygulaması yok gibi. Bu, yeniden kullanılabilir yaprak sınıflarına, yeniden kullanılabilir temel sınıflara ve yeniden kullanılabilir görünüm/belge sınıflarına izin verir.

## <a name="pros-and-cons"></a>Artıları ve Eksileri

MFC'nin paylaşılan sürümünü neden kullanmalısınız?

- Paylaşılan kitaplığın kullanılması daha küçük uygulamalara neden olabilir (MFC kitaplığı kullanan en az uygulama 10K'dan azdır).

- MFC'nin paylaşılan sürümü MFC Extension DLl'leri ve normal MFC DL'leri destekler.

- Paylaşılan MFC kitaplıklarını kullanan bir uygulama oluşturmak, MFC'yi bağlamaya gerek olmadığından statik olarak bağlı bir MFC uygulaması oluşturmaktan daha hızlıdır. Bu, özellikle bağlayıcının hata ayıklama bilgilerini sıkıştırması gereken **hata** ayıklama oluştururda doğrudur — hata ayıklama bilgilerini zaten içeren bir DLL ile bağlantı kurarak, uygulamanızda sıkıştırılabilen daha az hata ayıklama bilgisi vardır.

MFC'nin paylaşılan sürümünü neden kullanmamalısınız:

- Paylaşılan kitaplığı kullanan bir uygulamayı gönderme, Programınızla Birlikte MFCxx.DLL (ve diğerleri) kitaplığını göndermenizi gerektirir. MFCxx.DLL birçok DLs gibi serbestçe dağıtılabilir, ancak yine de KURULUM programınızda DLL yüklemeniz gerekir. Buna ek olarak, hem programınız hem de MFC DL'lerin kendileri tarafından kullanılan C-runtime kitaplığını içeren MSVCRTxx.DLL'yi göndermeniz gerekir.

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>Nasıl Bir MFC Uzantısı DLL yazmak için

MFC Extension DLL, MFC sınıflarının işlevselliğini süslemek için yazılmış sınıfları ve işlevleri içeren bir DLL'dir. Bir MFC Extension DLL, paylaşılan MFC DL'leri bir uygulamanın kullandığı şekilde kullanır ve birkaç ek husus alalar:

- Yapı işlemi, paylaşılan MFC kitaplıklarını birkaç ek derleyici ve bağlayıcı seçeneğiyle kullanan bir uygulama oluşturmaya benzer.

- MFC Extension DLL'nin `CWinApp`türetilmiş bir sınıfı yoktur.

- Bir MFC Uzantısı DLL `DllMain`özel bir . AppWizard değiştirebileceğiniz bir `DllMain` işlev sağlar.

- Bir MFC Uzantı DLL genellikle bir mfc uzantısı DLL uygulama için `CRuntimeClass`es veya kaynak dışa aktarmak istiyorsa oluşturmak için bir `CDynLinkLibrary` başlatma yordamı sağlar. Uygulama başına `CDynLinkLibrary` verilerin MFC uzantısı DLL tarafından tutulması gerekiyorsa, türetilmiş bir sınıf kullanılabilir.

Bu hususlar aşağıda daha ayrıntılı olarak açıklanmıştır. Ayrıca, aşağıdakileri gösterdiğinden, MFC Advanced Concepts [örneğine](../overview/visual-cpp-samples.md) de bakmalısınız:

- Paylaşılan kitaplıkları kullanarak bir uygulama oluşturma. (DLLHUSK. EXE, MFC kitaplıklarının yanı sıra diğer DL'lere dinamik olarak bağlanan bir MFC uygulamasıdır.)

- Bir MFC Uzantısı DLL oluşturma. (MFC uzantısı DLL'nin oluşturulmasında kullanılan özel `_AFXEXT` bayraklar gibi özel bayraklar)

- MFC Uzantılı DL'lere iki örnek. Bunlardan biri, sınırlı dışa aktarımlı bir MFC Extension DLL'nin temel yapısını (TESTDLL1) ve diğerinin tüm sınıf arabirimini (TESTDLL2) dışa aktarımı gösterir.

Hem istemci uygulaması hem de herhangi bir MFC uzantısı DLLs MFCxx.DLL aynı sürümünü kullanmanız gerekir. MFC DLL kuralına uymalı ve MFC uzantılı DLL'nizin hem hata ayıklama hem de perakende (/sürüm) sürümünü sağlamalısınız. Bu, istemci programlarının uygulamalarının hem hata ayıklama hem de perakende sürümlerini oluşturmasına ve bunları tüm DL'lerin uygun hata ayıklama veya perakende sürümüyle bağlamasına izin verir.

> [!NOTE]
> C++ adı mangling ve dışa aktarma sorunları olduğundan, bir MFC uzantısı DLL'den gelen dışa aktarma listesi, farklı platformlar için aynı DLL ve DL'lerin hata ayıklama ve perakende sürümleri arasında farklı olabilir. Perakende MFCxx.DLL yaklaşık 2000 ihraç giriş noktaları vardır; hata ayıklama MFCxxD.DLL yaklaşık 3000 dışa aktarılan giriş noktaları vardır.

### <a name="quick-note-on-memory-management"></a>Bellek Yönetimi Üzerine Hızlı Not

Bu teknik notun sonuna yakın "Bellek Yönetimi" başlıklı bölüm, MFC paylaşılan sürümü ile MFCxx.DLL uygulanması açıklar. Yalnızca bir MFC uzantısı DLL uygulamak için bilmeniz gereken bilgiler burada açıklanmıştır.

MFCxx.DLL ve istemci uygulamasının adres alanına yüklenen tüm MFC uzantılı DL'ler, aynı uygulamada yatmış gibi aynı bellek ayırıcısını, kaynak yüklemeyi ve diğer MFC "global" durumlarını kullanır. MFC'ye statik olarak bağlanan MFC olmayan DLL kitaplıkları ve normal MFC DLL'leri tam tersini yaptığı ndan ve her DLL'nin kendi bellek havuzundan ayrılmasına sahip olduğu için bu önemlidir.

Bir MFC uzantısı DLL bellek ayırırsa, o zaman bu bellek serbestçe başka bir uygulama tahsis nesne ile intermix olabilir. Ayrıca, paylaşılan MFC kitaplıklarını kullanan bir uygulama çökerse, işletim sisteminin koruması DLL'yi paylaşan diğer MFC uygulamalarının bütünlüğünü korur.

Benzer şekilde, kaynakları yüklemek için geçerli yürütülebilir dosya gibi diğer "global" MFC durumları da istemci uygulaması ve tüm MFC uzantısı DLL'ler ile MFCxx.DLL kendisi arasında paylaşılır.

### <a name="building-an-mfc-extension-dll"></a>Bir MFC uzantısı DLL oluşturma

Bir MFC uzantısı DLL projesi oluşturmak için AppWizard'ı kullanabilirsiniz ve bu proje otomatik olarak uygun derleyici ve bağlayıcı ayarlarını oluşturur. Ayrıca değiştirebileceğiniz `DllMain` bir işlev oluşturmak oldu.

Varolan bir projeyi MFC uzantısı DLL'ye dönüştürüyorsanız, MFC'nin paylaşılan sürümünü kullanarak bir uygulama oluşturmak için standart kurallarla başlayın ve ardından aşağıdakileri yapın:

- Derleyici bayraklarına **/D_AFXEXT** ekleyin. Project Properties iletişim kutusunda C/C++ düğümünü seçin. Ardından Önİşlemci kategorisini seçin. Makroları Tanımla alanına ekleyerek, `_AFXEXT` öğelerin her birini yarı iki nokta noktayla ayırın.

- **/Gy** derleyici anahtarını kaldırın. Project Properties iletişim kutusunda C/C++ düğümünü seçin. Ardından Kod Oluşturma kategorisini seçin. "İşlev Düzeyi Bağlantısını Etkinleştir" seçeneğinin etkinleştirildiğinden emin olun. Bağlayıcı başvurulmamış işlevleri kaldırmaz, çünkü bu sınıfları dışa aktarmayı kolaylaştırır. Özgün proje statik olarak MFC'ye bağlı normal bir MFC DLL oluşturmak için kullanılıyorsa, **/MT[d]** derleyici sebunu **/MD[d]** olarak değiştirin.

- LINK için **/DLL** seçeneği ile bir dışa aktarma kitaplığı oluşturun. Bu, hedef türü olarak Win32 Dinamik Bağlantı Kitaplığı belirterek yeni bir hedef oluşturduğunuzda ayarlanır.

### <a name="changing-your-header-files"></a>Üstbilgi Dosyalarınızı Değiştirme

Bir MFC uzantısı DLL'nin amacı genellikle bu işlevselliği kullanabilen bir veya daha fazla uygulamaya bazı yaygın işlevleri dışa aktarmaktır. Bu, istemci uygulamalarınız için kullanılabilen dışa aktarma sınıfları ve genel işlevler için aşağı kaynar.

Bunu yapmak için üye işlevlerin her birinin uygun şekilde alma veya dışa aktarma olarak işaretlendiğini sigortalamalısınız. Bu özel bildirimler `__declspec(dllexport)` gerektirir: ve `__declspec(dllimport)`. Sınıflarınız istemci uygulamaları tarafından kullanıldığında, bunların `__declspec(dllimport)`'. MFC uzantısı DLL kendisi inşa edilirken, onlar `__declspec(dllexport)`olarak bildirilmelidir. Buna ek olarak, istemci programları yük zamanında onlara bağlamak, böylece işlevleri aslında dışa aktarılmalıdır.

Tüm sınıfı dışa `AFX_EXT_CLASS` aktarmak için sınıf tanımını kullanın. Bu makro çerçeve tarafından `__declspec(dllexport)` ne `_AFXDLL` `_AFXEXT` zaman ve ne `__declspec(dllimport)` zaman `_AFXEXT` tanımlanır olarak tanımlanır, ancak ne zaman tanımlanmaz olarak tanımlanır. `_AFXEXT`yukarıda açıklandığı gibi, yalnızca MFC uzantısı DLL'nizi kurarken tanımlanır. Örneğin:

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>Tüm Sınıfı Dışa Aktarma

Bazen sınıfınızın sadece bireysel gerekli üyeleri dışa aktarmak isteyebilirsiniz. Örneğin, türetilmiş bir `CDialog`sınıf dışa aktarıyorsanız, yalnızca oluşturucuyu `DoModal` ve aramayı dışa aktarmanız gerekebilir. Bu üyeleri DLL'leri kullanarak dışa aktarabilirsiniz. DEF dosyası, ancak aynı `AFX_EXT_CLASS` şekilde dışa aktarmak için gereken tek tek üyeleri üzerinde de aynı şekilde kullanabilirsiniz.

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

Bunu yaptığınızda, sınıfın tüm üyelerini artık dışa aktarmadığınız için ek bir sorunla karşılaşabilirsiniz. Sorun, MFC makrolarının çalışma şeklidir. MFC'nin yardımcı makrolarından bazıları veri üyelerini gerçekten beyan eder veya tanımlar. Bu nedenle, bu veri üyelerinin de DLL'nizden dışa aktarılması gerekir.

Örneğin, bir MFC uzantısı DLL inşa ederken DECLARE_DYNAMIC makro aşağıdaki gibi tanımlanır:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

"Statik" `AFX_DATA`olarak başlayan satır, sınıfınızın içinde statik bir nesne beyan ediyor. Bu sınıfı doğru bir şekilde dışa aktarmak ve istemciden çalışma zamanı bilgilerine erişmek için. EXE, bu statik nesneyi dışa aktarmanız gerekiyor. Statik nesne `AFX_DATA`değiştirici ile bildirilir olduğundan, yalnızca DLL'nizi inşa `AFX_DATA` `__declspec(dllexport)` ederken olması ve `__declspec(dllimport)` istemcinizin çalıştırılabilir olarak tanımlanması gerekir.

Yukarıda da belirtildiği `AFX_EXT_CLASS` gibi, zaten bu şekilde tanımlanır. Sınıf tanımınızın etrafındakiyle `AFX_DATA` `AFX_EXT_CLASS` aynı olması için yeniden tanımlamanız gerekir.

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

MFC her `AFX_DATA` zaman makroları içinde tanımladığı veri öğeleri üzerinde sembolü kullanır, bu nedenle bu teknik tüm bu senaryolar için çalışacaktır. Örneğin, DECLARE_MESSAGE_MAP için çalışacaktır.

> [!NOTE]
> Sınıfın seçili üyeleri yerine sınıfın tamamını dışa aktarıyorsanız, statik veri üyeleri otomatik olarak dışa aktarılır.

DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanan `CArchive` sınıflar için çıkarma işleciotomatik olarak dışa aktarmak için aynı tekniği kullanabilirsiniz. Sınıf bildirimlerini paranteze alarak arşiv işlecini dışa aktarma (. H dosyası) aşağıdaki kod ile:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXT sınırlamaları

Birden fazla MFC uzantılı DL'niz olmadığı sürece MFC uzantılı DL'leriniz için _**AFXEXT** ön işlemci simgesini kullanabilirsiniz. MFC uzantısı DL'leri arayan veya kendi MFC uzantısı DLL'lerinizdeki sınıflardan türetilen ve daha sonra MFC sınıflarından türeyen MFC uzantılı DL'leriniz varsa, belirsizliği önlemek için kendi önişlemci simgenizi kullanmanız gerekir.

Sorun şu ki, Win32'de, herhangi bir `__declspec(dllexport)` veriyi bir DLL'den aktarım olacaksa ve `__declspec(dllimport)` bir DLL'den aktabilmek için açık bir şekilde beyan etmeniz gerekir. Tanımlarken, `_AFXEXT`MFC üstbilgisinin doğru `AFX_EXT_CLASS` tanımlandığınızdan emin olun.

Birden çok katmanınız olduğunda, `AFX_EXT_CLASS` bir MFC uzantısı DLL yeni sınıflar dışa aktarmanın yanı sıra başka bir MFC uzantısı DLL'den diğer sınıfları içe aktardığından, bu tür bir sembol yeterli değildir. Bu sorunla başa çıkmak için, DLL'yi kullanarak DLL'nin kendisini inşa ettiğinizi gösteren özel bir önişlemci simgesi kullanın. Örneğin, iki MFC uzantısı DLs, A.DLL ve B.DLL düşünün. Her biri sırasıyla A.H ve B.H.'deki bazı sınıfları dışa aktarır. B.DLL, A.DLL'deki sınıfları kullanır. Üstbilgi dosyaları şuna benzer:

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

A.DLL inşa edildiğinde, **/DA_IMPL** ile inşa edilir ve B.DLL inşa edildiğinde / **DB_IMPL**ile inşa edilir. Her DLL için ayrı semboller kullanılarak CExampleB dışa aktarılır ve B.DLL inşa edilirken CExampleA alınır. CExampleA, A.DLL'yi kurarken dışa aktarılır ve B.DLL (veya başka bir istemci) tarafından kullanıldığında içe aktarılır.

Bu tür katmanlama, yerleşik `AFX_EXT_CLASS` ve `_AFXEXT` önişlemci sembolleri kullanılarak yapılamaz. Yukarıda açıklanan teknik, Bu sorunu, MFC'nin OLE, Veritabanı ve Ağ MFC uzantısı DLL'lerini kurarken kullandığı mekanizmadan farklı olmayan bir şekilde çözer.

### <a name="not-exporting-the-entire-class"></a>Tüm Sınıfı Dışa Aktarma

Yine, tüm bir sınıf ihraç değilken özel dikkat çekmek zorunda kalacak. MFC makroları tarafından oluşturulan gerekli veri öğelerinin doğru şekilde dışa aktarıldığından emin olabilirsiniz. Bu, özel sınıf makroyeniden `AFX_DATA` tanımlayarak yapılabilir. Bu, tüm sınıfı dışa aktarmadığınız her zaman yapılmalıdır.

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

### <a name="dllmain"></a>Dllmain

Aşağıda, MFC uzantıdınız DLL için ana kaynak dosyanıza yerleştirmeniz gereken tam kod vekod verilmelidir. Standart içerir sonra gelmelidir. Bir MFC uzantısı DLL için başlangıç dosyaları oluşturmak için AppWizard `DllMain` kullandığınızda, sizin için bir sağlar unutmayın.

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

Modülleri `AfxInitExtensionModule` yakalama çağrısı çalışma zamanı sınıfları`CRuntimeClass` (yapıları) yanı sıra`COleObjectFactory` `CDynLinkLibrary` nesne fabrikaları (nesneleri) daha sonra nesne oluşturulduğunda kullanılmak üzere. (isteğe bağlı) `AfxTermExtensionModule` arama, MFC uzantısı DLL'den her işlem çıktığında (işlem çıktığında veya `FreeLibrary` arama sonucunda DLL boşaltıldığında olur) MFC uzantısı DLL'yi temizlemesine olanak tanır. Çoğu MFC uzantılı DL dinamik olarak yüklenmediğinden (genellikle, alma kitaplıkları üzerinden bağlanır), çağrı `AfxTermExtensionModule` genellikle gerekli değildir.

Uygulamanız MFC uzantısı DL'leri dinamik olarak yükler ve `AfxTermExtensionModule` serbest hale sağlarsa, yukarıda gösterildiği gibi aramayı unutmayın. Ayrıca `AfxLoadLibrary` kullandığınızdan emin `AfxFreeLibrary` olun ve (Win32 işlevleri `LoadLibrary` yerine ve) `FreeLibrary`uygulamanız birden fazla iş parçacığı kullanıyorsa veya dinamik olarak bir MFC uzantısı DLL yüklerse. MFC uzantısı DLL yüklendiğinde ve boşaltıldığında çalıştıran başlatma ve kapatma kodunun genel MFC durumunu bozmadığını kullanmak `AfxLoadLibrary` ve `AfxFreeLibrary` sigortalamak.

Üstbilgi dosyası AFXDLLX. H, MFC uzantılı DL'lerde kullanılan yapılar için `AFX_EXTENSION_MODULE` tanım `CDynLinkLibrary`ve .

Global *extensionDLL* gösterildiği gibi bildirilmelidir. MFC'nin 16 bit sürümünün aksine, bu süre zarfında bellek ayırabilir ve MFC işlevlerini arayabilirsiniz, çünkü MFCxx.DLL çağrılır `DllMain` zaman tamamen başharfe çevrilir.

### <a name="sharing-resources-and-classes"></a>Kaynakları ve Sınıfları Paylaşma

Basit MFC uzantısı DLS'ler istemci uygulamasına yalnızca birkaç düşük bant genişliği işlevi dışa aktarmanız gerekir ve başka bir şey değil. Daha fazla kullanıcı arabirimi yoğun DL'ler, kaynakları ve C++ sınıflarını istemci uygulamasına aktarmak isteyebilir.

Kaynak dışa aktarma bir kaynak listesi üzerinden yapılır. Her uygulamada `CDynLinkLibrary` nesnelerin tek bağlantılı bir listesi vardır. Kaynak ararken, kaynakları yükleyen standart MFC uygulamalarının çoğu önce geçerli`AfxGetResourceHandle`kaynak modülüne bakar ( `CDynLinkLibrary` ) ve yoksa istenen kaynağı yüklemeye çalışan nesnelerin listesini yürü.

C++ sınıf adı verilen C++ nesnelerinin dinamik oluşturulması benzerdir. MFC nesne deserialization mekanizması, daha `CRuntimeClass` önce depolanan ne dayalı gerekli türde C++ nesnedinamik oluşturarak yeniden oluşturabilirsiniz, böylece tüm nesnelerin kayıtlı olması gerekir.

İstemci uygulamasının MFC uzantısı DLL'nizdeki sınıfları kullanmasını `DECLARE_SERIAL`istiyorsanız, istemci uygulamasına görünür olması için sınıflarınızı dışa aktarmanız gerekir. Bu da `CDynLinkLibrary` liste yürüyerek yapılır.

MFC Gelişmiş Kavramlar örnek [DLLHUSK](../overview/visual-cpp-samples.md)durumunda, liste gibi bir şey görünüyor:

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

MFCxx.DLL genellikle kaynak ve sınıf listesinde son sırada yer almaktadır. MFCxx.DLL, tüm standart komut iI'leri için istem dizeleri de dahil olmak üzere tüm standart MFC kaynaklarını içerir. Listenin kuyruğuna yerleştirmek, DL'lerin ve istemci uygulamasının kendisinin standart MFC kaynaklarının kendi kopyasına sahip olmamasını, bunun yerine MFCxx.DLL'deki paylaşılan kaynaklara güvenmesini sağlar.

Tüm DL'lerin kaynaklarını ve sınıf adlarını istemci uygulamasının ad alanıyla birleştirmek, seçtiğiniz ne leri veya adlarını dikkatli olmanız gerektiği ne kadar dezavantajlıdır. Elbette, kaynaklarınızı veya bir `CDynLinkLibrary` nesneyi istemci uygulamasına dışa aktarmayarak bu özelliği devre dışı kullanabilirsiniz. [DLLHUSK](../overview/visual-cpp-samples.md) örneği, paylaşılan kaynak adı alanını birden çok üstbilgi dosyası kullanarak yönetir. Paylaşılan kaynak dosyalarını kullanma yla ilgili daha fazla ipucu için [Teknik Not 35'e](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) bakın.

### <a name="initializing-the-dll"></a>DLL'yi başlatma

Yukarıda belirtildiği gibi, genellikle kaynaklarınızı `CDynLinkLibrary` ve sınıflarınızı istemci uygulamasına aktarmak için bir nesne oluşturmak istersiniz. DLL'yi başlatmanız için dışa aktarılan bir giriş noktası sağlamanız gerekir. Minimal, bu hiçbir argüman alır ve hiçbir şey döner geçersiz bir rutin, ama sizin gibi bir şey olabilir.

DLL'nizi kullanmak isteyen her istemci uygulaması, bu yaklaşımı kullanıyorsanız bu başlatma yordamını çağırmalıdır. Ayrıca bu `CDynLinkLibrary` nesneyi aradıktan `DllMain` `AfxInitExtensionModule`hemen sonra da ayırabilirsiniz.

Başlatma yordamı, geçerli `CDynLinkLibrary` uygulamanın yığınında MFC uzantısı DLL bilgilerinize bağlı bir nesne oluşturmalıdır. Bu aşağıdakilerle yapılabilir:

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

Bu örnekte rutin adı, *InitXxxDLL,* istediğiniz şey olabilir. **Bu extern "C"** olması gerekmez, ancak bunu yaparken ihracat listesini korumak için kolaylaştırır.

> [!NOTE]
> MFC uzantıdınızı normal bir MFC DLL'den kullanıyorsanız, bu başlatma işlevini dışa aktarmanız gerekir. Bu işlev, herhangi bir MFC uzantısı DLL sınıfları veya kaynakları kullanmadan önce normal MFC DLL'den çağrılmalıdır.

### <a name="exporting-entries"></a>Girişleri Dışa Aktarma

Sınıflarınızı dışa aktarmanın en `__declspec(dllimport)` `__declspec(dllexport)` basit yolu, dışa aktarmak istediğiniz her sınıf ve global işlevi kullanmaktır. Bu çok daha kolay hale getirir, ancak hangi işlevleri dışa aktarır üzerinde daha az kontrole sahip ve ordinal tarafından işlevleri dışa aktaramazsınız beri her giriş noktası (aşağıda açıklanan) adlandırma daha az verimlidir. TESTDLL1 ve TESTDLL2 girişlerini dışa aktarmak için bu yöntemi kullanır.

Daha verimli bir yöntem (ve MFCxx.DLL tarafından kullanılan yöntem) her girişi elle dışa aktarmaktır. DEF dosyası. DLL'mizden seçici ihracat yaptığımıziçin (yani her şeyden değil), hangi arayüzleri ihraç etmek istediğimize karar vermeliyiz. Bu, bağlayıcıya ezilmiş adları . DEF dosyası. Gerçekten bunun için sembolik bir bağlantı olması gerekmedikçe herhangi bir C++ sınıfları dışa aktarmayın.

C++ sınıflarını bir . ile dışa aktarmayı denediyseniz DEF dosyası önce, otomatik olarak bu listeyi oluşturmak için bir araç geliştirmek isteyebilirsiniz. Bu iki aşamalı bağlantı işlemi kullanılarak yapılabilir. DLL'nizi hiçbir dışa aktarma olmadan bir kez bağla ve bağlantı nın bir . MAP dosyası. Şey. MAP dosyası dışa aktarılmak gereken işlevlerin bir listesini oluşturmak için kullanılabilir, bu nedenle bazı yeniden düzenleme ile, sizin için İhracat girişleri oluşturmak için kullanılabilir. DEF dosyası. MFCxx.DLL ve OLE ve Veritabanı MFC uzantısı DLLs için ihracat listesi, sayısı birkaç bin, böyle bir süreç ile oluşturuldu (tamamen otomatik olmasa da ve bazı el ayarı gerektirir arada bir).

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp vs CDynLinkLibrary

Bir MFC Uzantı DLL'nin kendi türetilmiş nesnesi `CWinApp`yoktur; bunun yerine istemci `CWinApp`uygulamanın -türetilmiş nesne ile çalışması gerekir. Bu istemci uygulaması ana ileti pompası, boşta döngü ve benzeri sahibi olduğu anlamına gelir.

MFC Extension DLL'nizin her uygulama için ek veri tutması gerekiyorsa, yukarıda açıklanan InitXxxDLL yordamında yeni bir sınıf türetebilir `CDynLinkLibrary` ve oluşturabilirsiniz. Çalışırken, DLL belirli Bir MFC uzantısı `CDynLinkLibrary` DLL için bir bulmak için geçerli uygulamanın nesne listesini denetleyebilirsiniz.

### <a name="using-resources-in-your-dll-implementation"></a>DLL Uygulamanızda Kaynakları Kullanma

Yukarıda belirtildiği gibi, varsayılan kaynak yükü istenen `CDynLinkLibrary` kaynağa sahip ilk EXE veya DLL'yi arayan nesnelerin listesini yürütür. Tüm MFC API'leri ve tüm `AfxFindResourceHandle` iç kod, nerede bulunsa da kaynak bulmak için kaynak listesini yürümek için kullanır.

Kaynakları yalnızca belirli bir yerden yüklemek istiyorsanız, API'leri `AfxGetResourceHandle` kullanın ve `AfxSetResourceHandle` eski tutamacı kaydedin ve yeni tutamacı ayarlayın. İstemci uygulamasına dönmeden önce eski kaynak tanıtıcısını geri yüklediğinden emin olun. Örnek TESTDLL2, menüyü açıkça yüklemek için bu yaklaşımı kullanır.

Listeyi yürümek, biraz daha yavaş olması ve kaynak kimliği aralıklarını yönetmeyi gerektirmesi dezavantajları dır. Birkaç MFC uzantılı DLL'ye bağlanan bir istemci uygulaması, DLL örnek tanıtıcısını belirtmek zorunda kalmadan DLL tarafından sağlanan herhangi bir kaynağı kullanabilir. `AfxFindResourceHandle`belirli bir eşleşmeyi aramak için kaynak listesini yürümek için kullanılan bir API'dir. Kaynağın adını ve türünü alır ve kaynak tutamacını ilk bulunduğu yerde (veya NULL) döndürür.

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>DLL Sürümünü Kullanan Bir Uygulama Yazma

### <a name="application-requirements"></a>Başvuru Şartları

MFC'nin paylaşılan sürümünü kullanan bir uygulama birkaç basit kurala uymalıdır:

- Bir `CWinApp` nesne olmalı ve bir mesaj pompası için standart kurallara uyun.

- Gerekli derleyici bayrakları kümesi ile derlenmelidir (aşağıya bakın).

- MFCxx alma kitaplıkları ile bağlantı gerekir. Gerekli derleyici bayraklarını ayarlayarak, MFC üstbilgisi bağlantı zamanında uygulamanın hangi kitaplıkla bağlantı kurması gerektiğini belirler.

- Çalıştırılabilir çalıştırmak için, MFCxx.DLL yolda veya Windows sistem dizini olmalıdır.

### <a name="building-with-the-development-environment"></a>Kalkınma Ortamı ile Bina

Standart varsayılanların çoğuna sahip dahili makefileyi kullanıyorsanız, DLL sürümünü oluşturmak için projeyi kolayca değiştirebilirsiniz.

Aşağıdaki adım, NAFXCWD ile bağlantılı doğru işleyen bir MFC uygulamanız olduğunu varsayar. LIB (hata ayıklama için) ve NAFXCW. LIB (perakende için) ve MFC kitaplığı paylaşılan sürümünü kullanmak için dönüştürmek istiyorum. Visual C++ ortamını çalıştırıyorsunuz ve dahili bir proje dosyanız var.

1. **Projeler** menüsünde **Özellikler'i**tıklatın. **Project Defaults**altındaki **Genel** sayfada, Microsoft Foundation Classes'ı Paylaşılan Bir DLL'de (MFCxx(d).dll) **MFC'yi kullanacak** şekilde ayarlayın.

### <a name="building-with-nmake"></a>NMAKE ile Bina

Visual C++'ın harici makefile özelliğini kullanıyorsanız veya doğrudan NMAKE kullanıyorsanız, derleyici ve bağlayıcı seçeneklerini desteklemek için makefilenizi yeniden doldurmanız gerekir

Gerekli derleyici bayrakları:

- **/D_AFXDLL /MD**
   **/D_AFXDLL**

Standart MFC üstbilgisinin tanımlanması için bu simgeye ihtiyaç duyar:

- **/MD** Uygulama, C çalışma zamanı kitaplığın DLL sürümünü kullanmalıdır

Diğer tüm derleyici bayrakları MFC varsayılanlarını izler (örneğin, hata ayıklama için _DEBUG).

Kitaplıkların bağlayıcı listesini edin. NAFXCWD değiştirin. LIB MFCxxD.LIB ve NAFXCW değiştirin. LIB'den MFCxx.LIB'e. LIBC'yi değiştirin. MSVCRT ile LIB. Lib. Diğer MFC kitaplıkları gibi MFCxxD.LIB'in herhangi bir C-runtime kitaplıkların **önüne** yerleştirilmesi önemlidir.

İsteğe bağlı olarak hem perakende hem de hata ayıklama kaynak derleyici seçeneklerinize (kaynakları **/R**ile derleyen) **/D_AFXDLL** ekleyin). Bu, MFC DLS'lerde bulunan kaynakları paylaşarak son yürütülebilirliğinizi küçültebilir.

Bu değişiklikler yapıldıktan sonra tam bir yeniden oluşturma gerekir.

### <a name="building-the-samples"></a>Örnekleri Oluşturma

MFC örnek programlarının çoğu Visual C++ veya komut satırından paylaşılan NMAKE uyumlu MAKEFILE'dan oluşturulabilir.

MFCxx.DLL kullanmak için bu örneklerden herhangi birini dönüştürmek için, yükleyebilirsiniz. MAK dosyası Visual C++ içine ve yukarıda açıklandığı gibi Proje seçeneklerini ayarlayın. NMAKE yapısını kullanıyorsanız, NMAKE komut satırında "AFXDLL=1" belirtebilirsiniz ve bu da paylaşılan MFC kitaplıklarını kullanarak örneği oluşturur.

MFC Advanced Concepts örnek [DLLHUSK,](../overview/visual-cpp-samples.md) MFC'nin DLL sürümüyle oluşturulmuştür. Bu örnek sadece MFCxx.DLL ile bağlantılı bir uygulamanın nasıl inşa edilebildiğini göstermekle kalmıyor, aynı zamanda daha sonra bu teknik notta açıklanan MFC Extension DLls gibi MFC DLL paketleme seçeneğinin diğer özelliklerini de göstermektedir.

### <a name="packaging-notes"></a>Ambalaj Notları

DLs perakende sürümü (MFCxx[U]. DLL) serbestçe dağıtılabilir. DL'lerin hata ayıklama sürümü serbestçe dağıtılamaz ve yalnızca uygulamanızın geliştirilmesi sırasında kullanılmalıdır.

Hata ayıklama DL'leri hata ayıklama bilgileriyle sağlanır. Visual C++ hata ayıklama yöntemini kullanarak, uygulamanızın yürütülmesini ve DLL'yi izleyebilirsiniz. Sürüm DLs (MFCxx[U]. DLL) hata ayıklama bilgileri içermez.

DL'leri özelleştirip yeniden inşa ederseniz, onlara MFC SRC dosyası MFCDLL'den başka bir şey aramalısınız. MAK yapı seçeneklerini açıklar ve DLL'yi yeniden adlandırma mantığını içerir. Bu DL'ler birçok MFC uygulaması tarafından paylaşıladığından, dosyaları yeniden adlandırmak gereklidir. MFC DLL'lerinin özel sürümünün, sisteme yüklenenlerin yerini alması paylaşılan MFC DLL'leri kullanarak başka bir MFC uygulamasını bozabilir.

MFC DLS'lerin yeniden oluşturulması önerilmez.

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>MFCxx.DLL Nasıl Uygulanır?

Aşağıdaki bölümde MFC DLL (MFCxx.DLL ve MFCxxD.DLL) nasıl uygulandığı açıklanmaktadır. Tüm yapmak istediğiniz uygulama ile MFC DLL kullanmak ise burada ayrıntıları anlamak da önemli değildir. Burada ayrıntıları nasıl bir MFC uzantısı DLL yazmak için anlamak için gerekli değildir, ancak bu uygulamayı anlamak kendi DLL yazmak yardımcı olabilir.

### <a name="implementation-overview"></a>Uygulamaya Genel Bakış

MFC DLL gerçekten yukarıda açıklandığı gibi bir MFC Uzantısı DLL özel bir durumdur. Bu sınıflar çok sayıda ihracat çok sayıda vardır. MFC DLL'de yaptığımız ve normal bir MFC uzantısı DLL'den daha özel hale getiren birkaç ek şey vardır.

### <a name="win32-does-most-of-the-work"></a>Win32 İşin Çoğunu Yapar

MFC'nin 16 bit sürümü, yığın segmentindeki uygulama başına veriler, bazı 80x86 montaj kodu tarafından oluşturulan özel segmentler, işlem başına özel durum bağlamları ve diğer teknikler dahil olmak üzere bir dizi özel teknike ihtiyaç duydu. Win32, çoğu zaman istediğiniz dll'deki işlem başına verileri doğrudan destekler. Çoğunlukla MFCxx.DLL sadece NAFXCW olduğunu. LIB bir DLL içinde paketlenmiş. MFC kaynak koduna bakarsanız, yapılması gereken çok az özel durum olduğundan, _AFXDLL çok az #ifdef bulabilirsiniz. Windows 3.1'de Win32 ile özellikle başa çıkmak için özel durumlar vardır (aksi takdirde Win32s olarak da bilinir). Win32s, işlem başına DLL verilerini doğrudan desteklemez, bu nedenle MFC DLL'nin işlem yerel verilerini elde etmek için iş parçacığı yerel depolama (TLS) Win32 API'lerini kullanması gerekir.

### <a name="impact-on-library-sources-additional-files"></a>Kütüphane Kaynakları, Ek Dosyalar Üzerindeki Etkisi

**_AFXDLL** sürümünün normal MFC sınıf kitaplığı kaynakları ve üstbilgi üzerindeki etkisi nispeten küçüktür. Özel bir sürüm dosyası vardır (AFXV_DLL. H) yanı sıra ek bir üstbilgi dosyası (AFXDLL_. H) ana AFXWIN tarafından dahil edilmiştir. H üstbilgi. The AFXDLL_. H üstbilgisi, `CDynLinkLibrary` her iki `_AFXDLL` uygulamanın ve MFC Uzantılı DL'lerin sınıf ve diğer uygulama ayrıntılarını içerir. The AFXDLLX. MFC Extension DLL'leri oluşturmak için H üstbilgisi sağlanır (ayrıntılar için yukarıya bakın).

MFC SRC'deki MFC kitaplığı için düzenli kaynaklar `_AFXDLL` #ifdef altında bazı ek koşullu kod var. Ek bir kaynak dosyası (DLLINIT. CPP) MFC paylaşılan sürümü için ekstra DLL başlatma kodu ve diğer tutkal içerir.

MFC'nin paylaşılan sürümünü oluşturmak için ek dosyalar sağlanır. (DLL'nin nasıl inşa edilene ilişkin ayrıntılar için aşağıya bakın.)

- Iki. DEF dosyaları hata ayıklama (MFCxxD.DEF) ve DLL sürümü (MFCxx.DEF) sürümleri için MFC DLL giriş noktaları dışa aktarmak için kullanılır.

- Bir. RC dosyası (MFCDLL. RC) tüm standart MFC kaynaklarını ve DLL için bir VERSIONINFO kaynağını içerir.

- A. CLW dosyası (MFCDLL. CLW) ClassWizard kullanarak MFC sınıflarında gezinmeye izin vermek için sağlanır. Not: Bu özellik MFC'nin DLL sürümüne özgü değildir.

### <a name="memory-management"></a>Bellek Yönetimi

MFCxx.DLL kullanan bir uygulama, paylaşılan C-runtime DLL olan MSVCRTxx.DLL tarafından sağlanan ortak bir bellek ayırıcısı kullanır. Uygulama, herhangi bir MFC uzantısı DLLs ve yanı sıra MFC DLS'ler kendilerini bu paylaşılan bellek ayırıcı kullanın. Bellek ayırma için paylaşılan bir DLL kullanarak, MFC DLLs daha sonra uygulama veya tersi tarafından serbest bırakılır bellek tahsis edebilirsiniz. Hem uygulama hem de DLL aynı ayırıcıyı kullanması gerektiğinden, C++ global **işlecinin yeni** veya **işleci silmesini**geçersiz kılmamalısınız. Aynı kurallar C çalışma zamanı bellek ayırma yordamları **(malloc,** **realloc,** **ücretsiz**, ve diğerleri gibi) geri kalanı için geçerlidir.

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>Ordinals ve sınıf __declspec(dllexport) ve DLL adlandırma

C++ derleyicisinin `class` **__declspec(dllexport)** işlevini kullanmayız. Bunun yerine, dış kitaplık kaynaklarına (MFCxx.DEF ve MFCxxD.DEF) bir dışa aktarma listesi eklenir. Yalnızca bu seçili giriş noktaları kümesi (işlevler ve veriler) dışa aktarılır. MFC özel uygulama işlevleri veya sınıfları gibi diğer semboller dışa aktarılmaz Tüm dışa aktarımlar yerleşik veya yerleşik olmayan ad tablosunda dize adı olmadan tüm dışa aktarımlar tarafından yapılır.

`class` **__declspec(dllexport)** kullanmak daha küçük DLL'ler oluşturmak için uygun bir alternatif olabilir, ancak MFC gibi büyük bir DLL durumunda, varsayılan dışa aktarma mekanizması verimlilik ve kapasite sınırları vardır.

Tüm bu demektir ki çok yürütme veya yükleme hızı ödün vermeden sadece yaklaşık 800 KB serbest MFCxx.DLL işlevsellik büyük miktarda paketi olabilir. MFCxx.DLL bu teknik kullanılmasaydı 100K daha büyük olurdu. Bu da mümkün sonunda ek giriş noktaları eklemek için yapar. DEF dosyası, ordinal ile dışa aktarma nın hız ve boyut verimliliğinden ödün vermeden basit sürümlere izin verir. MFC sınıf kitaplığındaki ana sürüm düzeltmeleri kitaplık adını değiştirir. Yani, MFC30. DLL, MFC sınıf kitaplığı sürüm 3.0 içeren yeniden dağıtılabilir DLL'dir. Bu DLL bir yükseltme, diyelim ki, varsayımsal bir MFC 3.1, DLL MFC31 adlı olacaktır. Onun yerine DLL. Yine, MFC DLL'nin özel bir sürümünü oluşturmak için MFC kaynak kodunu değiştirirseniz, farklı bir ad kullanın (ve tercihen adında "MFC" olmayan bir ad kullanın).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
