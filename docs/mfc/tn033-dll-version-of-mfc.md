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
ms.openlocfilehash: c627f891efc893f4eb8dae4bfb0b3b78f7af1a46
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215939"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC'nin DLL Sürümü

Bu notta, MFC uygulamaları ve MFC uzantı dll 'Leri ile MFCxx.DLL ve MFCxxD.DLL (x MFC sürüm numarasıdır) paylaşılan dinamik bağlantı kitaplıklarını nasıl kullanabileceğinizi açıklar. Normal MFC DLL 'Leri hakkında daha fazla bilgi için bkz. [MFC 'YI dll 'nin bir parçası olarak kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md).

Bu teknik notta, dll 'lerin üç yönü ele alınmaktadır. Son iki, daha ileri düzey kullanıcılara yöneliktir:

- [MFC uzantı DLL 'i oluşturma](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC 'nin DLL sürümünü kullanan bir MFC uygulaması oluşturma](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC paylaşılan dinamik bağlantı kitaplıkları nasıl uygulanır](#_mfcnotes_how_the_mfc30.dll_is_implemented)

MFC 'yi kullanarak MFC olmayan uygulamalarla kullanılabilecek bir DLL oluşturmaya ilgileniyorsanız (buna normal MFC DLL adı verilir), [teknik notta 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)' e bakın.

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL desteğe genel bakış: terminoloji ve dosyalar

**Normal MFC DLL**: MFC sınıflarından bazılarını kullanarak tek başına dll oluşturmak IÇIN normal MFC DLL kullanırsınız. Uygulama/DLL sınırının içindeki arabirimler "C" arabirimlerdir ve istemci uygulamasının bir MFC uygulaması olması gerekmez.

Bu, MFC 1,0 ' de desteklenen DLL desteğinin sürümüdür. [Teknik not11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) ve mfc Gelişmiş kavramları örnek [DLLScreenCap](../overview/visual-cpp-samples.md)bölümünde açıklanmaktadır.

> [!NOTE]
> Visual C++ sürüm 4,0 itibariyle, **USRDLL** terimi kullanımdan KALDıRıLMıŞTıR ve MFC 'ye statik olarak bağlanan normal BIR mfc dll ile değiştirilmiştir. MFC 'ye dinamik olarak bağlanan normal bir MFC DLL de oluşturabilirsiniz.

MFC 3,0 (ve üzeri), OLE ve veritabanı sınıfları dahil olmak üzere tüm yeni işlevlerle normal MFC DLL 'Lerini destekler.

**AFXDLL**: Bu, MFC kitaplıklarının paylaşılan sürümü olarak da adlandırılır. Bu, MFC 2,0 ' ye eklenen yeni DLL desteği 'dir. MFC kitaplığı, bir dizi dll 'de (aşağıda açıklanmıştır) ve bir istemci uygulaması ya da DLL, gerek duyduğu dll 'Leri dinamik olarak bağlar. Uygulama/DLL sınırı içindeki arabirimler C++/MFC sınıf arabirimlerdir. İstemci uygulaması bir MFC uygulaması OLMALıDıR. Bu, tüm MFC 3,0 işlevlerini destekler (özel durum: UNICODE, veritabanı sınıfları için desteklenmez).

> [!NOTE]
> Visual C++ sürüm 4,0 itibariyle, bu tür DLL 'nin "uzantı DLL" olarak adlandırılmaktadır.

Bu notta, şunlar da dahil olmak üzere tüm MFC DLL kümesine başvurmak için MFCxx.DLL kullanılır:

- Hata ayıklama: MFCxxD.DLL (Birleşik) ve MFCSxxD. LIB (statik).

- Yayın: MFCxx.DLL (Birleşik) ve MFCSxx. LIB (statik).

- Unicode hata ayıklama: MFCxxUD.DLL (Birleşik) ve MFCSxxD. LIB (statik).

- Unicode sürümü: MFCxxU.DLL (Birleşik) ve MFCSxxU. LIB (statik).

> [!NOTE]
> MFCSxx [U] [D]. LıB kitaplıkları MFC paylaşılan DLL 'Leriyle birlikte kullanılır. Bu kitaplıklar, uygulamaya veya DLL 'ye statik olarak bağlı olması gereken kodu içerir.

Uygulama, ilgili içeri aktarma kitaplıklarına bağlanır:

- Hata Ayıkla: MFCxxD. LIB

- Yayın: MFCxx. LIB

- Unicode hata ayıklama: MFCxxUD. LIB

- Unicode sürümü: MFCxxU. LIB

Bir "MFC uzantı DLL", MFCxx.DLL (ve/veya diğer MFC paylaşılan DLL 'Ler) üzerinde oluşturulan bir DLL 'dir. Burada MFC bileşen mimarisi ' de açılır. Bir MFC sınıfından faydalı bir sınıf türetirsiniz veya başka bir MFC benzeri araç seti oluşturursanız, bunu bir DLL 'ye yerleştirebilirsiniz. Bu DLL, son istemci uygulaması gibi MFCxx.DLL kullanır. Bu, yeniden kullanılabilir yaprak sınıflarına, yeniden kullanılabilir temel sınıflara ve yeniden kullanılabilir görünüm/belge sınıflarına izin verir.

## <a name="pros-and-cons"></a>Profesyonelleri ve dezavantajları

Neden MFC 'nin paylaşılan sürümünü kullanmalıyım?

- Paylaşılan kitaplığın kullanılması, daha küçük uygulamalara neden olabilir (MFC kitaplığının çoğunu kullanan en küçük bir uygulama 10.000 'den azdır).

- MFC 'nin paylaşılan sürümü MFC uzantı dll 'Lerini ve normal MFC DLL 'Lerini destekler.

- Paylaşılan MFC kitaplıklarını kullanan bir uygulama oluşturmak, MFC 'nin kendisini bağlamak gerekli olmadığından statik olarak bağlanmış bir MFC uygulaması derlemeden daha hızlıdır. Bu, bağlayıcının hata ayıklama bilgilerini sıkıştıracağı **hata ayıklama** yapılarında (hata ayıklama bilgilerini zaten IÇEREN bir dll ile bağlantı kurarak), uygulamanızda sıkıştırmak için daha az hata ayıklama bilgisi olduğunu özellikle doğrudur.

Neden MFC 'nin paylaşılan sürümünü kullanmamalısınız:

- Paylaşılan kitaplığı kullanan bir uygulamayı teslim etmek için MFCxx.DLL (ve diğer) kitaplığı programınıza sevk etmeniz gerekir. MFCxx.DLL birçok dll gibi serbestçe yeniden dağıtılabilir, ancak yine de DLL 'yi kurulum programınıza yüklemelisiniz. Ayrıca, hem programınız hem de MFC DLL 'Leri tarafından kullanılan C-Runtime kitaplığını içeren MSVCRTxx.DLL teslim etmeniz gerekir.

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>MFC uzantı DLL yazma

MFC uzantı DLL 'si, MFC sınıflarının işlevselliğini süsleme için yazılan sınıfları ve işlevleri içeren bir DLL 'dir. MFC uzantı DLL 'SI, paylaşılan MFC DLL 'Lerini bir uygulamanın kullandığı şekilde kullanır, birkaç ek dikkat edin:

- Yapı işlemi, birkaç ek derleyici ve bağlayıcı seçeneği ile paylaşılan MFC kitaplıklarını kullanan bir uygulama oluşturmaya benzer.

- MFC uzantı DLL 'sinin `CWinApp` türetilmiş sınıfı yok.

- MFC uzantı DLL 'SI özel bir sağlamalıdır `DllMain` . AppWizard, `DllMain` değiştirebileceğiniz bir işlev sağlar.

- MFC uzantı DLL 'si genellikle `CDynLinkLibrary` MFC uzantısı DLL 'si `CRuntimeClass` uygulamaya veya kaynakları uygulamaya vermeyi istiyorsa, oluşturmak için bir başlatma yordamı sağlar. `CDynLinkLibrary`Uygulama başına VERILERIN MFC UZANTıSı dll 'i tarafından tutulması gerekiyorsa türetilmiş bir sınıfı kullanılabilir.

Bu konular aşağıda daha ayrıntılı olarak açıklanmıştır. Ayrıca, şu şekilde gösterildiği üzere MFC gelişmiş kavramlar örneği [DLLHUSK](../overview/visual-cpp-samples.md) öğesine başvurmalısınız:

- Paylaşılan kitaplıkları kullanarak bir uygulama oluşturma. (DLLHUSK.EXE, MFC kitaplıklarına ve diğer dll 'lere dinamik olarak bağlanan bir MFC uygulamasıdır.)

- MFC uzantı DLL 'SI oluşturma. ( `_AFXEXT` MFC UZANTı DLL oluşturulurken kullanılan gibi özel bayrakları unutmayın)

- MFC uzantı dll 'lerinin iki örneği. Bir MFC uzantı DLL 'inin, sınırlı dışarı aktarmalar (TESTDLL1) ile temel yapısını gösterir ve diğer bir sınıf arabiriminin (TESTDLL2) dışa aktarılması anlamına gösterilir.

Hem istemci uygulaması hem de MFC uzantı dll 'Lerinin aynı MFCxx.DLL sürümünü kullanması gerekir. MFC DLL 'nin kuralını izlemeniz ve MFC uzantı DLL 'nizin hem hata ayıklama hem de perakende (/Release) sürümünü sağlamanız gerekir. Bu, istemci programlarının uygulamalarının hem hata ayıklama hem de perakende sürümlerini oluşturmasına ve bunları tüm dll 'lerin uygun hata ayıklamasına veya perakende sürümüne bağlanmasına izin verir.

> [!NOTE]
> C++ ad değiştirmeyi ve dışa aktarma sorunları nedeniyle, bir MFC uzantı DLL 'den dışarı aktarma listesi, farklı platformlar için aynı DLL ve DLL 'lerin hata ayıklama ve perakende sürümleri arasında farklı olabilir. Perakende MFCxx.DLL, 2000 'e aktarılmış giriş noktaları içerir; hata ayıklama MFCxxD.DLL, 3000 'e aktarılmış giriş noktaları içerir.

### <a name="quick-note-on-memory-management"></a>Bellek yönetimine hızlı bir şekilde göz

Bu teknik notun sonundaki "bellek yönetimi" başlıklı Bölüm, MFCxx.DLL uygulamasının, MFC 'nin paylaşılan sürümü ile uygulanmasını açıklar. Yalnızca bir MFC uzantı DLL 'sini uygulamak için bilmeniz gereken bilgiler burada açıklanmıştır.

MFCxx.DLL ve bir istemci uygulamasının adres alanına yüklenen tüm MFC uzantı dll 'Leri aynı uygulama için aynı bellek ayırıcı, kaynak yükleme ve diğer MFC "genel" durumlarını kullanacaktır. Bu, MFC olmayan DLL kitaplıkları ve MFC 'ye statik olarak bağlanan normal MFC DLL 'Lerinin tam tersini yapması ve her DLL 'nin kendi bellek havuzunu ayırmasını sağlamak açısından önemlidir.

Bir MFC uzantısı DLL 'SI bellek ayırırsa, bu bellek, uygulama tarafından ayrılan diğer herhangi bir nesneyle serbestçe ayrılabilir. Ayrıca, paylaşılan MFC kitaplıklarını kullanan bir uygulama kilitlenirse, işletim sisteminin korunması DLL 'yi paylaşan diğer MFC uygulamalarının bütünlüğünü korur.

Benzer şekilde, kaynakları yüklemek için geçerli yürütülebilir dosya gibi diğer "Global" MFC durumları da istemci uygulaması ile tüm MFC uzantı dll 'Leri ve MFCxx.DLL arasında paylaşılır.

### <a name="building-an-mfc-extension-dll"></a>MFC uzantı DLL 'SI oluşturma

Bir MFC uzantı DLL projesi oluşturmak için AppWizard 'ı kullanabilirsiniz ve ilgili derleyici ve bağlayıcı ayarlarını otomatik olarak oluşturur. Ayrıca, değiştirebileceğiniz bir işlev de oluşturur `DllMain` .

Varolan bir projeyi bir MFC uzantı DLL 'sine dönüştürüyorsanız, MFC 'nin paylaşılan sürümünü kullanarak uygulama oluşturmaya yönelik standart kurallarla başlayın, ardından aşağıdakileri yapın:

- Derleyici bayraklarına **/D_AFXEXT** ekleyin. Proje Özellikleri iletişim kutusunda C/C++ düğümünü seçin. Sonra Önişlemci kategorisini seçin. `_AFXEXT`Öğelerin her birini noktalı virgülle ayırarak makroları tanımla alanına ekleyin.

- **/GY** derleyici anahtarını kaldırın. Proje Özellikleri iletişim kutusunda C/C++ düğümünü seçin. Ardından kod oluşturma kategorisini seçin. "Işlev düzeyinde bağlamayı etkinleştir" seçeneğinin etkin olmadığından emin olun. Bağlayıcı başvurulmayan işlevleri kaldıracağından, bu, sınıfların dışarı aktarılmasını kolaylaştırır. Özgün proje MFC 'ye statik olarak bağlanan normal bir MFC DLL oluşturmak için kullanılıyorsa **/MT [d]** derleyici seçeneğini **/md [d]** olarak değiştirin.

- BAĞLAMAK için **/DLL** seçeneğiyle bir dışarı aktarma kitaplığı oluşturun. Bu, yeni bir hedef oluşturduğunuzda, hedef türü olarak Win32 dinamik bağlantı kitaplığı belirterek ayarlanır.

### <a name="changing-your-header-files"></a>Üst bilgi dosyalarınızı değiştirme

MFC uzantı DLL 'SI, genellikle bazı yaygın işlevleri bu işlevselliği kullanan bir veya daha fazla uygulamaya dışarı aktarmak için kullanılır. Bu bobin, istemci uygulamalarınız için kullanılabilir olan sınıfları ve genel işlevleri dışarı aktarmaya yöneliktir.

Bunu yapmak için, her üye işlevinin uygun şekilde içeri veya dışarı aktarma olarak işaretlendiğinden emin olmanız gerekir. Özel bildirimler gerekir: `__declspec(dllexport)` ve `__declspec(dllimport)` . Sınıflarınız istemci uygulamalar tarafından kullanıldığında, olarak bildirilmesini istemeniz gerekir `__declspec(dllimport)` . MFC uzantı DLL 'SI oluşturulduğunda, olarak bildirilmelidir `__declspec(dllexport)` . Ayrıca, işlevler gerçekten aktarılmalıdır, böylece istemci programları bunlara yükleme zamanında bağlanır.

Tüm sınıfınızı dışarı aktarmak için, `AFX_EXT_CLASS` sınıf tanımında kullanın. Bu makro, ve tanımlandığı gibi Framework tarafından `__declspec(dllexport)` tanımlanır `_AFXDLL` `_AFXEXT` , ancak tanımsız olarak tanımlanır `__declspec(dllimport)` `_AFXEXT` . `_AFXEXT`Yukarıda açıklandığı gibi, yalnızca MFC uzantı DLL 'niz oluşturulurken tanımlanmıştır. Örnek:

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>Sınıfın tamamı dışarı aktarılmıyor

Bazen, sınıfınızın yalnızca tek gereken üyelerini dışarı aktarmak isteyebilirsiniz. Örneğin, bir `CDialog` türetilmiş sınıfı dışarı aktarıyorsanız, yalnızca oluşturucuyu ve çağrısını dışarı aktarmanız gerekebilir `DoModal` . Bu üyeleri DLL ' i kullanarak dışarı aktarabilirsiniz. , Ancak `AFX_EXT_CLASS` dışarı aktarmanız gereken tek tek üyelerde aynı şekilde de kullanabilirsiniz.

Örnek:

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

Bunu yaptığınızda, artık sınıfın tüm üyelerini dışarı aktaramadığı için ek bir sorunla karşılaşabilirsiniz. Sorun MFC makrolarının çalışma yoludur. MFC 'nin yardımcı makrolarının bazıları aslında veri üyelerini bildirir veya tanımlar. Bu nedenle, bu veri üyelerinin DLL 'nizden da verilmesi gerekecektir.

Örneğin, DECLARE_DYNAMIC makrosu MFC uzantı DLL 'SI oluşturulurken aşağıdaki gibi tanımlanır:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

"Static" başlayan çizgi, `AFX_DATA` sınıfınızın içinde statik bir nesne bildiriyor. Bu sınıfı doğru dışarı aktarıp bir istemciden çalışma zamanı bilgilerine erişin. EXE, bu statik nesneyi dışarı aktarmanız gerekir. Statik nesne değiştiriciyle bildirildiği `AFX_DATA` için, yalnızca `AFX_DATA` `__declspec(dllexport)` DLL 'nizi oluştururken ve bunu `__declspec(dllimport)` istemci yürütülebilir dosyanızı oluştururken olduğu gibi tanımlayarak tanımlamanız gerekir.

Yukarıda anlatıldığı gibi, `AFX_EXT_CLASS` Bu şekilde zaten tanımlanmış. `AFX_DATA`Sınıf tanımınızın etrafında aynı olacak şekilde yeniden tanımlamanız yeterlidir `AFX_EXT_CLASS` .

Örnek:

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

MFC her zaman `AFX_DATA` kendi makroları içinde tanımladığı veri öğelerinde sembolünü kullanır, bu nedenle bu teknik bu tür senaryolar için çalışacaktır. Örneğin, DECLARE_MESSAGE_MAP için çalışacaktır.

> [!NOTE]
> Sınıfın seçili üyeleri yerine sınıfının tamamını dışarı aktarıyorsanız statik veri üyeleri otomatik olarak dışarı aktarılabilir.

`CArchive`DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanan sınıfların ayıklama işlecini otomatik olarak dışarı aktarmak için aynı tekniği kullanabilirsiniz. Sınıf bildirimlerini ayraç içine alarak arşiv işlecini dışarı aktarın (içinde bulunur. H dosyası) aşağıdaki kodla:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXT sınırlamaları

MFC uzantı dll 'leri için _**afxext** ön işlemci sembolünü, birden çok mfc uzantısı DLL katmanınız olmadığı sürece kullanabilirsiniz. Kendi MFC uzantı dll 'larınızda bulunan ve daha sonra MFC sınıflarından türeten sınıfları çağıran MFC uzantı dll 'Leri varsa, karışıklığı önlemek için kendi önişlemci sembolünü kullanmanız gerekir.

Bu sorun, Win32 'de, bir DLL 'den aktarılmış gibi herhangi bir veriyi açıkça bildirmeniz `__declspec(dllexport)` ve `__declspec(dllimport)` bir dll 'den içeri aktarılmanız gerekir. Tanımladığınızda `_AFXEXT` , MFC üstbilgileri `AFX_EXT_CLASS` doğru şekilde tanımlandığından emin olur.

Birden çok katmanınız olduğunda, bir `AFX_EXT_CLASS` MFC uzantı DLL 'si yeni sınıfların dışarı aktarılmasının yanı sıra başka BIR MFC UZANTı dll 'den başka sınıflar içeri aktardığından, gibi bir sembol yeterli değildir. Bu sorunla başa çıkmak için dll 'yi kullanarak DLL 'nin kendisini oluşturduğunuzu belirten özel bir ön işlemci sembolünü kullanın. Örneğin, iki MFC uzantı dll 'si, A.DLL ve B.DLL düşünün. Her biri, sırasıyla bir. H ve B. H içindeki bazı sınıfları dışa aktarır. B.DLL, A.DLL sınıfları kullanır. Üst bilgi dosyaları şuna benzer:

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

A.DLL oluşturulduğunda, **/DA_IMPL** oluşturulur ve B.DLL oluşturulduğunda, **/DB_IMPL**ile oluşturulur. Her DLL için ayrı semboller kullanarak CExampleB aktarılır ve CExampleA B.DLL oluşturulurken içeri aktarılır. CExampleA, A.DLL oluşturulurken ve B.DLL (ya da başka bir istemci) kullanıldığında içeri aktarılırken içeri aktarılır.

Yerleşik `AFX_EXT_CLASS` ve önişlemci sembolleri kullanılırken bu tür katmanlama yapılamaz `_AFXEXT` . Yukarıda açıklanan teknik, MFC 'nin kendi OLE, veritabanı ve ağ MFC uzantı dll 'Lerini oluştururken kullandığı mekanizmanın aksine bir şekilde bu sorunu çözer.

### <a name="not-exporting-the-entire-class"></a>Sınıfın tamamı dışarı aktarılmıyor

Yine, bir sınıfın tamamını dışa aktarırken özel bir dikkat etmeniz gerekir. MFC makroları tarafından oluşturulan gerekli veri öğelerinin doğru şekilde verildiğinden emin olmanız gerekir. Bu, `AFX_DATA` özel sınıfınıza yönelik makroya yeniden tanımlayarak yapılabilir. Bu, tüm sınıfı dışarı aktardığınız zaman yapılmalıdır.

Örnek:

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

MFC uzantı DLL 'niz için ana kaynak dosyanıza yerleştirmeniz gereken tam kod aşağıda verilmiştir. Standart dahil edildikten sonra gelmelidir. Bir MFC uzantı DLL 'SI için başlangıç dosyaları oluşturmak üzere AppWizard kullandığınızda, `DllMain` sizin için bir sağlar.

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

İçin yapılan çağrı, `AfxInitExtensionModule` Modül çalışma zamanı sınıfları ( `CRuntimeClass` yapılar) ve nesne fabrikaları ( `COleObjectFactory` nesneler), daha sonra nesne oluşturulduğunda kullanılmak üzere yakalar `CDynLinkLibrary` . İçin (isteğe bağlı), MFC `AfxTermExtensionModule` `FreeLibrary` uzantı dll 'sinden her bir işlem ayrıldığında (işlem ÇıKTıĞıNDA veya dll bir çağrı sonucu olarak kaldırıldığında gerçekleşir) MFC uzantı dll 'sini temizlemesini sağlar. Çoğu MFC uzantı dll 'Leri dinamik olarak yüklenmediğinden (genellikle içeri aktarma kitaplıkları aracılığıyla bağlantılarlarsa), çağrısı `AfxTermExtensionModule` genellikle gerekli değildir.

Uygulamanız MFC uzantı dll 'Lerini dinamik olarak yükler ve serbest bırakır, yukarıda gösterildiği gibi çağırdığınızdan emin olun `AfxTermExtensionModule` . Ayrıca, `AfxLoadLibrary` `AfxFreeLibrary` `LoadLibrary` `FreeLibrary` uygulamanız birden çok iş parçacığı kullanıyorsa veya bir MFC uzantı dll 'sini dinamik olarak yüklerse, ve (Win32 işlevleri yerine) öğesini de ve `AfxLoadLibrary`Ve `AfxFreeLibrary` Yöntem kullanarak, MFC uzantı dll 'si yüklendiğinde ve kaldırıldığında çalıştırılan başlangıç ve kapalı kodu genel MFC durumunu bozmaz.

AFXDLLX üstbilgi dosyası. H, MFC uzantı dll 'Lerinde ve için tanım gibi kullanılan yapılar için özel tanımlar içerir `AFX_EXTENSION_MODULE` `CDynLinkLibrary` .

Genel *extensionDLL* gösterilen şekilde bildirilmelidir. MFC 'nin 16 bit sürümünden farklı olarak, MFCxx.DLL, bu süre boyunca bellek ayırabilir ve bu süre içinde çağrı yaparak MFC işlevlerini çağırabilirsiniz `DllMain` .

### <a name="sharing-resources-and-classes"></a>Kaynakları ve sınıfları paylaşma

Basit MFC uzantı dll 'Lerinin yalnızca birkaç düşük bant genişlikli işlevi istemci uygulamasına ve başka hiçbir şey uygulamasına ihtiyacı vardır. Daha fazla kullanıcı arabirimi yoğun dll 'Leri istemci uygulamasına kaynakları ve C++ sınıflarını dışarı aktarmak isteyebilir.

Kaynakları dışa aktarma bir kaynak listesi aracılığıyla yapılır. Her uygulamada, listedir bağlantılı bir nesne listesi bulunur `CDynLinkLibrary` . Kaynak ararken, kaynakları yükleyen standart MFC uygulamalarının çoğu, geçerli kaynak modülünde () önce görünür `AfxGetResourceHandle` ve bulunamazsa, `CDynLinkLibrary` istenen kaynağı yüklemeye çalışan nesnelerin listesini inceleyin.

C++ sınıf adı verilen C++ nesnelerinin dinamik oluşturulması benzerdir. MFC nesne seri durumundan çıkarma mekanizmasının, `CRuntimeClass` daha önce depolanmaya dayalı olarak gerekli türde C++ nesnesini dinamik olarak oluşturarak yeniden oluşturabilmesi için tüm nesneleri kayıtlı olması gerekir.

İstemci uygulamasının, MFC uzantı DLL 'inizdeki sınıfları kullanmasını istiyorsanız `DECLARE_SERIAL` , sınıflarınızı istemci uygulamasına görünür olacak şekilde dışarı aktarmanız gerekir. Bu, liste yürüyerek de yapılır `CDynLinkLibrary` .

MFC gelişmiş kavramlar örnek [DLLHUSK](../overview/visual-cpp-samples.md)örneğinde, liste şöyle görünür:

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

MFCxx.DLL genellikle kaynak ve sınıf listesinde en son bir yoldur. MFCxx.DLL tüm standart komut kimliklerinin istem dizeleri dahil olmak üzere tüm standart MFC kaynaklarını içerir. Listenin sonuna yerleştirilmesi dll 'Lerin ve istemci uygulamasının kendi standart MFC kaynaklarının kendi kopyasına sahip olmasa da, bunun yerine MFCxx.DLL paylaşılan kaynaklara güvenmelerini sağlar.

Tüm dll 'lerin kaynak ve sınıf adlarını istemci uygulamanın ad alanı içinde birleştirmek, hangi kimlikleri veya adları seçtiğiniz konusunda dikkatli olmanız gereken olumsuz bir şeydir. Kurs veya bir nesneyi istemci uygulamasına dışarı aktarıp bu özelliği devre dışı bırakabilirsiniz `CDynLinkLibrary` . [DLLHUSK](../overview/visual-cpp-samples.md) örneği, birden çok üstbilgi dosyası kullanarak paylaşılan kaynak adı alanını yönetir. Paylaşılan kaynak dosyalarını kullanma hakkında daha fazla ipucu için bkz. [teknik nota 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) .

### <a name="initializing-the-dll"></a>DLL başlatılıyor

Yukarıda belirtildiği gibi genellikle `CDynLinkLibrary` kaynak ve sınıflarınızı istemci uygulamasına dışarı aktarmak için bir nesne oluşturmak istersiniz. DLL 'yi başlatmak için bir içe aktarılmış giriş noktası sağlamanız gerekir. En düşük düzeyde, bu bir bağımsız değişken alan ve hiçbir şey döndüren void bir yordamdır, ancak istediğiniz herhangi bir şey olabilir.

Bu yaklaşımı kullanırsanız, DLL 'nizi kullanmak isteyen her bir istemci uygulamasının bu başlatma yordamını çağırması gerekir. Bu nesneyi, çağrıldıktan `CDynLinkLibrary` hemen sonra da ayırabilirsiniz `DllMain` `AfxInitExtensionModule` .

Başlatma yordamı, `CDynLinkLibrary` MFC UZANTı dll bilgilerine kablolu, geçerli uygulamanın yığınında bir nesne oluşturmalı. Bu, aşağıdakiler ile yapılabilir:

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

Bu örnekteki yordamın adı, *InitXxxDLL* , istediğiniz herhangi bir şey olabilir. **Extern "C"** olması gerekmez, ancak bunu yapmak dışa aktarma listesinin korunmasını kolaylaştırır.

> [!NOTE]
> MFC uzantı DLL 'nizi normal bir MFC DLL 'den kullanırsanız, bu başlatma işlevini dışarı aktarmanız gerekir. Herhangi bir MFC uzantısı DLL sınıfı veya kaynağı kullanılmadan önce bu işlevin normal MFC DLL 'sinden çağrılması gerekir.

### <a name="exporting-entries"></a>Girişleri dışarı aktarma

Sınıflarınızı dışarı aktarmanın basit yolu, `__declspec(dllimport)` `__declspec(dllexport)` dışarı aktarmak istediğiniz her bir sınıfta ve genel işlevde kullanılır. Bu, bu işlemi çok daha kolay hale getirir ancak her giriş noktasını (aşağıda açıklanmıştır) adlandırırken daha az verimlidir, ancak işlevleri sıraya göre dışarı aktaryükleyemezsiniz. TESTDLL1 ve TESTDLL2, girişlerini dışarı aktarmak için bu yöntemi kullanın.

Daha verimli bir Yöntem (ve MFCxx.DLL tarafından kullanılan yöntem), içindeki her girişi adlandırarak her bir girişi el ile dışarı aktarmamasıdır. DEF dosyası. DLL 'imizden seçmeli dışarı aktarmaları dışarı aktardığımız için (her şey değil), hangi belirli arabirimlerin dışarı aktarılacağını seçmemiz gerekir. Bu, içindeki girdiler formundaki bağlayıcı için karıştırılmış adları belirtmeniz gerektiğinden zordur. DEF dosyası. Gerçekten kendisi için bir sembolik bağlantısına sahip olmanız gerekmedikçe, hiçbir C++ sınıfını dışarı aktarmayın.

C++ sınıflarını ile dışarı aktarmaya çalıştıysanız. Daha önce, bu listeyi otomatik olarak oluşturmak için bir araç geliştirmek isteyebilirsiniz. Bu, iki aşamalı bir bağlantı işlemi kullanılarak yapılabilir. DLL 'nizi dışarı aktarımlar olmadan bir kez bağlayın ve bağlayıcının bir oluşturmasına izin verin. EŞLEME dosyası. İçin. EŞLEME dosyası, dışarı aktarılması gereken işlevlerin bir listesini oluşturmak için kullanılabilir. bu nedenle, bazı yeniden düzenleme işlemleri için dışarı aktarma girdilerinizi oluşturmak üzere kullanılabilir. DEF dosyası. MFCxx.DLL ve OLE ve veritabanı MFC uzantısı DLL 'Leri için dışa aktarma listesi, bu tür bir işlem ile oluşturulmuştur (tamamen otomatik olmasa da bir yandan her bir kez bir kez ayarlama gerektirir).

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp ve CDynLinkLibrary

MFC uzantı DLL 'sinin `CWinApp` kendi kendine türetilmiş bir nesnesi yoktur; Bunun yerine, `CWinApp` istemci uygulamasının türetilmiş nesnesiyle çalışması gerekir. Bu, istemci uygulamanın ana ileti göndericisi, boşta döngüsü vb. sahibi olduğu anlamına gelir.

MFC uzantı DLL 'nizin her bir uygulama için ek verileri tutması gerekiyorsa, öğesinden yeni bir sınıf türetebilir `CDynLinkLibrary` ve bunu yukarıdaki InitXxxDLL yordamında oluşturabilirsiniz. Çalışırken, DLL geçerli uygulamanın nesne listesini denetleyerek `CDynLinkLibrary` söz konusu mfc uzantısı DLL 'si için bir tane bulur.

### <a name="using-resources-in-your-dll-implementation"></a>DLL uygulamanızda kaynakları kullanma

Yukarıda belirtildiği gibi, varsayılan kaynak yükü, `CDynLinkLibrary` istenen kaynağa sahip Ilk exe veya dll 'yi arayan nesne listesini gösterecektir. Tüm MFC API 'Lerinin yanı sıra, tüm iç kod, `AfxFindResourceHandle` kaynak listesini nerede bulabileceğinizi fark etmeksizin kaynak listesini bulmak için kullanır.

Yalnızca belirli bir konumdan kaynak yüklemek istiyorsanız, API 'Leri kullanın `AfxGetResourceHandle` ve `AfxSetResourceHandle` eski tanıtıcıyı kaydedin ve yeni tanıtıcıyı ayarlayın. İstemci uygulamasına geri dönmek için eski kaynak tanıtıcısını geri yüklediğinizden emin olun. Örnek TESTDLL2, bir menüyü açıkça yüklemek için bu yaklaşımı kullanır.

Listenin yürümesi biraz daha yavaş olduğu ve kaynak KIMLIĞI aralıklarının yönetilmesi gereken dezavantajlara sahiptir. Birkaç MFC uzantı dll 'sine bağlantı sağlayan bir istemci uygulamasının, DLL örneği tanıtıcısını belirtmek zorunda kalmadan herhangi bir DLL tarafından sağlanmış kaynağı kullanabilmesi avantajına sahiptir. `AfxFindResourceHandle`, belirli bir eşleşmeyi aramak üzere kaynak listesini yürütirecek bir API 'dir. Bir kaynağın adını ve türünü alır ve ilk bulduğu kaynak tanıtıcısını (veya NULL) döndürür.

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>DLL sürümünü kullanan bir uygulama yazma

### <a name="application-requirements"></a>Uygulama gereksinimleri

MFC 'nin paylaşılan sürümünü kullanan bir uygulama, birkaç basit kurala uymalıdır:

- Bir `CWinApp` nesnesi olmalıdır ve ileti göndericisinin standart kurallarını izlemelidir.

- Bir gerekli derleyici bayrakları kümesiyle derlenmesi gerekir (aşağıya bakın).

- MFCxx içeri aktarma kitaplıklarıyla bağlantı gerekir. Gerekli derleyici bayraklarını ayarlayarak, MFC üstbilgileri uygulamanın bağlanması gereken kitaplığı bağlantı zamanına göre belirlenir.

- Yürütülebilir dosyayı çalıştırmak için MFCxx.DLL yolda veya Windows sistem dizininde olmalıdır.

### <a name="building-with-the-development-environment"></a>Geliştirme ortamıyla derleme

Standart varsayılanların çoğu ile iç derleme görevleri dosyasını kullanıyorsanız, projeyi DLL sürümünü oluşturmak için kolayca değiştirebilirsiniz.

Aşağıdaki adım, NAFXCWD ile bağlantılı bir MFC uygulamasının düzgün çalıştığını varsayar. LIB (hata ayıklama için) ve NAFXCW. LIB (perakende için) ve MFC kitaplığının paylaşılan sürümünü kullanacak şekilde dönüştürmek istiyorsunuz. Visual C++ ortamını çalıştırıyorsunuz ve dahili bir proje dosyasına sahipsiniz.

1. **Projeler** menüsünde, **Özellikler**' e tıklayın. **Proje Varsayılanları**altındaki **genel** sayfasında, Microsoft Foundation sınıfları **paylaşılan bir dll 'de MFC kullanacak** şekilde ayarlayın (MFCxx (d). dll).

### <a name="building-with-nmake"></a>NMAKE ile derleme

Visual C++ dış makefile özelliğini kullanıyorsanız veya NMAKE doğrudan kullanıyorsa, derleme görevleri dosyasını derleyici ve bağlayıcı seçeneklerini destekleyecek şekilde düzenlemeniz gerekir

Gerekli derleyici bayrakları:

- **/D_AFXDLL/MD** 
   **/D_AFXDLL**

Standart MFC üstbilgilerinin tanımlanması için bu sembolün olması gerekir:

- **/Md** Uygulamanın, C çalışma zamanı kitaplığının DLL sürümünü kullanması gerekir

Diğer tüm derleyici bayrakları MFC varsayılanlarını (örneğin, hata ayıklama için _DEBUG) izler.

Kitaplıkların bağlayıcı listesini düzenleyin. NAFXCWD öğesini değiştirin. LIB ile MFCxxD. LIB ve NAFXCW değiştirin. LıB to MFCxx. LIB. LIBC 'yi değiştirin. MSVCRT ile LIB. LIB. Diğer herhangi bir MFC kitaplığında olduğu gibi, MFCxxD. LIB ' in herhangi bir C-Runtime kitaplığı 'ndan **önce** yerleştirilmesi önemlidir.

İsteğe bağlı olarak, hem perakende hem de hata ayıklama kaynak derleyicisi seçeneklerinizin (bu kaynakları **/r**ile derlediğinde) ekleme **/D_AFXDLL** . Bu, MFC DLL 'Lerinde bulunan kaynakları paylaşarak son yürütülebilir dosyanızı daha küçük hale getirir.

Bu değişiklikler yapıldıktan sonra tam yeniden oluşturma gereklidir.

### <a name="building-the-samples"></a>Örnekleri oluşturma

MFC örnek programlarının çoğu, komut satırından Visual C++ veya paylaşılan bir NMAKE uyumlu derleme görevleri dosyası içinden oluşturulabilir.

Bu örneklerden herhangi birini MFCxx.DLL kullanacak şekilde dönüştürmek için, ' yi yükleyebilirsiniz. MAK dosyasını Visual C++ ve yukarıda açıklandığı gibi proje seçeneklerini ayarlayın. NMAKE derlemesini kullanıyorsanız, NMAKE komut satırında "AFXDLL = 1" belirtebilir ve paylaşılan MFC kitaplıklarını kullanarak örneği oluşturacaksınız.

MFC gelişmiş kavramlar örnek [DLLHUSK](../overview/visual-cpp-samples.md) , MFC 'nin dll sürümü ile oluşturulmuştur. Bu örnek yalnızca MFCxx.DLL ile bağlantılı bir uygulamanın nasıl oluşturulduğunu gösterir, ancak aynı zamanda bu teknik notun ilerleyen kısımlarında açıklanan MFC uzantı dll 'Leri gibi MFC DLL paketleme seçeneğinin diğer özelliklerini gösterir.

### <a name="packaging-notes"></a>Paketleme notları

Dll 'lerin perakende sürümü (MFCxx [U]. DLL) ücretsiz olarak yeniden dağıtılabilir. Dll 'lerin hata ayıklama sürümü, serbestçe yeniden dağıtılabilir değildir ve yalnızca uygulamanızın geliştirilmesi sırasında kullanılmalıdır.

Hata ayıklama dll 'Leri hata ayıklama bilgileri ile sağlanır. Visual C++ hata ayıklayıcısını kullanarak, uygulamanızın yürütülmesini ve DLL dosyasını da izleyebilirsiniz. Sürüm dll 'Leri (MFCxx [U]. DLL) hata ayıklama bilgisi içermez.

Dll 'Leri özelleştirir veya yeniden oluşturursanız, bunları "MFCxx" yerine bir hata olarak çağırmanız gerekir MFCDLL. MAK derleme seçeneklerini açıklar ve DLL 'yi yeniden adlandırma mantığını içerir. Bu dll 'Ler birçok MFC uygulaması tarafından paylaşıldığından dosyaların yeniden adlandırılması gerekir. MFC DLL 'lerinin özel sürümünüzün, sistemdeki yüklü olanların yerini alacak, paylaşılan MFC DLL 'Lerini kullanarak başka bir MFC uygulamasını bozabilir.

MFC DLL 'Lerinin yeniden oluşturulması önerilmez.

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>MFCxx.DLL nasıl uygulanır

Aşağıdaki bölümde, MFC DLL 'sinin (MFCxx.DLL ve MFCxxD.DLL) nasıl uygulandığı açıklanmaktadır. Buradaki ayrıntıları anlamak, uygulamanız ile MFC DLL 'i kullanmak istiyorsanız da önemli değildir. Buradaki ayrıntılar, bir MFC uzantısı DLL dosyasının nasıl yazılacağını anlamak için gerekli değildir, ancak bu uygulamayı anlamak kendi DLL 'nizi yazmanıza yardımcı olabilir.

### <a name="implementation-overview"></a>Uygulamaya genel bakış

MFC DLL 'SI, yukarıda açıklandığı gibi bir MFC uzantı DLL 'inin gerçekten özel bir durumdur. Çok sayıda sınıf için çok sayıda dışarı aktarmaları vardır. MFC DLL 'de, normal MFC uzantısı DLL ' den daha da çok özel hale yaptığımız birkaç ek şey vardır.

### <a name="win32-does-most-of-the-work"></a>Win32, Işin çoğunu

MFC 'nin 16 bit sürümü, yığın kesimindeki uygulama başına verileri, bazı 80x86 derleme kodu tarafından oluşturulan özel kesimleri, işlem başına özel durum bağlamlarını ve diğer teknikleri içeren bir dizi özel tekniği gerekli değildir. Win32, bir DLL 'de işlem başına verileri doğrudan destekler, bu da çoğu zaman istediğiniz şeydir. Çoğu bölüm için MFCxx.DLL yalnızca NAFXCW ' dir. DLL içinde LıB paketlenmiş. MFC kaynak koduna bakarsanız, yapılması gereken çok az sayıda özel durum olduğundan çok az sayıda #ifdef _AFXDLL bulacaksınız. Özellikle Windows 3,1 (örneğin, Win32s olarak bilinir) üzerinde Win32 ile başa çıkmak için olan özel durumlar. Win32s, işlem başına DLL verilerini doğrudan desteklemez. böylece, MFC DLL 'nin işlem yerel verilerini almak için iş parçacığı yerel depolama (TLS) Win32 API 'Lerini kullanması gerekir.

### <a name="impact-on-library-sources-additional-files"></a>Kitaplık kaynakları, ek dosyalar üzerindeki etki

Normal MFC sınıf kitaplığı kaynakları ve üst bilgilerinde **_AFXDLL** sürümünün etkisi nispeten daha düşük. Özel bir sürüm dosyası (AFXV_DLL) vardır. H) ek bir üst bilgi dosyası da (AFXDLL_. H) ana AFXWıN tarafından dahil edilmiştir. H üst bilgisi. AFXDLL_. H üstbilgisi, `CDynLinkLibrary` hem uygulama hem de `_AFXDLL` MFC uzantı dll 'lerinin sınıfını ve diğer uygulama ayrıntılarını içerir. AFXDLLX. R üst bilgisi, MFC uzantı dll 'Leri oluşturmak için sağlanır (Ayrıntılar için yukarıya bakın).

MFC SRC 'deki MFC kitaplığına yönelik normal kaynaklar #ifdef altında bazı ek koşullu koda sahiptir `_AFXDLL` . Ek bir kaynak dosyası (DLLINIT. CPP), ek DLL başlatma kodunu ve MFC 'nin paylaşılan sürümüne yönelik diğer tutkalla içerir.

MFC 'nin paylaşılan sürümünü oluşturmak için ek dosyalar sağlanır. (DLL oluşturma hakkında ayrıntılı bilgi için aşağıya bakın.)

- İkiye. DEF dosyaları, DLL 'nin hata ayıklama (MFCxxD. DEF) ve Release (MFCxx. DEF) sürümleri için MFC DLL giriş noktaları dışarı aktarmak için kullanılır.

- Kızılötesi. RC dosyası (MFCDLL. RC), DLL için tüm standart MFC kaynaklarını ve VERSIONıNFO kaynağını içerir.

- A. CLW dosyası (MFCDLL. CLW), ClassWizard kullanarak MFC sınıflarına göz atmaya izin vermek için sağlanır. Not: Bu özellik MFC 'nin DLL sürümüne özgü değildir.

### <a name="memory-management"></a>Bellek Yönetimi

MFCxx.DLL kullanan bir uygulama, paylaşılan C-Runtime DLL 'SI MSVCRTxx.DLL tarafından sunulan ortak bir bellek ayırıcısını kullanır. Uygulama, tüm MFC uzantı dll 'Leri ve MFC DLL 'Lerinin kendisi bu paylaşılan bellek ayırıcısını kullanır. Bellek ayırma için paylaşılan bir DLL kullanarak, MFC DLL 'Leri daha sonra uygulama tarafından serbest bırakılan veya tam tersi bellek ayırabilir. Hem uygulama hem de DLL aynı ayırıcıyı kullanması gerektiğinden, C++ Global **işleci New** veya **operator delete**' i geçersiz kılmamalıdır. Aynı kurallar C çalışma zamanı bellek ayırma yordamlarının geri kalanı için geçerlidir ( **malloc**, **realloc**, **ücretsiz**ve diğerleri gibi).

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>Sıra sayıları ve sınıf __declspec (dllexport) ve DLL adlandırması

`class` **`__declspec(dllexport)`** C++ derleyicisinin işlevlerini kullanmıyoruz. Bunun yerine, bir dışarı aktarma listesi sınıf kitaplığı kaynaklarına (MFCxx. DEF ve MFCxxD. DEF) dahildir. Yalnızca bu seçim giriş noktaları kümesi (işlevler ve veriler) verilir. MFC özel uygulama işlevleri veya sınıfları gibi diğer semboller dışa aktarılmaz tüm dışarı aktarmalar, yerleşik veya yerleşik olmayan ad tablosunda dize adı olmadan sıralı olarak yapılır.

Kullanmak `class` **`__declspec(dllexport)`** , daha küçük dll 'ler oluşturmak için uygun bir alternatif olabilir, ancak MFC gibi büyük bir dll söz konusu olduğunda, varsayılan dışa aktarma mekanizması verimlilik ve kapasite sınırlarına sahiptir.

Bu tümünün anlamı, büyük miktarda yürütme veya yükleme hızına ödün vermeden 800 KB 'lık sürüm MFCxx.DLL çok sayıda işlevselliği paketleyebileceğiniz anlamına gelir. MFCxx.DLL 100K daha büyük olabilir ve bu teknik kullanılmadı. Bu Ayrıca, sonunda ek giriş noktaları eklemeyi olanaklı hale getirir. DEF dosyası, sıralı olarak dışa aktarmanın hız ve boyut verimliliğine ödün vermeden basit sürüm oluşturmaya izin vermek için. MFC sınıf kitaplığındaki ana sürüm düzeltmeleri kitaplık adını değiştirecek. Diğer bir deyişle MFC30.DLL, MFC sınıf kitaplığının 3,0 sürümünü içeren yeniden dağıtılabilir DLL 'dir. Bu DLL 'nin bir yükseltmesi olan, bir kuramsal MFC 3,1 ' de, DLL bunun yerine MFC31.DLL olarak adlandırılır. MFC DLL 'nin özel bir sürümünü oluşturmak için MFC kaynak kodunu değiştirirseniz, farklı bir ad (ve tercihen "MFC" adında "MFC" olmadan) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
