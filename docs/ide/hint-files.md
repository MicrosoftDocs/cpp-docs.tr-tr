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
ms.openlocfilehash: 98734522410b867d735d0af25f440d5b45874563
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393288"
---
# <a name="hint-files"></a>İpucu Dosyaları

A *ipucu dosyası* yardımcı olan Visual Studio tümleşik geliştirme ortamı (IDE) Visual C++ tanımlayıcıları, işlevlerle makrolar adları gibi yorumlar. Bir Visual C++ projesinin, IDE açtığınızda *sistem ayrıştırma* projedeki her kaynak dosyasındaki kodu inceler ve her bir tanımlayıcı hakkında bilgi toplar. IDE özellikleri desteklemek için bu bilgileri kullanır. ardından **sınıf görünümü** tarayıcı ve **gezinti çubuğu**.

Visual C++ 2010'da sunulan ayrıştırma sistem C/C++ sözdizimi anlar, ancak bir makro içeren bir ifade hatalı yorumlayan. Makro yazılan sözdizimsel olarak yanlış olması için kaynak kodu neden olursa, deyim anlaşılabilir. Kaynak kod derlenir ve dosyaların konumudur değiştirir, deyim sözdizimsel olarak doğru dönüşebilir [makro tanımlayıcısı](../preprocessor/hash-define-directive-c-cpp.md) tanımına sahip. Ayrıştırma sistem makroları yorumlamak için ipucu dosyaları kullandığından projesi oluşturmaya gerek kalmadan çalışır. Bu nedenle, bir tarama özelliği gibi **sınıf görünümü** hemen kullanılabilir.

Kullanıcı tarafından özelleştirilebilir ipucu dosyada *ipuçları*, C/C++ makro tanımları aynı söz dizimini sahip. Visual C++ çoğu proje için yeterli olan bir yerleşik ipucu dosyası içerir, ancak Visual Studio tanımlayıcıları işleme iyileştirmek için kendi ipucu dosyaları oluşturabilirsiniz.

> [!IMPORTANT]
> Değiştirme ya da bir ipucu dosyası ekleyin, .sdf dosya ve/veya VC.db değişikliklerin etkili olması Çözüm dosyasındaki silmeniz gerekir.

## <a name="scenario"></a>Senaryo

Aşağıdaki kod ile inceleyin bir kaynak dosyası olduğunu varsayın **sınıf görünümü** tarayıcı. `STDMETHOD` Makro bildirir adlandırılmış bir yöntem `myMethod` bir parametre alır ve bir işaretçi döndüren bir **HRESULT**.

```cpp
// Source code file.
STDMETHOD(myMethod)(int parameter1);
```

Aşağıdaki makro tanımları ayrı üstbilgi dosyasındadır.

```cpp
// Header file.
#define STDMETHOD(method) HRESULT (STDMETHODCALLTYPE * method)
#define STDMETHODCALLTYPE __stdcall
#define HRESULT void*
```

Adlı bir işlev için kaynak kodu ayrıştırma sistem yorumlanamıyor `STDMETHOD` bildirilmesi için görünür ve iki parametre listeleri olduğundan bildirimi sözdizimsel olarak yanlış. Tanımları için keşfetmek için üst bilgi dosyasını ayrıştırma sistem açmaz `STDMETHOD`, `STDMETHODCALLTYPE`, ve `HRESULT` makroları. Ayrıştırma sistem yorumlanamıyor çünkü `STDMETHOD` makrosu, tüm deyimi yoksayar ve daha sonra ayrıştırma devam eder.

Projenizin bir veya daha fazla önemli üstbilgi dosyalarına bağımlı çünkü ayrıştırma sistem üstbilgi dosyası kullanmaz. Herhangi bir üst bilgi dosyası değişirse, ayrıştırma sistem tüm üst bilgi dosyaları, projenizdeki IDE'nin performansı yavaşlattığını edilemeyeceğini gerekebilir. Bunun yerine, ayrıştırma sistem nasıl işleneceğini belirtin ipuçları kullanır `STDMETHOD`, `STDMETHODCALLTYPE`, ve `HRESULT` makroları.

