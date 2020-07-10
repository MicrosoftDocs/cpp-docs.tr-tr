---
title: /LTCG (Bağlama zamanı kodu üretme)
description: MSVC bağlayıcı seçeneği/LTCG, tüm program iyileştirmesi için bağlantı zamanı kod oluşturmayı mümkün hale getirmenizi.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
ms.openlocfilehash: c954794d6d0fd087eee74ebb7e86d77b89a9a8fc
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180805"
---
# <a name="ltcg-link-time-code-generation"></a>`/LTCG`(Bağlama zamanı kodu oluşturma)

**`/LTCG`** Tam program iyileştirmesi gerçekleştirmek veya profil temelli iyileştirme (PGO) araçları oluşturmak, eğitim gerçekleştirmek ve profil temelli iyileştirilmiş derlemeler oluşturmak için kullanın.

## <a name="syntax"></a>Sözdizimi

> **`/LTCG`**[**`:`**{**`INCREMENTAL`**|**`NOSTATUS`**|**`STATUS`**|**`OFF`**}]

Bu seçenekler, Visual Studio 2015 ' den itibaren kullanım dışıdır:

> **`/LTCG:`**{**`PGINSTRUMENT`**|**`PGOPTIMIZE`**|**`PGUPDATE`**}

### <a name="arguments"></a>Arguments

**`INCREMENTAL`**<br/>
Seçim Bağlayıcının tüm proje iyileştirme veya bağlantı zamanı kodu oluşturma (LTCG) öğesinin tamamı yerine bir düzenleme tarafından etkilenen dosyalara uygulandığını belirtir. Varsayılan olarak, bu bayrak **`/LTCG`** belirtildiğinde ayarlanır ve tüm proje, tüm program iyileştirmesi kullanılarak bağlanır.

**`NOSTATUS`**&#124;**`STATUS`**<br/>
Seçim Bağlayıcının bağlantının yüzdesini gösteren bir ilerleme göstergesi görüntüleyip görüntülemediğini belirtir. Varsayılan olarak, bu durum bilgileri gösterilmez.

**`OFF`**<br/>
Seçim Bağlama sırasında kod oluşturmayı devre dışı bırakır. Bu davranış, **`/LTCG`** komut satırında belirtilmediğinde ile aynıdır.

**`PGINSTRUMENT`**<br/>
Seçim Bu seçenek, Visual Studio 2015 ' den itibaren kullanım dışıdır. Bunun yerine, **`/LTCG`** `[/GENPROFILE` Profil temelli `/FASTGENPROFILE` iyileştirme için bir belgelenmiş derleme oluşturmak üzere ve veya] (genprofile-fastgenprofile-Generate-profiling-instrumented-Build.MD) kullanın. Belgelenmiş çalışmalardan toplanan veriler, iyileştirilmiş bir görüntü oluşturmak için kullanılır. Daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](../profile-guided-optimizations.md). Bu seçeneğin kısa biçimi, **`/LTCG:PGI`** .

**`PGOPTIMIZE`**<br/>
Seçim Bu seçenek, Visual Studio 2015 ' den itibaren kullanım dışıdır. Bunun yerine, **`/LTCG`** [`/USEPROFILE`](useprofile.md) en iyi duruma getirilmiş bir görüntü oluşturmak için ve kullanın. Daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](../profile-guided-optimizations.md). Bu seçeneğin kısa biçimi, **`/LTCG:PGO`** .

**`PGUPDATE`**<br/>
Seçim Bu seçenek, Visual Studio 2015 ' den itibaren kullanım dışıdır. Bunun yerine, **`/LTCG`** **`/USEPROFILE`** iyileştirilmiş bir görüntüyü yeniden derlemek için ve kullanın. Daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](../profile-guided-optimizations.md). Bu seçeneğin kısa biçimi, **`/LTCG:PGU`** .

## <a name="remarks"></a>Açıklamalar

**`/LTCG`** Seçeneği bağlayıcının derleyiciye çağrı yapmasını ve tam program iyileştirmesi gerçekleştirmesini söyler. Profil temelli iyileştirme de yapabilirsiniz. Daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](../profile-guided-optimizations.md).

Aşağıdaki özel durumlarla birlikte bağlayıcı seçeneklerini, ve **`/LTCG`** **`/USEPROFILE`** seçeneklerinin önceki PGO başlatma birleşimine belirtilmeyen ve ' ın PGO birleşimine ekleyemezsiniz **`/LTCG`** **`/GENPROFILE`** :

- [`/BASE`](base-base-address.md)

- [`/FIXED`](fixed-fixed-base-address.md)

- **`/LTCG`**

- [`/MAP`](map-generate-mapfile.md)

- [`/MAPINFO`](mapinfo-include-information-in-mapfile.md)

- [`/NOLOGO`](nologo-suppress-startup-banner-linker.md)

- [`/OUT`](out-output-file-name.md)

- [`/PGD`](pgd-specify-database-for-profile-guided-optimizations.md)

- [`/PDB`](pdb-use-program-database.md)

- [`/PDBSTRIPPED`](pdbstripped-strip-private-symbols.md)

- [`/STUB`](stub-ms-dos-stub-file-name.md)

- [`/VERBOSE`](verbose-print-progress-messages.md)

**`/LTCG`** **`/GENPROFILE`** Ve kullanarak oluşturduğunuzda, PGO 'yu başlatmak için ve seçenekleriyle birlikte belirtilen tüm bağlayıcı seçeneklerinin belirtilmesi gerekmez **`/LTCG`** **`/USEPROFILE`** ; ancak bunlar kapsanıyor.

