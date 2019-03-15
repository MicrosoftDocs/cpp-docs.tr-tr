---
title: İpucu Dosyaları
ms.date: 02/26/2019
f1_keywords:
- cpp.hint
- vc.hint.file
helpviewer_keywords:
- stop file
- cpp.hint
- hint file
- cpp.stop
- Class View, hint file
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
ms.openlocfilehash: 3d8b3be76fea454ed3b3dd3fd2a44174f34c065c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823591"
---
# <a name="hint-files"></a>İpucu Dosyaları

A *ipucu dosyası* Aksi takdirde C++ gözatma veritabanı ayrıştırıcı tarafından Atlanan bölgeleri neden makrolar içerir. Visual C++ projesi açtığınızda, ayrıştırıcının her proje kaynak dosyada kod analiz eder ve her bir tanımlayıcı hakkında bilgi içeren bir veritabanı oluşturur. IDE, kod gözatma desteği veren bilgiler gibi özellikleri kullanır **sınıf görünümü** tarayıcı ve **gezinti çubuğu**.

C++ gözatma veritabanı ayrıştırıcı büyük miktarda kod kısa bir sürede ayrıştırabilen belirsiz bir ayrıştırıcısıdır. Hızlı nedenlerinden biri, içerik bloklarının atlar olmasıdır. Örneği için yalnızca bir işlevin parametreleri ve konumunu kaydeder ve içeriğini yok sayar. Belirli makrolar, başlangıç ve bitiş bloğunun belirlemek için kullanılan buluşsal yöntemler için sorunlara neden olabilir. Bu sorunlar, yanlış kaydedilecek bölgeleri neden.

Atlanan Bu bölgeler, birden çok yolla bildirilebilir:

- Eksik türleri ve içindeki işlevler **sınıf görünümü**, **Git** ve **gezinti çubuğu**

- Yanlış kapsamlarda **gezinti çubuğu**

- Önerilerinizi **oluşturma bildirimi/tanımı** zaten tanımlanmış olan işlevler

İpucu dosyası olarak C/C++ makro tanımları aynı söz dizimine sahip kullanıcı tarafından özelleştirilebilir ipuçları içerir. Visual C++, çoğu proje için yeterli olan bir yerleşik ipucu dosyası içerir. Ancak, projeniz için özel bir ayrıştırıcı iyileştirmek için kendi ipucu dosyaları oluşturabilirsiniz.

> [!IMPORTANT]
> Değiştirme ya da bir ipucu dosyası ekleyin, değişikliklerin etkili olması ek adımlar uygulamanız gerekir:
> - Visual Studio 2017 sürüm 15.6 önce sürümlerde: .Sdf dosya ve/veya çözüm VC.db dosyada yapılan tüm değişiklikler silin.
> - Visual Studio 2017 sürüm 15.6 15.9 aracılığıyla: Kapatın ve yeni ipucu dosyaları ekledikten sonra çözümü yeniden açın.

## <a name="scenario"></a>Senaryo

```cpp
#define NOEXCEPT noexcept
void Function() NOEXCEPT
{
}
```

Bir ipucu dosyası olmadan `Function` içinde gösterilmesini **sınıf görünümü**, **Git** veya **gezinti çubuğu**. Bu Makro tanımında bir ipucu dosyası ekledikten sonra ayrıştırıcının artık anlar ve değiştirir `NOEXCEPT` işlevi düzgün ayrıştırılamadı izin veren makro:

```cpp.hint
#define NOEXCEPT
```

## <a name="disruptive-macros"></a>Kesintiye uğratan makroları

Ayrıştırıcının kesintiye makroları iki kategorisi vardır:

- Bir işlev adorn anahtar sözcükleri kapsülleyen makroları

   ```cpp
   #define NOEXCEPT noexcept
   #define STDMETHODCALLTYPE __stdcall
   ```

   Bu tür makroları, makro adı ipucu dosyasında gereklidir:

   ```cpp.hint
   #define NOEXCEPT
   #define STDMETHODCALLTYPE
   ```

