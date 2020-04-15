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
ms.openlocfilehash: 8037cb8025cc85a8479528490e1512531cbcc035
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322308"
---
# <a name="hint-files"></a>İpucu Dosyaları

İpucu *dosyası,* aksi takdirde kod bölgelerinin C++ Gözatma Veritabanı Parser tarafından atlanmasına neden olacak makrolar içerir. Visual Studio C++ projesini açtığınızda, arayıcı projedeki her kaynak dosyadaki kodu analiz eder ve her tanımlayıcı hakkında bilgi içeren bir veritabanı oluşturur. IDE bu bilgileri **Sınıf Görünümü** tarayıcısı ve **Gezinti Çubuğu**gibi kod tarama özelliklerini desteklemek için kullanır.

C++ Tarama Veritabanı Parser kısa bir süre içinde kod büyük miktarda ayrıştırabilir bulanık bir arayıcı. Hızlı olmasının bir nedeni blokların içeriğini atlamasa olur. Örneğin, yalnızca bir işlevin konumunu ve parametrelerini kaydeder ve içeriğini yoksayılsa. Bazı makrolar, bir bloğun başlangıcını ve sonunu belirlemek için kullanılan buluşsal sorunlara neden olabilir. Bu sorunlar, kod bölgelerinin yanlış kaydedilmesine neden olur.

Bu atlanan bölgeler birden çok şekilde tezahür edebilir:

- **Sınıf Görünümünde**Eksik türleri ve işlevleri , **Git** ve **Gezinti Çubuğu**

- **Gezinti Çubuğu'ndaki** yanlış kapsamlar

- Zaten tanımlanmış işlevler için **Bildirim/Tanım Oluşturma** Önerileri

İpucu dosyası, C/C++ makro tanımları ile aynı sözdizimine sahip kullanıcı tarafından özelleştirilebilir ipuçları içerir. Visual C++ çoğu proje için yeterli olan yerleşik bir ipucu dosyası içerir. Ancak, özellikle projeniz için ayrıştırıcıyı geliştirmek için kendi ipucu dosyalarınızı oluşturabilirsiniz.

> [!IMPORTANT]
> Bir ipucu dosyasını değiştirir veya eklerseniz, değişikliklerin etkili olması için ek adımlar atmanız gerekir:
>
> - Visual Studio 2017 sürüm 15.6 önceki sürümlerde: Tüm değişiklikler için çözümdeki .sdf dosyasını ve/veya VC.db dosyasını silin.
> - Visual Studio 2017 sürüm 15.6 ve sonraki sürümde: Yeni ipucu dosyaları ekledikten sonra çözümü kapatın ve yeniden açın.

## <a name="scenario"></a>Senaryo

```cpp
#define NOEXCEPT noexcept
void Function() NOEXCEPT
{
}
```

`Function` İpucu dosyası olmadan, Sınıf **Görünümünde**görünmüyor , Git **veya** Gezinti **Çubuğu**. Bu makro tanımı ile bir ipucu dosyası ekledikten sonra, `NOEXCEPT` parser şimdi anlar ve doğru işlevi ayrıştırmak için izin veren makro, değiştirir:

```cpp.hint
#define NOEXCEPT
```

## <a name="disruptive-macros"></a>Yıkıcı Makrolar

Ayrıştırıcıyı bozan iki makro kategorisi vardır:

- Bir işlevi süsleyen anahtar kelimeleri kapsülleyen makrolar

   ```cpp
   #define NOEXCEPT noexcept
   #define STDMETHODCALLTYPE __stdcall
   ```

   Bu makro türleri için ipucu dosyasında yalnızca makro adı gereklidir:

   ```cpp.hint
   #define NOEXCEPT
   #define STDMETHODCALLTYPE
   ```

- Dengesiz köşeli ayraçlar içeren makrolar

   ```cpp
   #define BEGIN {
   ```

   Bu makro türleri için, ipucu dosyasında hem makro adı hem de içeriği gereklidir:

   ```cpp.hint
   #define BEGIN {
   ```

