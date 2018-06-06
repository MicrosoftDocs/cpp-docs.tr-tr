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
ms.openlocfilehash: dc4266e8b01201226c53584bed9f90ed9dcabef7
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703739"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (Bağlama Zamanı Kodu Oluşturma)

Kullanım **/LTCG** bütün program iyileştirmesi gerçekleştirmek için veya profil temelli iyileştirme (PGO) araçları oluşturmak, eğitim gerçekleştirmek ve profil temelli oluşturmak için en iyi duruma getirilmiş derlemeleri.

## <a name="syntax"></a>Sözdizimi

> **/ LTCG**[**:**{**ARTIMLI**|**NOSTATUS**|**DURUM** | **OFF**}]<br/>

Bu seçenekler, Visual Studio 2015'te itibaren kullanım dışıdır:

> **/ LTCG:**{**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>Arguments

**ARTIMLI** (isteğe bağlı)<br/>
Bağlayıcı yalnızca bütün program iyileştirmesi veya bağlama zamanı kodu oluşturma (LTCG) tüm proje yerine bir düzen etkilenen dosyalar kümesine uygulanacağını belirtir. Varsayılan olarak, ne zaman bu bayrağı ayarlanmamış **/LTCG** belirtilirse, ve tüm proje bütün program iyileştirmesi kullanarak bağlanır.

**NOSTATUS** &#124; **durum** (isteğe bağlı)<br/>
Bağlayıcı bağlantıyı yüzdesini tamamlandıktan gösteren bir İlerleme göstergesi görüntülenip görüntülenmeyeceğini belirtir. Varsayılan olarak, bu durum bilgisi görüntülenmez.

**Devre dışı** (isteğe bağlı)<br/>
Bağlama zamanı kodu oluşturma devre dışı bırakır. Bu davranış ne zaman aynıdır **/LTCG** komut satırında belirtilmemiş.

**PGINSTRUMENT** (isteğe bağlı)<br/>
Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, kullanın **/LTCG** ve [/GENPROFILE veya /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) profil temelli iyileştirme için izleme eklenmiş bir yapı oluşturmak için. İzleme eklenmiş kaynak dosyadan toplanan veriler, en iyi duruma getirilmiş bir görüntü oluşturmak için kullanılır. Daha fazla bilgi için bkz: [profil temelli iyileştirme](profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGI**.

**PGOPTIMIZE** (isteğe bağlı)<br/>
Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, kullanın **/LTCG** ve [/USEPROFILE](useprofile.md) en iyi duruma getirilmiş bir görüntü oluşturmak için. Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGO**.

**PGUPDATE** (isteğe bağlı)<br/>
Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, kullanın **/LTCG** ve **/USEPROFILE** en iyi duruma getirilmiş bir görüntü yeniden oluşturma. Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGU**.

## <a name="remarks"></a>Açıklamalar

**/LTCG** seçenek derleyici çağırın ve bütün program iyileştirmesi gerçekleştirme bağlayıcı söyler. Ayrıca yapabilirsiniz profil temelli iyileştirme. Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md).

Aşağıdaki istisnalar PGO bileşimi için bağlayıcı seçenekleri ekleyemezsiniz **/LTCG** ve **/USEPROFILE** önceki PGO başlatma birleşimi içinde belirtilmemiş  **/ LTCG** ve **/GENPROFILE** seçenekleri:

- [/ BASE](../../build/reference/base-base-address.md)

- [/ SABİT](../../build/reference/fixed-fixed-base-address.md)

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

İle birlikte belirtilen herhangi bir bağlayıcı seçenekleri **/LTCG** ve **/GENPROFILE** PGO başlatmak için seçenekleri kullanarak oluşturduğunuzda belirtilmesi gerekmez **/LTCG** ve **/USEPROFILE**; bunlar kapsanan.

Bu makalenin geri kalanında anlatılmaktadır **/LTCG** bağlama zamanı kodu oluşturma bakımından.

**/ LTCG** ile kapsanan [/GL](../../build/reference/gl-whole-program-optimization.md).

Kullanarak derlenen bir modül aktarılırsa bağlama zamanı kodu oluşturma bağlayıcı çağırır **/GL** veya bir MSIL Modülü (bkz [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md)). Açıkça belirtmezseniz **/LTCG** geçirdiğiniz zaman **/GL** veya bağlayıcı, bağlayıcı sonunda MSIL modüllerle bunu algılar ve bağlantıyı kullanarak yeniden **/LTCG**. Açıkça belirtmek **/LTCG** geçirdiğiniz zaman **/GL** ve hızlı olası bağlayıcı için MSIL modüller yapı performans.

Daha hızlı performans için kullanmak **/LTCG: ARTIMLI**. Bu seçenek, yalnızca tüm proje yerine bir kaynak dosya değişikliği etkilenen dosyaları kümesini yeniden iyileştirmek için bağlayıcı söyler. Bu, gerekli bağlantı süresi önemli ölçüde azaltabilir. Artımlı bağlantılandırma olarak aynı seçeneği değil.

**/ LTCG** ile kullanım için geçerli değil [/ARTIMLI](../../build/reference/incremental-link-incrementally.md).

Zaman **/LTCG** kullanarak derlenmiş modüller bağlamak için kullanılan [/Og](../../build/reference/og-global-optimizations.md), [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), veya [/Ox](../../build/reference/ox-full-optimization.md), Aşağıdaki en iyi duruma getirme gerçekleştirilir:

- Çapraz modülü satır içi kullanım

- İnterprocedural yazmaç ayırma (yalnızca 64-bit işletim sistemleri)

- Özel çağırma kuralı (yalnızca x86)

- Küçük TLS öteleme (yalnızca x86)

- Yığın çift hizalama (yalnızca x86)

- Geliştirilmiş bellek Kesinleştirme (Genel değişkenler ve giriş parametreleri için daha iyi girişim bilgileri)

> [!NOTE]
> Bağlayıcı hangi iyileştirmeleri her işlevi derlemek için kullanılan belirler ve bağlantı aynı anda aynı iyileştirmeler uygular.

Kullanarak **/LTCG** ve **/Ogt** çift hizalama iyileştirme neden olur.

Varsa **/LTCG** ve **/Ogs** belirtilirse, çift hizalama gerçekleştirilmez. Bir uygulamada işlevlerin çoğunu boyutu için derlenmiş birkaç işlevlerle hızı için derlenmiş varsa (kullanarak örneğin, [en iyi duruma getirme](../../preprocessor/optimize.md) pragma), derleyici çift bunlar çağırırsanız boyutu için iyileştirilmiş işlevleri hizalar çift hizalama gerektiren işlevleri.

Derleyici işlev çağrısı siteleri belirleyebiliyorsanız derleyici bir işlev açık çağırma kuralı değiştiricileri yoksayar ve işlev çağırma iyileştirmek çalışır:

- Yazmaçları Parametreler

- hizalama için parametreleri yeniden Sırala

- kullanılmayan parametrelerini kaldırın

Bir işlev işaretçisi bir işlevi çağrıldıysa ya da bir işlevi kullanarak derlenmiş bir modül dışında çağrılır **/GL**, derleyici işlevin çağırma iyileştirmek çalışmaz.

> [!NOTE]
> Kullanırsanız **/LTCG** ve yeniden tanımlamanız `mainCRTStartup`, uygulamanızın genel nesneler başlatılmış önce yürütülen kullanıcı kodu için ilgili beklenmeyen davranışlara sahip olabilir. Bu sorunu gidermek için üç yolu vardır: değil yeniden tanımlamanız `mainCRTStartup`, içeren dosyası derleme değil `mainCRTStartup` kullanarak **/LTCG**, veya genel değişkenler ve nesneleri statik olarak başlatılamadı.

### <a name="ltcg-and-msil-modules"></a>/ LTCG ve MSIL modülleri

Kullanarak derlenmiş modüller [/GL](../../build/reference/gl-whole-program-optimization.md) ve [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) bağlayıcı girişi olarak kullanılabilir olduğunda **/LTCG** belirtilir.

- **/ LTCG** yerel nesne dosyaları kabul edebilir ve karışık yerel/Yönetilen Nesne dosyaları (kullanarak derlenmiş **/CLR**). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

- **/LTCG:PGI** kullanarak derlenmiş yerel modülleri kabul etmiyorum **/GL** ve   **/CLR**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açın **özellik sayfaları** iletişim kutusu. Bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **genel** özellik sayfası.

1. Değiştirme **bütün Program iyileştirmesi** özelliği.

Ayrıca uygulayabilirsiniz **/LTCG** seçerek belirli derlemeleri için **yapı** > **profil temelli iyileştirme** menü çubuğunda ya da bir profil seçme Projesi için kısayol menüsünde destekli en iyi duruma getirme seçenekleri.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
