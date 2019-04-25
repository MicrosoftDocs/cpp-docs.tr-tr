---
title: Bağlayıcı Araçları Hatası LNK2005
ms.date: 11/04/2016
f1_keywords:
- LNK2005
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
ms.openlocfilehash: 8b4f75b90254c702ecb2afb65108278a59df69ed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299211"
---
# <a name="linker-tools-error-lnk2005"></a>Bağlayıcı Araçları Hatası LNK2005

> *Sembol* nesnesinde zaten tanımlı

Simgenin *sembol* birden çok kez tanımlandı.

Bu hata, önemli hata tarafından izlenir [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).

### <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Genellikle bu hata, ayrılmış anlamına gelir *tek tanım kuralı*, veren kullanılan şablon, işlev, türü veya belirli nesne dosyasına nesne için yalnızca bir tanımı ve yalnızca bir tanımı için tüm yürütülebilir dosya arasında dışarıdan görünen nesneleri veya işlevleri.

Bu hata için bazı yaygın nedenleri aşağıdadır.

- Bir üstbilgi dosyası bir değişkeni tanımlar. Bu hata oluşabilir. Örneğin, projenizde birden fazla kaynak dosyada bu üst bilgi dosyasını dahil ederseniz, hatayla sonuçlanır:

    ```h
    // LNK2005_global.h
    int global_int;  // LNK2005
    ```

   Olası çözümleri şunlardır:

   - Değişken bildirme `extern` üstbilgi dosyasında: `extern int global_int;`, daha sonra tanımlamak ve isteğe bağlı olarak, bir ve yalnızca bir kaynak dosyada başlatılamıyor: `int global_int = 17;`. Bu artık genel bir değişkendir bildirme tarafından herhangi bir kaynak dosyada kullanabileceğiniz `extern`, örneğin, üstbilgi dosyasını dahil. Bu çözüm için genel değişkenler tavsiye ederiz ancak iyi yazılım Mühendisliği uygulama genel değişkenler en aza indirir.

   - Değişken bildirme [statik](../../cpp/storage-classes-cpp.md#static): `static int static_int = 17;`. Bu durum, geçerli nesne dosyası tanımına kapsamını sınırlar ve kendilerine ait kopyasında değişkeni sağlamak birden çok nesne dosyaları sağlar. Statik değişkenler üstbilgi dosyalarında olası Karışıklığı önlemek ile genel değişkenler nedeniyle tanımladığınız önerilmemektedir. Statik değişken tanımlar, bunları kullanan kaynak dosyalarıyla taşımak tercih eder.

   - Değişken bildirme [selectany](../../cpp/selectany.md): `__declspec(selectany) int global_int = 17;`. Bu bağlayıcının dış başvuruları tarafından kullanım için bir tanımı çekme ve rest atmak bildirir. Bu çözüm bazen içeri aktarma kitaplıkları birleştirilirken yararlıdır. Aksi takdirde, bu bağlayıcı hatalarını önlemek için bir yol önermiyoruz.

- Bir üstbilgi dosyası olmayan bir işlev tanımlar. Bu hata oluşabilir `inline`. Birden fazla kaynak dosyada bu üst bilgi dosyasını dahil ederseniz, yürütülebilir dosya işlevinin birden çok tanım alın.

    ```h
    // LNK2005_func.h
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   Olası çözümleri şunlardır:

   - Ekleme `inline` anahtar sözcüğü işlevin:

        ```h
        // LNK2005_func_inline.h
        inline int sample_function(int k) { return 42 * (k % 167); }
        ```

   - İşlev gövdesi üstbilgi dosyasından kaldırın ve bildirimi yalnızca bırakın ve ardından bir ve yalnızca bir kaynak dosyada işlevi uygulayın:

        ```h
        // LNK2005_func_decl.h
        int sample_function(int);
        ```

        ```cpp
        // LNK2005_func_impl.cpp
        int sample_function(int k) { return 42 * (k % 167); }
        ```

- Üye işlevleri sınıf bildirimi dışında bir üstbilgi dosyasında tanımlarsanız, bu hatayı da meydana gelebilir:

    ```h
    // LNK2005_member_outside.h
    class Sample {
    public:
        int sample_function(int);
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   Bu sorunu gidermek için üye işlev tanımları bir sınıf içinde taşıyın. Sınıf bildirimi içinde tanımlanmış üye işlevleri, örtük olarak satır içine alınmış.

    ```h
    // LNK2005_member_inline.h
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }
    };
    ```

- CRT ve standart kitaplığı birden fazla sürümünü bağlarsanız, bu hata oluşabilir. Örneğin, hem Perakende ve hata ayıklama CRT kitaplığı veya bir kitaplık statik ve dinamik sürümleri veya iki farklı sürümünü standart kitaplığı için yürütülebilir dosyanın bağlantı çalışırsanız, bu hata birçok kez bildirilebilir. Bu sorunu gidermek için her kitaplığı biri dışında tüm kopyasını bağlantı komuttan kaldırın. Perakende karışımı ve kitaplıkları veya farklı bir kitaplıkta aynı yürütülebilir dosya sürümlerini hatalarını önermiyoruz.

   Varsayılan dışındaki kitaplıkları komut satırında kullanmak için bağlayıcı bildirmek için kullanın ve kitaplıkları belirtin [/nodefaultlıb](../../build/reference/nodefaultlib-ignore-libraries.md) varsayılan kitaplıkları devre dışı bırakma seçeneği. IDE'de kitaplıklarını kullanın ve ardından açmak için belirtmek için projenizin başvurular eklemek **özellik sayfaları** iletişim ve projeniz için **bağlayıcı**, **giriş** özelliği sayfasında, ya da ayarlanmış **tüm varsayılan kitaplıkları Yoksay**, veya **belirli varsayılan kitaplıkları Yoksay** varsayılan kitaplıkları devre dışı bırakmak için özellikleri.

- Kullanırken statik ve dinamik kitaplıklar kullanımını karışımı varsa, bu hata oluşabilir [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği. Örneğin, bir DLL kullanmak için yürütülebilir dosya bağlanan statik CRT'deki oluşturuyorsanız bu hata oluşabilir. Bu sorunu gidermek için yalnızca statik kitaplıklar veya yalnızca dinamik kitaplıklar yürütülebilir dosya kullanmak için yapı tüm kitaplıkları ve tüm yürütülebilir için kullanın.

- Simge paketlenmiş bir işlev ise bu hata oluşabilir (ile derleme tarafından oluşturulan [/Gy](../../build/reference/gy-enable-function-level-linking.md)) ve birden fazla dosyasında bulunan, ancak derleme arasında değiştirildi. Bu sorunu gidermek için paket işlevini içeren tüm dosyaları yeniden derleyin.

- Sembol farklı kitaplıklarındaki iki üye nesneleri farklı şekilde tanımlanmış ve her iki üye nesneleri kullanılan bu hata oluşabilir. Statik olarak bağlanan kitaplıklar, bu sorunu gidermek için bir üye nesne yalnızca bir kitaplıktan kullanın ve bu kitaplık, ilk bağlayıcı komut satırına eklemek için yoludur. Her iki simge kullanmak için bunları ayırt etmek için bir yol oluşturmanız gerekir. Örneğin, kaynak kitaplıklarından oluşturabilirsiniz, her bir benzersiz ad alanı kitaplıkta sarabilirsiniz. Alternatif olarak, özgün kitaplıkları birine başvuruları kaydırma, özgün kitaplığa yeni kitaplığına bağlantı ve ardından özgün kitaplık yerine yeni kitaplığınızı yürütülebilir bağlamak için benzersiz adlar kullanan yeni bir sarmalayıcı kitaplıktır oluşturabilirsiniz.

- Bu hata oluşabilir bir `extern const` değişkeni iki kez tanımlanmış ve her tanımı farklı bir değer içeriyor. Bu sorunu gidermek için sabit yalnızca bir kez tanımlayın ve ad alanlarını veya `enum class` tanımları, sabitleri ayırt etmek için.

- Uuid.lib tanımlayan GUID'leri (örneğin, oledb.lib ve adsiid.lib) diğer .lib dosyaları ile birlikte kullanıyorsanız bu hata oluşabilir. Örneğin:

    ```Output
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject
    already defined in uuid.lib(go7.obj)
    ```

   Bu sorunu gidermek için ekleme [/Force: multıple](../../build/reference/force-force-file-output.md) bağlayıcı komut satırı seçenekleri ve emin olun, uuid.lib başvurulan ilk kitaplığıdır.