## <a name="editor-support"></a>Editör Desteği

Visual Studio 2017 sürüm 15.8'den başlayarak rahatsız edici makroları tanımlamak için çeşitli özellikler vardır:

- Ayrıştırıcı tarafından atlanan bölgelerin içindeki makrolar vurgulanır.

- Vurgulanan makroyu içeren bir ipucu dosyası oluşturmak veya makroyu ipucu dosyasına eklemek için varolan bir ipucu dosyası varsa, hızlı eylem vardır.

![Vurgulanan Makro.](media/hint-squiggle-and-actions.png "İpucu squiggle ve Hızlı Eylemler")

Hızlı Eylemler'den birini çalıştırdıktan sonra, arayıcı ipucu dosyasından etkilenen dosyaları geri alır.

Varsayılan olarak, sorun makro bir öneri olarak vurgulanır. Vurgu, kırmızı veya yeşil dalgalı gibi daha belirgin bir şeyle değiştirilebilir.  >  **Araçlar****Seçenekleri** > **View****Text Editor** >  **Macros in Skipped Browsing Regions**  > Metin**Düzenleyicisi C/C++** Görünümü altında **Kod Squiggles** bölümünde Atlanan Tarama Bölgelerinde Makrolar seçeneğini kullanın.

![Atlanan Tarama Bölgeleri Seçeneğindeki Makrolar.](media/skipped-regions-squiggle-option.png "Atlanan bölgeler dalgalı seçeneği.")

## <a name="display-browsing-database-errors"></a>Tarama Veritabanı Hatalarını Görüntüleme

**Project** > **Display Tarama Veritabanı Hataları** menüsü, Hata **Listesinde**ayrıştırılamamış tüm bölgeleri görüntüler. Komut, ilk ipucu dosyasını oluşturmayı kolaylaştırmak içindir. Ancak, arayıcı hatanın nedeninin yıkıcı bir makro olup olmadığını söyleyemez, bu nedenle her hatayı değerlendirmeniz gerekir. Görüntülü **Tarama Veritabanı Hataları** komutunu çalıştırın ve etkilenen dosyayı düzenleyiciye yüklemek için her hataya gidin. Dosya yüklendikten sonra, bölge içinde makrovarsa, bunlar vurgulanır. Hızlı Eylemler'i bir ipucu dosyasına eklemek için çağırabilirsiniz. İpucu dosyası güncelleştirmeden sonra, hata listesi otomatik olarak güncelleştirilir. Alternatif olarak, ipucu dosyasını el ile değiştiriyorsanız, bir güncelleştirmeyi tetiklemek için **Rescan Solution** komutunu kullanabilirsiniz.

## <a name="architecture"></a>Mimari

İpucu **dosyaları, Çözüm Gezgini'nde**gösterilen mantıksal dizinlerle değil, fiziksel dizinlerle ilgilidir. İpucu dosyasının etkili olması için projenize bir ipucu dosyası eklemeniz gerekmez. Ayrıştma sistemi yalnızca kaynak dosyalarını ayrışttığında ipucu dosyalarını kullanır.

Her ipucu dosyası **cpp.ipucu**adlı . Birçok dizin bir ipucu dosyası içerebilir, ancak belirli bir dizinde yalnızca bir ipucu dosyası oluşabilir.

Projeniz sıfır veya daha fazla ipucu dosyasından etkilenebilir. İpucu dosyaları yoksa, ayrıştma sistemi çözülemez kaynak kodunu yok saymak için hata kurtarma tekniklerini kullanır. Aksi takdirde, ayrıştma sistemi ipuçlarını bulmak ve toplamak için aşağıdaki stratejiyi kullanır.

### <a name="search-order"></a>Arama Siparişi

Ayrıştma sistemi, aşağıdaki sırada ipucu dosyaları için dizinarar.

