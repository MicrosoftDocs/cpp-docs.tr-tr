---
title: İpucu dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- cpp.hint
- vc.hint.file
dev_langs:
- C++
helpviewer_keywords:
- stop file
- cpp.hint
- hint file
- cpp.stop
- Class View, hint file
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 687e5cba94693a752f934d7816e6a7c36e318354
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33336703"
---
# <a name="hint-files"></a>İpucu Dosyaları
A *ipucu dosyası* yardımcı olan Visual Studio tümleşik geliştirme ortamı (IDE) yorumlama adlarını, İşlevler ve makrolar gibi Visual C++ tanımlayıcıları. Bir Visual C++ proje, IDE açtığınızda *sistem ayrıştırma* kodunu projeyi her kaynak dosyasında çözümler ve her bir tanımlayıcı hakkında bilgi toplar. IDE gibi özellikleri desteklemek için bu bilgileri kullanıyorsa **sınıf görünümü** tarayıcı ve **gezinti çubuğu**.  
  
 Visual C++ 2010'da sunulan ayrıştırma sistem C/C++ sözdizimi anlar ancak makro içeren bir ifade hatalı yorumlayan. Makro yazılmış sözdizimsel olarak yanlış görünüyor kaynak kodu neden olursa deyim yorumlanabilir. Kaynak kodu derlenir ve preprocesser değiştirir deyim sözdizimsel olarak doğru olabilir [makro tanımlayıcısı](../preprocessor/hash-define-directive-c-cpp.md) tanımına sahip. Ayrıştırma sistem makroları yorumlamaya ipucu dosyaları kullandığından projeyi oluşturmak zorunda kalmadan çalışır. Bu nedenle, bir tarama özelliği gibi **sınıf görünümü** hemen kullanılabilir.  
  
 İpucu dosyası kullanıcı özelleştirilebilir içeren *ipuçları*, C/C++ makrosu tanımları ile aynı söz dizimini sahip. Visual C++ projelerinin çoğu için yeterlidir yerleşik ipucu dosyası içerir, ancak Visual Studio tanımlayıcıları işleme biçimini geliştirmek için kendi ipucu dosyaları oluşturabilirsiniz.  
  
> [!IMPORTANT]
>  Değiştirme veya ipucu dosya ekleme, .sdf dosya ve/veya değişikliklerin etkili olması çözümde VC.db dosyasında silmeniz gerekir.  
  
## <a name="scenario"></a>Senaryo  
 Aşağıdaki kod ile inceleyin bir kaynak dosyası olduğunu varsayın **sınıf görünümü** tarayıcı. `STDMETHOD` Makrosu bildirir adlı bir yöntem `myMethod` bir parametre alır ve bir işaretçi döndüren bir **HRESULT**.  
  
```  
// Source code file.  
STDMETHOD(myMethod)(int parameter1);  
```  
  
 Aşağıdaki makrosu tanımları ayrı bir üstbilgi dosyasında yer alır.  
  
```  
// Header file.  
#define STDMETHOD(method) HRESULT (STDMETHODCALLTYPE * method)  
#define STDMETHODCALLTYPE __stdcall  
#define HRESULT void*  
```  
  
 STDMETHOD adlı bir işlev bildirilmesi göründüğünden ayrıştırma sistem kaynak kodunu yorumlanamıyor ve iki parametre listeleri içerdiğinden bildirim sözdizimsel olarak geçersiz. Ayrıştırma sistem tanımlarında bulmak için üstbilgi dosyası açılmaz `STDMETHOD`, `STDMETHODCALLTYPE`, ve `HRESULT` makroları. Ayrıştırma sistem yorumlanamıyor çünkü `STDMETHOD` makrosu, tüm deyimi yoksayar ve sonra ayrıştırma devam eder.  
  
 Projenizi bir veya daha fazla önemli üstbilgi dosyalarına dayanan çünkü ayrıştırma sistem başlık dosyalarını kullanmaz. Üstbilgi dosyası değişirse, ayrıştırma sistem tüm IDE performans yavaşlatır projenize üstbilgi dosyaları yeniden gözden geçirin gerekebilir. Bunun yerine, ayrıştırma sistem nasıl işleneceğini belirtin ipuçları kullanır `STDMETHOD`, `STDMETHODCALLTYPE`, ve `HRESULT` makroları.  
  
 Nasıl bir ipucu gerektiğini biliyor musunuz? Ve ne tür bir ipucu gerekiyorsa, oluşturmalısınız? İpucu gereklidir bir oturum varsa bir tanımlayıcı görünümünü **sınıf görünümü** görünümünde tutarsız **Düzenleyicisi**. Örneğin, **sınıf görünümü** görüntüleme bildiğiniz bir sınıf üyesi var olabilir veya üyenin adı yanlış. Sık karşılaşılan sorunları ipuçları türleri hakkında daha fazla bilgi için bkz: ne makroları gerektiren bir ipucu? Bu konunun ilerleyen bölümlerinde bölümü.  
  
