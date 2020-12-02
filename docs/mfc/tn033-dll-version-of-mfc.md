---
title: "TN033: MFC'nin DLL Sürümü"
description: MFC uygulamaları ve MFC uzantı dll 'Leri ile MFC paylaşılan dinamik bağlantı kitaplıklarını nasıl kullanacağınızı gösterir.
ms.date: 11/30/2020
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.openlocfilehash: b9330fe7c756f962a8b06a04b840bfda343f3a49
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440319"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC'nin DLL Sürümü

Bu notta, *`MFCxx.DLL`* *`MFCxxD.DLL`* MFC UYGULAMALARı ve MFC uzantı dll 'leri ile ve ( *xx* MFC sürüm numarası) paylaşılan dinamik bağlantı kitaplıklarını nasıl kullanabileceğinizi açıklar. Normal MFC DLL 'Leri hakkında daha fazla bilgi için bkz. [MFC 'YI dll 'nin bir parçası olarak kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md).

Bu teknik notta, dll 'lerin üç yönü ele alınmaktadır. Son iki, daha ileri düzey kullanıcılara yöneliktir:

- [MFC uzantı DLL 'i oluşturma](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC 'nin DLL sürümünü kullanan bir MFC uygulaması oluşturma](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC paylaşılan dinamik bağlantı kitaplıkları nasıl uygulanır](#_mfcnotes_how_the_mfc30.dll_is_implemented)

MFC 'yi kullanarak MFC olmayan uygulamalarla kullanılabilecek bir DLL oluşturmaya ilgileniyorsanız ( *normal MFC DLL* olarak bilinir), [teknik notta 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)' e bakın.

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL desteğe genel bakış: terminoloji ve dosyalar

**Normal MFC DLL**: MFC sınıflarından bazılarını kullanarak tek başına dll oluşturmak IÇIN normal MFC DLL kullanırsınız. Uygulama/DLL sınırının içindeki arabirimler "C" arabirimlerdir ve istemci uygulamasının bir MFC uygulaması olması gerekmez.

Normal MFC DLL 'Leri MFC 1,0 ' de desteklenen dll 'lerin sürümüdür. Bunlar [teknik notta 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) ve mfc Gelişmiş kavramlar örneğinde açıklanırlar [`DLLScreenCap`](../overview/visual-cpp-samples.md) .

> [!NOTE]
> Visual C++ sürüm 4,0 itibariyle, **USRDLL** terimi kullanımdan KALDıRıLMıŞTıR ve MFC 'ye statik olarak bağlanan normal BIR mfc dll ile değiştirilmiştir. MFC 'ye dinamik olarak bağlanan normal bir MFC DLL de oluşturabilirsiniz.

MFC 3,0 (ve üzeri), OLE ve veritabanı sınıfları dahil olmak üzere tüm yeni işlevlerle normal MFC DLL 'Lerini destekler.

**AFXDLL**: MFC kitaplıklarının paylaşılan sürümü olarak da adlandırılır. Bu, MFC 2,0 ' de yeni DLL desteği eklenmiştir. MFC kitaplığı bir dizi dll 'de (aşağıda açıklanmıştır). İstemci uygulaması veya DLL, gerektirdiği dll 'Leri dinamik olarak bağlar. Uygulama/DLL sınırı içindeki arabirimler C++/MFC sınıf arabirimlerdir. İstemci uygulaması bir MFC uygulaması OLMALıDıR. Bu DLL tüm MFC 3,0 işlevselliğini destekler (özel durum: UNICODE, veritabanı sınıfları için desteklenmez).

> [!NOTE]
> Visual C++ sürüm 4,0 itibariyle, bu tür DLL 'nin "uzantı DLL" olarak adlandırılmaktadır.

Bu notta *`MFCxx.DLL`* , şunlar da dahil olmak üzere tüm MFC DLL kümesine başvurmak için kullanılır:

- Hata Ayıkla: *`MFCxxD.DLL`* (Birleşik) ve *`MFCSxxD.LIB`* (statik).

- Yayın: *`MFCxx.DLL`* (birleştirilmiş) ve *`MFCSxx.LIB`* (statik).

- Unicode hata ayıklama: *`MFCxxUD.DLL`* (birleştirilmiş) ve *`MFCSxxD.LIB`* (statik).

- Unicode sürümü: *`MFCxxU.DLL`* (birleştirilmiş) ve *`MFCSxxU.LIB`* (statik).

> [!NOTE]
> *`MFCSxx[U][D].LIB`* KITAPLıKLAR MFC paylaşılan DLL 'leriyle birlikte kullanılır. Bu kitaplıklar, uygulamaya veya DLL 'ye statik olarak bağlı olması gereken kodu içerir.

Uygulama, ilgili içeri aktarma kitaplıklarına bağlanır:

- H *`MFCxxD.LIB`*

- Yayın *`MFCxx.LIB`*

- Unicode hata ayıklama: *`MFCxxUD.LIB`*

- Unicode sürümü: *`MFCxxU.LIB`*

*MFC UZANTı dll* 'si *`MFCxx.DLL`* (veya diğer mfc paylaşılan DLL 'leri) genişleten bir dll 'dir. Burada MFC bileşen mimarisi ' de açılır. Bir MFC sınıfından faydalı bir sınıf türetirsiniz veya başka bir MFC benzeri araç seti oluşturursanız, bunu bir DLL 'ye yerleştirebilirsiniz. DLL 'niz *`MFCxx.DLL`* , en son istemci uygulaması gibi kullanır. MFC uzantısı DLL yeniden kullanılabilir yaprak sınıflarına, yeniden kullanılabilir temel sınıflara ve yeniden kullanılabilir görünüm ve belge sınıflarına izin verir.

## <a name="pros-and-cons"></a>Profesyonelleri ve dezavantajları

Neden MFC 'nin paylaşılan sürümünü kullanmalıyım?