- Eşleşmeyen ayraç içeren makroları

   ```cpp
   #define BEGIN {
   ```

   Bu tür makroları, makro adı hem de içeriğini ipucu dosyasında gerekir:

   ```cpp.hint
   #define BEGIN {
   ```

## <a name="editor-support"></a>Düzenleyicisi desteği

Visual Studio 2017 sürüm 15,8 kesintiye uğratan makroları tanımlamak için birkaç özellik vardır. başlangıç:

- Ayrıştırıcı tarafından Atlanan bölgeleri içinde makroların vurgulanır.

- Hızlı bir vurgulanan makro içeren bir ipucu dosyası oluşturmak için eylem veya makro ipucu dosyasına eklemek için bir varolan ipucu dosyası ise.

![Vurgulanan makrosu. ](media/hint-squiggle-and-actions.png "İpucu kapalıysa ve hızlı Eylemler")

Hızlı Eylemler birini yürütüldükten sonra ayrıştırıcının ipucu dosyası tarafından etkilenen dosyalar reparses.

Varsayılan olarak, sorunu makrosu öneri olarak vurgulanır. Vurgulama kırmızı veya yeşil dalgalı çizgi gibi daha belirgin bir şey değiştirilebilir. Kullanım **makroları atlandı gözatma bölgelerde** seçeneğini **kod dalgalı çizgiler** bölümüne **Araçları** > **seçenekleri**  >  **Metin düzenleyici** > **C/C++** > **görünümü**.

![Atlanan gözatma bölgeler seçenek makroları. ](media/skipped-regions-squiggle-option.png "Bölgeleri dalgalı çizgi seçenek atlandı.")

## <a name="display-browsing-database-errors"></a>Gözatma veritabanı hataları görüntüleme

**Proje** > **görünen gözatma veritabanı hataları** menü komutunu görüntüler olarak ayrıştırılamadı tüm bölgeler **hata listesi**. Komut, ilk ipucu dosyası derleme kolaylaştırmak için tasarlanmıştır. Ancak, ayrıştırıcının her hata değerlendirmelidir. böylece hatanın nedenini kesintiye uğratan bir makro olduğunu anlayamaz. Çalıştırma **görünen gözatma veritabanı hataları** komut ve etkilenen dosyayı düzenleyicide yüklenecek her bir hata gidin. Dosya yüklendiğinde makroların bölgenin içinde olduğunda vurgulanmış. Bunları bir ipucu dosyasına eklemek için hızlı Eylemler çağırabilirsiniz. İpucu dosyası güncelleştirmesinden sonra hata listesinde otomatik olarak güncelleştirilir. Alternatif olarak, el ile ipucu dosyası değiştiriyorsanız kullanabilirsiniz **yeniden tarama çözüm** güncelleştirme tetiklemek için komutu.

## <a name="architecture"></a>Mimari

İpucu dosyaları ilişkili fiziksel dizinlerine, gösterilen mantıksal dizinleri **Çözüm Gezgini**. Projenize bir etkiye sahip olma ipucu dosyası için bir ipucu dosyası eklemeniz gerekmez. Yalnızca kaynak dosyaları ayıklarken ayrıştırma sistem ipucu dosyaları kullanır.

Her ipucu dosyası adlı **cpp.hint**. Birden çok dizini bir ipucu dosyası içerebilir, ancak yalnızca bir ipucu dosyası belirli bir dizinde ortaya çıkabilir.

Sıfır veya daha fazla ipucu dosyaları projenize etkilenebilir. İpucu dosya yoksa, ayrıştırma sistem şifresi çözülemeyen bir kaynak kodu yok sayılacak hata kurtarma teknikleri kullanır. Aksi takdirde ayrıştırma sistem bulmak ve ipuçları toplamak için aşağıdaki stratejisi kullanır.