- Visual C++**(vcpackages)** için yükleme paketini içeren dizin. Bu dizin, **windows.h**gibi sık kullanılan sistem dosyalarındaki simgeleri açıklayan yerleşik bir ipucu dosyası içerir. Sonuç olarak, projeniz ihtiyaç duyduğu ipuçlarının çoğunu otomatik olarak devralır.

- Kaynak dosyanın kök dizininden kaynak dosyanın kendisini içeren dizine giden yol. Tipik bir Visual Studio C++ projesinde, kök dizini çözüm veya proje dosyasını içerir.

   Bu kuralın istisnası, *bir durdurma dosyasının* kaynak dosyaya giden yolda olmasıdır. Stop dosyası **cpp.stop**adlı herhangi bir dosyadır. Durdurma dosyası arama sırası üzerinde ek denetim sağlar. Kök dizini başlayarak yerine, ayrıştma sistemi kaynak dosyaiçeren dizini için stop dosyası içeren dizin arar. Tipik bir projede, durdurma dosyasına ihtiyacınız yoktur.

### <a name="hint-gathering"></a>İpucu Toplama

İpucu dosyası sıfır veya daha fazla *ipucu*içerir. İpucu, c/c++ makrosu gibi tanımlanır veya silinir. Diğer bir `#define` süre, önişlemci yönergesi bir ipucu `#undef` oluşturur veya yeniden tanımlar ve yönerge bir ipucusa siler.

Ayrıştırma sistemi, daha önce açıklanan arama emrindeki her ipucu dosyasını açar. Her dosyanın ipuçlarını *etkili ipuçları*kümesinde birikir ve ardından kodunuzdatanımlayıcıları yorumlamak için etkili ipuçlarını kullanır.

Ayrıştma sistemi ipuçları biriktirmek için bu kuralları kullanır:

- Yeni ipucu zaten tanımlanmamış bir ad belirtirse, yeni ipucu etkili ipuçlarına adı ekler.

- Yeni ipucu zaten tanımlanmış bir ad belirtirse, yeni ipucu varolan ipucunu yeniden tanımlar.

- Yeni ipucu, varolan etkili bir ipucunu belirten bir `#undef` yönergeyse, yeni ipucu varolan ipucunu siler.

İlk kural, etkili ipuçlarının önceden açılmış ipucu dosyalarından devraldığı anlamına gelir. Son iki kural, arama siparişindeki ipuçlarının daha önceki ipuçlarını geçersiz kılabilir anlamına gelir. Örneğin, dizinde kaynak dosyası içeren bir ipucu dosyası oluşturursanız, önceki ipuçlarını geçersiz kılabilirsiniz.

