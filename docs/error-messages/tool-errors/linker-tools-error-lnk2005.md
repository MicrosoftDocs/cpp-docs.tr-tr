---
title: Bağlayıcı Araçları Hatası LNK2005
ms.date: 11/04/2016
f1_keywords:
- LNK2005
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
ms.openlocfilehash: 6090478c3761c477250b6706a350e261b51f2a05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353234"
---
# <a name="linker-tools-error-lnk2005"></a>Bağlayıcı Araçları Hatası LNK2005

> nesnede zaten tanımlanan *sembol*

Sembol *sembolü* birden çok kez tanımlanmıştır.

Bu hatayı ölümcül hata [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md)takip ediyor.

### <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Genel olarak, bu hata, belirli bir nesne dosyasında kullanılan şablon, işlev, tür veya nesne için yalnızca bir tanım ve dışarıdan görünen nesneler veya işlevler için yürütülebilir tüm genelinde yalnızca bir tanım sağlayan *tek tanım kuralını*kırdığınız anlamına gelir.

Bu hatanın bazı yaygın nedenleri aşağıda veda edinilir.

- Üstbilgi dosyası bir değişken tanımladığında bu hata oluşabilir. Örneğin, bu üstbilgi dosyanı projenizde birden fazla kaynak dosyaya eklerseniz, bir hata sonucu:

    ```h
    // LNK2005_global.h
    int global_int;  // LNK2005
    ```

   Olası çözümler şunlardır:

  - Üstbilgi `extern` dosyasındaki değişkeni `extern int global_int;`bildirin: , sonra tanımlayın ve isteğe bağlı `int global_int = 17;`olarak tek ve tek bir kaynak dosyada başlatılması: . Bu değişken artık herhangi bir kaynak dosyada kullanabileceğiniz `extern`bir genel dir, örneğin, üstbilgi dosyasını ekleyerek beyan ederek. Bu çözümü küresel olması gereken değişkenler için öneriyoruz, ancak iyi yazılım mühendisliği uygulamaları küresel değişkenleri en aza indirir.

  - Değişken [statik](../../cpp/storage-classes-cpp.md#static)bildirin : `static int static_int = 17;`. Bu, tanımın kapsamını geçerli nesne dosyasıyla sınırlandırAn ve birden çok nesne dosyasının değişkenin kendi kopyasına sahip olmasını sağlar. Genel değişkenlerle karışıklık potansiyeli nedeniyle üstbilgi dosyalarında statik değişkenler tanımlamanızı önermiyoruz. Statik değişken tanımlarını bunları kullanan kaynak dosyalara taşımayı tercih edin.

  - Değişken [selectany](../../cpp/selectany.md)bildirin : `__declspec(selectany) int global_int = 17;`. Bu, bağlayıcıya tüm dış başvurular tarafından kullanılmak üzere bir tanım seçmesi ve geri kalanını atmasını söyler. Bu çözüm bazen alma kitaplıklarını birleştirirken kullanışlıdır. Aksi takdirde, bağlayıcı hatalarını önlemek için bir yol olarak önermiyoruz.

- Üstbilgi dosyası olmayan `inline`bir işlev tanımladığında bu hata oluşabilir. Bu üstbilgi dosyasını birden fazla kaynak dosyaya eklerseniz, yürütülebilir işlevin birden çok tanımını alırsınız.

    ```h
    // LNK2005_func.h
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   Olası çözümler şunlardır:

  - İşlev `inline` için anahtar kelime ekleyin:

    ```h
    // LNK2005_func_inline.h
    inline int sample_function(int k) { return 42 * (k % 167); }
    ```

  - İşlev gövdesini üstbilgi dosyasından kaldırın ve yalnızca bildirimi bırakın, ardından işlevi tek ve tek bir kaynak dosyada uygulayın:

    ```h
    // LNK2005_func_decl.h
    int sample_function(int);
    ```

    ```cpp
    // LNK2005_func_impl.cpp
    int sample_function(int k) { return 42 * (k % 167); }
    ```

- Üstbilgi dosyasında sınıf bildirimi dışında üye işlevleri tanımlarsanız bu hata da oluşabilir:

    ```h
    // LNK2005_member_outside.h
    class Sample {
    public:
        int sample_function(int);
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   Bu sorunu gidermek için, üye işlev tanımlarını sınıf içinde taşıyın. Sınıf bildirimi içinde tanımlanan üye işlevler örtülü olarak sıralanır.

    ```h
    // LNK2005_member_inline.h
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }
    };
    ```

- Bu hata, standart kitaplığın veya CRT'nin birden fazla sürümünü bağlarsanız oluşabilir. Örneğin, hem perakende satış hem de hata ayıklama CRT kitaplıklarını veya kitaplığın statik ve dinamik sürümlerini veya standart kitaplığın iki farklı sürümlerini çalıştırılabilir'inize bağlamayı denerseniz, bu hata birçok kez bildirilebilir. Bu sorunu gidermek için, bağlantı komutundan her kitaplığın bir kopyası dışında tümünün kaldırılmasını sağlayın. Perakende ve hata ayıklama kitaplıklarını veya kitaplığın farklı sürümlerini aynı yürütülebilir şekilde karıştırmanızı önermiyoruz.

   Bağlayıcıya varsayılanlar dışındaki kitaplıkları kullanmasını söylemek için komut satırında kullanılacak kitaplıkları belirtin ve varsayılan kitaplıkları devre dışı kullanabilirsiniz [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) seçeneğini kullanın. IDE'de, kullanılacak kitaplıkları belirtmek için projenize başvurular ekleyin ve ardından projeniz için **Özellik Sayfaları** iletişim kutusunu açın ve **Bağlayıcı**, **Giriş** özelliği sayfasında, Varsayılan Kitaplıkları devre dışı bırakabilmek için Tüm **Varsayılan Kitaplıkları Yokla**veya **Belirli Varsayılan Kitaplıkları YokSay** özelliğini ayarlayın.

- [/clr](../../build/reference/clr-common-language-runtime-compilation.md) seçeneğini kullandığınızda statik ve dinamik kitaplıkları karıştırırsanız bu hata oluşabilir. Örneğin, bu hata, yürütülebilir olan statik CRT bağlantıları kullanmak için bir DLL oluşturursanız oluşabilir. Bu sorunu gidermek için, yalnızca statik kitaplıklar veya yalnızca çalıştırılabilir tüm ve yürütülebilir kullanmak için oluşturduğunuz kitaplıklar için yalnızca dinamik kitaplıklar kullanın.

- Bu hata, sembol paketlenmiş bir işlevse [(/Gy](../../build/reference/gy-enable-function-level-linking.md)ile derlenerek oluşturulmuştur) ve birden fazla dosyaya dahil edilmişse, derlemeler arasında değiştirildiyse oluşabilir. Bu sorunu gidermek için, paket işlevi içeren tüm dosyaları yeniden derleyin.

- Bu hata, sembol farklı kitaplıklarda iki üye nesnede farklı tanımlanmışsa ve her iki üye nesne de kullanılırsa bu hata oluşabilir. Kitaplıklar statik olarak bağlandığında bu sorunu gidermenin bir yolu, üye nesneyi yalnızca bir kitaplıktan kullanmak ve bu kitaplığı önce bağlayıcı komut satırına eklemektir. Her iki sembolü de kullanmak için, onları ayırt etmek için bir yol oluşturmanız gerekir. Örneğin, kitaplıkları kaynaktan oluşturabiliyorsanız, her kitaplığı benzersiz bir ad alanına sarabilirsiniz. Alternatif olarak, başvuruları özgün kitaplıklardan birine kaydırmak, yeni kitaplığı özgün kitaplıklara bağlamak ve ardından yürütülebilir olan kitabı özgün kitaplığınız yerine yeni kitaplığınıza bağlamak için benzersiz adlar kullanan yeni bir sarıcı kitaplığı oluşturabilirsiniz.

- Bir `extern const` değişken iki kez tanımlanırsa ve her tanımda farklı bir değere sahipse, bu hata oluşabilir. Bu sorunu gidermek için, sabiti yalnızca bir `enum class` kez tanımlayın veya sabitleri ayırt etmek için ad boşluklarını veya tanımları kullanın.

- Bu hata, guids (örneğin, oledb.lib ve adsiid.lib) tanımlayan diğer .lib dosyaları ile birlikte uuid.lib kullanırsanız oluşabilir. Örneğin:

    ```Output
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject
    already defined in uuid.lib(go7.obj)
    ```

   Bu sorunu gidermek için bağlayıcı komut satırı seçeneklerine [/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md) ekleyin ve uuid.lib'in başvurulan ilk kitaplık olduğundan emin olun.