### <a name="search-order"></a>Arama sırası

Ayrıştırma sistem ipucu dosyaları için dizinleri şu sırayla arar.

- Visual C++ için yükleme paketini içeren dizine (**vcpackages**). Bu dizin gibi sık kullanılan sistem dosyaları, simgeler tanımlayan bir yerleşik ipucu dosyası içeren **windows.h**. Sonuç olarak, projeniz otomatik olarak en çok ihtiyaç duyduğu ipuçları devralır.

- Kaynak dosyayı içeren dizine kök dizininde bir kaynak dosyasının yolu. Normal bir Visual C++ projesinin kök dizinine çözüm veya proje dosyasını içerir.

   Bu kuralın istisnası, bir *durdurma dosya* içinde kaynak dosyasının yolu. Adlı bir dosyaya bir Durma dosyasıdır **cpp.stop**. Durdurma dosya arama sırası üzerinde ek denetim sağlar. Kök dizininden başlayarak yerine, kaynak dosyasını içeren dizine durdurma dosyasını içeren dizinden ayrıştırma sistem arar. Tipik bir projede bir Durma dosyası gerekmez.

### <a name="hint-gathering"></a>İpucu toplanıyor

Sıfır veya daha fazla ipucu dosyası içeren *ipuçları*. İpucu tanımlanan veya yalnızca C/C++ makro gibi silindi. Diğer bir deyişle, `#define` önişlemci yönergesi oluşturur veya bir ipucu'ı yeniden tanımladığı ve `#undef` yönergesi bir ipucu siler.

Ayrıştırma sistem daha önce açıklanan arama sırayla her ipucu dosyası açılır. Bir dizi her dosyanın ipuçları biriktirir *etkili ipuçları*ve daha sonra kodunuzda tanımlayıcıları yorumlamak için etkili ipuçları kullanır.

Ayrıştırma sistem ipuçları ulaşıncaya kadar bu kuralları kullanır:

- Yeni ipucu zaten tanımlı olmayan bir ad belirtiyorsa, yeni ipucu için etkili ipuçları adını ekler.

- Yeni ipucu zaten tanımlı bir ad belirtiyorsa, yeni ipucu mevcut ipucu yeniden tanımlar.

- Yeni ipucu ise bir `#undef` yönergesi, var olan bir etkin ipucu belirtir, mevcut ipucu yeni ipucu siler.

İlk kural etkili ipuçları önceden açılmış ipucu dosyalarından devralınır anlamına gelir. Son iki kural daha sonra arama sırası ipuçlarına önceki ipuçları kılabilirsiniz anlamına gelir. Örneğin, bir kaynak dosyasını içeren dizin ipucu dosyası oluşturursanız, önceki açıklanmıyorsa geçersiz kılabilirsiniz.