- Paylaşılan kitaplığın kullanılması, daha küçük uygulamalara neden olabilir. (MFC kitaplığının çoğunu kullanan en az bir uygulama 10.000 'den azdır).

- MFC 'nin paylaşılan sürümü MFC uzantı dll 'Lerini ve normal MFC DLL 'Lerini destekler.

- Statik olarak bağlanmış MFC uygulamasından paylaşılan MFC kitaplıklarını kullanan bir uygulama oluşturmak daha hızlıdır. Bunun nedeni, MFC 'nin kendisini bağlamak gerekli değildir. Bu **`DEBUG`** , bağlayıcının hata ayıklama bilgilerini sıkıştıracağı derlemeler için de geçerlidir. Uygulamanız, hata ayıklama bilgilerini zaten içeren bir DLL 'ye bağlandığında, sıkıştırmak için daha az hata ayıklama bilgisi vardır.

Neden MFC 'nin paylaşılan sürümünü kullanmamalısınız:

- Paylaşılan kitaplığı kullanan bir uygulamayı teslim etmek, *`MFCxx.DLL`* programınıza ve diğer kitaplıkları sizin için sevk etmeniz gerekir. *`MFCxx.DLL`* birçok dll gibi serbestçe yeniden dağıtılabilir, ancak yine de DLL 'yi kurulum programınıza yüklemelisiniz. Ayrıca, hem programınız hem de MFC DLL 'Leri tarafından kullanılan diğer yeniden dağıtılabilir kitaplıkları da teslim etmeniz gerekir.

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> MFC uzantı DLL yazma

MFC uzantı DLL 'si, MFC sınıflarının işlevlerini genişletmek için sınıflar ve işlevler içeren bir DLL 'dir. MFC uzantı DLL 'SI, paylaşılan MFC DLL 'Lerini bir uygulamanın kullandığı şekilde kullanır, bazı ek noktalara sahiptir:

- Yapı işlemi, birkaç ek derleyici ve bağlayıcı seçeneği ile paylaşılan MFC kitaplıklarını kullanan bir uygulama oluşturmaya benzer.

- MFC uzantı DLL 'sinin `CWinApp` türetilmiş sınıfı yok.

- MFC uzantı DLL 'SI özel bir sağlamalıdır `DllMain` . AppWizard, `DllMain` değiştirebileceğiniz bir işlev sağlar.

- MFC uzantı dll 'si, bir MFC `CDynLinkLibrary` UZANTıSı dll, `CRuntimeClass` uygulamaya türleri veya kaynakları dışarı aktardığında, genellikle oluşturmak için bir başlatma yordamı sağlar. `CDynLinkLibrary`Uygulama başına VERILERIN MFC UZANTıSı dll 'i tarafından tutulması gerekiyorsa türetilmiş bir sınıfı kullanılabilir.

Bu konular aşağıda daha ayrıntılı olarak açıklanmıştır. Ayrıca MFC gelişmiş kavramlar örneğine bakın [`DLLHUSK`](../overview/visual-cpp-samples.md) . Şunu gösterir:

- Paylaşılan kitaplıkları kullanarak bir uygulama oluşturun. ( *`DLLHUSK.EXE`* MFC kitaplıklarına ve diğer dll 'lere dinamik olarak bağlanan BIR MFC uygulamasıdır.)

- MFC uzantı DLL 'SI oluşturun. ( `_AFXEXT` MFC UZANTıSı DLL oluştururken kullanılan özel bayrakların nasıl kullanıldığını gösterir.)

- MFC uzantı dll 'lerinin iki örneğini oluşturun. Bir MFC uzantı DLL 'inin, sınırlı dışarı aktarmalar (TESTDLL1) ile temel yapısını gösterir ve diğer bir sınıf arabiriminin (TESTDLL2) dışa aktarılması anlamına gösterilir.

Hem istemci uygulaması hem de MFC uzantı dll 'Lerinin aynı sürümünü kullanması gerekir *`MFCxx.DLL`* . MFC DLL 'Lerinin kurallarını izleyin ve MFC uzantı DLL 'nizin hem hata ayıklama hem de sürüm ( **`/release`** ) sürümünü sağlayın. Bu uygulama, istemci programlarının uygulamalarının hata ayıklama ve sürüm sürümlerini oluşturmasına ve bunları tüm dll 'lerin uygun hata ayıklama veya yayın sürümüyle bağlanmasına izin verir.

> [!NOTE]
> C++ ad değiştirmeyi ve dışa aktarma sorunları nedeniyle, bir MFC uzantısı DLL 'sinden dışarı aktarma listesi, farklı platformlar için aynı DLL ve DLL 'lerin hata ayıklama ve sürüm sürümleri arasında farklı olabilir. Yayında *`MFCxx.DLL`* 2000 'ye aktarılmış giriş noktası bulunur; hata ayıklama, *`MFCxxD.DLL`* 3000 ile ilgili giriş noktaları hakkında bilgi içerir.

### <a name="quick-note-on-memory-management"></a>Bellek yönetimine hızlı bir şekilde göz

Bu teknik notun sonundaki "bellek yönetimi" başlıklı Bölüm, uygulamasının *`MFCxx.DLL`* paylaşılan BIR MFC sürümü ile uygulanmasını açıklar. Yalnızca bir MFC uzantı DLL 'sini uygulamak için bilmeniz gereken bilgiler burada açıklanmıştır.

*`MFCxx.DLL`* ve bir istemci uygulamasının adres alanına yüklenen tüm MFC uzantı dll 'Leri aynı uygulama gibi aynı bellek ayırıcı, kaynak yükleme ve diğer MFC "genel" durumlarını kullanır. MFC olmayan DLL kitaplıkları ve MFC 'ye statik olarak bağlanan normal MFC DLL 'Lerinin tam tersini yaptığı için bu önemlidir: her DLL kendi bellek havuzunu ayırır.

Bir MFC uzantısı DLL 'SI bellek ayırırsa, bu bellek, uygulama tarafından ayrılan diğer herhangi bir nesneyle serbestçe ayrılabilir. Ayrıca, paylaşılan MFC kitaplıklarını kullanan bir uygulama kilitlenirse, işletim sistemi DLL 'yi paylaşan diğer MFC uygulamalarının bütünlüğünü korur.

Benzer şekilde, kaynakları yüklemek için geçerli yürütülebilir dosya gibi diğer "Global" MFC durumları, istemci uygulaması, tüm MFC uzantı dll 'Leri ve kendisi arasında da paylaşılır *`MFCxx.DLL`* .

### <a name="building-an-mfc-extension-dll"></a>MFC uzantı DLL 'SI oluşturma

Bir MFC uzantı DLL projesi oluşturmak için AppWizard 'ı kullanabilirsiniz ve uygun derleyici ve bağlayıcı ayarlarını otomatik olarak oluşturur. Ayrıca, değiştirebileceğiniz bir `DllMain` işlev oluşturur.

Var olan bir projeyi bir MFC uzantı DLL 'sine dönüştürüyorsanız, MFC 'nin paylaşılan sürümünü kullanarak yapı oluşturan standart ayarlarla başlayın. Ardından aşağıdaki değişiklikleri yapın:

- **`/D_AFXEXT`** Derleyici bayraklarına ekleyin. Proje Özellikleri iletişim kutusunda **C/C++**  >  **Önişlemci** kategorisini seçin. `_AFXEXT`Öğelerin her birini noktalı virgülle ayırarak **makroları tanımla** alanına ekleyin.

- **`/Gy`** Derleyici anahtarını kaldırın. Proje Özellikleri iletişim kutusunda **C/C++**  >  **kod üretimi** kategorisini seçin. **Function-Level bağlamayı etkinleştir** özelliğinin etkin olmadığından emin olun. Bağlayıcı başvurulmayan işlevleri kaldırmadığından, bu ayar sınıfların dışarı aktarılmasını kolaylaştırır. Özgün proje MFC 'ye statik olarak bağlanan normal bir MFC DLL 'SI derlenip **`/MT`** (veya) **`/MTd`** derleyici seçeneğini **`/MD`** (veya) olarak değiştirin **`/MDd`** .

- BAĞLAMA seçeneğiyle bir dışarı aktarma kitaplığı oluşturun **`/DLL`** . Bu seçenek, yeni bir hedef oluşturduğunuzda ve hedef türü olarak Win32 Dynamic-Link kitaplığı belirttiğinizde ayarlanır.

### <a name="changing-your-header-files"></a>Üst bilgi dosyalarınızı değiştirme

MFC uzantısı DLL 'nin olağan hedefi, bazı yaygın işlevleri bu işlevselliği kullanan bir veya daha fazla uygulamaya dışarı aktarmaktır. Temel olarak, DLL sınıfları ve genel işlevleri istemci uygulamalarınız tarafından kullanılmak üzere dışarı aktarır.

Her üye işlevin uygun şekilde içeri veya dışarı aktarma için işaretlendiğinden emin olmak için özel bildirimleri `__declspec(dllexport)` ve kullanın `__declspec(dllimport)` . İstemci uygulamaları sınıflarınızı kullandıklarında, olarak bildirilmesini istemeniz gerekir `__declspec(dllimport)` . MFC uzantı DLL 'sinin kendisi yapılandırıldığında, işlevleri olarak bildirilmelidir `__declspec(dllexport)` . İstemci programlarının yükleme zamanında bağlanabilmesi için, oluşturulan DLL 'nin işlevleri de dışarı aktarmanız gerekir.

Tüm sınıfınızı dışarı aktarmak için, `AFX_EXT_CLASS` sınıf tanımında kullanın. Framework bu makroyu `__declspec(dllexport)` `_AFXDLL` , ve tanımlandığı gibi tanımlar `_AFXEXT` , ancak `__declspec(dllimport)` `_AFXEXT` tanımlanmadığında olarak tanımlar. `_AFXEXT` yalnızca MFC uzantı DLL 'niz oluşturulurken tanımlanmıştır. Örnek:

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>Sınıfın tamamı dışarı aktarılmıyor

Bazen, sınıfınızın yalnızca tek gereken üyelerini dışarı aktarmak isteyebilirsiniz. Örneğin, bir türetilmiş sınıfı dışarı aktardığınızda `CDialog` , yalnızca oluşturucuyu ve çağrısını dışarı aktarmanız gerekebilir `DoModal` . Bu üyeleri DLL 'nin DEF dosyasını kullanarak dışarı aktarabilirsiniz, ancak `AFX_EXT_CLASS` aynı zamanda dışarı aktarmanız gereken ayrı üyelerde aynı şekilde kullanabilirsiniz.

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

Bunu yaptığınızda, sınıfın tüm üyelerini dışarı aktarmazsanız ek bir sorunla karşılaşabilirsiniz. Sorun MFC makrolarının çalışma yoludur. MFC 'nin yardımcı makrolarının bazıları aslında veri üyelerini bildirir veya tanımlar. DLL 'nizin bu veri üyelerini de dışarı aktarmanız gerekir.

Örneğin, DECLARE_DYNAMIC makrosu MFC uzantı DLL 'SI oluşturulurken aşağıdaki gibi tanımlanır:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

Başlangıç satırı, `static AFX_DATA` sınıfınızın içinde statik bir nesne bildirir. Bu sınıfı doğru dışarı aktarmak ve bir istemci EXE 'sinden çalışma zamanı bilgilerine erişmek için bu statik nesneyi dışarı aktarmanız gerekir. Statik nesne değiştiriciyle bildirildiği `AFX_DATA` için, yalnızca `AFX_DATA` `__declspec(dllexport)` DLL 'nizi oluştururken olarak tanımlamanız gerekir. `__declspec(dllimport)`İstemci yürütülebilir dosyanızı oluştururken olarak tanımlayın.

Yukarıda anlatıldığı gibi, `AFX_EXT_CLASS` Bu şekilde zaten tanımlanmış. Yalnızca `AFX_DATA` sınıf tanımınızın etrafında olacak şekilde yeniden tanımlamanız gerekir `AFX_EXT_CLASS` .

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

`CArchive`DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanan sınıfların ayıklama işlecini otomatik olarak dışarı aktarmak için aynı tekniği kullanabilirsiniz. Sınıf bildirimlerini (başlık dosyasında bulunur) aşağıdaki kodla birleştirerek arşiv işlecini dışarı aktarın:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXT sınırlamaları

MFC uzantı dll 'lerinin `_AFXEXT` birden çok katmanınız olmadığı sürece MFC uzantı dll 'lerinizin ön işlemci simgesini kullanabilirsiniz. Kendi MFC uzantı dll 'larınızda bulunan ve daha sonra MFC sınıflarından türeten sınıfları çağıran MFC uzantı dll 'Leri varsa, karışıklığı önlemek için kendi önişlemci sembolünü kullanmanız gerekir.

Bu sorun, Win32 'de, `__declspec(dllexport)` BIR DLL 'den dışarı aktarmak ve `__declspec(dllimport)` bir dll 'den içeri aktarmak üzere herhangi bir veriyi açık bir şekilde bildirmeniz gerekir. Tanımladığınızda `_AFXEXT` , MFC üstbilgileri `AFX_EXT_CLASS` doğru şekilde tanımlandığından emin olur.

Birden çok katmanınız olduğunda, gibi bir sembol `AFX_EXT_CLASS` yeterlidir: BIR MFC uzantı DLL 'si kendi sınıflarını dışarı aktarabilir ve ayrıca başka BIR MFC UZANTı dll 'den diğer sınıfları içeri aktarabilir. Bu sorunla başa çıkmak için DLL 'yi kullanmak yerine DLL 'nin kendisini oluşturduğunuzu belirten özel bir ön işlemci sembolünü kullanın. Örneğin, iki adet MFC uzantı dll 'si, *`A.DLL`* ve, düşünün *`B.DLL`* . Bunlar *`A.H`* , sırasıyla ve içindeki bazı sınıfları dışa aktarır *`B.H`* . *`B.DLL`* sınıfından sınıfları kullanır *`A.DLL`* . Üst bilgi dosyaları şuna benzer:

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

*`A.DLL`* İnşa edildiğinde, ile oluşturulmuştur **`/DA_IMPL`** ve *`B.DLL`* , ile oluşturulmuştur **`/DB_IMPL`** . Her DLL için ayrı semboller kullanarak, `CExampleB` `CExampleA` derleme sırasında içeri aktarılır ve içeri aktarılır *`B.DLL`* . `CExampleA` , *`A.DLL`* *`B.DLL`* veya diğer bir istemci tarafından kullanıldığında derleme ve içeri aktarma sırasında aktarılır.

Yerleşik `AFX_EXT_CLASS` ve önişlemci sembolleri kullanılırken bu tür katmanlama yapılamaz `_AFXEXT` . Yukarıda açıklanan teknikte bu sorun MFC tarafından aynı şekilde çözülemez. MFC, OLE, veritabanı ve ağ MFC uzantı dll 'Lerini oluştururken bu tekniği kullanır.

### <a name="not-exporting-the-entire-class"></a>Sınıfın tamamı dışarı aktarılmıyor

Yine, bir sınıfın tamamını dışa aktarırken özel bir dikkat etmeniz gerekir. MFC makroları tarafından oluşturulan gerekli veri öğelerinin doğru şekilde aktarıldığından emin olun. Özel sınıfınızın makrosunu yeniden tanımlayarak bunu yapabilirsiniz `AFX_DATA` . Tüm sınıfı dışarı aktarıyorsanız her seferinde yeniden tanımlama.

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

MFC uzantı DLL 'niz için ana kaynak dosyanıza yerleştirmeniz gereken kod aşağıda verilmiştir. Standart dahil edildikten sonra gelmelidir. Bir MFC uzantı DLL 'SI için başlangıç dosyaları oluşturmak üzere AppWizard kullandığınızda, sizin için bir sağlar `DllMain` .

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

İçin yapılan çağrı, `AfxInitExtensionModule` modülün çalışma zamanı sınıfları ( `CRuntimeClass` yapılar) ve nesne fabrikaları ( `COleObjectFactory` nesneler), daha sonra nesne oluşturulduğunda kullanmak üzere yakalar `CDynLinkLibrary` . İçin (isteğe bağlı), MFC `AfxTermExtensionModule` `FreeLibrary` uzantı dll 'sinden her bir işlem ayrıldığında (işlem ÇıKTıĞıNDA veya dll bir çağrı ile kaldırıldığında gerçekleşir) MFC uzantı dll 'sini temizlemeye izin verir. Çoğu MFC uzantı dll 'Leri dinamik olarak yüklenmediğinden (normalde içeri aktarma kitaplıkları aracılığıyla bağlantılarlarsa), bu çağrı `AfxTermExtensionModule` genellikle gerekli değildir.

Uygulamanız MFC uzantı dll 'Lerini dinamik olarak yükler ve serbest bırakır, yukarıda gösterildiği gibi çağırdığınızdan emin olun `AfxTermExtensionModule` . Ayrıca, `AfxLoadLibrary` `AfxFreeLibrary` `LoadLibrary` `FreeLibrary` uygulamanız birden çok iş parçacığı kullanıyorsa veya bir MFC uzantı dll 'sini dinamik olarak yüklerse, ve (Win32 işlevleri yerine) öğesini de ve `AfxLoadLibrary`Ve `AfxFreeLibrary` Yöntem kullanarak, MFC uzantı dll 'si yüklendiğinde ve kaldırıldığında çalıştırılan başlatma ve kapatılma kodu genel MFC durumunu bozmaz.

Üstbilgi dosyası, *`AFXDLLX.H`* MFC uzantı dll 'lerinde ve için tanım gibi kullanılan yapılar için özel tanımlar içerir `AFX_EXTENSION_MODULE` `CDynLinkLibrary` .

Genel *extensionDLL* gösterilen şekilde bildirilmelidir. MFC 'nin 16 bit sürümünden farklı olarak, bu süre boyunca bellek ayırabilir ve bu süre içinde, *`MFCxx.DLL`* çağrılan zaman tarafından tam olarak BAŞLATıLDıĞıNDAN MFC işlevlerini çağırabilirsiniz `DllMain` .

### <a name="sharing-resources-and-classes"></a>Kaynakları ve sınıfları paylaşma

Basit MFC uzantı dll 'Lerinin yalnızca birkaç düşük bant genişlikli işlevi istemci uygulamasına ve başka hiçbir şey uygulamasına ihtiyacı vardır. Daha fazla kullanıcı arabirimi yoğun dll 'Leri istemci uygulamasına kaynakları ve C++ sınıflarını dışarı aktarmak isteyebilir.

Kaynakları dışa aktarma bir kaynak listesi aracılığıyla yapılır. Her uygulamada, listedir bağlantılı bir nesne listesi bulunur `CDynLinkLibrary` . Kaynak ararken, kaynakları yükleyen standart MFC uygulamalarının çoğu, geçerli kaynak modülünde () önce görünür `AfxGetResourceHandle` ve bulunamazsa, `CDynLinkLibrary` istenen kaynağı yüklemeye çalışan nesnelerin listesini inceleyin.

C++ sınıf adı verilen C++ nesnelerinin dinamik oluşturulması benzerdir. MFC nesne seri durumundan çıkarma mekanizmasının, `CRuntimeClass` daha önce depolanmaya dayalı olarak gerekli türde C++ nesnesini dinamik olarak oluşturarak yeniden oluşturabilmesi için tüm nesneleri kayıtlı olması gerekir.

İstemci uygulamasının MFC uzantı DLL 'inizdeki sınıfları kullanmasını istiyorsanız `DECLARE_SERIAL` , sınıfları istemci uygulamasına görünür hale getirmek için dışarı aktarmanız gerekir. Ayrıca, liste yürüyerek de yapılır `CDynLinkLibrary` .

MFC gelişmiş kavramlar örneğinde [`DLLHUSK`](../overview/visual-cpp-samples.md) , liste şöyle görünür:

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

*`MFCxx.DLL`* Giriş genellikle kaynak ve sınıf listesinde son olarak gelir. *`MFCxx.DLL`* Tüm standart komut kimliklerinin istem dizeleri dahil olmak üzere tüm standart MFC kaynaklarını içerir. Listenin sonuna yerleştirilmesi, dll 'Lerin ve istemci uygulamasının kendi kopyaları yerine içindeki paylaşılan kaynaklara dayanmasına olanak tanır *`MFCxx.DLL`* .

Tüm dll 'lerin kaynak ve sınıf adlarını istemci uygulamanın ad alanı içinde birleştirmek, hangi kimlikleri veya adları seçtiğiniz konusunda dikkatli olmanız gereken olumsuz bir şeydir. Kaynaklarınızı veya bir nesneyi istemci uygulamasına dışarı aktarıp bu özelliği devre dışı bırakabilirsiniz `CDynLinkLibrary` . [`DLLHUSK`](../overview/visual-cpp-samples.md)Örnek, birden çok üstbilgi dosyası kullanarak paylaşılan kaynak adı alanını yönetir. Paylaşılan kaynak dosyalarını kullanma hakkında daha fazla ipucu için bkz. [teknik nota 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) .

### <a name="initializing-the-dll"></a>DLL başlatılıyor

Yukarıda belirtildiği gibi genellikle `CDynLinkLibrary` kaynak ve sınıflarınızı istemci uygulamasına dışarı aktarmak için bir nesne oluşturmak istersiniz. DLL 'yi başlatmak için bir içe aktarılmış giriş noktası sağlamanız gerekir. En düşük düzeyde, hiçbir `void` bağımsız değişken alan ve hiçbir şey döndüren bir yordamdır, ancak istediğiniz herhangi bir şey olabilir.

Bu yaklaşımı kullanırsanız, DLL 'nizi kullanmak isteyen her bir istemci uygulamasının bu başlatma yordamını çağırması gerekir. Bu nesneyi, ' i `CDynLinkLibrary` `DllMain` çağırdıktan hemen sonra da ayırabilirsiniz `AfxInitExtensionModule` .

Başlatma yordamı, `CDynLinkLibrary` MFC UZANTı dll bilgilerine kablolu, geçerli uygulamanın yığınında bir nesne oluşturmalı. Bunu, şöyle bir işlev tanımlayarak yapabilirsiniz:

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

Bu örnekteki yordamın adı, *InitXxxDLL* , istediğiniz herhangi bir şey olabilir. Bunun olması gerekmez **`extern "C"`** , ancak dışa aktarma listesinin bakımını daha kolay hale getirir.

> [!NOTE]
> MFC uzantı DLL 'nizi normal bir MFC DLL 'den kullanırsanız, bu başlatma işlevini dışarı aktarmanız gerekir. Herhangi bir MFC uzantısı DLL sınıfı veya kaynağı kullanılmadan önce bu işlevin normal MFC DLL 'sinden çağrılması gerekir.

### <a name="exporting-entries"></a>Girişleri dışarı aktarma

Sınıflarınızı dışarı aktarmanın basit yolu, `__declspec(dllimport)` `__declspec(dllexport)` dışarı aktarmak istediğiniz her bir sınıfta ve genel işlevde kullanılır. Bu çok daha kolaydır, ancak aşağıda açıklandığı gibi bir DEF dosyasındaki her giriş noktasını adlandırırken daha az verimlidir. Bunun nedeni, hangi işlevlerin verileceği üzerinde daha az denetiminiz olması olabilir. Ve işlevleri sıraya göre dışarı aktarabilirsiniz. TESTDLL1 ve TESTDLL2, girişlerini dışarı aktarmak için bu yöntemi kullanın.

Daha verimli bir yöntem, her girdiyi DEF dosyasında adlandırarak dışarı aktarmak. Bu yöntem tarafından kullanılır *`MFCxx.DLL`* . DLL 'imizden seçmeli olarak dışarı aktardığımız için hangi belirli arabirimlerin dışarı aktarılmasını istiyoruz. Bu, bağlayıcı dosya içindeki girdiler biçiminde karışmış adları belirtmeniz gerektiğinden zordur. Gerçekten kendisi için bir sembolik bağlantısına sahip olmanız gerekmedikçe, hiçbir C++ sınıfını dışarı aktarmayın.

Daha önce bir DEF dosyası ile C++ sınıflarını dışarı aktarmaya çalıştıysanız, bu listeyi otomatik olarak oluşturmak için bir araç geliştirmek isteyebilirsiniz. Bu, iki aşamalı bir bağlantı işlemi kullanılarak yapılabilir. DLL 'nizi dışarı aktarımlar olmadan bir kez bağlayın ve bağlayıcının bir harıta dosyası oluşturmasına izin verin. EŞLEME dosyası, verilmesi gereken işlevlerin bir listesini içerir. Bazı yeniden düzenleme ile, DEF dosyanız için dışarı aktarma girdilerini oluşturmak üzere onu kullanabilirsiniz. İçin dışa aktarma listesi *`MFCxx.DLL`* ve OLE ve VERITABANı mfc uzantısı DLL 'leri, bu tür bir işlem ile oluşturulmuştur (tamamen otomatik olmasa da) ve her bir kez bir kez ayarlama gerektirir.

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp ve CDynLinkLibrary

MFC uzantı DLL 'SI `CWinApp` kendi kendine türetilmiş bir nesnesine sahip değildir. Bunun yerine, `CWinApp` istemci uygulamasının türetilmiş nesnesiyle birlikte çalışmalıdır. Bu, istemci uygulamanın ana ileti göndericisi, boşta döngüsü vb. sahibi olduğu anlamına gelir.

MFC uzantı DLL 'nizin her bir uygulama için ek verileri tutması gerekiyorsa, öğesinden yeni bir sınıf türetebilir `CDynLinkLibrary` ve yukarıda açıklanan yordamın içinde oluşturabilirsiniz `InitXxxDLL` . Çalışırken, DLL geçerli uygulamanın nesne listesini denetleyerek `CDynLinkLibrary` söz konusu mfc uzantısı DLL 'si için bir tane bulur.

### <a name="using-resources-in-your-dll-implementation"></a>DLL uygulamanızda kaynakları kullanma

Yukarıda belirtildiği gibi, varsayılan kaynak yükü, `CDynLinkLibrary` istenen kaynağa sahip Ilk exe veya dll 'yi arayan nesne listesini gösterecektir. Tüm MFC API 'Leri ve tüm iç kodlar, `AfxFindResourceHandle` kaynak listesini nerede olduğunu fark etmeksizin kaynak listesini bulmak için kullanır.

Yalnızca belirli bir konumdan kaynak yüklemek istiyorsanız, API 'Leri kullanın `AfxGetResourceHandle` ve `AfxSetResourceHandle` eski tanıtıcıyı kaydedin ve yeni tanıtıcıyı ayarlayın. İstemci uygulamasına geri dönmek için eski kaynak tanıtıcısını geri yüklediğinizden emin olun. Örnek TESTDLL2, bir menüyü açıkça yüklemek için bu yaklaşımı kullanır.

Listenin bir dezavantajına sahiptir: biraz daha yavaştır ve kaynak KIMLIĞI aralıklarının yönetilmesini gerektirir. Birkaç MFC uzantı dll 'sine bağlantı sağlayan bir istemci uygulamasının, DLL örneği tanıtıcısını belirtmek zorunda kalmadan herhangi bir DLL tarafından sağlanmış kaynağı kullanabilmesi avantajına sahiptir. `AfxFindResourceHandle` , belirli bir eşleşmeyi aramak üzere kaynak listesini yürütirecek bir API 'dir. Bir kaynağın adını ve türünü alır ve kaynak tanıtıcısını, kaynağı ilk bulduğu veya NULL olarak döndürür.

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> DLL sürümünü kullanan bir uygulama yazma

### <a name="application-requirements"></a>Uygulama gereksinimleri

MFC 'nin paylaşılan sürümünü kullanan bir uygulama birkaç temel kurala uymalıdır:

- Bir `CWinApp` nesnesi olmalıdır ve ileti göndericisinin standart kurallarını izlemelidir.

- Bir gerekli derleyici bayrakları kümesiyle derlenmesi gerekir (aşağıya bakın).

- MFCxx içeri aktarma kitaplıklarıyla bağlantı gerekir. Gerekli derleyici bayraklarını ayarlayarak, MFC üstbilgileri uygulamanın bağlanması gereken kitaplığı bağlantı zamanına göre belirlenir.

- Yürütülebilir dosyayı çalıştırmak için, *`MFCxx.DLL`* yolda veya Windows sistem dizininde olması gerekir.

### <a name="building-with-the-development-environment"></a>Geliştirme ortamıyla derleme

Standart varsayılanların çoğu ile iç derleme görevleri dosyasını kullanıyorsanız, projeyi DLL sürümünü oluşturmak için kolayca değiştirebilirsiniz.

Aşağıdaki adım, *`NAFXCWD.LIB`* (hata ayıklama için) ve (yayın için) ile bağlantılı MFC uygulamasının düzgün şekilde çalıştığını *`NAFXCW.LIB`* ve bu dosyayı MFC kitaplığının paylaşılan sürümünü kullanacak şekilde dönüştürmek istediğinizi varsayar. Visual Studio ortamını çalıştırıyorsunuz ve bir iç proje dosyası var.

1. **Projeler** menüsünde **Özellikler**' i seçin. **Proje Varsayılanları** altındaki **genel** sayfasında, Microsoft Foundation sınıfları **paylaşılan bir dll 'de MFC kullanacak** şekilde ayarlayın (MFCxx (d). dll).

### <a name="building-with-nmake"></a>NMAKE ile derleme

Derleyicinin dış makefile özelliğini kullanıyorsanız veya NMAKE doğrudan kullanıyorsa, gerekli derleyici ve bağlayıcı seçeneklerini desteklemek için derleme görevleri dosyasını düzenlemeniz gerekir.

Gerekli derleyici bayrakları:

- **`/D_AFXDLL /MD`**
  **`/D_AFXDLL`**

Standart MFC üst bilgilerinde `_AFXDLL` tanımlanacak simgenin olması gerekir.

- **`/MD`** Uygulamanın, C çalışma zamanı kitaplığının DLL sürümünü kullanması gerekir.

Diğer tüm derleyici bayrakları MFC varsayılanlarını (örneğin, `_DEBUG` hata ayıklama için) izler.

Kitaplıkların bağlayıcı listesini düzenleyin. *`NAFXCWD.LIB`* Olarak değiştirin *`MFCxxD.LIB`* ve öğesini *`NAFXCW.LIB`* olarak değiştirin *`MFCxx.LIB`* . *`LIBC.LIB`* İle değiştirin *`MSVCRT.LIB`* . Diğer herhangi bir MFC kitaplığında olduğu gibi, *`MFCxxD.LIB`* herhangi bir C çalışma zamanı kitaplığı **öncesinde** yerleştirilmesi önemlidir.

İsteğe bağlı olarak **`/D_AFXDLL`** hem sürüm hem de hata ayıklama kaynağı derleyicisi seçeneklerine (kaynaklarını ile olan kaynakları derlediğinde **`/R`** ) ekleyin. Bu seçenek, MFC DLL 'Lerinde bulunan kaynakları paylaşarak son yürütülebilir dosyanızı daha küçük hale getirir.

Bu değişiklikler yapıldıktan sonra tam yeniden oluşturma gereklidir.

### <a name="building-the-samples"></a>Örnekleri oluşturma

MFC örnek programlarının çoğu, komut satırından Visual C++ veya paylaşılan bir NMAKE uyumlu derleme görevleri dosyası içinden oluşturulabilir.

Bu örneklerden herhangi birini kullanmak üzere dönüştürmek için *`MFCxx.DLL`* Mak dosyasını Visual C++ yükleyebilir ve yukarıda açıklandığı gibi proje seçeneklerini ayarlayabilirsiniz. NMAKE derlemesini kullanıyorsanız, `AFXDLL=1` NMAKE komut satırında ve PAYLAŞıLAN MFC kitaplıklarını kullanarak örneği oluşturacak şekilde belirtebilirsiniz.

MFC gelişmiş kavramlar örnek [DLLHUSK](../overview/visual-cpp-samples.md) , MFC 'nin dll sürümü ile oluşturulmuştur. Bu örnek yalnızca ile bağlantılı bir uygulamanın nasıl oluşturulduğunu gösterir *`MFCxx.DLL`* , ancak bu teknik notun ilerleyen kısımlarında AÇıKLANAN MFC uzantı dll 'leri gıbı MFC DLL paketleme seçeneğinin diğer özelliklerini de gösterir.

### <a name="packaging-notes"></a>Paketleme notları

Dll 'lerin yayın sürümleri ( *`MFCxx.DLL`* ve *`MFCxxU.DLL`* ) serbestçe yeniden dağıtılabilir. Dll 'lerin hata ayıklama sürümleri serbestçe yeniden dağıtılabilir ve yalnızca uygulamanızın geliştirilmesi sırasında kullanılmalıdır.

Hata ayıklama dll 'Leri hata ayıklama bilgileri ile sağlanır. Visual C++ hata ayıklayıcısını kullanarak hem uygulamanızın hem de DLL 'inin yürütülmesini izleyebilirsiniz. Sürüm dll 'Leri ( *`MFCxx.DLL`* ve *`MFCxxU.DLL`* ) hata ayıklama bilgisi içermez.

Dll 'Leri özelleştirip yeniden yapılandırırsanız, bunları "MFCxx" dışında bir şekilde çağırmanız gerekir. MFC SRC dosyası *`MFCDLL.MAK`* derleme seçeneklerini açıklar ve DLL 'yi yeniden adlandırma mantığını içerir. Bu dll 'Ler birçok MFC uygulaması tarafından paylaşıldığından dosyaların yeniden adlandırılması gerekir. MFC DLL 'lerinin özel sürümünün sistemde yüklü olanları değiştirmesini, paylaşılan MFC DLL 'Lerini kullanarak başka bir MFC uygulamasını bozabilir.

MFC DLL 'Lerinin yeniden oluşturulması önerilmez.

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> MFCxx.DLL nasıl uygulanır

Aşağıdaki bölümde, MFC DLL 'sinin ( *`MFCxx.DLL`* ve) nasıl *`MFCxxD.DLL`* uygulandığı açıklanmaktadır. Buradaki ayrıntıları anlamak, uygulamanız ile MFC DLL 'i kullanmak istiyorsanız da önemli değildir. Buradaki ayrıntılar, bir MFC uzantısı DLL dosyasının nasıl yazılacağını anlamak için gerekli değildir, ancak bu uygulamayı anlamak kendi DLL 'nizi yazmanıza yardımcı olabilir.

### <a name="implementation-overview"></a>Uygulamaya genel bakış

MFC DLL 'SI, yukarıda açıklandığı gibi bir MFC uzantı DLL 'inin gerçekten özel bir durumdur. Çok sayıda sınıf için çok sayıda dışarı aktarmaları vardır. MFC DLL 'de, normal MFC uzantısı DLL ' den daha da çok özel hale yaptığımız birkaç ek şey vardır.

### <a name="win32-does-most-of-the-work"></a>Win32, Işin çoğunu

MFC 'nin 16 bit sürümü, yığın kesimindeki uygulama başına verileri, bazı 80x86 derleme kodu tarafından oluşturulan özel kesimleri, işlem başına özel durum bağlamlarını ve diğer teknikleri içeren bir dizi özel tekniği gerekli değildir. Win32, bir DLL 'de işlem başına verileri doğrudan destekler, bu da çoğu zaman istediğiniz şeydir. Çoğu bölüm için *`MFCxx.DLL`* yalnızca *`NAFXCW.LIB`* bir dll 'de paketlenmiştir. MFC kaynak koduna bakarsanız birkaç `#ifdef _AFXDLL` durum bulacaksınız, çünkü yapılması gereken çok sayıda özel durum yoktur. Özellikle Windows 3,1 (örneğin, Win32s olarak bilinir) üzerinde Win32 ile başa çıkmak için olan özel durumlar. Win32s, işlem başına DLL verilerini doğrudan desteklemez. MFC DLL 'SI, işlem yerel verilerini almak için iş parçacığı yerel depolaması (TLS) Win32 API 'Lerini kullanmalıdır.

### <a name="impact-on-library-sources-additional-files"></a>Kitaplık kaynakları, ek dosyalar üzerindeki etki

`_AFXDLL`Normal MFC sınıf kitaplığı kaynakları ve başlıklarındaki sürümün etkisi nispeten daha düşük. *`AFXV_DLL.H`* *`AFXDLL_.H`* Ana üst bilgi tarafından eklenen özel bir sürüm dosyası () ve ek üstbilgi dosyası () vardır *`AFXWIN.H`* . *`AFXDLL_.H`* Üst bilgi, `CDynLinkLibrary` hem uygulama hem de `_AFXDLL` MFC uzantı dll 'lerinin sınıfını ve diğer uygulama ayrıntılarını içerir. *`AFXDLLX.H`* Üst bilgi, MFC uzantı dll 'leri oluşturmak için sağlanır (Ayrıntılar için yukarıya bakın).

MFC SRC 'deki MFC kitaplığına yönelik normal kaynaklar #ifdef altında bazı ek koşullu koda sahiptir `_AFXDLL` . Ek bir kaynak dosyası ( *`DLLINIT.CPP`* ), ek dll başlatma kodunu ve MFC 'nin paylaşılan sürümüne yönelik diğer tutkalla içerir.

MFC 'nin paylaşılan sürümünü oluşturmak için ek dosyalar sağlanır. (DLL oluşturma hakkında ayrıntılı bilgi için aşağıya bakın.)

- DLL 'nin hata ayıklama ( *`MFCxxD.DEF`* ) ve Release () sürümleri IÇIN MFC DLL giriş noktaları dışarı aktarmak için ıkı def dosya kullanılır *`MFCxx.DEF`* .

- Bir RC dosyası ( *`MFCDLL.RC`* ) tüm standart MFC kaynaklarını ve `VERSIONINFO` DLL için bir kaynağı içerir.

- *`MFCDLL.CLW`* ClassWizard kullanarak MFC sınıflarına göz atmaya izin vermek için BIR CLW dosyası () sağlanır. Bu özellik MFC 'nin DLL sürümüne özgü değildir.

### <a name="memory-management"></a>Bellek Yönetimi

Kullanan bir uygulama *`MFCxx.DLL`* *`MSVCRTxx.DLL`* , paylaşılan C-çalışma zamanı dll 'i tarafından sağlanmış ortak bir bellek ayırıcısı kullanır. Uygulama, tüm MFC uzantı dll 'Leri ve MFC DLL 'Leri bu paylaşılan bellek ayırıcısını kullanır. Bellek ayırma için paylaşılan bir DLL kullanarak, MFC DLL 'Leri daha sonra uygulama tarafından serbest bırakılan veya tam tersi bellek ayırabilir. Hem uygulama hem de DLL aynı ayırıcıyı kullanması gerektiğinden, C++ global veya ' i geçersiz kılmamanız gerekir **`operator new`** **`operator delete`** . Aynı kurallar C çalışma zamanı bellek ayırma yordamlarının geri kalanı için de geçerlidir (örneğin,, `malloc` `realloc` `free` ve diğerleri).

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>Sıra sayıları ve sınıf __declspec (dllexport) ve DLL adlandırması

`class` **`__declspec(dllexport)`** C++ derleyicisinin işlevlerini kullanmıyoruz. Bunun yerine, sınıf kitaplığı kaynaklarına (ve) dışarı aktarmalar listesi dahildir *`MFCxx.DEF`* *`MFCxxD.DEF`* . Yalnızca bir giriş noktaları kümesi (işlevler ve veriler) verilir. MFC özel uygulama işlevleri veya sınıfları gibi diğer semboller aktarılmaz. Tüm dışarı aktarmalar, yerleşik veya yerleşik olmayan ad tablosunda dize adı olmadan sıralı olarak yapılır.

Kullanmak `class` **`__declspec(dllexport)`** , daha küçük dll 'ler oluşturmak için uygun bir alternatif olabilir, ancak MFC gibi büyük bir dll 'de, varsayılan dışa aktarma mekanizmasının verimlilik ve kapasite limitleri vardır.

Bunun hepsi anlamı, yayında büyük bir işlev miktarını, *`MFCxx.DLL`* çok fazla yürütme veya yükleme hızıyla ödün vermeden 800 KB 'lık bir işlevselliğe paketedebiliyoruz. *`MFCxx.DLL`* 100 KB daha büyük olan bu tekniğin kullanılmıştı. Tekniği, DEF dosyasının sonuna ek giriş noktaları eklemek mümkün hale getirir. Sıraya göre dışarı aktarmanın hız ve boyut verimliliğine ödün vermeden basit sürüm oluşturma olanağı sağlar. MFC sınıf kitaplığındaki ana sürüm düzeltmeleri kitaplık adını değiştirecek. Diğer bir deyişle, *`MFC30.DLL`* MFC sınıf kitaplığının 3,0 sürümünü içeren yeniden DAĞITILABILIR dll 'dir. Bu DLL 'nin bir yükseltmesi olan, bir kuramsal MFC 3,1 ' de, DLL 'nin bunun yerine adlandırılmış olduğunu varsayalım *`MFC31.DLL`* . MFC DLL 'nin özel bir sürümünü oluşturmak için MFC kaynak kodunu değiştirirseniz, farklı bir ad (ve tercihen "MFC" adında "MFC" olmadan) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