İpuçlarının nasıl toplandığını gösteren bir tasvir için [Örnek](#example) bölümüne bakın.

### <a name="syntax"></a>Sözdizimi

Makrooluşturmak ve silmek için önişlemci yönergeleriyle aynı sözdizimini kullanarak ipuçları oluşturur ve silebilirsiniz. Aslında, ayrıştma sistemi ipuçlarını değerlendirmek için C/C++ ön işlemcisini kullanır. Önişlemci yönergeleri hakkında daha fazla bilgi için [#define Direktifi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md) ve [#undef Yönergesi (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)'ye bakın.

Yalnızca olağandışı sözdizimi `@<`öğeleri `@=`, `@>` , ve değiştirme dizeleri vardır. Bu ipucu dosyasına özgü değiştirme dizeleri yalnızca *harita* makrolarında kullanılır. Harita, verileri, işlevleri veya olayları diğer verilerle, işlevlerle veya olay işleyicileriyle ilişkilendiren bir makro kümesidir. Örneğin, `MFC` [ileti eşlemleri](../../mfc/reference/message-maps-mfc.md)oluşturmak `ATL` için haritalar kullanır ve [nesne haritaları](../../atl/reference/object-map-macros.md)oluşturmak için haritalar kullanır. İpucu dosyasına özgü değiştirme dizeleri, bir haritanın başlangıç, ara ve bitiş öğelerini işaretler. Yalnızca bir harita makrosu adı önemlidir. Bu nedenle, her değiştirme dizesi kasıtlı olarak makronun uygulanmasını gizler.

İpuçları şu sözdizimini kullanır:

|Sözdizimi|Anlamı|
|------------|-------------|
|`#define`*ipucu-isim* *değiştirme-dize*<br /><br /> `#define`*ipucu-isim* `(` *parametresi*, ... `)` *değiştirme dizesi*|Yeni bir ipucu tanımlayan veya varolan bir ipucunu yeniden tanımlayan bir önişlemci yönergesi. Yönergeden sonra, önişlemci kaynak kodundaki *ipucu adının* her oluşumunu *değiştirme dizesiyle*değiştirir.<br /><br /> İkinci sözdizimi formu işlev benzeri bir ipucu tanımlar. Kaynak kodunda işlev benzeri bir ipucu oluşursa, önişlemci önce kaynak kodundaki karşılık gelen bağımsız değişkenle *değiştirme dizesinde* *parametrenin* her oluşumunu değiştirir ve ardından *ipucu adını* *değiştirme dizesi*ile değiştirir.|
|`@<`|Bir dizi eş öğenin başlangıcını gösteren bir ipucu dosyası belirli *değiştirme dizesi.*|
|`@=`|Bir ara eş öğeöğesini gösteren bir ipucu dosyası belirli *değiştirme dizesi.* Bir haritada birden çok harita öğesi olabilir.|
|`@>`|Bir dizi eş öğenin sonunu gösteren bir ipucu dosyası belirli *değiştirme dizesi.*|
|`#undef`*ipucu adı*|Varolan bir ipucunu silen önişlemci yönergesi. İpucunun adı *ipucu adı* tanımlayıcısı tarafından sağlanır.|
|`//`*yorum yapın*|Tek satırlık bir yorum.|
|`/*`*yorum yapın*`*/`|Çok satırlı bir yorum.|

## <a name="example"></a>Örnek

Bu örnek, ipucu dosyalarından ipuçlarının nasıl biriktiğini gösterir. Durdur dosyaları bu örnekte kullanılmaz.

Resimde Visual Studio C++ projesindeki bazı fiziksel dizinler gösterilmektedir. `vcpackages`İpuçlarında `Debug` `A1`ve `A2` dizinlerde ipucu dosyaları vardır.

### <a name="hint-file-directories"></a>İpucu Dosya Dizinleri

![Ortak ve proje&#45;belirli ipucu dosya dizinleri.](media/hintfile.png "HintDosyası")

### <a name="directories-and-hint-file-contents"></a>Dizinler ve İpucu Dosya İçeriği

Bu liste, bu projede ipucu dosyaları içeren dizinleri ve bu ipucu dosyalarının içeriğini gösterir. Dizin ipucu dosyasındaki birçok `vcpackages` ipucundan yalnızca bazıları listelenir:

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

### <a name="effective-hints"></a>Etkili İpuçları

Bu tablo, bu projedeki kaynak dosyaların etkili ipuçlarını listeler:

- Kaynak Dosya: A1_A2_B.cpp

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

Bu notlar önceki listeye uygulanır:

- Etkili `vcpackages`ipuçları , , `Debug` `A1`, ve `A2` dizinler vardır.

- İpucu **#undef** dosyasındaki `Debug` #undef yönergesi, dizin ipucu dosyasındaki `#define _In_` ipucunu `vcpackages` kaldırdı.

- Dizindeki `A1` ipucu dosyası yeniden `START_NAMESPACE`tanımlar.

- `#undef` Dizindeki `A2` ipucu, dizin ipucu `OBRACE` `CBRACE` dosyasındaki `Debug` ve dizin ipucu dosyasındaki ipuçlarını kaldırdı.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projeleri için Oluşturulan Dosya Türleri](file-types-created-for-visual-cpp-projects.md)<br>
[#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)<br>
[#undef Yönergesi (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)<br>
[SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)<br>