Nasıl bir ipucu gerektiğini biliyor musunuz? Ve ne tür bir ipucu ihtiyacınız varsa oluşturmalısınız? Bir oturum ipucu gereklidir, bir tanımlayıcıda görünümünü **sınıf görünümü** görünümünde tutarsız **Düzenleyicisi**. Örneğin, **sınıf görünümü** var olduğunu bildiğiniz bir sınıf üyesinin görüntülemez olabilir veya üyenin adı yanlış. Sık karşılaşılan sorunları çözmek ipuçları türleri hakkında daha fazla bilgi için bkz: ne makroları gerektiren bir ipucu? Bu konunun ilerleyen bölümlerinde bölümü.

## <a name="architecture"></a>Mimari

İpucu dosyaları fiziksel dizinlerle ilgilidir, mantıksal dizinleri içinde gösterilen **Çözüm Gezgini**. Projeniz bir etkiye sahip olma ipucu dosyası için bir ipucu dosyası eklemek gerekmez. Yalnızca kaynak dosyaları ayıklarken ayrıştırma sistem ipucu dosyaları kullanır.

Her ipucu dosyası adlı **cpp.hint**. Bu nedenle, birden çok dizini bir ipucu dosyası içerebilir ancak yalnızca bir ipucu dosyası belirli bir dizinde ortaya çıkabilir.

Sıfır veya daha fazla ipucu dosyaları projenize etkilenebilir. İpucu dosya yoksa, ayrıştırma sistem şifresi çözülemeyen bir kaynak kodu yok sayılacak hata kurtarma teknikleri kullanır. Aksi takdirde ayrıştırma sistem bulmak ve ipuçları toplamak için aşağıdaki stratejisi kullanır.

### <a name="search-order"></a>Arama sırası

Ayrıştırma sistem ipucu dosyaları için dizinleri şu sırayla arar.

- Visual C++ için yükleme paketini içeren dizine (**vcpackages**). Bu dizin gibi sık kullanılan sistem dosyaları, simgeler tanımlayan bir yerleşik ipucu dosyası içeren **windows.h**. Sonuç olarak, projeniz otomatik olarak en çok ihtiyaç duyduğu ipuçları devralır.

- Kaynak dosyayı içeren dizine kök dizininde bir kaynak dosyasının yolu. Normal bir Visual C++ projesinin kök dizinine çözüm veya proje dosyasını içerir.

   Bu kuralın istisnası, bir *durdurma dosya* içinde kaynak dosyasının yolu. Durdurma dosya adında bir dosya arama sırası üzerinde ek denetim sunan ve **cpp.stop**. Kök dizininden başlayarak yerine, kaynak dosyasını içeren dizine durdurma dosyasını içeren dizinden ayrıştırma sistem arar. Tipik bir projede bir Durma dosyası gerekmez.

### <a name="hint-gathering"></a>İpucu toplanıyor

Sıfır veya daha fazla ipucu dosyası içeren *ipuçları*. İpucu tanımlanan veya yalnızca C/C++ makro gibi silindi. Diğer bir deyişle, `#define` önişlemci yönergesi oluşturur veya bir ipucu'ı yeniden tanımladığı ve `#undef` yönergesi bir ipucu siler.

Ayrıştırma sistem her ipucu dosyası daha önce açıklanan arama düzenini açılır, her bir dosyanın ipuçları kümesi olarak birikir *etkili ipuçları*ve daha sonra kodunuzda tanımlayıcıları yorumlamak için etkili ipuçları kullanır.

Ayrıştırma sistem ipuçları ulaşıncaya kadar aşağıdaki kuralları kullanır.

- Yeni ipucu zaten tanımlı olmayan bir ad belirtir, yeni ipucu için etkili ipuçları adını ekler.

- Yeni ipucu zaten tanımlı bir ad belirtiyorsa, yeni ipucu mevcut ipucu yeniden tanımlar.

- Yeni ipucu ise bir `#undef` yönergesi, var olan bir etkin ipucu belirtir, mevcut ipucu yeni ipucu siler.

İlk kural etkili ipuçları önceden açılmış ipucu dosyalarından devralınır anlamına gelir. Son iki kural daha sonra arama sırayla ipuçları daha önce gerçekleşen ipuçları kılabilirsiniz anlamına gelir. Örneğin, bir kaynak dosyasını içeren dizin ipucu dosyası oluşturursanız, önceki açıklanmıyorsa geçersiz kılabilirsiniz.

İpuçları nasıl toplanır bir gösterimi için bkz. `Example` bu konunun ilerleyen bölümlerinde.

