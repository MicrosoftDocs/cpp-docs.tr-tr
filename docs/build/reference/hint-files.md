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
ms.openlocfilehash: de299f17686d68956e9847d47743d8931734d4ad
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075198"
---
# <a name="hint-files"></a>İpucu Dosyaları

*İpucu dosyası* , C++ Aksi takdirde kod bölgelerinin göz atma veritabanı ayrıştırıcısı tarafından atlanmasına neden olacak makrolar içerir. Bir Visual Studio C++ projesi açtığınızda, ayrıştırıcı projedeki her kaynak dosyasındaki kodu analiz eder ve her tanımlayıcı hakkında bilgi içeren bir veritabanı oluşturur. IDE, **sınıf görünümü** tarayıcısı ve **Gezinti çubuğu**gibi kod gözatma özelliklerini desteklemek için bu bilgileri kullanır.

C++ Göz atma veritabanı ayrıştırıcısı, büyük miktarlarda kodu kısa bir süre içinde ayrıştırabilen, benzer bir ayrıştırıcıdır. Bir nedenden dolayı, blokların içeriğini atlamalarından biri hızlıdır. Örneğin, yalnızca bir işlevin konumunu ve parametrelerini kaydeder ve içeriğini yoksayar. Belirli makrolar, bir bloğun başlangıcını ve sonunu belirlemede kullanılan buluşsal yöntemler için soruna neden olabilir. Bu sorunlar kodun bölümlerinin yanlış kaydedilmemesine neden olur.

Atlanan bu bölgeler birden çok şekilde bildirim alabilir:

- **Sınıf görünümü**eksik türler ve işlevler, **Git** ve **Gezinti çubuğu**

- **Gezinti çubuğunda** yanlış kapsamlar

- Önceden tanımlanmış işlevler için **bildirim/tanım oluşturma** önerileri

İpucu dosyası, C/C++ Macro tanımlarıyla aynı sözdizimine sahip olan kullanıcı tarafından özelleştirilebilir ipuçları içerir. Görsel C++ , çoğu proje için yeterli olan yerleşik bir ipucu dosyası içerir. Bununla birlikte, ayrıştırıcısı özellikle projeniz için geliştirmek üzere kendi ipucu dosyalarınızı oluşturabilirsiniz.

> [!IMPORTANT]
> Bir ipucu dosyası değiştirir veya eklerseniz, değişikliklerin etkili olması için ek adımlar uygulamanız gerekir:
> - Visual Studio 2017 sürüm 15,6 ' den önceki sürümlerde: tüm değişiklikler için çözümdeki. sdf dosyasını ve/veya VC. db dosyasını silin.
> - Visual Studio 2017 sürüm 15,6 ve sonraki sürümlerde: yeni ipucu dosyaları ekledikten sonra çözümü kapatın ve yeniden açın.

## <a name="scenario"></a>Senaryo

```cpp
#define NOEXCEPT noexcept
void Function() NOEXCEPT
{
}
```

İpucu dosyası olmadan, `Function` **sınıf görünümü**gösterilmez, veya **gezinti çubuğuna** **gidin** . Bu makro tanımıyla bir ipucu dosyası eklendikten sonra, ayrıştırıcı artık işlevin doğru ayrıştırmasına izin veren `NOEXCEPT` makrosunu anlamıştır ve değiştirir:

```cpp.hint
#define NOEXCEPT
```

## <a name="disruptive-macros"></a>Kesintiye uğratan makrolar

Ayrıştırıcıyı kesintiye uğratan iki makro kategorisi vardır:

- İşlev sağlayan anahtar sözcükleri kapsülleyen makrolar

   ```cpp
   #define NOEXCEPT noexcept
   #define STDMETHODCALLTYPE __stdcall
   ```

   Bu tür makrolar için ipucu dosyasında yalnızca makro adı gereklidir:

   ```cpp.hint
   #define NOEXCEPT
   #define STDMETHODCALLTYPE
   ```

