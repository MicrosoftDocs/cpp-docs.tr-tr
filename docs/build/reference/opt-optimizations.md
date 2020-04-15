---
title: /OPT (İyileştirmeler)
ms.date: 05/18/2018
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
ms.openlocfilehash: b25db4d6c260c3c6751de293aa2a82df8aa05e7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336219"
---
# <a name="opt-optimizations"></a>/OPT (İyileştirmeler)

LINK öğesinin bir yapı sırasında gerçekleştirdiği iyileştirmeleri denetler.

## <a name="syntax"></a>Sözdizimi

> **/OPT:**{**REF** | **NOREF**}<br/>
> **/OPT:**{**ICF**[**=**_yinelemeler_] | **NOICF**}<br/>
> **/OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>Bağımsız Değişkenler

**REF** &#124; **NOREF**

**/OPT:REF,** hiç başvurulamayan işlevleri ve verileri ortadan kaldırır; **/OPT:NOREF** hiç başvurulamayan işlevleri ve verileri tutar.

/OPT:REF etkinleştirildiğinde, LINK *COMDATs*olarak bilinen başvurulan olmayan paketlenmiş işlevleri ve verileri kaldırır. Bu iyileştirme, geçişli COMDAT eleme olarak bilinir. **/OPT:REF** seçeneği de artımlı bağlamayı devre dışı kılabilir.