Bu makalenin geri kalanında, tarafından gerçekleştirilen bağlantı zamanı kod üretimi ele alınmaktadır **`/LTCG`** .

**`/LTCG`**, ile birlikte kapsanıyor [`/GL`](gl-whole-program-optimization.md) .

Bağlayıcı, veya MSIL Modülü kullanılarak derlenen bir modül geçirildiğinde bağlantı sırasında kod oluşturmayı çağırır **`/GL`** (bkz. [ `.netmodule` dosyaları bağlayıcı girişi olarak](netmodule-files-as-linker-input.md)görüntüle). **`/LTCG`** Bağlayıcıya bir veya MSIL modülleri geçirdiğinizde açıkça belirtmezseniz **`/GL`** , bağlayıcı sonunda bu durumu algılar ve kullanarak bağlantıyı yeniden başlatır **`/LTCG`** . Mümkün olan **`/LTCG`** **`/GL`** en hızlı yapı performansına yönelik olarak BAĞLAYıCıYA ve MSIL modüllerini bağlayıcıya geçirdiğinizde belirtin.

Daha da hızlı performans için kullanın **`/LTCG:INCREMENTAL`** . Bu seçenek, bağlayıcının tüm proje yerine yalnızca kaynak dosya değişikliğinden etkilenen dosyaları yeniden iyileştirmasını söyler. Bu seçenek, gereken bağlantı süresini önemli ölçüde azaltabilir. Bu seçenek [artımlı bağlama](incremental-link-incrementally.md)ile aynı seçenek değildir.

**`/LTCG`** ile kullanım için geçerli değildir [`/INCREMENTAL`](incremental-link-incrementally.md) .

**`/LTCG`**,, Veya kullanılarak derlenen modülleri bağlamak için kullanıldığında [`/Og`](og-global-optimizations.md) [`/O1`](o1-o2-minimize-size-maximize-speed.md) [`/O2`](o1-o2-minimize-size-maximize-speed.md) [`/Ox`](ox-full-optimization.md) , aşağıdaki iyileştirmeler gerçekleştirilir:

- Modüller arası satır içi

- Interyordamla kayıt ayırma (yalnızca 64 bitlik işletim sistemleri)

- Özel çağırma kuralı (yalnızca x86)

- Küçük TLS değiştirme (yalnızca x86)

- Yığın çift hizalaması (yalnızca x86)

- İyileştirilmiş bellek Kesinleştirme (genel değişkenler ve giriş parametreleri için daha iyi girişim bilgileri)

> [!NOTE]
> Bağlayıcı, her işlevi derlemek için hangi iyileştirmelerin kullanıldığını belirler ve bağlantı zamanında aynı iyileştirmeleri uygular.

**`/LTCG`**' I kullanarak **`/O2`** çift hizalama iyileştirmesine neden olur.

**`/LTCG`** Ve **`/O1`** belirtilirse, çift hizalama yapılmaz. Bir uygulamadaki işlevlerin çoğu hız için derlenirse (örneğin, pragma kullanılarak), boyut için derlenmiş birkaç işlev ile [`optimize`](../../preprocessor/optimize.md) derleyici, çift hizalama gerektiren işlevleri çağırdıklarında boyut için iyileştirilmiş işlevleri çift hizalar.

Derleyici bir işlevin tüm çağrı sitelerini tanımlayabiliyorsanız, derleyici bir işlev üzerinde açık çağırma kuralı değiştiricilerini yoksayar ve işlevin çağırma kuralını iyileştirmenize çalışır:

- kayıtlarda parametreleri geçirme

- hizalama için parametreleri yeniden sırala

- Kullanılmayan parametreleri Kaldır

Bir işlev bir işlev işaretçisi aracılığıyla çağrılırsa veya bir işlev kullanılarak derlenen bir modülün dışından çağrılırsa, **`/GL`** derleyici işlevin çağırma kuralını en iyi hale getirmeyi denemez.

> [!NOTE]
> **`/LTCG`** Ve yeniden tanımlama kullanırsanız `mainCRTStartup` , uygulamanız genel nesneler başlatılmadan önce yürütülen Kullanıcı koduyla ilişkili öngörülemeyen davranışlara sahip olabilir. Bu sorunu gidermek için üç yol vardır: ' i yeniden tanımlama `mainCRTStartup` , kullanarak içeren dosyayı derleme `mainCRTStartup` **`/LTCG`** veya genel değişkenleri ve nesneleri statik olarak başlatma.

### <a name="ltcg-and-msil-modules"></a>`/LTCG`ve MSIL modülleri

Ve kullanılarak derlenen modüller [`/GL`](gl-whole-program-optimization.md) [`/clr`](clr-common-language-runtime-compilation.md) , belirtildiğinde bağlayıcı için giriş olarak kullanılabilir **`/LTCG`** .

- **`/LTCG`** yerel nesne dosyalarını ve karma yerel/yönetilen nesne dosyalarını kabul edebilir (kullanılarak derlenir **`/clr`** ). **`/clr:pure`** Ve **`/clr:safe`** derleyici seçenekleri visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ve sonrasında desteklenmez.

- **`/LTCG:PGI`** ve kullanılarak derlenen yerel modülleri kabul etmez **`/GL`****`/clr`**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **genel** özellik sayfasını seçin.

1. **Tüm program iyileştirme** özelliğini değiştirin.

Ayrıca **`/LTCG`** **Build**  >  , menü çubuğunda**Profil temelli iyileştirme** oluştur ' u seçerek veya projenin kısayol menüsündeki profil temelli iyileştirme seçeneklerinden birini seçerek belirli yapılar için de uygulayabilirsiniz.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)\
[MSVC bağlayıcı seçenekleri](linker-options.md)
