---
title: /LTCG (Bağlama Zamanı Kodu Üretme)
ms.date: 03/14/2018
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
ms.openlocfilehash: 40fb591952180735de3a2c226a3953a303c7d90f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810321"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (Bağlama Zamanı Kodu Üretme)

Kullanım **/LTCG** tüm programı iyileştirme gerçekleştirmek için veya profil temelli iyileştirme (PGO) araçları, eğitim gerçekleştirmek, oluşturup profil temelli oluşturmak en iyi duruma getirilmiş derlemeleri.

## <a name="syntax"></a>Sözdizimi

> **/ LTCG**[**:**{**ARTIMLI**|**NOSTATUS**|**DURUMU** | **OFF**}]<br/>

Bu seçenekler, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır:

> **/LTCG:**{**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>Arguments

**ARTIMLI**<br/>
(İsteğe bağlı) Bağlayıcı yalnızca bütün program iyileştirmesi veya bağlama sırasında kod oluşturma (LTCG) projenin tamamı yerine bir düzenleme tarafından etkilenen dosya kümesi için geçerli olduğunu belirtir. Varsayılan olarak, ne zaman bu bayrağı ayarlanmamış **/LTCG** belirtilen ve tüm proje bütün program iyileştirmesi kullanarak bağlanır.

**NOSTATUS** &#124; **STATUS**<br/>
(İsteğe bağlı) Bağlayıcı bağlantıyı yüzde tamamlandıktan gösteren bir İlerleme göstergesi görüntülenip görüntülenmeyeceğini belirtir. Varsayılan olarak, bu durum bilgisi görüntülenmez.

**KAPALI**<br/>
(İsteğe bağlı) Bağlama zamanı kod oluşturmayı devre dışı bırakır. Bu ne zaman aynı, davranıştır **/LTCG** komut satırında belirtilmemiş.

**PGINSTRUMENT**<br/>
(İsteğe bağlı) Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, **/LTCG** ve [/genprofıle veya fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) profil temelli iyileştirme için izleme eklenmiş bir yapı oluşturmak için. İzleme eklenmiş çalıştırmalardan toplanan veriler, iyileştirilmiş görüntü oluşturmak için kullanılır. Daha fazla bilgi için [permutasyonları iyileştirmeleri](../profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGI**.

**PGOPTIMIZE**<br/>
(İsteğe bağlı) Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, **/LTCG** ve [/USEPROFILE](useprofile.md) iyileştirilmiş görüntü oluşturmak için. Daha fazla bilgi için [permutasyonları iyileştirmeleri](../profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGO**.

**PGUPDATE**<br/>
(İsteğe bağlı) Bu seçenek, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır. Bunun yerine, **/LTCG** ve **/USEPROFILE** en iyi duruma getirilmiş bir görüntüsünü yeniden oluşturmak için. Daha fazla bilgi için [permutasyonları iyileştirmeleri](../profile-guided-optimizations.md). Bu seçeneğin kısa form **/LTCG:PGU**.

## <a name="remarks"></a>Açıklamalar

**/LTCG** seçeneği bağlayıcıya derleyici çağırın ve bütün program iyileştirmesi gerçekleştirme. Bunu da yapabilirsiniz profil temelli iyileştirme. Daha fazla bilgi için [permutasyonları iyileştirmeleri](../profile-guided-optimizations.md).

Aşağıdaki istisnalar, bağlayıcı seçenekleri için PGO birleşimi ekleyemezsiniz **/LTCG** ve **/USEPROFILE** önceki PGO başlatma birleşimi içinde belirtilmemiş  **/ LTCG** ve **/genprofıle** seçenekleri:

- [/ BASE](base-base-address.md)

- [/ FIXED](fixed-fixed-base-address.md)

- **/LTCG**

- [/MAP](map-generate-mapfile.md)

- [/ MAPINFO](mapinfo-include-information-in-mapfile.md)

- [/ NOLOGO](nologo-suppress-startup-banner-linker.md)

- [/ OUT](out-output-file-name.md)

- [/ PGD](pgd-specify-database-for-profile-guided-optimizations.md)

- [/PDB](pdb-use-program-database.md)

- [/ PDBSTRIPPED](pdbstripped-strip-private-symbols.md)

- [/ STUB](stub-ms-dos-stub-file-name.md)

- [/ VERBOSE](verbose-print-progress-messages.md)

İle birlikte belirtilen herhangi bir bağlayıcı seçenekleri **/LTCG** ve **/genprofıle** PGO başlatmak için seçenekleri kullanarak oluşturduğunuzda belirtilmesi gerekmez **/LTCG** ve **/USEPROFILE**; bunlar kapsanan.

Bu makalenin geri kalanında anlatılmaktadır **/LTCG** açısından bağlama zamanı kodu oluşturma.

**/ LTCG** ile örtük [/GL](gl-whole-program-optimization.md).

Kullanılarak derlenmiş bir modül iletilmezse, bağlama sırasında kod oluşturma bağlayıcı çağırır **/GL** veya bir MSIL Modülü (bkz [bağlayıcı girişi olarak .netmodule dosyaları](netmodule-files-as-linker-input.md)). Açıkça belirtmezseniz **/LTCG** gönderdiğinizde **/GL** veya MSIL modüllerine bağlayıcı sonunda bağlayıcı bunu algılar ve bağlantıyı kullanarak yeniden **/LTCG**. Açıkça belirtmeniz **/LTCG** gönderdiğinizde **/GL** ve MSIL modüllerine bağlayıcı için en hızlı olası performans oluşturun.

Daha hızlı performans için **/LTCG: ARTIMLI**. Bu seçenek yalnızca projenin tamamı yerine bir kaynak dosya değişikliği etkilenen dosya kümesini yeniden iyileştirmek için söyler. Bu durum, gerekli bağlantı süresi önemli ölçüde azaltabilir. Bu, artımlı bağlamayı olarak aynı seçenek değildir.

**/ LTCG** ile kullanım için geçerli değil [/INCREMENTAL](incremental-link-incrementally.md).

Zaman **/LTCG** kullanılarak derlenmiş modüller bağlantı için kullanılan [/Og](og-global-optimizations.md), [/O1](o1-o2-minimize-size-maximize-speed.md), [/O2](o1-o2-minimize-size-maximize-speed.md), veya [/Ox](ox-full-optimization.md), Aşağıdaki en iyi duruma getirme gerçekleştirilir:

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

Kullanılarak derlenmiş modüller [/GL](gl-whole-program-optimization.md) ve [/CLR](clr-common-language-runtime-compilation.md) bağlayıcı giriş olarak kullanılabilir olduğunda **/LTCG** belirtilir.

- **/ LTCG** yerel nesne dosyaları kabul edebilir ve karma yerel/Yönetilen Nesne dosyaları (kullanılarak derlenmiş **/CLR**). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

- **/LTCG:PGI** kullanılarak derlenmiş yerel modülleri kabul etmiyor **/GL** ve   **/CLR**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Bkz: [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **genel** özellik sayfası.

1. Değiştirme **tüm Program iyileştirmesi** özelliği.

Ayrıca uygulayabilirsiniz **/LTCG** seçerek belirli derlemelerde **derleme** > **profil temelli iyileştirme** profili birini seçerek veya menü çubuğunda Proje için kısayol menüsündeki Kılavuzlu iyileştirme seçenekleri.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