## <a name="architecture"></a>Mimari  
 İpucu dosyaları fiziksel dizinlerle ilgilidir, içinde mantıksal dizinleri gösterilen **Çözüm Gezgini**. Projeniz etkili olabilmesi ipucu dosyası için bir ipucu dosya eklemek gerekmez. Yalnızca kaynak dosyalarını ayrıştırırken ayrıştırma sistem ipucu dosyaları kullanır.  
  
 Her ipucu dosyası adlı **cpp.hint**. Bu nedenle, birden çok dizini bir ipucu dosyası içerebilir ancak yalnızca bir ipucu dosyası içinde belirli bir dizin ortaya çıkabilir.  
  
 Projenizi sıfır veya daha fazla ipucu dosyaları tarafından etkilenebilir. İpucu dosya yoksa ayrıştırma sistem şifresi çözülemeyen kaynak kodu yoksaymak için hata kurtarma teknikleri kullanır. Aksi takdirde ayrıştırma sistem bulmak ve ipuçlarını toplamak için aşağıdaki stratejisi kullanır.  
  
### <a name="search-order"></a>Arama sırası  
 Ayrıştırma sistem dizinleri ipucu dosyaları için aşağıdaki sırayla arar.  
  
-   Visual C++ için yükleme paketini içeren dizine (**vcpackages**). Bu dizin, sık kullanılan sistem dosyaları, simgeler gibi açıklar bir yerleşik ipucu dosyasını içeren **windows.h**. Sonuç olarak, projeniz gerekli ipuçları çoğunu otomatik olarak devralır.  
  
-   Kaynak dosyası içeren dizine kaynak dosyasının kök dizin yolu. Tipik bir Visual C++ projesinde kök dizin çözüm ya da proje dosyası içerir.  
  
     Bu kural için özel durum, bir *Dur dosya* yolunda kaynak dosyasına. Stop dosyası arama sırası ek denetim sunar ve adlı dosyayı **cpp.stop**. Kök dizininden başlayarak yerine, kaynak dosyasını içeren dizine Dur dosyasını içeren dizininden ayrıştırma sistem arar. Tipik bir projede Dur dosya gerekmez.  
  
### <a name="hint-gathering"></a>İpucu toplanıyor  
 Sıfır veya daha fazla ipucu dosyası içeren *ipuçları*. İpucu tanımlanan veya yeni bir C/C++ makrosu gibi silindi. Diğer bir deyişle, `#define` önişlemci yönergesi oluşturur veya bir ipucu yeniden tanımlar ve `#undef` yönergesi ipucu siler.  
  
 Ayrıştırma sistem daha önce açıklanan arama sırayla her ipucu dosyası açıldığında, her bir dosyanın ipuçları bir kümesine öğelerden *etkili ipuçları*ve daha sonra kodunuzda tanımlayıcıları yorumlamak için etkili ipuçları kullanır.  
  
 Ayrıştırma sistem ipuçları birikmesine aşağıdaki kuralları kullanır.  
  
-   Yeni ipucu zaten tanımlı değil bir ad belirtiyorsa, yeni ipucu etkili ipuçları adı ekler.  
  
-   Yeni ipucu zaten tanımlı bir ad belirtiyorsa, yeni ipucu varolan ipucu yeniden tanımlamaktadır.  
  
-   Yeni ipucu ise bir `#undef` yönerge, varolan bir etkili ipucu belirtir, varolan ipucu yeni ipucu siler.  
  
 İlk kural etkili ipuçları önceden açılan ipucu dosyalarından devralınacağı anlamına gelir. Son iki kural daha sonra arama sırayla ipuçları önceki oluştu ipuçları kılabilirsiniz anlamına gelir. Örneğin, bir kaynak dosyasını içeren dizinde bir ipucu dosyası oluşturursanız, önceki İpucu geçersiz kılabilirsiniz.  
  
 İpuçları nasıl toplanır bir gösterimi için bkz: `Example` bu konunun ilerleyen bölümlerinde.  
  
