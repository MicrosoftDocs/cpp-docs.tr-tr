---
title: "TN033: MFC'nin DLL sürümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.dll
dev_langs: C++
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fb1fb4094e5a54f82aa6aeebffe576965838cf7e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC'nin DLL Sürümü
Bu Not MFCxx.DLL kullanabilirsiniz ve MFC uygulamaları ve MFC uzantı DLL'leri ile dinamik bağlantı kitaplıkları (x MFC sürüm numarası olduğu yer) MFCxxD.DLL paylaşılan nasıl açıklanmaktadır. Normal MFC DLL'leri hakkında daha fazla bilgi için bkz: [DLL'in bir parçası olarak MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md).  
  
 Bu teknik Not dll dosyaları üç yönlerini kapsar. Son iki daha gelişmiş kullanıcılar için şunlardır:  
  
- [MFC uzantı DLL nasıl oluşturulacağına](#_mfcnotes_how_to_write_an_mfc_extension_dll)  
  
- [Nasıl MFC'nin DLL sürümü kullanan MFC uygulaması oluşturma](#_mfcnotes_writing_an_application_that_uses_the_dll_version)  
  
- [MFC dinamik bağlantı kitaplıklarının nasıl paylaşılacağını uygulanır](#_mfcnotes_how_the_mfc30.dll_is_implemented)  
  
 MFC dışı uygulamaları (normal bir MFC DLL denir) ile kullanılabilir MFC kullanarak DLL'den oluşturulmasında ilgileniyorsanız başvurmak [Teknik Not 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md).  
  
## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL desteği'ne genel bakış: terminoloji ve dosyaları  
 **Normal MFC DLL**: MFC sınıfları bazıları kullanarak tek başına bir DLL oluşturmak için normal bir MFC DLL kullanın. Arabirimler uygulama/DLL sınır arasında "C" arabirimlerdir ve istemci uygulaması, MFC uygulaması olmak zorunda değildir.  
  
 DLL desteği MFC 1.0 desteklenen sürümüdür. Bölümünde açıklanan [Teknik Not 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) ve MFC Gelişmiş kavramları örnek [ile ilgili](../visual-cpp-samples.md).  
  
> [!NOTE]
>  Visual C++ sürüm 4.0 itibariyle terimi **USRDLL** kullanımdan kalkmıştır ve MFC'ye normal bir MFC DLL olarak değiştirilir. Ayrıca, normal dinamik olarak MFC'ye bağlanan bir MFC DLL da oluşturabilirsiniz.  
  
 MFC 3.0 (ve üstü) Normal MFC DLL'leri OLE ve veritabanı sınıfları dahil olmak üzere tüm yeni işlevselliği ile destekler.  
  
 **AFXDLL**: Bu aynı zamanda MFC kitaplıkları bir paylaşılan sürümü olarak adlandırılır. MFC 2. 0'eklenen yeni DLL desteği budur. MFC Kitaplığı (aşağıda açıklanmıştır) DLL'leri çeşitli olduğundan ve bir istemci uygulaması ya da DLL gerektiriyorsa DLL'leri dinamik olarak bağlar. Uygulama/DLL sınır arasında arabirimlerdir C + +/ MFC sınıfı arabirimleri. İstemci uygulaması MFC uygulaması olması gerekir. Bu, tüm MFC 3.0 işlevselliği destekler (özel durum: UNICODE veritabanı sınıfları için desteklenmiyor).  
  
> [!NOTE]
>  Visual C++ sürüm 4.0 itibariyle bu tür bir DLL için "Uzantı DLL." adlandırılır  
  
 Bu Not MFCxx.DLL içeren MFC DLL ayarlayın, tüm başvurmak için kullanacağınız:  
  
-   Hata ayıklama: (birleştirilmiş) MFCxxD.DLL ve MFCSxxD.LIB (statik).  
  
-   Sürüm: (birleştirilmiş) MFCxx.DLL ve MFCSxx.LIB (statik).  
  
-   Unicode hata ayıklama: (birleştirilmiş) MFCxxUD.DLL ve MFCSxxD.LIB (statik).  
  
-   Unicode sürüm: (birleştirilmiş) MFCxxU.DLL ve MFCSxxU.LIB (statik).  
  
> [!NOTE]
>  MFCSxx [U] [D]. LIB kitaplıkları kullanıldığı MFC ile birlikte paylaşılan DLL'ler. Bu kitaplıklar uygulama veya DLL statik olarak bağlanmalıdır kodu içerir.  
  
 Bir uygulama bağlantılar karşılık gelen içeri aktarma kitaplıkları için:  
  
-   Hata ayıklama: MFCxxD.LIB  
  
-   Yayın: MFCxx.LIB  
  
-   Unicode hata ayıklama: MFCxxUD.LIB  
  
-   Unicode yayın: MFCxxU.LIB  
  
 Bir "MFC uzantı DLL" MFCxx.DLL yerleşik bir DLL'dir (ve/veya diğer MFC DLL'leri paylaşılan). Burada MFC bileşen mimarisi devreye girer. Bir MFC sınıfı yararlı bir sınıf türetin ya da başka bir MFC benzeri Araç Seti yapı DLL'de yerleştirebilirsiniz. DLL olarak MFCxx.DLL, kullanır ultimate istemci uygulaması yapar. Bu, yeniden kullanılabilir yaprak sınıfları, yeniden kullanılabilir temel sınıflar ve yeniden kullanılabilir görünüm/belge sınıfları izin verir.  
  
## <a name="pros-and-cons"></a>Artıları ve eksileri  
 Neden MFC paylaşılan sürümünü kullanmalısınız  
  
-   Paylaşılan kitaplık kullanma (MFC kitaplığını çoğunu kullanan en az bir uygulama değerinden 10 K'dır) küçük uygulamalarda neden olabilir.  
  
-   MFC uzantı DLL'leri ve Normal MFC DLL'leri MFC paylaşılan sürümünü destekler.  
  
-   Paylaşılan MFC kitaplıkları kullanan bir uygulama oluşturmaya MFC'nin bağlamak gerekli olmadığı için statik olarak bağlantılı bir MFC uygulaması oluşturma daha hızlıdır. Bu özellikle geçerlidir **hata ayıklama** burada bağlayıcı gerekir compact hata ayıklama bilgileri derlemeleri — zaten hata ayıklama bilgilerini içeren bir DLL ile bağlayarak, uygulamanızdaki sıkıştırmak için daha az hata ayıklama bilgisi yoktur.  
  
 Neden MFC'nin paylaşılan sürümü kullanmamanız gerekir:  
  
-   Paylaşılan kitaplık kullanan bir uygulamayı sevkiyat gerektirir MFCxx.DLL (ve diğerleri) sevk programınızla kitaplığı. MFCxx.DLL gibi birçok DLL'leri ücretsiz olarak dağıtılabilen, ancak hala Kurulum programınıza DLL yüklemeniz gerekir. Ayrıca, hem programınız ve MFC DLL'leri tarafından kullanılan C çalışma zamanı kitaplığı içerir MSVCRTxx.DLL birlikte gerekir.  
  
##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>MFC uzantı DLL'si yazma  
 MFC uzantı DLL sınıfları ve MFC sınıfları işlevselliğini süslemek için yazılmış işlevleri içeren bir DLL'dir. MFC uzantı DLL paylaşılan MFC DLL'leri, uygulama ile birkaç ek hususlar kullanan aynı şekilde kullanır:  
  
-   Derleme işlemi, paylaşılan MFC kitaplıkları birkaç ek derleyici ve bağlayıcı seçenekleri kullanan bir uygulama oluşturmak için benzer.  
  
-   MFC uzantı DLL sahip olmayan bir `CWinApp`-türetilmiş sınıf.  
  
-   MFC uzantı DLL özel bir sağlamalısınız `DllMain`. AppWizard sağlayan bir `DllMain` değiştirebileceğiniz işlevi.  
  
-   Bir MFC uzantı DLL'si genellikle oluşturmak için bir başlatma yordamının sağlayacak bir **CDynLinkLibrary** MFC uzantı DLL vermek isterse `CRuntimeClass`es veya kaynakları uygulamaya. Türetilen bir sınıftan **CDynLinkLibrary** uygulama başına veri MFC uzantı DLL tarafından korunmalıdır varsa kullanılabilir.  
  
 Bu noktalar aşağıdaki daha ayrıntılı olarak açıklanmıştır. MFC Gelişmiş kavramları örnek ayrıca başvurmalıdır [DLLHUSK](../visual-cpp-samples.md) beri bu gösterilmektedir:  
  
-   Paylaşılan kitaplıklar kullanarak uygulama oluşturma. (DLLHUSK. EXE MFC kitaplıkları sair DLL'leri dinamik olarak bağlanan bir MFC uygulamasıdır.)  
  
-   MFC uzantı DLL oluşturma. (Not gibi özel bayrakları `_AFXEXT` MFC uzantı DLL'si oluşturulmasında kullanılan)  
  
-   MFC uzantı DLL'leri iki örnekleri. Bir MFC uzantı DLL sınırlı verir (TESTDLL1) ile ve tüm sınıf arabirimi (TESTDLL2) dışarı aktarma diğer programları temel yapısını gösterir.  
  
 İstemci uygulaması ve tüm MFC uzantı DLL'leri MFCxx.DLL aynı sürümünü kullanmanız gerekir. MFC DLL kuralı izleyin ve her iki bir hata ayıklama sağlamak ve perakende (/ sürüm), MFC uzantı DLL sürümü. Bu, kendi uygulamalarında hata ayıklama ve perakende sürümleri oluşturmak ve bunları uygun hata ayıklama veya tüm DLL'ler'ın perakende sürümüne bağlamak için istemci programları izin verir.  
  
> [!NOTE]
>  C++ bozma adlandırın ve sorunları dışarı aktarmak için MFC uzantı DLL dışarı aktarma listesi farklı platform için aynı DLL hata ayıklama ve perakende sürümleri ve DLL'ler farklı olabilir. Perakende MFCxx.DLL hakkında 2000 giriş noktaları dışarı; hata ayıklama MFCxxD.DLL yaklaşık 3000 giriş noktaları dışarı.  
  
### <a name="quick-note-on-memory-management"></a>Hızlı not bellek yönetimi  
 Bu teknik Not sonuna yakın alan "bellek yönetimi" başlıklı bölüme MFC'nin paylaşılan sürümü MFCxx.DLL uygulamasıyla açıklar. Bilgiler yalnızca DLL burada açıklanan MFC uzantı uygulamak için bilmeniz gerekir.  
  
 Aynı uygulamada değilmiş gibi MFCxx.DLL ve bir istemci uygulamanın adres alanına yüklenen tüm MFC uzantı DLL'leri aynı bellek ayırıcısı, kaynak yükleme ve diğer MFC "Genel" durumlarını kullanır. MFC DLL kitaplıkları ve statik olarak MFC'ye Normal MFC DLL'leri tam tersi yapın ve her DLL dışında kendi bellek havuzu ayırma sahip olduğundan, bu önemlidir.  
  
 Ardından MFC uzantı DLL'si bellek ayırır, bu bellek diğer uygulama ayrılan nesneleri intermix serbestçe. Ayrıca, paylaşılan MFC kitaplıkları kullanan bir uygulama çökerse işletim sisteminin koruma DLL paylaşımı başka bir MFC Uygulama bütünlüğünü korur.  
  
 Benzer şekilde, kaynakları yüklemek için geçerli yürütülebilir dosya gibi diğer "Genel" MFC durumları da istemci uygulaması ve tüm MFC uzantı DLL'leri yanı sıra arasında MFCxx.DLL kendisini paylaşılır.  
  
### <a name="building-an-mfc-extension-dll"></a>MFC uzantı DLL oluşturma  
 MFC uzantı DLL projesi oluşturmak için AppWizard kullanabilirsiniz ve uygun derleyici ve bağlayıcı ayarlarını otomatik olarak oluşturur. Ayrıca oluşturmak olan bir `DllMain` değiştirebileceğiniz işlevi.  
  
 MFC uzantı DLL varolan projeyi dönüştürüyorsanız MFC paylaşılan sürümünü kullanarak bir uygulama oluşturmak için standart kurallar ile başlayın, ardından aşağıdakilerden birini yapın:  
  
-   Ekleme **/D_AFXEXT** derleyici bayraklarına. Proje Özellikleri iletişim kutusunda C/C++ düğümünü seçin. Ardından önişlemci kategorisini seçin. Ekleme `_AFXEXT` tanımlamak makroları alana öğelerin her biri noktalı virgül.  
  
-   Kaldırma **/Gy** derleyici anahtar. Proje Özellikleri iletişim kutusunda C/C++ düğümünü seçin. Ardından kod oluşturma kategorisini seçin. "İşlev düzeyi bağlamayı etkinleştir" seçeneği etkin emin olun. Bu, bağlayıcı başvurulmayan işlevleri kaldırmayacaktır çünkü sınıflarını dışarı aktarmak daha kolay hale getirir. MFC DLL özgün proje bir normal oluşturmak için kullanılıyorsa, statik olarak MFC'ye değişiklik bağlı **/MT [d]** derleyici seçeneği **/MD [d]**.  
  
-   Bir verme kitaplıkla yapı **/dll** bağlantı seçeneği. Win32 dinamik bağlantı kitaplığı hedef türü olarak belirterek yeni bir hedef oluşturduğunuzda bu ayarlanır.  
  
### <a name="changing-your-header-files"></a>Üstbilgi dosyaları değiştiriliyor  
 MFC uzantı DLL'si genellikle ortak işlevselliğinin bu işlevselliği kullanabilirsiniz bir veya daha fazla uygulama için dışarı aktarmak için hedefidir. Sınıfları ve istemci uygulamalarınız için kullanılabilen genel işlevleri dışarı aktarma için bu boils.  
  
 Bunu yapmak için her üye işlevleri içeri veya dışarı aktarma uygun şekilde olarak işaretlenmiş güvence altına gerekir. Bu özel bildirimleri gerektirir: **__declspec(dllexport)** ve **__declspec(dllimport)**. İstemci uygulamaları tarafından kullanılan, sınıflar, bunları olarak bildirilmesi için istediğiniz **__declspec(dllimport)**. MFC uzantı DLL'si kendisini oluşturulmuştur, bunlar olarak bildirilmelidir **__declspec(dllexport)**. Böylece istemci programları için yükleme zamanında bağlama Ayrıca işlevleri gerçekte, aktarılması gerekir.  
  
 Tüm sınıfınız dışarı aktarmak için kullanın **AFX_EXT_CLASS** sınıf tanımında. Bu makrosu framework tarafından tanımlanan **__declspec(dllexport)** zaman **_AFXDLL** ve `_AFXEXT` tanımlı, ancak olarak tanımlanan **__declspec(dllimport)** zaman `_AFXEXT` tanımlı değil. `_AFXEXT`yukarıda açıklandığı gibi yalnızca MFC uzantı DLL oluşturulurken tanımlanır. Örneğin:  
  
```  
class AFX_EXT_CLASS CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
### <a name="not-exporting-the-entire-class"></a>Bütün sınıfı dışa değil  
 Bazen sınıfınızın yalnızca tek tek gerekli üyeleri vermek isteyebilirsiniz. Dışa aktarıyorsanız, örneğin, bir `CDialog`-türetilmiş sınıf, yalnızca Oluşturucusu vermeniz gerekebilir ve `DoModal` çağırın. DLL kullanarak bu üyelerin dışarı aktarabilirsiniz. DEF dosyası, ancak de kullanabilir **AFX_EXT_CLASS** kadar aynı şekilde dışarı aktarmak için gereken tek tek üyeleri üzerinde.  
  
 Örneğin:  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
    AFX_EXT_CLASS CExampleDialog();
AFX_EXT_CLASS int DoModal();
*// rest of class definition  
 .  
 .  
 .  
};  
```  
  
 Bunu yaptığınızda, sınıfın tüm üyeleri artık verdiğiniz çünkü bir ek sorunlarla karşılaşabilirsiniz. Yönteminde, MFC makroları çalışma sorunudur. MFC'nin yardımcı makroları çeşitli gerçekte bildirme veya veri üyeleri tanımlayın. Bu nedenle, bu veri üyeleri de DLL dosyasından verilmesi gerekir.  
  
 Örneğin, `DECLARE_DYNAMIC` makrosu MFC uzantı DLL'si oluştururken aşağıdaki gibi tanımlanır:  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
    static CRuntimeClass* PASCAL _GetBaseClass();

\  
    public: \  
    static AFX_DATA CRuntimeClass class##class_name; \  
    virtual CRuntimeClass* GetRuntimeClass() const;

\  
```  
  
 Başlayan satır "statik `AFX_DATA`" sınıfınızın içinde statik bir nesne bildirme. Bu sınıf doğru şekilde dışa aktarmak ve çalışma zamanı bilgileri bir istemciden erişmek için. EXE, bu statik nesneyi dışarı aktarmanız gerekmez. Statik nesne değiştiricisi ile bildirildiğinden `AFX_DATA`, yalnızca tanımlamanız gerekecek `AFX_DATA` olmasını **__declspec(dllexport)** DLL dosyanızı oluştururken ve olarak tanımlamak **__declspec(dllimport)** istemciniz yürütülebilir oluştururken.  
  
 Yukarıda açıklandığı gibi **AFX_EXT_CLASS** bu yolla zaten tanımlandı. Yeniden tanımlamak yeterlidir `AFX_DATA` aynı olacak şekilde **AFX_EXT_CLASS** Sınıf tanımınız geçici.  
  
 Örneğin:  
  
```  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
class CExampleView : public CView  
{  
    DECLARE_DYNAMIC() *// ... class definition ...  
};  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
 MFC her zaman kullanır `AFX_DATA` gibi senaryolar için bu tekniği çalışacak şekilde kendi makroları içinde tanımladığı veri öğelerinde simgesi. Örneğin, için çalışır `DECLARE_MESSAGE_MAP`.  
  
> [!NOTE]
>  Seçilen sınıf üyeleri yerine bütün sınıfı dışa aktarıyorsanız, statik veri üyeleri otomatik olarak dışarı aktarılır.  
  
 Otomatik olarak dışa aktarmak için aynı tekniği kullanabilirsiniz `CArchive` ayıklama işleci için sınıfları kullanan `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları. Arşiv işleci sınıf bildirimleri köşeli ayraç kullanarak dışarı aktar (bulunur. H dosyası) aşağıdaki kod ile:  
  
```  
#undef AFX_API  
#define AFX_API AFX_EXT_CLASS  
 
<your class declarations here>  
 
#undef AFX_API  
#define AFX_API  
```  
  
### <a name="limitations-of-afxext"></a>_AFXEXT Sınırlamaları  
 _ Kullanabilirsiniz**AFXEXT** , MFC uzantı DLL'leri MFC uzantı DLL'leri çok katmanlı olmayan sürece ön işlemci simgesi. MFC uzantı DLL'leri çağıran veya kendi MFC uzantı sonra MFC sınıflarından, DLL'leri sınıflarda öğesinden türetilen varsa, Karışıklığı önlemek için kendi önişlemci sembolü kullanmanız gerekir.  
  
 Söz konusu Win32 sorunudur, herhangi bir veri olarak açıkça bildirmelidir **__declspec(dllexport)** DLL'den dışarı aktarılacak ise ve **__declspec(dllimport)** DLL'den dışarı aktarılacak ise. Tanımladığınızda `_AFXEXT`, MFC üstbilgileri olduğundan emin olun **AFX_EXT_CLASS** doğru tanımlanmadı.  
  
 Olduğunda, birden çok katman, bir sembol gibi **AFX_EXT_CLASS** MFC uzantı DLL'si yeni sınıfları dışarı aktarma yanı sıra bu yana diğer sınıfları başka bir MFC uzantı DLL içeri aktarma yeterli değildir. Bu sorunları gidermek için DLL'i kullanmak DLL kendisini oluşturduğunuzu gösteren özel bir önişlemci sembolü kullanın. Örneğin, iki MFC uzantı DLL'leri, A.DLL ve B.DLL düşünün. Her A.H ve B.H'taki bazı sınıflarda sırasıyla verin. B.DLL a.DLL'den sınıfları kullanır. Üstbilgi dosyaları şunun gibi görünür:  
  
```  
/* A.H */  
#ifdef A_IMPL  
 #define CLASS_DECL_A   __declspec(dllexport)  
#else  
 #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
 
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
 
/* B.H */  
#ifdef B_IMPL  
 #define CLASS_DECL_B   __declspec(dllexport)  
#else  
 #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
 
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition .. };  
```  
  
 A.dll oluşturulduğunda ile oluşturulmuştur **/D A_IMPL** ve B.DLL oluşturulduğunda ile yerleşiktir **/D B_IMPL**. Her DLL için ayrı sembol kullanarak CExampleB aktarılır ve CExampleA b.dll oluşturulduğunda içe aktarılır. CExampleA a.dll oluşturulurken dışarı ve içeri B.DLL (veya başka bir istemci) tarafından kullanıldığında.  
  
 Bu tür katmanlama yerleşik kullanırken yapılamaz **AFX_EXT_CLASS** ve `_AFXEXT` önişlemci simgeleri. Yukarıda açıklanan teknikleri MFC'nin mekanizması kullanır. Bu, OLE, veritabanı ve ağ MFC uzantı DLL'leri oluştururken bir şekilde benzemeyen bu sorunu çözer.  
  
### <a name="not-exporting-the-entire-class"></a>Bütün sınıfı dışa değil  
 Sınıfının tümüne aktarıyorsanız değil, özel dikkat edin gerekecektir. MFC makroları tarafından oluşturulan tüm gerekli veri öğelerinin doğru verildiğinden emin olmanız gerekir. Bu yeniden tanımlayarak yapılabilir **AFX_DATA** , belirli sınıfı makrosu için. Bu, bütün sınıfı dışarı aktarma değil dilediğiniz zaman yapılmalıdır.  
  
 Örneğin:  
  
```  
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
*//class definition   
 .  
 .  
 .  
};  
 
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### <a name="dllmain"></a>DllMain  
 Ana kaynak dosyanızda, MFC uzantı DLL'si yerleştirmelisiniz tam kod aşağıda verilmiştir. Standart içerir sonra gelmelidir. MFC uzantı DLL'si başlangıç dosyalarını oluşturmak için AppWizard kullandığınızda, bu kaynakları not bir `DllMain` sizin için.  
  
```  
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
  
 Çağrısı `AfxInitExtensionModule` modülleri çalışma zamanı sınıfları yakalar (`CRuntimeClass` yapıları) yanı sıra kendi nesne oluşturucuları (`COleObjectFactory` nesneler) kullanmak için sonraki olduğunda **CDynLinkLibrary** nesnesi oluşturulur. (İsteğe bağlı) çağrısı `AfxTermExtensionModule` her işlem ayırır olduğunda MFC Temizleme için MFC uzantı DLL'si izin verir. (işlem çıktığında ya da DLL sonucu olarak kaldırıldığında gerçekleşir bir **FreeLibrary** çağrısı) MFC uzantı DLL . Çoğu MFC uzantı DLL'leri dinamik olarak yüklenmez bu yana (genellikle, bunlar, içeri aktarma kitaplıkları bağlı), çağrısı `AfxTermExtensionModule` genellikle gerekli değildir.  
  
 Uygulamanızı yükler ve MFC uzantı DLL'leri dinamik olarak boşaltır, çağırdığınızdan emin olun `AfxTermExtensionModule` yukarıda gösterildiği gibi. Ayrıca kullandığınızdan emin olun `AfxLoadLibrary` ve `AfxFreeLibrary` (Win32 işlevleri yerine **LoadLibrary** ve **FreeLibrary**) uygulamanız birden çok iş parçacığı kullanıyorsa veya dinamik olarak bir MFC yüklüyorsa uzantı DLL. Kullanarak `AfxLoadLibrary` ve `AfxFreeLibrary` MFC uzantı DLL yüklendiğinde ve kaldırıldığında yürütülen başlatma ve kapatma kodunun genel MFC durumunu bozuk olmayan oluşturmasını sağlar.  
  
 Üstbilgi dosyası AFXDLLX. H tanımı gibi MFC uzantı DLL'leri içinde kullanılan yapılar için özel tanımları içerir `AFX_EXTENSION_MODULE` ve **CDynLinkLibrary**.  
  
 Genel *extensionDLL* gösterildiği gibi bildirilmelidir. MFC 16-bit sürümüne, bellek ayırabilir ve MFCxx.DLL tamamen başlatılmış olduğundan bu süre boyunca çağırabilirsiniz MFC işlevleri, `DllMain` olarak adlandırılır.  
  
### <a name="sharing-resources-and-classes"></a>Kaynakları ve sınıfları paylaşma  
 Basit MFC uzantı DLL'leri yalnızca birkaç düşük bant genişlikli istemci uygulaması ve hiçbir şey için daha fazla dışarı aktarma işlevleri. Daha fazla kullanıcı arabirimi yoğun DLL'leri kaynakları ve C++ sınıfları istemci uygulamasına vermek isteyebilirsiniz.  
  
 Kaynakları dışarı aktarma, bir kaynak listesi üzerinden yapılır. Her iki uygulamada ayrı olarak bağlantılı bir listesidir **CDynLinkLibrary** nesneleri. Bir kaynak ararken kaynakları yükleyen standart MFC uygulamalarının çoğunu geçerli kaynak modülüne bakar (`AfxGetResourceHandle`) ve ilerlemesi bulunamadı listesini **CDynLinkLibrary** nesneleri yüklenmeye çalışılıyor İstenen kaynak.  
  
 C++ nesneleri bir C++ sınıf adı verilen dinamik oluşturulmasını benzer. MFC nesne seri durumdan çıkarma mekanizması tümüne sahip olması `CRuntimeClass` nesneleri kaydedilen ne daha önce depolanan üzerinde bağlı olarak gerekli tür C++ nesnesinin dinamik olarak oluşturarak yeniden.  
  
 MFC uzantı DLL'si olan sınıfları kullanmak için istemci uygulaması istiyorsanız `DECLARE_SERIAL`, istemci uygulamasına görünür olmasını, sınıfları dışarı gerekecektir. Bu adım adım ilerlemenizi sağlayarak gerçekleştirilir **CDynLinkLibrary** listesi.  
  
 MFC Gelişmiş kavramları örnek durumunda [DLLHUSK](../visual-cpp-samples.md), liste şöyle görünür:  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
 |      |  
    TESTDLL2.DLL TESTDLL2.DLL  
 |      |  
    TESTDLL1.DLL TESTDLL1.DLL  
 |      |  
 |      |  
    MFC90D.DLL MFC90.DLL  
```  
  
 MFCxx.DLL kaynak ve sınıf listesi genellikle son. MFCxx.DLL tüm standart komut kimlikleri için komut istemi dizeleri dahil olmak üzere tüm standart MFC kaynakları içerir. Listenin tail yerleştirme verir DLL'ler ve yüklüyse istemci uygulamanın kendisinin bir MFCxx.dll paylaşılan kaynakları yerine Bel üzere ancak standart MFC kaynakları, kendi kopyası.  
  
 İstemci uygulamanın ad alanına birleştirme kaynakları ve sınıf adlarını tüm DLL'ler hangi kimlikleri dikkatli olmak zorunda dezavantajı veya adları var. Kuşkusuz bu özellik ya da vererek olmayan kaynaklarınızı devre dışı bırakabilirsiniz veya **CDynLinkLibrary** istemci uygulamasına nesne. [DLLHUSK](../visual-cpp-samples.md) örnek birden çok başlık dosyalarını kullanarak paylaşılan kaynak ad alanı yönetir. Bkz: [Teknik Not 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) paylaşılan kaynak dosyalarını kullanma hakkında daha fazla ipucu için.  
  
### <a name="initializing-the-dll"></a>DLL başlatma  
 Yukarıda belirtildiği gibi genellikle oluşturmak istediğiniz bir **CDynLinkLibrary** kaynakları ve sınıfları istemci uygulamaya dışa aktarmak için nesne. DLL başlatmak için dışarı aktarılan giriş noktası sağlamanız gerekir. En düşük düzeyde, bu bağımsız değişken almayan ve hiçbir şey döndüren, void bir yordamdır, ancak istediğiniz herhangi bir şey olabilir.  
  
 Bu yaklaşımı kullanırsanız, DLL kullanmak istediği her istemci uygulaması bu başlatma yordam çağırmalıdır. Bu ayrıca ayırabilir **CDynLinkLibrary** nesnesinde, `DllMain` çağırdıktan hemen sonra `AfxInitExtensionModule`.  
  
 Başlatma yordamı oluşturmalısınız bir **CDynLinkLibrary** , MFC uzantı DLL bilgi kadar kablolu geçerli uygulamanın yığınındaki nesnesi. Bu aşağıdaki ile yapılabilir:  
  
```  
extern "C" extern void WINAPI InitXxxDLL()  
{  
    new CDynLinkLibrary(extensionDLL);

}  
```  
  
 Rutin adı *InitXxxDLL* Bu örnekte, istediğiniz herhangi bir şey olabilir. Olması gerekmez `extern "C"`, ancak bunu yapar verme listesine korumak daha kolay yapmak.  
  
> [!NOTE]
>  Normal MFC DLL, MFC uzantı DLL kullanırsanız, bu başlatma işlevi dışarı aktarmanız gerekir. Bu işlev, Normal MFC DLL herhangi bir MFC uzantı DLL sınıfları veya kaynakları kullanmadan önce çağrılmalıdır.  
  
### <a name="exporting-entries"></a>Girişleri dışarı aktarma  
 Sınıflarını dışarı aktarmak için basit bir yolla kullanmaktır **__declspec(dllimport)** ve **__declspec(dllexport)** her bir sınıf ve dışarı aktarmak istediğiniz genel işlevi. Bu, çok daha kolay hale getirir, ancak hangi işlevleri dışarı üzerinde daha az denetime sahip ve sıralı olarak işlevleri verilemiyor (aşağıda açıklanmıştır) her bir giriş noktası adlandırma değerinden daha az verimlidir. TESTDLL1 ve TESTDLL2 girdilerinin dışarı aktarmak için bu yöntemi kullanın.  
  
 Daha verimli bir yöntem (ve MFCxx.DLL tarafından kullanılan yöntem) her giriş el ile her giriş adlandırma tarafından verilmesidir. DEF dosyası. Seçmeli dışarı bizim DLL'den (diğer bir deyişle, her şeyin) verdiğiniz olduğundan, biz dışarı aktarmak için istediğimiz hangi belirli arabirimleri karar vermeniz gerekir. Girdiler biçiminde bağlayıcı karıştırılmış adlar belirtmelisiniz beri bu zordur. DEF dosyası. Sembolik bağlantı için gerçekten gerekli olmadıkça herhangi C++ sınıfları vermeyin.  
  
 Bunu denediyseniz C++ dışarı aktarma ile sınıfları bir. DEF bu listeyi otomatik olarak oluşturmak için bir araç geliştirmek isteyebilirsiniz önce dosya. Bu yapılabilir iki aşamalı bağlama işlemini kullanma. DLL kez hiçbir dışarı aktarma ile bağlantı ve oluşturmak bağlayıcı izin bir. Harita dosyası. . EŞLEME dosyası, bazı yeniden düzenleme ile bu verme girişlerinizi oluşturmak için kullanılacak şekilde dışa mı, işlevlerin bir listesini oluşturmak için kullanılabilir. DEF dosyası. (Tamamen otomatik değildir ve bir süre her bir kez ayarlama bazı el gerektirir ancak) verme listesi MFCxx.DLL ve OLE ve veritabanı MFC uzantı DLL'leri, birkaç bin sayısı, böyle bir işlem oluşturuldu.  
  
### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp vs. CDynLinkLibrary  
 Bir MFC uzantı DLL'si sahip olmayan bir `CWinApp`-nesnesinin kendi türetilmiş; bunun yerine birlikte çalışmalısınız `CWinApp`-nesne istemci uygulamasının türetilmiş. Bu, istemci uygulaması ana ileti göndericisi, boşta döngü vb. sahibi olduğu anlamına gelir.  
  
 MFC uzantı DLL her uygulama için ek veri tutması gerekiyorsa, yeni bir sınıf türetin **CDynLinkLibrary** ve yordam açıklanmaktadır yukarıda InitXxxDLL oluşturun. Çalıştırırken, DLL geçerli uygulama listesini denetleyebilirsiniz **CDynLinkLibrary** belirli MFC uzantısı DLL bulmak için nesneleri.  
  
### <a name="using-resources-in-your-dll-implementation"></a>DLL uygulamanızda kaynaklarını kullanma  
 Yukarıda belirtildiği gibi varsayılan kaynak yükü listesini yükselteceğinizi **CDynLinkLibrary** ilk EXE veya istenen kaynak DLL arayan nesneleri. Tüm MFC API'leri yanı sıra tüm iç kod kullanan `AfxFindResourceHandle` bulunduğu olsun hiçbir kaynak bulmak için kaynak listesi yürütmek için.  
  
 Yalnızca belirli bir konumdan kaynakları yüklemek isterseniz, API'lerini kullanan `AfxGetResourceHandle` ve `AfxSetResourceHandle` eski tutamacı kaydedip yeni tutamacı ayarlayın. İstemci uygulamasına geri dönmeden önce eski kaynak tanıtıcısını geri yüklediğinizden emin olun. Örnek TESTDLL2, açıkça bir menü yüklemek için bu yaklaşımı kullanır.  
  
 Listenin taramasını kısmen daha yavaştır ve kaynak kimlik aralıklarını yönetmeyi gerektirir dezavantajları vardır. Birkaç MFC uzantı DLL'leri bağlanan istemci uygulaması herhangi bir DLL tarafından sağlanan kaynak DLL örneği işleyicisi belirtmek zorunda kalmadan kullanabileceğiniz avantajına sahiptir. `AfxFindResourceHandle`bir API, belirli bir eşleşme için aranacak kaynak listesi taramasını için kullanılır. Bir kaynak türü ve adını alır ve ilk bulunduğu kaynak tanıtıcısı (veya NULL) döndürür.  
  
##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>DLL sürümü kullanan bir uygulamayı yazma  
  
### <a name="application-requirements"></a>Uygulama gereksinimleri  
 MFC paylaşılan sürümünü kullanan bir uygulamayı birkaç basit kurallara uymalıdır:  
  
-   Gerekir bir `CWinApp` nesnesi ve standart kurallar için bir ileti Pompalama izleyin.  
  
-   Gerekli derleyici bayrakları (aşağıya bakın) bir dizi derlenmiş gerekir.  
  
-   MFCxx içeri aktarma kitaplıkları ile bağlamanız gerekir. MFC üstbilgileri gerekli derleyici bayrakları ayarlayarak, uygulama ile bağlanması gereken hangi kitaplığı bağlantı zaman belirler.  
  
-   Yürütülebilir dosyayı çalıştırmak için MFCxx.DLL yolunda veya Windows sistem dizininde olması gerekir.  
  
### <a name="building-with-the-development-environment"></a>Geliştirme ortamı oluşturma  
 Standart varsayılanlara çoğuyla iç derleme görevleri dosyası kullanıyorsanız, DLL sürümü oluşturmak için proje kolayca değiştirebilirsiniz.  
  
 Aşağıdaki adımı NAFXCWD ile bağlantılı düzgün çalışan bir MFC uygulamayı olduğunu varsayar. LIB (için hata ayıklama) ve NAFXCW. LIB (Perakende için) ve paylaşılan MFC kitaplık sürümünü kullanacak şekilde dönüştürmek istersiniz. Visual C++ ortamına çalıştıran ve bir iç proje dosyasına sahip.  
  
1.  Üzerinde **projeleri** menüsünde tıklatın **özellikleri**. İçinde **genel** altında sayfa **Proje Varsayılanları**, Microsoft Foundation sınıfları kümesine **MFC'yi paylaşılan DLL'de** (MFCxx(d).dll).  
  
### <a name="building-with-nmake"></a>NMAKE ile oluşturma  
 Visual C++ dış derleme görevleri dosyası özelliğini kullanarak veya NMAKE doğrudan kullanıyorsanız, derleyici ve bağlayıcı seçenekleri desteklemek için derleme görevleri dosyası Düzenle gerekir  
  
 Gerekli derleyici bayrakları:  
  
 **/ D_AFXDLL /MD**  
 **/ D_AFXDLL**  
  
 Standart MFC üstbilgileri tanımlanması için bu simgeyi gerekir:  
  
 **/MD**  
 Uygulama C çalışma zamanı kitaplığı DLL sürümü kullanmanız gerekir  
  
 Diğer tüm derleyici bayrakları (örneğin, hata ayıklama için _DEBUG) MFC Varsayılanları izleyin.  
  
 Kitaplık bağlayıcı listesini düzenleyin. Değişiklik NAFXCWD. İçin MFCxxD.LIB LIB ve NAFXCW değiştirin. LIB MFCxx.LIB için. LIBC değiştirin. İle MSVCRT LIB. LIB. Diğer MFC kitaplığı ile MFCxxD.LIB yerleştirilir önemli olduğu gibi **önce** C çalışma zamanı kitaplıkları.  
  
 İsteğe bağlı olarak ekleyin **/D_AFXDLL** perakende ve hata ayıklama kaynağı derleyici seçenekleri (gerçekten kaynaklarla derlenen bir **/R**). Bu, son yürütülebilir MFC DLL'leri mevcut olan kaynakları paylaşarak küçültür.  
  
 Bu değişiklikler yapıldıktan sonra bir tam yeniden oluşturma gereklidir.  
  
### <a name="building-the-samples"></a>Örnekleri oluşturma  
 MFC örnek programların çoğu, Visual C++ ya da komut satırından paylaşılan NMAKE uyumlu derleme görevleri oluşturulabilir.  
  
 MFCxx.DLL kullanmak için bu örnekleri hiçbirini dönüştürmek için yükleyebilirsiniz. MAK dosya Visual C++ ve yukarıda açıklandığı gibi proje seçenekleri ayarlayın. NMAKE derleme kullanıyorsanız, belirtebilmeniz için "AFXDLL = 1" üzerinde NMAKE komut satırı ve, paylaşılan MFC kitaplıkları kullanarak örneği oluşturur.  
  
 MFC Gelişmiş kavramları örnek [DLLHUSK](../visual-cpp-samples.md) MFC'nin DLL sürümü ile oluşturulmuş. Bu örnek yalnızca MFCxx.DLL ile bağlantılı bir uygulamanın nasıl oluşturulacağını gösterir, ancak aynı zamanda MFC DLL paketleme seçeneği MFC uzantı DLL'leri daha sonra bu Teknik Not açıklandığı gibi diğer özelliklerini gösterir.  
  
### <a name="packaging-notes"></a>Paketleme notları  
 DLL'ler (MFCxx [U] perakende sürümü. DLL) ücretsiz olarak yeniden dağıtılabilir. DLL'lerde hata ayıklama sürümü, ücretsiz olarak dağıtılabilen değildir ve yalnızca, uygulama geliştirme sırasında kullanılmalıdır.  
  
 DLL'lerde hata ayıklama, hata ayıklama bilgileri ile sağlanır. Visual C++ hata ayıklayıcı kullanarak, DLL yanı sıra, uygulamanızın yürütülmesini izleyebilirsiniz. Yayın DLL'leri (MFCxx [U]. DLL) hata ayıklama bilgilerini içermez.  
  
 Özelleştirme veya DLL'leri yeniden oluşturun, sonra bunları bir şey "MFCxx" MFC SRC dosya MFCDLL dışında çağırmalıdır. MAK derleme seçenekleri açıklar ve DLL yeniden adlandırma mantığı içerir. Bu DLL'ler potansiyel olarak birçok MFC Uygulama tarafından paylaşılan dosyaları yeniden adlandırma gerekli olduğu. MFC DLL'leri Değiştir özel sürümüne sahip olanlar sistemde yüklü paylaşılan MFC DLL'leri kullanmanın başka bir MFC uygulaması kesilebilir.  
  
 MFC DLL'leri yeniden önerilmez.  
  
##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>MFCxx.DLL nasıl uygulanır  
 Aşağıdaki bölümde, MFC DLL (MFCxx.DLL ve MFCxxD.DLL) nasıl uygulandığı açıklanmaktadır. Ayrıntılarını burada da olmayan anlama, tüm yapmak istiyorsanız, MFC DLL uygulamanızla birlikte kullanmak önemlidir. Ayrıntılarını burada MFC uzantı DLL'si yazmak nasıl anlamak için gerekli değildir, ancak bu uygulama anlama kendi DLL yazmanıza yardımcı olabilir.  
  
### <a name="implementation-overview"></a>Uygulama genel bakış  
 MFC DLL gerçekten özel bir MFC uzantı DLL'si, yukarıda açıklandığı gibi bir durumdur. Dışarı aktarmalar çok sayıda sınıfları için çok fazla sayıda sahiptir. Normal bir MFC uzantı DLL'si daha özel olun biz MFC DLL'inde yapmak birkaç ek nokta vardır.  
  
### <a name="win32-does-most-of-the-work"></a>Win32 işlerin çoğunu yapar  
 MFC 16-bit sürümünü çeşitli uygulama başına veri yığını kesimindeki bazı 80 x 86 bütünleştirilmiş kodu, işlem başına özel durum bağlamı ve başka teknikler tarafından oluşturulan özel kesimler de dahil olmak üzere özel teknikler gerekli. Win32 doğrudan işlem içi verileri DLL'de, çoğu zaman istediğiniz olduğu destekler. Çoğunlukla MFCxx.DLL yalnızca NAFXCW ' dir. DLL içinde paketlenmiş LIB. MFC kaynak kodu bakarsanız, yapılması gereken çok az sayıda özel durumlar olduğundan, çok az #ifdef _AFXDLL bulabilirsiniz. Vardır özellikle Win32 Windows (Win32 da bilinir) 3.1'uğraşmanız olan özel durumlar. MFC DLL iş parçacığı yerel depolaması (TLS) işlem yerel verileri elde etmek için Win32 API'ları kullanın gerekir doğrudan Win32 destek işlem içi DLL verileri değil yapar.  
  
### <a name="impact-on-library-sources-additional-files"></a>Kitaplık kaynakları, ek dosyalar üzerinde etkisi  
 Etkisini **_AFXDLL** normal MFC sınıf kitaplığı kaynağı ve üstbilgileri sürümünde görece küçük. Özel sürüm dosyası (AFXV_DLL. H) yanı sıra ek üstbilgi dosyası (AFXDLL_. H) tarafından ana AFXWIN dahil. H üstbilgisi. AFXDLL_. H üstbilgisi içerir **CDynLinkLibrary** sınıfı ve diğer uygulama ayrıntılarını her ikisi de **_AFXDLL** uygulamaları ve MFC uzantı DLL'leri. AFXDLLX. H üstbilgi MFC uzantı DLL'leri (Ayrıntılar için yukarıdaki bakın) oluşturmak için sağlanır.  
  
 Bazı ek koşullu kod altında normal kaynakları MFC SRC MFC kitaplığına sahip **_AFXDLL** #ifdef. Bir ek kaynak dosyası (DLLINIT. Fazladan DLL başlatma kod ve diğer Birleştirici MFC paylaşılan sürümü için CPP) içerir.  
  
 MFC paylaşılan sürümünü oluşturmak için ek dosyalar sağlanır. (Aşağıda DLL oluşturma hakkında ayrıntılı bilgi için bkz.)  
  
-   İki. DEF Dosyaları (MFCxxD.DEF) hata ayıklama MFC DLL Giriş noktalarına dışa aktarmak için kullanılır ve DLL sürümleri (MFCxx.DEF) bırakın.  
  
-   Bir. RC dosya (MFCDLL. RC) tüm standart MFC kaynakları ve VERSIONINFO kaynak DLL için içerir.  
  
-   A. CLW dosyası (MFCDLL. MFC gözatma izin verecek şekilde ClassWizard kullanarak sınıfları CLW) sağlanır. Not: Bu özellik belirli MFC'nin DLL sürümü değil.  
  
### <a name="memory-management"></a>Bellek Yönetimi  
 MFCxx.DLL kullanarak bir uygulamayı paylaşılan C çalışma zamanı DLL MSVCRTxx.DLL tarafından sağlanan ortak bir bellek ayırıcısı kullanır. Uygulama, tüm MFC uzantı DLL'leri ve MFC DLL'leri yanı bu paylaşılan bellek ayırıcısı kullanın. MFC DLL'leri, paylaşılan bir DLL için bellek ayırma kullanarak, daha sonra uygulama tarafından veya serbest bellek ayrılabilir. Uygulama ve DLL aynı ayırıcısı kullanmanız gerekir çünkü genel C++ geçersiz `operator new` veya `operator delete`. C çalışma zamanı bellek ayırma yordamları geri kalanı için aynı kuralları uygula (gibi `malloc`, `realloc`, **ücretsiz**ve diğerleri).  
  
### <a name="ordinals-and-class-declspecdllexport-and-dll-naming"></a>Sıra numaraları ve sınıf __declspec(dllexport) ve DLL adlandırma  
 Biz kullanmayın `class` **__declspec(dllexport)** C++ derleyicisi işlevselliğini. Bunun yerine, dışarı aktarma listesini sınıf kitaplığı kaynaklarıyla (MFCxx.DEF ve MFCxxD.DEF) dahil edilir. Giriş noktaları (İşlevler ve veriler) select bu kümesi verilir. MFC özel uygulama işlevleri ya da sınıflarını gibi diğer simgelerini verilmemiş tüm dışarı sıra yerleşik veya yerleşik olmayan adı tablosundaki bir dize adı olmadan tarafından yapılır.  
  
 Kullanarak `class` **__declspec(dllexport)** küçük DLL'leri oluşturmak için ancak büyük DLL MFC, dışa aktarma mekanizması varsayılan gibi söz konusu olduğunda uygun bir alternatif olan verimliliği ve kapasite olabilir sınırlar.  
  
 Tüm Bunun anlamı nedir işlevi yalnızca yaklaşık 800 kadar yürütme tehlikeye veya hızlı yükleme olmadan KB'dir MFCxx.DLL sürümde, büyük bir miktarını paketleyebilirsiniz. MFCxx.DLL olabilirdi 100K daha büyük Bu teknik karşılanmadığını kullanılır. Bu ayrıca, sonunda ek giriş noktaları eklemek mümkün kılar. Sıralı olarak verme hızını ve boyutu verimliliği ödün vermeden basit sürüm oluşturma izni DEF dosyası. MFC Sınıf Kitaplığı'nda ana sürüm düzeltmelerini kitaplık adını değiştirir. Diğer bir deyişle, MFC30. MFC sınıf kitaplığı 3.0 sürümünü içeren redistributable DLL DLL'dir. Bu DLL yükseltmesini söyleyin, kuramsal bir MFC 3.1 DLL MFC31 adlı. DLL yerine. MFC DLL, özel bir sürümünü oluşturmak için MFC kaynak kodunda değişiklik yaparsanız, yeniden, farklı bir ad (ve tercihen biri adında "MFC" olmadan) kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)

