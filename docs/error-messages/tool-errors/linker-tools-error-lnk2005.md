---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK2005'
title: Bağlayıcı Araçları Hatası LNK2005
ms.date: 11/04/2016
f1_keywords:
- LNK2005
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
ms.openlocfilehash: c6de300bc731104f51056911515d0cc7a95e05f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338498"
---
# <a name="linker-tools-error-lnk2005"></a>Bağlayıcı Araçları Hatası LNK2005

> *sembol* nesnede zaten tanımlandı

Sembol *sembolü* birden çok kez tanımlandı.

Bu hatanın ardından önemli hata [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).

### <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Genellikle, bu hata, belirli bir nesne dosyasındaki kullanılan herhangi bir şablon, işlev, tür veya nesne için yalnızca bir tanıma izin veren *bir tanım kuralını* bozmış ve dışarıdan görünür nesneler veya işlevler için tek bir tanım sunan tek bir tanım kuralına sahip olduğunuz anlamına gelir.

Bu hatanın bazı yaygın nedenleri aşağıda verilmiştir.

- Bu hata, bir üstbilgi dosyası bir değişkeni tanımlıyorsa oluşabilir. Örneğin, bu üstbilgi dosyasını projenizde birden fazla kaynak dosyasına eklerseniz bir hata oluşur:

    ```h
    // LNK2005_global.h
    int global_int;  // LNK2005
    ```

   Olası çözümler şunlardır:

  - **`extern`** Başlık dosyasında değişkeni bildirin: `extern int global_int;` , daha sonra tanımlayın ve isteğe bağlı olarak tek bir kaynak dosyasında başlatın: `int global_int = 17;` . Bu değişken, **`extern`** Örneğin, başlık dosyasını ekleyerek herhangi bir kaynak dosyasında kullanabileceğiniz küresel bir geneldir. Bu çözümü genel olması gereken değişkenler için öneririz, ancak iyi yazılım mühendisliği uygulaması genel değişkenleri en aza indirir.

  - [Statik](../../cpp/storage-classes-cpp.md#static)değişkeni bildirin: `static int static_int = 17;` . Bu, tanımın kapsamını geçerli nesne dosyası ile kısıtlar ve birden fazla nesne dosyasının değişkenin kendi kopyasına sahip olmasına izin verir. Genel değişkenlerle karışıklığa neden olduğu için üst bilgi dosyalarında statik değişkenler tanımlamanızı önermiyoruz. Statik değişken tanımlarını onları kullanan kaynak dosyalara taşımayı tercih edin.

  - [Selectany](../../cpp/selectany.md)değişkenini bildirin: `__declspec(selectany) int global_int = 17;` . Bu, bağlayıcının tüm dış başvurular tarafından kullanılmak üzere bir tanım seçmesini ve geri kalanını atmasını söyler. Bu çözüm bazen içeri aktarma kitaplıklarını birleştirirken yararlı olur. Aksi takdirde, bağlayıcı hatalarından kaçınmanın bir yolu olarak önerilmez.

- Bu hata, üstbilgi dosyası olmayan bir işlevi tanımlıyorsa oluşabilir **`inline`** . Bu üstbilgi dosyasını birden fazla kaynak dosyasına eklerseniz, çalıştırılabilir dosyada işlevin birden fazla tanımını alırsınız.

    ```h
    // LNK2005_func.h
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   Olası çözümler şunlardır:

  - **`inline`** İşlevine anahtar sözcüğü ekleyin:

    ```h
    // LNK2005_func_inline.h
    inline int sample_function(int k) { return 42 * (k % 167); }
    ```

  - Başlık dosyasından işlev gövdesini kaldırın ve yalnızca bildirimi bırakın, sonra işlevi tek bir kaynak dosyasında uygulayın:

    ```h
    // LNK2005_func_decl.h
    int sample_function(int);
    ```

    ```cpp
    // LNK2005_func_impl.cpp
    int sample_function(int k) { return 42 * (k % 167); }
    ```

- Bu hata, bir başlık dosyasında sınıf bildiriminin dışında üye işlevleri tanımlarsanız de oluşabilir:

    ```h
    // LNK2005_member_outside.h
    class Sample {
    public:
        int sample_function(int);
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   Bu sorunu giderecek şekilde, sınıf içindeki üye işlev tanımlarını taşıyın. Bir sınıf bildiriminde tanımlanan üye işlevleri örtülü olarak satır içine alınır.

    ```h
    // LNK2005_member_inline.h
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }
    };
    ```

- Bu hata, standart kitaplığın veya CRT 'ın birden fazla sürümünü bağlarsanız meydana gelebilir. Örneğin, hem perakende hem de hata ayıklama CRT kitaplıklarını ya da bir kitaplığın statik ve dinamik sürümlerini ya da standart kitaplığın iki farklı sürümünü yürütülebilir dosyaya bağlamayı denerseniz, bu hata birçok kez bildirilebilir. Bu sorunu onarmak için, her kitaplığın bir kopyasını bağlantı komutundan kaldırın. Aynı yürütülebilir dosyada, perakende ve hata ayıklama kitaplıklarını ya da bir kitaplığın farklı sürümlerini karıştırmanızı önermiyoruz.

   Bağlayıcının varsayılanlar dışındaki kitaplıkları kullanmasını söylemek için, komut satırında kullanılacak kitaplıkları belirtin ve varsayılan kitaplıkları devre dışı bırakmak için [/nodefaultlib](../../build/reference/nodefaultlib-ignore-libraries.md) seçeneğini kullanın. IDE 'de, kullanılacak kitaplıkları belirtmek için projenize başvurular ekleyin ve ardından projeniz için **Özellik sayfaları** iletişim kutusunu açın ve **bağlayıcı**, **giriş** özelliği sayfasında, varsayılan kitaplıkları devre dışı bırakmak Için **tüm varsayılan kitaplıkları Yoksay** veya **belirli varsayılan kitaplıkları Yoksay** özelliklerini belirleyin.

- [/Clr](../../build/reference/clr-common-language-runtime-compilation.md) seçeneğini kullandığınızda, statik ve dinamik kitaplıkların kullanımını karıştırırsanız bu hata oluşabilir. Örneğin, çalıştırılabilir dosyada statik CRT ile bağlantı için bir DLL oluşturursanız bu hata oluşabilir. Bu sorunu onarmak için yalnızca statik kitaplıkları veya yalnızca dinamik kitaplıkları veya yürütülebilir dosyada kullanmak için oluşturduğunuz tüm kitaplıkları kullanın.

- Bu hata, sembol paketlenmiş bir işlev ise ( [/GY](../../build/reference/gy-enable-function-level-linking.md)ile derlenerek oluşturulur) ve birden fazla dosyaya dahil edilmiştir ancak derlemeler arasında değiştirilmişse meydana gelir. Bu sorunu onarmak için paketlenmiş işlevi içeren tüm dosyaları yeniden derleyin.

- Bu hata, sembolün farklı kitaplıklardaki iki üye nesnesi içinde farklı tanımlanmış olması ve her iki üye nesnesinin de kullanılması durumunda meydana gelebilir. Kitaplıklar statik olarak bağlandığında bu sorunu gidermenin bir yolu, üye nesnesini yalnızca bir kitaplıktan kullanmak ve önce bu kitaplığı bağlayıcı komut satırına eklemek içindir. Her iki sembolü de kullanmak için, bunları ayırt etmek için bir yol oluşturmanız gerekir. Örneğin, bir kaynaktan kitaplıkları derleyebilir, her kitaplığı benzersiz bir ad alanında kaydırabilirsiniz. Alternatif olarak, özgün kitaplıkların birine başvuruları sarmalamak için benzersiz adlar kullanan yeni bir sarmalayıcı kitaplığı oluşturabilir, yeni kitaplığı özgün kitaplığa bağlayabilir ve ardından özgün kitaplık yerine yürütülebilir dosyayı yeni kitaplığınıza bağlayabilirsiniz.

- Bu hata `extern const` , bir değişken iki kez tanımlanmışsa ve her tanımda farklı bir değere sahip olduğunda meydana gelebilir. Bu sorunu onarmak için, sabiti yalnızca bir kez tanımlayın veya **`enum class`** sabitleri ayırt etmek için ad alanları veya tanımlar kullanın.

- Bu hata, GUID 'Leri tanımlayan diğer. lib dosyalarıyla birlikte UUID. lib kullandığınızda ortaya çıkabilir (örneğin, OLEDB. lib ve adsiid. lib). Örneğin:

    ```Output
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject
    already defined in uuid.lib(go7.obj)
    ```

   Bu sorunu onarmak için, bağlayıcı komut satırı seçeneklerine [/Force: MULTIPLE](../../build/reference/force-force-file-output.md) ekleyin ve UUID. lib ' in başvurulan ilk kitaplık olduğundan emin olun.