İpuçları nasıl toplanır bir gösterimi için bkz. [örnek](#example) bölümü.

### <a name="syntax"></a>Sözdizimi

Oluşturur ve ipuçları oluşturma ve silme makrolar önişlemci yönergeleri aynı söz dizimini kullanarak silin. Aslında, ayrıştırma sistem ipuçları değerlendirmek için C/C++ ön işlemci kullanır. Önişlemci yönergeleri hakkında daha fazla bilgi için bkz: [#define yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md) ve [#undef yönergesi (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md).

Yalnızca olağan dışı bir söz dizimi öğeleri `@<`, `@=`, ve `@>` değiştirme dizeleri. Bu ipucu dosyası özel bir yenileme dizeler yalnızca kullanılan *harita* makroları. Harita veri, İşlevler ve olayları ile ilgili diğer verileri, işlevleri veya olay işleyicileri makroları kümesidir. Örneğin, `MFC` eşlemeleri oluşturmak için kullandığı [ileti eşlemeleri](../../mfc/reference/message-maps-mfc.md), ve `ATL` eşlemeleri oluşturmak için kullandığı [nesne eşlemeleri](../../atl/reference/object-map-macros.md). İpucu dosyası belirli değiştirme dizelerini, başlangıç, Orta ve bitiş bir eşlemin öğelerini işaretleyin. Yalnızca bir eşleme makro adı büyük/küçük harf önemlidir. Bu nedenle, her bir değiştirme dizesi makro uygulamasını kasıtlı olarak gizler.

İpuçları, bu sözdizimini kullanın:

|Sözdizimi|Açıklama|
|------------|-------------|
|`#define` *İpucu-name* *değiştirme dizesi*<br /><br /> `#define` *İpucu-name* `(` *parametre*,... `)` *değiştirme dizesi*|Yeni bir ipucu tanımlar veya mevcut bir ipucu'ı yeniden tanımladığı bir önişlemci yönergesi. Yönergesinden sonra önişlemci her oluşumunun değiştirir *ipucu adı* ile kaynak kodundaki *değiştirme dizesi*.<br /><br /> İkinci sözdizimi formu, bir işlev benzeri ipucu tanımlar. Kaynak kodunda bir işlev benzeri ipucu ortaya çıkarsa, önişlemci önce her örneğini değiştirir *parametre* içinde *değiştirme dizesi* karşılık gelen bağımsız kaynak kodu ve ardından değiştirir *ipucu adı* ile *değiştirme dizesi*.|
|`@<`|İpucu dosyası belirli bir *değiştirme dizesi* harita öğeleri kümesi başlangıcını gösterir.|
|`@=`|İpucu dosyası belirli bir *değiştirme dizesi* Ara harita öğesi belirtir. Bir eşleme, birden çok harita öğelerine sahip olabilir.|
|`@>`|İpucu dosyası belirli bir *değiştirme dizesi* harita öğeleri kümesi sonunu gösterir.|
|`#undef` *İpucu-name*|Önişlemci yönergesi var olan bir ipucu siler. İpucu adını tarafından sağlanan *ipucu adı* tanımlayıcısı.|
|`//` *Açıklama*|Bir tek satır açıklama.|
|`/*` *Açıklama* `*/`|Çok satırlı yorum.|

## <a name="example"></a>Örnek

Bu örnek nasıl ipuçları ipucu dosyalarından biriktirilir gösterir. Bu örnekte durdurma dosyaları kullanılmaz.

Çizim, bazı fiziksel dizinlerin bir Visual C++ projesinde gösterir. İpucu dosyaları vardır `vcpackages`, `Debug`, `A1`, ve `A2` dizinleri.

### <a name="hint-file-directories"></a>İpucu dosyası dizinleri

![Ortak ve proje&#45;belirli ipucu dosyası dizinleri. ](media/hintfile.png "HintFile")

### <a name="directories-and-hint-file-contents"></a>Dizinler ve ipucu dosyası içeriği

Bu liste, bu projede ipucu dosyaları ve bu ipucu dosyaların içeriğini içeren dizinleri gösterir. Birçok ipuçları, yalnızca bazıları `vcpackages` dizin ipucu dosyası listelenmiştir:

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

Bu tabloda, bu projede kaynak dosyaları için etkili ipuçları listelenmiştir:

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

Bu Notlar Yukarıdaki listeye geçerlidir:

- Etkili ipuçları arasındadır `vcpackages`, `Debug`, `A1`, ve `A2` dizinleri.

- **#Undef** yönergesini `Debug` ipucu dosyası kaldırıldı `#define _In_` içinde İpucu `vcpackages` dizin ipucu dosyası.

- İpucu dosyasında `A1` dizin'ı yeniden tanımladığı `START_NAMESPACE`.

- `#undef` İçinde İpucu `A2` dizin ipuçları kaldırıldı `OBRACE` ve `CBRACE` içinde `Debug` dizin ipucu dosyası.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](file-types-created-for-visual-cpp-projects.md)<br>
[#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)<br>
[#undef Yönergesi (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)<br>
[SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)<br>

