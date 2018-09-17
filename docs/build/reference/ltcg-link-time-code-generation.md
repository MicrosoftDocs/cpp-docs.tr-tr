---
title: / LTCG (bağlama zamanı kodu oluşturma) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
dev_langs:
- C++
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e60bb086adbb1c573b21cafb54c61203c888e9a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725180"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (Bağlama Zamanı Kodu Oluşturma)

Kullanım **/LTCG** tüm programı iyileştirme gerçekleştirmek için veya profil temelli iyileştirme (PGO) araçları, eğitim gerçekleştirmek, oluşturup profil temelli oluşturmak en iyi duruma getirilmiş derlemeleri.

## <a name="syntax"></a>Sözdizimi

> **/ LTCG**[**:**{**ARTIMLI**|**NOSTATUS**|**DURUMU** | **OFF**}]<br/>

Bu seçenekler, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır:

> **/ LTCG:**{**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>Arguments

**ARTIMLI**<br/>
(İsteğe bağlı) Bağlayıcı yalnızca bütün program iyileştirmesi veya bağlama sırasında kod oluşturma (LTCG) projenin tamamı yerine bir düzenleme tarafından etkilenen dosya kümesi için geçerli olduğunu belirtir. Varsayılan olarak, ne zaman bu bayrağı ayarlanmamış **/LTCG** belirtilen ve tüm proje bütün program iyileştirmesi kullanarak bağlanır.

**NOSTATUS** &AMP;#124; **DURUMU**<br/>
(İsteğe bağlı) Bağlayıcı bağlantıyı yüzde tamamlandıktan gösteren bir İlerleme göstergesi görüntülenip görüntülenmeyeceğini belirtir. Varsayılan olarak, bu durum bilgisi görüntülenmez.

**KAPALI**<br/>
(İsteğe bağlı) Bağlama zamanı kod oluşturmayı devre dışı bırakır. Bu ne zaman aynı, davranıştır **/LTCG** komut satırında belirtilmemiş.

**PGINSTRUMENT**<br/>
(İsteğe bağlı) Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, **/LTCG** ve [/genprofıle veya fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) profil temelli iyileştirme için izleme eklenmiş bir yapı oluşturmak için. İzleme eklenmiş çalıştırmalardan toplanan veriler, iyileştirilmiş görüntü oluşturmak için kullanılır. Daha fazla bilgi için [profil temelli iyileştirme](profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGI**.

**PGOPTIMIZE**<br/>
(İsteğe bağlı) Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, **/LTCG** ve [/USEPROFILE](useprofile.md) iyileştirilmiş görüntü oluşturmak için. Daha fazla bilgi için [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGO**.

**PGUPDATE**<br/>
(İsteğe bağlı) Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, **/LTCG** ve **/USEPROFILE** en iyi duruma getirilmiş bir görüntüsünü yeniden oluşturmak için. Daha fazla bilgi için [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGU**.

## <a name="remarks"></a>Açıklamalar

**/LTCG** seçeneği bağlayıcıya derleyici çağırın ve bütün program iyileştirmesi gerçekleştirme. Bunu da yapabilirsiniz profil temelli iyileştirme. Daha fazla bilgi için [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md).

Aşağıdaki istisnalar, bağlayıcı seçenekleri için PGO birleşimi ekleyemezsiniz **/LTCG** ve **/USEPROFILE** önceki PGO başlatma birleşimi içinde belirtilmemiş  **/ LTCG** ve **/genprofıle** seçenekleri:

- [/ BASE](../../build/reference/base-base-address.md)

- [/ FIXED](../../build/reference/fixed-fixed-base-address.md)

- **/LTCG**

- [/MAP](../../build/reference/map-generate-mapfile.md)

- [/ MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)

- [/ NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)

- [/ OUT](../../build/reference/out-output-file-name.md)

- [/ PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)

- [/PDB](../../build/reference/pdb-use-program-database.md)

- [/ PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)

- [/ STUB](../../build/reference/stub-ms-dos-stub-file-name.md)

- [/ VERBOSE](../../build/reference/verbose-print-progress-messages.md)

İle birlikte belirtilen herhangi bir bağlayıcı seçenekleri **/LTCG** ve **/genprofıle** PGO başlatmak için seçenekleri kullanarak oluşturduğunuzda belirtilmesi gerekmez **/LTCG** ve **/USEPROFILE**; bunlar kapsanan.

Bu makalenin geri kalanında anlatılmaktadır **/LTCG** açısından bağlama zamanı kodu oluşturma.

**/ LTCG** ile örtük [/GL](../../build/reference/gl-whole-program-optimization.md).

Kullanılarak derlenmiş bir modül iletilmezse, bağlama sırasında kod oluşturma bağlayıcı çağırır **/GL** veya bir MSIL Modülü (bkz [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md)). Açıkça belirtmezseniz **/LTCG** gönderdiğinizde **/GL** veya MSIL modüllerine bağlayıcı sonunda bağlayıcı bunu algılar ve bağlantıyı kullanarak yeniden **/LTCG**. Açıkça belirtmeniz **/LTCG** gönderdiğinizde **/GL** ve MSIL modüllerine bağlayıcı için en hızlı olası performans oluşturun.

Daha hızlı performans için **/LTCG: ARTIMLI**. Bu seçenek yalnızca projenin tamamı yerine bir kaynak dosya değişikliği etkilenen dosya kümesini yeniden iyileştirmek için söyler. Bu durum, gerekli bağlantı süresi önemli ölçüde azaltabilir. Bu, artımlı bağlamayı olarak aynı seçenek değildir.

**/ LTCG** ile kullanım için geçerli değil [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md).

Zaman **/LTCG** kullanılarak derlenmiş modüller bağlantı için kullanılan [/Og](../../build/reference/og-global-optimizations.md), [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), veya [/Ox](../../build/reference/ox-full-optimization.md), Aşağıdaki en iyi duruma getirme gerçekleştirilir:

- Çapraz-modül inlining'i

- İnterprocedural yazmaç ayırma (yalnızca 64 bit işletim sistemleri)

- Özel çağırma kuralı (yalnızca x86)

- Küçük TLS öteleme (yalnızca x86)

- Yığın çift hizalama (yalnızca x86)

- Geliştirilmiş bellek Kesinleştirme (Genel değişkenler ve giriş parametreleri için daha iyi girişim bilgileri)

> [!NOTE]
> Bağlayıcı, her işlevin derlemek için hangi iyileştirmeleri kullanılan belirler ve bağlantı zamanında aynı iyileştirmeleri uygular.

Kullanarak **/LTCG** ve **/Ogt** çift hizalama iyileştirme neden olur.

Varsa **/LTCG** ve **/Ogs** belirtilirse, çift hizalama gerçekleştirilmez. Bir uygulamada işlevlerin çoğunu hız, boyutu için derlenmiş birkaç işlevleri ile derlenir, (kullanarak örneğin, [en iyi duruma getirme](../../preprocessor/optimize.md) pragma), derleyici çift bunlar çağırırsanız, boyutu için iyileştirilen işlevleri hizalar çift hizalama gerektiren işlevleri.

Derleyicinin tüm işlev çağrı sitelerini mevcutsa, derleyici bir işlevi açıkça çağırma kuralı değiştiricisi var yoksayar ve işlev çağırma kuralı iyileştirmek çalışır:

- yazmaçlarda Parametreler

- hizalama için parametreleri yeniden Sırala

- kullanılmayan parametreleri Kaldır

Bir işlev işaretçisi çağrılan bir işlev veya bir işlev kullanılarak derlenmiş bir modül dışında çağrılır **/GL**, derleyici işlev çağırma kuralı iyileştirmek çalışmaz.

> [!NOTE]
> Kullanırsanız **/LTCG** ve bulunabileceğini `mainCRTStartup`, uygulamanızın genel nesneler başlatılmadan önce yürüten kullanıcı kodu ilişkili öngörülemeyen davranışlara sahip olabilir. Bu sorunu gidermek için üç yolu vardır: değil bulunabileceğini `mainCRTStartup`, içeren dosyayı derlenmiyor `mainCRTStartup` kullanarak **/LTCG**, veya statik olarak genel değişkenleri ve nesneleri başlatılamadı.

### <a name="ltcg-and-msil-modules"></a>/ LTCG ve MSIL modülleri

Kullanılarak derlenmiş modüller [/GL](../../build/reference/gl-whole-program-optimization.md) ve [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) bağlayıcı giriş olarak kullanılabilir olduğunda **/LTCG** belirtilir.

- **/ LTCG** yerel nesne dosyaları kabul edebilir ve karma yerel/Yönetilen Nesne dosyaları (kullanılarak derlenmiş **/CLR**). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

- **/LTCG:PGI** kullanılarak derlenmiş yerel modülleri kabul etmiyor **/GL** ve   **/CLR**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Bkz: [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **genel** özellik sayfası.

1. Değiştirme **tüm Program iyileştirmesi** özelliği.

Ayrıca uygulayabilirsiniz **/LTCG** seçerek belirli derlemelerde **derleme** > **profil temelli iyileştirme** profili birini seçerek veya menü çubuğunda Proje için kısayol menüsündeki Kılavuzlu iyileştirme seçenekleri.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