- Dengesiz parantezler içeren makrolar

   ```cpp
   #define BEGIN {
   ```

   Bu tür makrolar için, ipucu dosyasında hem makro adı hem de içeriği gereklidir:

   ```cpp.hint
   #define BEGIN {
   ```

## <a name="editor-support"></a>Düzenleyici desteği

Visual Studio 2017 sürüm 15,8 ' den başlayarak, kesintiye uğratan makroları belirlemek için çeşitli özellikler vardır:

- Ayrıştırıcı tarafından atlanan bölgelerin içindeki makrolar vurgulanır.

- Vurgulanmış makroyu içeren bir ipucu dosyası oluşturmak için veya var olan bir ipucu dosyası varsa, ipucu dosyasına makroyu eklemek için hızlı bir eylem vardır.

![Vurgulanan makro.](media/hint-squiggle-and-actions.png "İpucu dalgalı çizgi ve hızlı eylemler")

Hızlı eylemlerden birini yürüttükten sonra, ayrıştırıcı ipucu dosyasından etkilenen dosyaları yeniden ayrıştırır.

Varsayılan olarak, sorunlu makro bir öneri olarak vurgulanır. Vurgu, kırmızı veya yeşil dalgalı çizgi gibi daha belirgin bir şekilde değiştirilebilir. **Araçlar** > **Seçenekler** > **metin Düzenleyicisi** > **CC++ /**  > **görünümü**' nün altındaki **Code dalgalı çizgiler** bölümündeki **makroları atlanan gözatma bölgelerinde** kullanın seçeneğini kullanın.

![Atlanan gözatma bölgelerinde makrolar seçeneği.](media/skipped-regions-squiggle-option.png "Atlanan bölge dalgalı çizgi seçeneği.")

## <a name="display-browsing-database-errors"></a>Gözatma veritabanı hatalarını görüntüle

**Proje** > **Gözatma veritabanı hatalarını görüntüle** menü komutu, **hata listesi**ayrıştıramadığı tüm bölgeleri görüntüler. Bu komut, ilk ipucu dosyasını oluşturmayı kolaylaştırmak için tasarlanmıştır. Ancak, ayrıştırıcı hatanın nedeninin kesintiye uğratan bir makro olup olmadığını söylemez, bu nedenle her bir hatayı değerlendirmelisiniz. **Tarama veritabanı hatalarını görüntüle** komutunu çalıştırın ve etkilenen dosyayı düzenleyicide yüklemek için her bir hataya gidin. Dosya yüklendikten sonra, herhangi bir makro bölgenin içindeyse, vurgulanırlar. Hızlı eylemleri bir ipucu dosyasına eklemek için çağırabilirsiniz. İpucu dosya güncelleştirmesinden sonra, hata listesi otomatik olarak güncelleştirilir. Alternatif olarak, ipucu dosyasını el ile değiştiriyorsanız, bir güncelleştirmeyi tetiklemek için **çözümü yeniden Tara** komutunu kullanabilirsiniz.

## <a name="architecture"></a>Mimari

İpucu dosyaları, **Çözüm Gezgini**gösterilen mantıksal dizinlerden değil, fiziksel dizinlerle ilgilidir. İpucu dosyasının bir etkisi olması için projenize ipucu dosyası eklemeniz gerekmez. Ayrıştırma sistemi yalnızca kaynak dosyaları ayrıştırdığında ipucu dosyalarını kullanır.

Her ipucu dosyası **cpp. İpucu**olarak adlandırılır. Birçok dizin bir ipucu dosyası içerebilir, ancak belirli bir dizinde yalnızca bir ipucu dosyası olabilir.

Projeniz, sıfır veya daha fazla ipucu dosyasından etkilenebilir. İpucu dosyası yoksa, ayrıştırma sistemi, ındeable kaynak kodu yok saymak için hata kurtarma tekniklerini kullanır. Aksi takdirde, ayrıştırma sistemi ipuçlarını bulmak ve toplamak için aşağıdaki stratejiyi kullanır.

### <a name="search-order"></a>Arama sırası

Ayrıştırma sistemi, ipucu dosyaları için dizinleri aşağıdaki sırayla arar.

- Görsel C++ için yükleme paketini içeren dizin (**vcpackages**). Bu dizin, **Windows. h**gibi sık kullanılan sistem dosyalarındaki sembolleri açıklayan bir yerleşik ipucu dosyası içerir. Sonuç olarak, projeniz ihtiyacı olan ipuçlarının çoğunu otomatik olarak devralır.

- Kaynak dosyanın kök dizininden kaynak dosyanın kendisini içeren dizine ait yol. Tipik bir Visual Studio C++ projesinde, kök dizin çözüm veya proje dosyasını içerir.

   Bu kuralın istisnası, bir *durdurma dosyasının* kaynak dosyanın yolunda olması durumunda olur. Durdurma dosyası, **cpp. Stop**adlı herhangi bir dosyadır. Bir durdurma dosyası arama sırası üzerinde ek denetim sağlar. Ayrıştırma sistemi, kök dizinden başlamak yerine, durdurma dosyasını içeren dizinden kaynak dosyayı içeren dizine göre arama yapar. Tipik bir projede, bir Dur dosyasına ihtiyacınız yoktur.

### <a name="hint-gathering"></a>İpucu toplama

İpucu dosyası sıfır veya daha fazla *İpucu*içeriyor. Bir ipucu, tıpkı C/C++ Macro gibi tanımlanır veya silinir. Diğer bir deyişle, `#define` Önişlemci yönergesi bir ipucu oluşturur veya yeniden tanımlar ve `#undef` yönergesi bir ipucu siler.

Ayrıştırma sistemi, daha önce açıklanan arama sırasında her bir ipucu dosyasını açar. Her bir dosyanın ipuçlarını bir dizi *etkin ipuçlarına*ayırır ve sonra kodunuzdaki tanımlayıcıları yorumlamak için etkili ipuçlarını kullanır.

Ayrıştırma sistemi, ipuçlarını biriktirmek için bu kuralları kullanır:

- Yeni ipucu önceden tanımlı olmayan bir ad belirtiyorsa, yeni ipucu adı etkili ipuçlarına ekler.

- Yeni ipucu zaten tanımlı bir ad belirtiyorsa, yeni ipucu varolan ipucunu tekrar tanımlar.

- Yeni İpucu Varolan bir etkin ipucunu belirten bir `#undef` yönergedir, yeni ipucu var olan ipucunu siler.

İlk kural, etkin ipuçlarının önceden açılan ipucu dosyalarından Devralındığı anlamına gelir. Son iki kural, daha sonra arama sırasında ipuçlarının önceki ipuçlarını geçersiz kılabileceği anlamına gelir. Örneğin, kaynak dosya içeren dizinde bir ipucu dosyası oluşturursanız, önceki ipuçlarını geçersiz kılabilirsiniz.

İpuçlarının nasıl toplandığını gösteren bir gösterimi için, [örnek](#example) bölümüne bakın.

### <a name="syntax"></a>Sözdizimi

Makrolar oluşturmak ve silmek için önişlemci yönergeleriyle aynı sözdizimini kullanarak ipuçları oluşturur ve silersiniz. Aslında, ayrıştırma sistemi ipuçlarını değerlendirmek için C/C++ Önişlemci 'yi kullanır. Önişlemci yönergeleri hakkında daha fazla bilgi için bkz. [#define yönergesi (c/C++)](../../preprocessor/hash-define-directive-c-cpp.md) ve [#undef yönergesi (c/C++)](../../preprocessor/hash-undef-directive-c-cpp.md).

Tek alışılmadık sözdizimi öğeleri `@<`, `@=`ve `@>` değiştirme dizeleridir. Bu ipucu-dosyaya özgü değiştirme dizeleri yalnızca *harita* makrolarında kullanılır. Eşleme, verileri, işlevleri veya olayları diğer verilerle, işlevlerle veya olay işleyicileriyle ilişkilendiren bir makrolar kümesidir. Örneğin, `MFC` [ileti haritaları](../../mfc/reference/message-maps-mfc.md)oluşturmak için haritaları kullanır ve `ATL` [nesne haritaları](../../atl/reference/object-map-macros.md)oluşturmak için haritalar kullanır. İpucu-dosyaya özgü değiştirme dizeleri, bir haritanın başlangıç, ara ve bitiş öğelerini işaret. Yalnızca bir harita makrosunun adı önemlidir. Bu nedenle, her bir değiştirme dizesi, makronun uygulanmasını kasıtlı olarak gizler.

İpuçları şu sözdizimini kullanır:

|Sözdizimi|Anlamı|
|------------|-------------|
|`#define` *İpucu-ad* *değiştirme-dize*<br /><br /> `#define` *İpucu-adı* `(` *parametresi*,...`)`*değiştirme-dize*|Yeni bir ipucu tanımlayan veya var olan bir ipucunu tekrar belirleyen bir ön işlemci yönergesi. Yönergeden sonra Önişlemci, kaynak kodundaki her bir *İpucu adı* tekrarını *değiştirme dizesiyle*değiştirir.<br /><br /> İkinci sözdizimi formu, işlev benzeri bir ipucu tanımlar. Kaynak kodunda işlev benzeri bir ipucu oluşursa, ön işlemci ilk olarak *değiştirme-dize* içindeki her *parametre* tekrarını kaynak kodunda karşılık gelen bağımsız değişkenle değiştirir ve ardından *İpucu adını* *değiştirme-dize*ile değiştirir.|
|`@<`|Bir harita öğeleri kümesinin başlangıcını belirten ipucu dosyasına özgü bir *değiştirme dizesi* .|
|`@=`|Bir ara eşleme öğesini belirten ipucu dosyasına özgü bir *değiştirme dizesi* . Bir haritanın birden çok eşleme öğesi olabilir.|
|`@>`|Bir harita öğeleri kümesinin sonunu belirten ipucu dosyasına özgü bir *değiştirme dizesi* .|
|`#undef` *İpucu-adı*|Var olan bir ipucunu silen Önişlemci yönergesi. İpucu adı, *İpucu adı* tanımlayıcısı tarafından sağlanır.|
|`//` *açıklaması*|Tek satırlık bir açıklama.|
|`/*` *açıklama* `*/`|Çok satırlı bir açıklama.|

## <a name="example"></a>Örnek

Bu örnek, ipuçlarının ipucu dosyalarından nasıl birikmiş olduğunu gösterir. Bu örnekte, dosyaları durdur kullanılmıyor.

Çizimde, Visual Studio C++ projesindeki bazı fiziksel dizinler gösterilmektedir. `vcpackages`, `Debug`, `A1`ve `A2` dizinlerinde ipucu dosyaları vardır.

### <a name="hint-file-directories"></a>İpucu dosya dizinleri

![Ortak ve projeye&#45;özgü İpucu dosya dizinleri.](media/hintfile.png "HintFile")

### <a name="directories-and-hint-file-contents"></a>Dizinler ve Ipucu dosya Içerikleri

Bu liste, bu projedeki ipucu dosyalarını içeren dizinleri ve bu ipucu dosyalarının içeriğini gösterir. `vcpackages` Directory ipucu dosyasındaki pek çok ipucu listelenir:

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

### <a name="effective-hints"></a>Etkili Ipuçları

Bu tabloda, bu projedeki kaynak dosyaları için geçerli ipuçları listelenmektedir:

- Kaynak dosya: A1_A2_B. cpp

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

Bu notlar önceki liste için geçerlidir:

- Etkili ipuçları `vcpackages`, `Debug`, `A1`ve `A2` dizinlerden.

- `Debug` ipucu dosyasındaki **#undef** yönergesi `vcpackages` Dizin ipucu dosyasındaki `#define _In_` ipucunu kaldırdı.

- `A1` dizinindeki ipucu dosyası `START_NAMESPACE`öğesini tekrar tanımlar.

- `A2` dizinindeki `#undef` ipucu, `Debug` Dizin ipucu dosyasındaki `OBRACE` ve `CBRACE` ipuçlarını kaldırdı.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)<br>
[#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)<br>
[#undef Yönergesi (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)<br>
[SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)<br>
