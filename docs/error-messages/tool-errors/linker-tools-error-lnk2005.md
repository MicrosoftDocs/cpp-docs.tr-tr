---
title: "Bağlayıcı araçları hatası LNK2005 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2005
dev_langs: C++
helpviewer_keywords: LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69b5201c3e035d1c0aca0105c136766eba3786f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2005"></a>Bağlayıcı Araçları Hatası LNK2005
*Sembol* nesnesinde zaten tanımlı  
  
Simgenin *simgesi* birden çok kez tanımlandı.   
  
Bu hata önemli hatası tarafından izlenir [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).  
  
### <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler  
  
Genellikle, bu hata, bozuk anlamına gelir *bir tanım kuralını*, böylece kullanılan şablon, işlevi, tür veya belirli nesne dosyası nesnesinde için yalnızca bir tanım ve yalnızca tek bir tanım tüm yürütülebilir dosyası arasında dışarıdan görünür nesneleri veya işlevleri.  
  
Bu hata için bazı yaygın nedenler şunlardır.  
  
-   Üstbilgi dosyası bir değişken tanımladığında bu hata oluşabilir. Projenizde birden fazla kaynak dosyasında bu üst bilgi dosyasını dahil ederseniz, örneğin, bir hata oluşur:  
  
    ```h  
    // LNK2005_global.h  
    int global_int;  // LNK2005
    ```  
  
    Olası çözümleri şunlardır:  
  
    -   Değişken bildirme `extern` üstbilgi dosyasında: `extern int global_int;`, sonra tanımlayın ve isteğe bağlı olarak tek bir kaynak dosyasında başlatılamıyor: `int global_int = 17;`. Bu artık genel bir değişkendir bildirme tarafından herhangi bir kaynak dosyada kullanabilirsiniz `extern`, örneğin, üst bilgi dosyasını dahil. Genel değişkenler için bu çözüm öneririz, ancak genel değişkenler iyi yazılım mühendislik yöntem en aza indirir.  
    
    -   Değişken bildirme [statik](../../cpp/storage-classes-cpp.md#static): `static int static_int = 17;`. Bu, geçerli nesne dosyası tanımına kapsamını sınırlar ve değişkeni kendi kopyasına sahip birden çok nesne dosyaları sağlar. Biz, olası Karışıklığı önlemek için genel değişkenleri ile nedeniyle üstbilgi dosyalarında statik değişkenleri tanımlayın önerilmez. Statik değişken tanımları, bunları kullanan kaynak dosyalarıyla taşımak tercih edilir.  
  
    -   Değişken bildirme [selectany](../../cpp/selectany.md): `__declspec(selectany) int global_int = 17;`. Bu, tüm dış başvurular kullanmak için bir tanım seçin ve rest atmak için bağlayıcı bildirir. Bu çözüm, bazen içeri aktarma kitaplıkları birleştirilirken yararlıdır. Aksi takdirde, bağlayıcı hatalarını önlemek için bir yol önermiyoruz.  
  
-   Üstbilgi dosyası olmayan bir işlev tanımladığında bu hata oluşabilir `inline`. Birden fazla kaynak dosyasında bu üst bilgi dosyasını dahil ederseniz, yürütülebilir dosya işlevinin birden çok tanımlarını alın.  
    
    ```h  
    // LNK2005_func.h  
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```  
  
    Olası çözümleri şunlardır:  
  
    -   Ekleme `inline` anahtar sözcüğü işlevi için: 

        ```h  
        // LNK2005_func_inline.h  
        inline int sample_function(int k) { return 42 * (k % 167); }  
        ```  
  
    -   İşlev gövdesi üstbilgi dosyadan kaldırın ve yalnızca bildirimi bırakın, ardından tek bir kaynak dosyasında işlevi uygulamak:  
  
        ```h  
        // LNK2005_func_decl.h  
        int sample_function(int);  
        ```  
  
        ```cpp  
        // LNK2005_func_impl.cpp  
        int sample_function(int k) { return 42 * (k % 167); }  
        ```  
-   Üye işlevleri sınıf bildiriminin dışında bir üst bilgi dosyasını tanımlayın. Bu hata ayrıca ortaya çıkabilir:  
  
    ```h  
    // LNK2005_member_outside.h  
    class Sample {
    public:
        int sample_function(int);  
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```  
  
    Bu sorunu gidermek için sınıf içinde üye işlev tanımları taşıyın. Sınıf bildirimi içinde tanımlanan üye işlevleri örtük olarak içermesinden.  
  
    ```h  
    // LNK2005_member_inline.h  
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }  
    };
    ```  
  
-   CRT ve standart kitaplığı birden fazla sürümünü bağlarsanız, bu hata oluşabilir. Örneğin, hem Perakende ve hata ayıklama CRT kitaplıkları veya bir kitaplık statik ve dinamik sürümleri veya standart kitaplığı iki farklı sürümü yürütülebilir dosyaya bağlantı çalışırsanız, bu hatanın birçok kez bildirilebilir. Bu sorunu gidermek için bağlantı komuttan her kitaplık biri hariç tüm kopyasını kaldırın. Perakende karıştırmak ve kitaplıkları veya farklı bir kitaplıkta aynı yürütülebilir dosya sürümlerini hata ayıklama önermiyoruz.  
  
    Komut satırında kitaplıkları Varsayılanları dışında kullanmak için bağlayıcı bildirmek için ve kullanmak kitaplıkları belirtin [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) varsayılan kitaplıkları devre dışı bırakma seçeneği. IDE içinde başvuruları kullanın ve sonra açmak için kitaplıkları belirtmek için projenize eklemek **özellik sayfaları** iletişim ve projeniz için **bağlayıcı**, **giriş** özelliği sayfasında, ya da ayarlamak **tüm varsayılan kitaplıkları Yoksay**, veya **belirli varsayılan kitaplıkları Yoksay** varsayılan kitaplıkları devre dışı bırakmak için özellikler.   
  
-   Bu hata kullandığınızda statik ve dinamik kitaplıkları kullanımını karışık oluşabilir [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği. Örneğin, statik CRT'deki bağlanan bir DLL kullanmak için yürütülebilir dosya olarak oluşturursanız bu hata oluşabilir. Bu sorunu gidermek için yalnızca statik kitaplıklar veya yalnızca dinamik kitaplıkları yürütülebilir tüm ve yürütülebilir dosya kullanmak için yapı kitaplıkları için kullanın.  
  
-   Simge paketlenmiş işlevi ise bu hata oluşabilir (ile derleme tarafından oluşturulan [/Gy](../../build/reference/gy-enable-function-level-linking.md)) ve birden fazla dosyada eklenmiştir, ancak derlemeleri arasında değiştirildi. Bu sorunu gidermek için paketlenmiş işlevini içeren tüm dosyaları yeniden derleyin.  
  
-   Simgenin farklı iki üye nesneler farklı kitaplıklarında tanımlanır ve her iki üye nesneleri kullanılır bu hata oluşabilir. Kitaplıkları statik olarak bağlantılı olduğunda bu sorunu çözmenin bir yolu üye nesne yalnızca bir kitaplıktan, bu kitaplığın ilk bağlayıcı komut satırında dahil kullanmaktır. Her iki simge kullanmak için bunları ayırt etmek için bir yol oluşturmanız gerekir. Örneğin, kaynak kitaplıklarından oluşturabilirsiniz, benzersiz bir ad alanı her kitaplıkta kayabilir. Alternatif olarak, özgün kitaplıklarından birini başvurular sarmalama, özgün kitaplık için yeni kitaplık bağlama ve ardından yeni kitaplığınızın özgün kitaplık yerine yürütülebilir bağlamak için benzersiz adlar kullanan yeni bir sarmalayıcı kitaplık oluşturabilirsiniz.  
  
-   Bu hata oluşabilir bir `extern const` değişkeni iki kez tanımlanmış ve her tanımı farklı bir değer içeriyor. Bu sorunu gidermek için sabit yalnızca bir kez tanımlayın veya ad alanları kullanın veya `enum class` sabitleri ayırt etmek için tanımlar.  
  
-   Uuid.lib GUID'ler (örneğin, oledb.lib ve adsiid.lib) tanımlayan diğer .lib dosyaları ile birlikte kullanıyorsanız, bu hata oluşabilir. Örneğin:  
  
    ```Output  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     Bu sorunu gidermek için ekleme [/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md) bağlayıcı komut satırı seçenekleri ve emin olun, uuid.lib başvurulan ilk kitaplığıdır.
  
## <a name="additional-information"></a>Ek bilgiler  
  
Araç takımı eski bir sürümünü kullanıyorsanız, bu Bilgi Bankası makaleleri belirli bu hatanın nedeni hakkında daha fazla bilgi için bkz:  
  
-   [MFC kitaplıkları ve CRT kitaplık Visual C++ yanlış sırayla bağlantılı bir LNK2005 hata oluşur.](https://support.microsoft.com/kb/148652)  
  
-   [Düzeltme: Genel aşırı yüklenmiş Delete işleci nedenler LNK2005](https://support.microsoft.com/kb/140440)  
  
-   [Visual c++ ATL yürütülebilir dosyanın (.exe) projesinde derlediğinizde LNK2005 hataları alırsınız](https://support.microsoft.com/kb/184235).  
  