Sınıf bildirimi içinde tanımlanan çizgili işlevler ve üye işlevler her zaman COMDATs vardır. /Gy seçeneği kullanılarak derlenirse, nesne dosyasındaki tüm işlevler [/Gy](gy-enable-function-level-linking.md) COMDAT'lara dönüştürülr. **Const** verileri COMDAT'lara yerleştirmek için, bunu `__declspec(selectany)`kullanarak bildirmeniz gerekir. Kaldırma veya katlama için veri belirtme hakkında bilgi için [selectany'ye](../../cpp/selectany.md)bakın.

Varsayılan olarak, **/OPT:REF** **/OPT:NOREF** veya [/HATA SACI](debug-generate-debug-info.md) belirtilmediği sürece bağlayıcı tarafından etkinleştirilir. Bu varsayılanı geçersiz kılmak ve başvurulmamış COMDAT'ları programda tutmak için **/OPT:NOREF'i**belirtin. Belirli bir sembolün kaldırılmasını geçersiz kılmak için [/INCLUDE](include-force-symbol-references.md) seçeneğini kullanabilirsiniz.

[/DEBUG](debug-generate-debug-info.md) belirtilirse, **/OPT** için varsayılan **NOREF**ve tüm işlevler görüntüde korunur. Bu varsayılanı geçersiz kılmak ve hata ayıklama oluşturmayı optimize etmek için **/OPT:REF**. Bu, yürütülebilir boyutunu azaltabilir ve hata ayıklama yapılarında bile yararlı bir optimizasyon olabilir. Hata ayıklama yapılarında aynı işlevleri korumak için **/OPT:NOICF'yi** de belirtmenizi öneririz. Bu yığın izlemelerini okumayı ve aksi takdirde birlikte katlanacak işlevlerde kesme noktalarını ayarlamayı kolaylaştırır.

**ICF**\[**=**_yinelemeler_] &#124; **NOICF**

Aynı COMDAT katlama gerçekleştirmek için **ICF**\[**=**_yinelemeleri_] kullanın. Fazlalık COMDAT'lar bağlayıcı çıktısından kaldırılabilir. İsteğe bağlı *yinelemeler* parametresi, yinelenenler için sembolleri geçiş için kaç kez belirtir. Varsayılan yineleme sayısı 1'dir. Ek yinelemeler, bir önceki yinelemede katlama sırasında kapsamda olmayan birden çok yineleme bulabilir.

Varsayılan olarak, **/OPT:ICF** **/OPT:NOICF** veya [/DEBUG](debug-generate-debug-info.md) belirtilmediği sürece bağlayıcı tarafından etkinleştirilir. Bu varsayılanı geçersiz kılmak ve COMDAT'ların programda katlanmasını önlemek için **/OPT:NOICF'** yi belirtin.

Hata ayıklama yapısında, COMDAT katlanmasını sağlamak için **/OPT:ICF'yi** açıkça belirtmeniz gerekir. Ancak, **/OPT:ICF** aynı verileri veya işlevleri birleştirebildiği için, yığın izlerinde görünen işlev adlarını değiştirebilir. Ayrıca, belirli işlevlerde kesme noktaları ayarlamayı veya hata ayıklayıcıdaki bazı verileri incelemeyi imkansız hale getirebilir ve kodunuzda tek adımda yaptığınızda sizi beklenmeyen işlevlere götürebilir. Kodun davranışı aynıdır, ancak hata ayıklama sunusu çok kafa karıştırıcı olabilir. Bu nedenle, küçük kodun avantajları bu dezavantajlardan daha ağır basmadığı sürece hata ayıklama yapılarında **/OPT:ICF** kullanmanızı önermiyoruz.

> [!NOTE]
> **/OPT:ICF** aynı adresin farklı işlevlere veya salt okunur veri üyelerine atanmasına (diğer bir şekilde **/Gy**kullanılarak derlendiğinde **const** değişkenler) atanmasına neden olabileceğinden, işlevler veya salt okunur veri üyeleri için benzersiz adreslere dayanan bir programı bozabilir. Daha fazla bilgi için bkz: [/Gy (İşlev Düzeyi Bağlamayı Etkinleştir)](gy-enable-function-level-linking.md).

**LBR** &#124; **NOLBR**

**/OPT:LBR** ve **/OPT:NOLBR** seçenekleri yalnızca ARM ikilileri için geçerlidir. Belirli ARM işlemci dal yönergeleri sınırlı bir kapsama sahip olduğundan, bağlayıcı aralık dışı bir adrese bir sıçrama algılarsa, şube talimatının hedef adresini gerçek hedefi hedefleyen bir şube yönergesi içeren bir kod "ada" adresiyle değiştirir. Genel kod boyutunu en aza indirmek için uzun şube yönergelerinin algılanmasını ve ara kod adalarının yerleşimini optimize etmek için **/OPT:LBR'yi** kullanabilirsiniz. **/OPT:NOLBR,** bağlantı sahibine, en iyi duruma getirilmesi olmaksızın, karşılaşılan uzun şube talimatları için kod adaları oluşturmasını emreder.

Varsayılan olarak, artımlı bağlantı etkinleştirilen olmadığında **/OPT:LBR** seçeneği ayarlanır. Artımlı olmayan, ancak uzun dal optimizasyonları olmayan bir bağlantı istiyorsanız, **/OPT:NOLBR**' yi belirtin. **/OPT:LBR** seçeneği artımlı bağlamayı devre dışı kılabilir.

## <a name="remarks"></a>Açıklamalar

Komut satırında kullanıldığında, bağlayıcı varsayılan olarak **/OPT:REF,ICF,LBR**olarak kullanılır. **/Hata Ayıklama** belirtilirse, varsayılan **/OPT:NOICF,NOLBR.**

**/OPT** optimizasyonları genellikle görüntü boyutunu azaltır ve program hızını artırır. Bu geliştirmeler daha büyük programlarda önemli olabilir, bu nedenle perakende yapılar için varsayılan olarak etkinleştirilir.

Bağlayıcı optimizasyonu önceden fazladan zaman alır, ancak optimize edilen kod, bağlantının düzeltmek için daha az yer değiştirmesi olduğunda ve daha küçük bir son görüntü oluşturduğunda zaman kazandırır ve pdb'ye yazmak için daha az hata ayıklama bilgisi olduğunda daha da fazla zaman kazandırır. Optimizasyon etkinleştirildiğinde, analizdeki küçük ek maliyet, bağlayıcıdaki zaman tasarrufundan daha küçük ikililer üzerinden geçtiğinden daha fazla dengelendiğinden, genel olarak daha hızlı bir bağlantı süresine neden olabilir.

**/OPT** bağımsız değişkenleri birlikte belirtilebilir, virgülle ayrılabilir. Örneğin, **/OPT:REF /OPT:NOICF**yerine **/OPT:REF,NOICF**belirtebilirsiniz.

**/OPT:REF** tarafından kaldırılan işlevleri ve **/OPT:ICF**tarafından katlanan işlevleri görmek için [/VERBOSE](verbose-print-progress-messages.md) bağlayıcı seçeneğini kullanabilirsiniz.

**/OPT** bağımsız değişkenleri genellikle Visual Studio IDE'deki **Yeni Proje** iletişim kutusu kullanılarak oluşturulan projeler için ayarlanır ve genellikle hata ayıklama ve sürüm yapılandırmaları için farklı değerlere sahiptir. Projenizdeki bu bağlayıcı seçenekleri için değer ayarlanmıyorsa, komut satırındaki bağlayıcı tarafından kullanılan varsayılan değerlerden farklı olabilecek proje varsayılanlarını alabilirsiniz.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:ICF veya OPT:REF bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. Yapılandırma **Özellikleri** > **Bağlayıcı** > **Optimizasyon** özelliği sayfasını seçin.

1. Bu özelliklerden birini değiştirin:

   - **COMDAT Katlamasını Etkinleştir**

   - **Başvurular**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:LBR bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. Yapılandırma **Özellikleri** > **Bağlayıcı** > **Komut Satırı** özellik sayfasını seçin.

1. **Ek Seçenekler**seçeneğini girin:

   `/opt:lbr` veya `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> ve özellikleri.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC Bağlayıcı Seçenekleri](linker-options.md)