### <a name="syntax"></a>Sözdizimi  
 İpuçları oluşturulur ve aynı söz dizimine oluşturmak ve makroları silme önişlemci yönergeleri ile silinir. Aslında, ayrıştırma sistem C/C++ ön işlemci ipuçları değerlendirmek için kullanır. Önişlemci yönergeleri hakkında daha fazla bilgi için bkz: [#define yönergesi (C/C++)](../preprocessor/hash-define-directive-c-cpp.md) ve [#undef yönergesi (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md).  
  
 Yalnızca olağan dışı sözdizimi öğeler `@<`, `@=`, ve `@>` değiştirme dizeleri. İle yalnızca kullanılan ipucu dosyası belirli değiştirme dizelerini bunlar *harita* makroları. Bir harita verilerini, işlevleri ya da olaylar diğer verileri, işlevleri veya olay işleyicileri ilişkili makroları kümesidir. Örneğin, `MFC` eşlemeleri oluşturmak için kullandığı [ileti eşlemeleri](../mfc/reference/message-maps-mfc.md), ve `ATL` eşlemeleri oluşturmak için kullandığı [nesne eşlemeleri](../atl/reference/object-map-macros.md). İpucu dosyası belirli değiştirme dizelerini bir harita başlangıç, Ara ve bitiş öğelerini belirtin. Yalnızca bir harita makro adını önemlidir. Bu nedenle, her değiştirme dizesini bilerek makrosu uyarlamasını gizler.  
  
 İpuçları aşağıdaki sözdizimini kullanın.  
  
|Sözdizimi|Açıklama|  
|------------|-------------|  
|`#define` *İpucu adı* *değiştirme dizesi*<br /><br /> `#define` *İpucu adı* `(` *parametresi*,... `)` *değiştirme dizesi*|Yeni bir ipucu tanımlar ya da varolan bir ipucu yeniden tanımlamaktadır preprocesser yönergesi. Her oluşumu önişlemci yönergesi sonra değiştirir *ipucu adı* içeren kaynak kodu *değiştirme dizesini*.<br /><br /> İkinci sözdizimi işlevi benzeri ipucu biçimini tanımlar. Önişlemci işlevi benzeri ipucu kaynak kodunda meydana gelirse, önce her oluşumu değiştirir. *parametresi* içinde *değiştirme dizesini* kaynak kodu ve değiştirir karşılık gelen bağımsız değişkeni ile *ipucu adı* ile *değiştirme dizesini*.|  
|`@<`|İpucu dosyası belirli bir *değiştirme dizesini* harita öğelerine kümesi başlangıcını gösterir.|  
|`@=`|İpucu dosyası belirli bir *değiştirme dizesini* Ara map öğesi gösterir. Bir harita birden çok harita öğelerine sahip olabilir.|  
|`@>`|İpucu dosyası belirli bir *değiştirme dizesini* harita öğelerine kümesi sonunu gösterir.|  
|`#undef` *İpucu adı*|Varolan bir ipucu siler önişlemci yönergesi. İpucu adı tarafından sağlanan *ipucu adı* tanımlayıcısı.|  
|`//` *Açıklama*|Tek satırlı yorum.|  
|`/*` *Açıklama* `*/`|Çok satırlı açıklaması.|  
  
## <a name="what-macros-require-a-hint"></a>Ne makroları gerektiren bir ipucu?  
 Belirli türde bir makroları ayrıştırma sistemiyle etkileyebilir. Bu bölümde, bir soruna neden olabilir makroları türleri ve bu sorunu çözmek için oluşturabileceğiniz ipucu türünü açıklar.  
  
### <a name="disruptive-macros"></a>Kesintiye uğratan makroları  
 Bazı makrolar ayrıştırma kaynak kodu hatalı yorumlayan başlatılmasına neden ancak gözatma deneyiminizi azaltmıyorsa göz ardı edilebilir. Örneğin, kaynak kodu ek açıklama dili ([SAL](../c-runtime-library/sal-annotations.md)) makroları yardımcı C++ öznitelikleri Bul programlama hataları çözümleyin. Kod gezinirken SAL ek açıklamaları yoksaymak istiyorsanız, ek açıklamanın gizleyen bir ipucu dosyası oluşturmak isteyebilirsiniz.  
  
 Aşağıdaki kaynak kodunda tür parametresi için `FormatWindowClassName()` işlevi `PXSTR`, ve parametre adı `szBuffer`. Ancak, ayrıştırma sistem hataları `_Pre_notnull_` ve `_Post_z_` parametre türü veya parametre adı için SAL ek açıklamaları.  
  
 **Kaynak kodu:**  
  
```  
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)  
```  
  
 **Stratejisi:** Null tanımı  
  
 Bu durumda mevcut sanki SAL ek açıklamaları işlemek için stratejidir. Bunu yapmak için değiştirme dizesi null ipucu belirtin. Sonuç olarak, ek açıklamalar, ayrıştırma sistem göz ardı eder ve **sınıf görünümü** tarayıcı bunları görüntülemez. (Visual C++ SAL ek açıklama gizler yerleşik ipucu dosyası içerir.)  
  
 **İpucu dosyası:**  
  
```  
#define _Pre_notnull_  
```  
  
### <a name="concealed-cc-language-elements"></a>Gizli bilgiler C/C++ dil öğeleri  
 Ayrıştırma sistem kaynak kodu misinterprets bir tipik bir makro C/C++ gizler varsa nedeni [işaretiyle niteleyerek](../cpp/punctuators-cpp.md) veya [anahtar sözcüğü](../cpp/keywords-cpp.md) belirteci. Diğer bir deyişle, bir makro noktalama işaretleri, bir çift yarısı gibi içerebilir `<>`, `[]`, `{}`, ve `()`.  
  
 Aşağıdaki kaynak kodda `START_NAMESPACE` makrosu gizler eşlenmemiş sol ayraç (`{`).  
  
 **Kaynak kodu:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
 **Stratejisi:** doğrudan kopyalama  
  
 Makro semantiği gözatma deneyimini kritik makrosuna aynı olan bir ipucu oluşturun. Ayrıştırma sistem makrosu ipucu dosyası tanımında çözümler.  
  
 Kaynak dosyasında makrosu diğer makrolar içeriyorsa, etkili ipuçları kümesinde zaten yalnızca olmaları durumunda bu makroları yorumlandığını unutmayın.  
  
 **İpucu dosyası:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
### <a name="maps"></a>Eşlemeleri  
 Bir harita başlangıç öğesi, bitiş öğesi ve sıfır veya daha fazla ara öğelerin tanımladığınız makroları oluşur. Ayrıştırma sistem C/C++ dil öğeleri her eşleme makrosu gizler ve tam bir C/C++ deyim sözdizimi birçok ayrı makrolar arasında dağıtılır çünkü eşlemeleri misinterprets.  
  
 Aşağıdaki kaynak kod tanımlar `BEGIN_CATEGORY_MAP`, `IMPLEMENTED_CATEGORY`, ve `END_CATEGORY_MAP` makroları.  
  
 **Kaynak kodu:**  
  
```  
#define BEGIN_CATEGORY_MAP(x)\  
static const struct ATL::_ATL_CATMAP_ENTRY* GetCategoryMap() throw() {\  
static const struct ATL::_ATL_CATMAP_ENTRY pMap[] = {  
#define IMPLEMENTED_CATEGORY( catid ) { _ATL_CATMAP_ENTRY_IMPLEMENTED, &catid },  
#define END_CATEGORY_MAP()\  
   { _ATL_CATMAP_ENTRY_END, NULL } };\  
   return( pMap ); }  
```  
  
 **Stratejisi:** tanımla harita öğelerine  
  
 Başlangıç, Orta (varsa) ve bitiş yönelik ipuçları belirtin öğeleri eşleme. Özel Harita değiştirme dizelerini kullanma `@<`, `@=`, ve `@>`. Daha fazla bilgi için bkz: `Syntax` bölümüne bakın.  
  
 **İpucu dosyası:**  
  
```  
// Start of the map.  
#define BEGIN_CATEGORY_MAP(x) @<  
// Intermediate map element.  
#define IMPLEMENTED_CATEGORY( catid ) @=  
// Intermediate map element.  
#define REQUIRED_CATEGORY( catid ) @=  
// End of the map.  
#define END_CATEGORY_MAP() @>  
```  
  
### <a name="composite-macros"></a>Bileşik makroları  
 Bileşik makroları bir veya daha fazla ayrıştırma sistem karıştırır makrosu türlerini içerir.  
  
 Aşağıdaki kaynak kodunu içerir `START_NAMESPACE` bir ad alanı kapsamı başlangıcını belirtir, makrosu ve `BEGIN_CATEGORY_MAP` makro bir harita başlangıcını belirtir.  
  
 **Kaynak kodu:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
 **Stratejisi:** doğrudan kopyalama  
  
 İpucu oluşturma `START_NAMESPACE` ve `BEGIN_CATEGORY_MAP` makrolar ve ipucu oluşturma `NSandMAP` aynı kaynak kodu daha önce gösterilen makrosu. Alternatif olarak, bileşik bir makrosu yalnızca kesintiye uğratan makroları ve boşluk içeriyorsa, bir null tanımı, değiştirilen dizedir ipucu tanımlayabilirsiniz.  
  
 Bu örnekte, varsayalım `START_NAMESPACE` ipucu Bu konu başlığı altında açıklandığı gibi zaten `Concealed C/C++ Language Elements` alt başlığı. Ve varsayın `BEGIN_CATEGORY_MAP` ipucu daha önce açıklandığı gibi sahip `Maps`.  
  
 **İpucu dosyası:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
### <a name="inconvenient-macros"></a>Kullanışsız makroları  
 Bazı makrolar ayrıştırma sistemi tarafından yorumlanabilen ancak makrosu uzun veya karmaşık olduğundan okumak kaynak kodunu zordur. Okunabilirlik amacıyla makrosu görüntüsünü basitleştiren bir ipucu sağlar.  
  
 **Kaynak kodu:**  
  
```  
#define STDMETHOD(methodName) HRESULT (STDMETHODCALLTYPE * methodName)  
```  
  
 **Stratejisi:** basitleştirme  
  
 Daha basit bir makro tanımı görüntüleyen bir ipucu oluşturun.  
  
 **İpucu dosyası:**  
  
```  
#define STDMETHOD(methodName) void* methodName  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ipuçlarını ipucu dosyalarından nasıl biriktiği gösterilmektedir. Bu örnekte, Dur dosyaları kullanılmaz.  
  
 Aşağıda bazı Visual C++ projesinde fiziksel dizinlerin gösterilmektedir. İpucu dosyaları olan `vcpackages`, `Debug`, `A1`, ve `A2` dizinleri.  
  
### <a name="hint-file-directories"></a>İpucu dosyası dizinleri  
 ![Ortak ve proje&#45;belirli ipucu dosyası dizinleri. ] (../ide/media/hintfile.png "HintFile")  
  
### <a name="directories-and-hint-file-contents"></a>Dizinler ve ipucu dosya içerikleri  
 Aşağıdaki listede ipucu dosyaları ve bu ipucu dosyaların içeriğini içeren bu projede dizinleri gösterir. Birçok ipuçlarında yalnızca bazılarını `vcpackages` dizin ipucu dosyası listelenir.  
  
-   vcpackages  
  
    ```  
    // vcpackages (partial list)  
    #define _In_  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    ```  
  
-   Hata ayıklama  
  
    ```  
    // Debug  
    #undef _In_  
    #define OBRACE {  
    #define CBRACE }  
    #define RAISE_EXCEPTION(x) throw (x)  
    #define START_NAMESPACE namespace MyProject {  
    #define END_NAMESPACE }  
    ```  
  
-   A1  
  
    ```  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {  
    ```  
  
-   A2  
  
    ```  
    // A2  
    #undef OBRACE  
    #undef CBRACE  
    ```  
  
### <a name="effective-hints"></a>Etkili ipuçları  
 Aşağıdaki tabloda bu projede kaynak dosyaları için etkili ipuçları listelenmektedir.  
  
-   Kaynak dosyası: A1_A2_B.cpp  
  
-   Etkili ipuçları:  
  
    ```  
    // vcpackages (partial list)  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    // Debug...  
    #define RAISE_EXCEPTION(x) throw (x)  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {   
    // ...Debug  
    #define END_NAMESPACE }  
    ```  
  
 Aşağıdaki notlar, yukarıdaki listeye geçerlidir.  
  
-   Etkili ipuçları arasındadır `vcpackages`, `Debug`, `A1`, ve `A2` dizinleri.  
  
-   **#Undef** yönergesini `Debug` kaldırılan ipucu dosyası `#define _In_` içinde İpucu `vcpackages` dizin ipucu dosyası.  
  
-   İpucu dosyasında `A1` dizini yeniden tanımlamaktadır `START_NAMESPACE`.  
  
-   `#undef` İçinde İpucu `A2` dizin ipuçları kaldırılan `OBRACE` ve `CBRACE` içinde `Debug` dizin ipucu dosyası.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md)    
 [#define yönergesi (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)   
 [#undef yönergesi (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)   
 [SAL ek açıklamaları](../c-runtime-library/sal-annotations.md)   
 [İleti eşlemeleri](../mfc/reference/message-maps-mfc.md)   
 [İleti eşleme makroları](../atl/reference/message-map-macros-atl.md)   
 [Nesne İşleme Makroları](../atl/reference/object-map-macros.md)