### <a name="syntax"></a>Sözdizimi

İpuçları oluşturulur ve aynı söz dizimine oluşturun ve makroları silme önişlemci yönergeleri ile silinir. Aslında, ayrıştırma sistem ipuçları değerlendirmek için C/C++ ön işlemci kullanır. Önişlemci yönergeleri hakkında daha fazla bilgi için bkz: [#define yönergesi (C/C++)](../preprocessor/hash-define-directive-c-cpp.md) ve [#undef yönergesi (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md).

Yalnızca olağan dışı bir söz dizimi öğeleri `@<`, `@=`, ve `@>` değiştirme dizeleri. Bunlar yalnızca kullanılır ipucu dosyası belirli değiştirme dizelerini *harita* makroları. Harita veri, İşlevler ve olayları ile ilgili diğer verileri, işlevleri veya olay işleyicileri makroları kümesidir. Örneğin, `MFC` eşlemeleri oluşturmak için kullandığı [ileti eşlemeleri](../mfc/reference/message-maps-mfc.md), ve `ATL` eşlemeleri oluşturmak için kullandığı [nesne eşlemeleri](../atl/reference/object-map-macros.md). İpucu dosyası belirli değiştirme dizelerini, başlangıç, Orta ve bitiş bir eşlemin öğelerini gösterir. Yalnızca bir eşleme makro adı büyük/küçük harf önemlidir. Bu nedenle, her bir değiştirme dizesi makro uygulamasını kasıtlı olarak gizler.

İpuçları, aşağıdaki sözdizimini kullanın.

|Sözdizimi|Açıklama|
|------------|-------------|
|`#define` *İpucu-name* *değiştirme dizesi*<br /><br /> `#define` *İpucu-name* `(` *parametre*,... `)` *değiştirme dizesi*|Yeni bir ipucu tanımlar veya mevcut bir ipucu'ı yeniden tanımladığı dosyaların konumudur yönergesi. Yönergesinden sonra önişlemci her oluşumunun değiştirir *ipucu adı* ile kaynak kodundaki *değiştirme dizesi*.<br /><br /> İkinci sözdizimi formu, bir işlev benzeri ipucu tanımlar. Kaynak kodunda bir işlev benzeri ipucu ortaya çıkarsa, önişlemci önce her örneğini değiştirir *parametre* içinde *değiştirme dizesi* karşılık gelen bağımsız kaynak kodu ve ardından değiştirir *ipucu adı* ile *değiştirme dizesi*.|
|`@<`|İpucu dosyası belirli bir *değiştirme dizesi* harita öğeleri kümesi başlangıcını gösterir.|
|`@=`|İpucu dosyası belirli bir *değiştirme dizesi* Ara harita öğesi belirtir. Bir eşleme, birden çok harita öğelerine sahip olabilir.|
|`@>`|İpucu dosyası belirli bir *değiştirme dizesi* harita öğeleri kümesi sonunu gösterir.|
|`#undef` *İpucu-name*|Önişlemci yönergesi var olan bir ipucu siler. İpucu adını tarafından sağlanan *ipucu adı* tanımlayıcısı.|
|`//` *Açıklama*|Tek satırlı yorum.|
|`/*` *Açıklama* `*/`|Çok satırlı yorum.|

## <a name="what-macros-require-a-hint"></a>Ne makroları gerektiren bir ipucu?

Belirli türlerdeki makroları ayrıştırma sistemiyle engelleyebilir. Bu bölümde, bir soruna neden makroları türlerini ve bu sorunu çözmek için oluşturabileceğiniz ipucu türünü açıklar.

### <a name="disruptive-macros"></a>Kesintiye uğratan makroları

Bazı makrolar ayrıştırma sistem kaynak kodu hatalı yorumlayan neden, ancak tarama deneyiminizi azaltmıyorsa yoksayılabilir. Örneğin, kaynak kod ek açıklama dili ([SAL](../c-runtime-library/sal-annotations.md)) makroları yardımcı olan C++ öznitelikleri Bul programlama hataları çözün. Kod gezindikçe SAL ek açıklamalarını gözardı istiyorsanız, ek açıklama gizleyen bir ipucu dosyası oluşturmak isteyebilirsiniz.

Aşağıdaki kaynak kodunda tür parametresi için `FormatWindowClassName()` işlevi `PXSTR`, ve parametre adı `szBuffer`. Ancak, ayrıştırma sistem hataları `_Pre_notnull_` ve `_Post_z_` SAL ek açıklamalarını parametre türü veya parametre adı.

**Kaynak kodu:**

```cpp
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)
```

**Stratejisi:** tanımı Null

Bu durumda bunlar yok edildiğinde SAL ek açıklamalarını değerlendirilecek stratejisidir. Bunu yapmak için bir değiştirme dizesi null bir ipucu belirtin. Sonuç olarak, ayrıştırma, ek açıklamalar yoksayar ve **sınıf görünümü** tarayıcı bunları göstermez. (Visual C++ SAL ek açıklaması gizleyen bir yerleşik ipucu dosyası içerir.)

**İpucu dosyası:**

```cpp.hint
#define _Pre_notnull_
```

### <a name="concealed-cc-language-elements"></a>C/C++ altına gizlenmiş dil öğeleri

Makro C/C++ gizler, ayrıştırma sistem kaynak kodu misinterprets sık karşılaşılan bir nedeni olduğundan [noktalama işaretçisi](../cpp/punctuators-cpp.md) veya [anahtar sözcüğü](../cpp/keywords-cpp.md) belirteci. Diğer bir deyişle, bir makro noktalama işaretçileri, bir çift yarısını gibi içerebilir `<>`, `[]`, `{}`, ve `()`.

Aşağıdaki kaynak kodundaki `START_NAMESPACE` makro gizler eşlenmemiş bir sol ayraç (`{`).

**Kaynak kodu:**

```cpp
#define START_NAMESPACE namespace MyProject {
```

**Stratejisi:** doğrudan kopyalama

Makro semantiği için gözatma deneyimini kritik, makro için aynı olan bir ipucu oluşturun. Ayrıştırma sistem Makro tanımında ipucu dosyası çözümler.

Kaynak dosyadaki makrosu diğer makroları içeriyorsa, etkili ipuçları kümesinde zaten yalnızca olmaları durumunda bu makroları yorumlanmasını unutmayın.

**İpucu dosyası:**

```cpp.hint
#define START_NAMESPACE namespace MyProject {
```

### <a name="maps"></a>Haritalar

Bir eşleme bir başlangıç öğesi, bitiş öğesi ve sıfır veya daha fazla ara öğeler belirlediğiniz makroları oluşur. Ayrıştırma sistem, çünkü her eşleme makro C/C++ Dil öğelerini gizler ve eksiksiz bir C/C++ deyiminin sözdizimi birçok ayrı makroları arasında dağıtılır haritalar misinterprets.

Aşağıdaki kaynak kodunu tanımlayan `BEGIN_CATEGORY_MAP`, `IMPLEMENTED_CATEGORY`, ve `END_CATEGORY_MAP` makroları.

**Kaynak kodu:**

```cpp
#define BEGIN_CATEGORY_MAP(x)\
static const struct ATL::_ATL_CATMAP_ENTRY* GetCategoryMap() throw() {\
static const struct ATL::_ATL_CATMAP_ENTRY pMap[] = {
#define IMPLEMENTED_CATEGORY( catid ) { _ATL_CATMAP_ENTRY_IMPLEMENTED, &catid },
#define END_CATEGORY_MAP()\
   { _ATL_CATMAP_ENTRY_END, NULL } };\
   return( pMap ); }
```

**Stratejisi:** harita öğelerine tanımlayın

İpuçları başlangıç, Orta (varsa) ve bitiş için belirtin bir eşlemin öğelerini. Özel Harita değiştirme dizelerini kullanma `@<`, `@=`, ve `@>`. Daha fazla bilgi için `Syntax` bölümüne bakın.

**İpucu dosyası:**

```cpp.hint
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

Bileşik makrolar, bir veya daha fazla ayrıştırma sistem işlemlerini birbirine karıştırmaktadır makrosu türlerini içerir.

Aşağıdaki kaynak kodunu içeren `START_NAMESPACE` ad alanı kapsamında başlangıcını belirtir, makro ve `BEGIN_CATEGORY_MAP` makrosu olarak bir harita başlangıcını belirtir.

**Kaynak kodu:**

```cpp
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP
```

**Stratejisi:** doğrudan kopyalama

İpuçları oluşturma `START_NAMESPACE` ve `BEGIN_CATEGORY_MAP` makroları ve ipucu oluşturup `NSandMAP` aynı kaynak kodu daha önce gösterildiği gibi makrosu. Alternatif olarak, bileşik bir makro yalnızca kesintiye uğratan makroları ve boşluk içeriyorsa, bir değiştirme dizesi null bir tanımıdır ipucu tanımlayabilirsiniz.

Bu örnekte, varsayalım `START_NAMESPACE` ipucu bu konuda açıklandığı zaten `Concealed C/C++ Language Elements` alt başlığı. Ve varsayar `BEGIN_CATEGORY_MAP` daha önce açıklandığı gibi bir ipucu sahip `Maps`.

**İpucu dosyası:**

```cpp.hint
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP
```

### <a name="inconvenient-macros"></a>Kullanışsız makroları

Bazı makrolar ayrıştırma sistem tarafından yorumlanabilir, ancak kaynak kodunu makrosu uzun veya çok karmaşık olduğu için okuma zordur. Okunabilirlik açısından, makro görüntülenmesini basitleştiren bir ipucu sağlar.

**Kaynak kodu:**

```cpp
#define STDMETHOD(methodName) HRESULT (STDMETHODCALLTYPE * methodName)
```

**Stratejisi:** basitleştirme

Daha basit bir makro tanımı görüntüleyen bir ipucu oluşturun.

**İpucu dosyası:**

```cpp.hint
#define STDMETHOD(methodName) void* methodName
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, ipuçları ipucu dosyalarından nasıl toplanır gösterir. Bu örnekte, Dur dosyaları kullanılmaz.

Aşağıdaki çizimde, bir Visual C++ projesinde fiziksel dizinlerle bazıları gösterilmektedir. İpucu dosyalar, `vcpackages`, `Debug`, `A1`, ve `A2` dizinleri.

### <a name="hint-file-directories"></a>İpucu dosyası dizinleri

![Ortak ve proje&#45;belirli ipucu dosyası dizinleri. ](../ide/media/hintfile.png "HintFile")

### <a name="directories-and-hint-file-contents"></a>Dizinler ve ipucu dosyası içeriği

Aşağıdaki listede, bu projede ipucu dosyaları ve bu ipucu dosyaların içeriğini içeren dizinleri gösterir. Birçok ipuçları, yalnızca bazıları `vcpackages` dizin ipucu dosyası listelenir.

- vcpackages

    ```cpp.hint
    // vcpackages (partial list)
    #define _In_
    #define _In_opt_
    #define _In_z_
    #define _In_opt_z_
    #define _In_count_(size)
    ```

- Hata ayıklama

    ```cpp.hint
    // Debug
    #undef _In_
    #define OBRACE {
    #define CBRACE }
    #define RAISE_EXCEPTION(x) throw (x)
    #define START_NAMESPACE namespace MyProject {
    #define END_NAMESPACE }
    ```

- A1

    ```cpp.hint
    // A1
    #define START_NAMESPACE namespace A1Namespace {
    ```

- A2

    ```cpp.hint
    // A2
    #undef OBRACE
    #undef CBRACE
    ```

### <a name="effective-hints"></a>Etkili ipuçları

Aşağıdaki tabloda, bu projede kaynak dosyaları için etkili ipuçları listeler.

- Kaynak dosya: A1_A2_B.cpp

- Etkili ipuçları:

    ```cpp.hint
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

- Etkili ipuçları arasındadır `vcpackages`, `Debug`, `A1`, ve `A2` dizinleri.

- **#Undef** yönergesini `Debug` ipucu dosyası kaldırıldı `#define _In_` içinde İpucu `vcpackages` dizin ipucu dosyası.

- İpucu dosyasında `A1` dizin'ı yeniden tanımladığı `START_NAMESPACE`.

- `#undef` İçinde İpucu `A2` dizin ipuçları kaldırıldı `OBRACE` ve `CBRACE` içinde `Debug` dizin ipucu dosyası.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[#define Yönergesi (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)<br>
[#undef Yönergesi (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)<br>
[SAL Ek Açıklamaları](../c-runtime-library/sal-annotations.md)<br>
[İleti eşlemeleri](../mfc/reference/message-maps-mfc.md)<br>
[İleti eşleme makroları](../atl/reference/message-map-macros-atl.md)<br>
[Nesne İşleme Makroları](../atl/reference/object-map-macros.md)