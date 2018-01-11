---
title: "-LTCG (bağlama zamanı kodu oluşturma) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
dev_langs: C++
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8f1abc58f0c36f37307e1d8053e4dd8a4cac06a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (Bağlama Zamanı Kodu Oluşturma)
```  
/LTCG[:INCREMENTAL|:NOSTATUS|:STATUS|:OFF|:PGINSTRUMENT|:PGOPTIMIZE|:PGUPDATE]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 : ARTIMLI (isteğe bağlı)  
 Bağlayıcı yalnızca bütün program iyileştirmesi veya bağlama zamanı kodu oluşturma (LTCG) tüm proje yerine bir düzen etkilenen dosyalar kümesine uygulanacağını belirtir. Varsayılan olarak, /LTCG belirtilir ve tüm proje bütün program iyileştirmesi kullanarak bağlı olduğunda bu bayrağı ayarlı değil.  
  
 : NOSTATUS &#124; : Durum (isteğe bağlı)  
 Bağlayıcı bağlantıyı yüzdesini tamamlandıktan gösteren bir İlerleme göstergesi görüntülenip görüntülenmeyeceğini belirtir. Varsayılan olarak, bu durum bilgisi görüntülenmez.  
  
 : (İsteğe bağlı) kapalı  
 Bağlama zamanı kodu oluşturma devre dışı bırakır. Bu davranış zaman /LTCG komut satırında belirtilmemiş aynıdır.  
  
 : PGINSTRUMENT (isteğe bağlı)  
 Bu seçeneği kullanım dışıdır. Bunun yerine, kullanın **/LTCG** ve **/GENPROFILE** veya **/FASTGENPROFILE** profil temelli iyileştirme için izleme eklenmiş bir yapı oluşturmak için.  
  
 İzleme eklenmiş kaynak dosyadan toplanan veriler, en iyi duruma getirilmiş bir görüntü oluşturmak için kullanılır. Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md). Kısa bu seçenek /LTCG:PGI biçimidir.  
  
 : PGOPTIMIZE (isteğe bağlı)  
 Bu seçeneği kullanım dışıdır. Bunun yerine, kullanın **/LTCG** ve **/USEPROFILE** en iyi duruma getirilmiş bir görüntü oluşturmak için. Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md). Kısa bu seçenek /LTCG:PGO biçimidir.  
  
 : PGUPDATE (isteğe bağlı)  
 Bu seçeneği kullanım dışıdır. Bunun yerine, kullanın **/LTCG** ve **/USEPROFILE** en iyi duruma getirilmiş bir görüntü oluşturmak için. Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md). Kısa bu seçenek /LTCG:PGU biçimidir.  
  
 /LTCG seçenek derleyici çağırın ve bütün program iyileştirmesi gerçekleştirme bağlayıcı söyler. Ayrıca yapabilirsiniz profil temelli iyileştirme. Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md).  
  
 Aşağıdaki istisnalar /LTCG ve önceki PGO başlatma birlikte /LTCG ve /GENPROFILE seçenekleri belirtilmedi /USEPROFILE PGO birleşimi bağlayıcı seçenekleri ekleyemezsiniz:  
  
-   [/ BASE](../../build/reference/base-base-address.md)  
  
-   [/ SABİT](../../build/reference/fixed-fixed-base-address.md)  
  
-   / LTCG  
  
-   [/ MAP](../../build/reference/map-generate-mapfile.md)  
  
-   [/ MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)  
  
-   [/ NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)  
  
-   [/ OUT](../../build/reference/out-output-file-name.md)  
  
-   [/ PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)  
  
-   [/ PDB](../../build/reference/pdb-use-program-database.md)  
  
-   [/ PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)  
  
-   [/ STUB](../../build/reference/stub-ms-dos-stub-file-name.md)  
  
-   [/ VERBOSE](../../build/reference/verbose-print-progress-messages.md)  
  
 Tüm /LTCG birlikte belirtilen bağlayıcı seçenekleri ve PGO başlatmak için /GENPROFILE seçenekleri /LTCG ve /USEPROFILE kullanarak oluşturduğunuzda belirtilmesi gerekmez; Bunlar uygulanmaktadır.  
  
 Bu konunun geri kalanında /LTCG bağlama zamanı kodu oluşturma bakımından açıklanır.  
  
 / LTCG kapsanan ile [/GL](../../build/reference/gl-whole-program-optimization.md).  
  
 Kullanarak derlenen bir modül aktarılırsa bağlama zamanı kodu oluşturma bağlayıcı çağırır **/GL** veya bir MSIL Modülü (bkz [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md)). Açıkça belirtmezseniz **/LTCG** geçirdiğiniz zaman **/GL** veya bağlayıcı, bağlayıcı sonunda MSIL modüllerle bunu algılar ve bağlantıyı kullanarak yeniden **/LTCG**. Açıkça belirtmek **/LTCG** geçirdiğiniz zaman **/GL** ve hızlı olası bağlayıcı için MSIL modüller yapı performans.  
  
 Daha hızlı performans için kullanmak **/LTCG: ARTIMLI**. Bu seçenek, yalnızca tüm proje yerine bir kaynak dosya değişikliği etkilenen dosyaları kümesini yeniden iyileştirmek için bağlayıcı söyler. Bu, gerekli bağlantı süresi önemli ölçüde azaltabilir. Artımlı bağlantılandırma olarak aynı seçeneği değil.  
  
 **/ LTCG** ile kullanım için geçerli değil [/ARTIMLI](../../build/reference/incremental-link-incrementally.md).  
  
 Zaman **/LTCG** kullanarak derlenmiş modüller bağlamak için kullanılan [/Og](../../build/reference/og-global-optimizations.md), [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), veya [/Ox](../../build/reference/ox-full-optimization.md), Aşağıdaki en iyi duruma getirme gerçekleştirilir:  
  
-   Çapraz modülü satır içi kullanım  
  
-   İnterprocedural yazmaç ayırma (yalnızca 64-bit işletim sistemleri)  
  
-   Özel çağırma kuralı (yalnızca x86)  
  
-   Küçük TLS öteleme (yalnızca x86)  
  
-   Yığın çift hizalama (yalnızca x86)  
  
-   Geliştirilmiş bellek Kesinleştirme (Genel değişkenler ve giriş parametreleri için daha iyi girişim bilgileri)  
  
> [!NOTE]
>  Bağlayıcı hangi iyileştirmeleri her işlevi derlemek için kullanılan belirler ve bağlantı aynı anda aynı iyileştirmeler uygular.  
  
 Kullanarak **/LTCG** ve **/Ogt** çift hizalama iyileştirme neden olur.  
  
 Varsa **/LTCG** ve **/Ogs** belirtilirse, çift hizalama gerçekleştirilmez. Bir uygulamada işlevlerin çoğunu boyutu için derlenmiş birkaç işlevlerle hızı için derlenmiş varsa (kullanarak örneğin, [en iyi duruma getirme](../../preprocessor/optimize.md) pragma), derleyici çift bunlar çağırırsanız boyutu için iyileştirilmiş işlevleri hizalar çift hizalama gerektiren işlevleri.  
  
 Derleyici işlev çağrısı siteleri belirleyebiliyorsanız derleyici bir işlev açık çağırma kuralı değiştiricileri yoksayar ve işlev çağırma iyileştirmek çalışır:  
  
-   Yazmaçları Parametreler  
  
-   hizalama için parametreleri yeniden Sırala  
  
-   kullanılmayan parametrelerini kaldırın  
  
 Bir işlev işaretçisi bir işlevi çağrıldıysa ya da bir işlevi kullanarak derlenmiş bir modül dışında çağrılır **/GL**, derleyici işlevin çağırma iyileştirmek çalışmaz.  
  
> [!NOTE]
>  Kullanırsanız **/LTCG** ve mainCRTStartup, tekrar tanımlayın, uygulamanızın genel nesneler başlatılmış önce yürütülen kullanıcı kodu için ilgili beklenmeyen davranışlara sahip olabilir.  Bu sorunu gidermek için üç yolu vardır: mainCRTStartup yeniden tanımlamanız değil, kullanarak mainCRTStartup içeren dosyası derleme değil **/LTCG**, veya genel değişkenler ve nesneleri statik olarak başlatılamadı.  
  
## <a name="ltcg-and-msil-modules"></a>/ LTCG ve MSIL modülleri  
 Kullanarak derlenmiş modüller [/GL](../../build/reference/gl-whole-program-optimization.md) ve [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) bağlayıcı girişi olarak kullanılabilir olduğunda **/LTCG** belirtilir.  
  
-   **/ LTCG** yerel nesne dosyaları, yerel ve yönetilen nesne dosyaları karma kabul edebilirsiniz (kullanarak derlenmiş **/CLR**) ve saf nesne dosyaları (kullanarak derlenmiş **/CLR: pure**), ve güvenli nesne dosyaları ( kullanarak derlenmiş **/CLR: safe**). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
-   **/ LTCG** kullanılarak oluşturulan güvenli .netmodules kabul edebilir **/CLR: safe /LN** Visual C++'ta ve **/target: Module** tüm Visual Studio .NET derleyici içinde. . Netmodules üretilen kullanarak **/CLR** veya **/CLR: pure** tarafından kabul edilmedi **/LTCG**.  
  
-   /LTCG:PGI kullanarak derlenmiş yerel modülleri kabul etmiyor **/GL** ve **/CLR**, veya saf modülleri (kullanılarak üretilen **/CLR: pure**)  
  
#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **yapılandırma özellikleri** klasör.  
  
3.  Seçin **genel** özellik sayfası.  
  
4.  Değiştirme **bütün Program iyileştirmesi** özelliği.  
  
 Ayrıca uygulayabilirsiniz **/LTCG** seçerek belirli derlemeleri için **yapı**, **profil temelli iyileştirme** menü çubuğunda veya profil temelli iyileştirme birini seçerek projesi için kısayol menüsünde Seçenekleri.  
  
#### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)