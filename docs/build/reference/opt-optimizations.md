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
ms.openlocfilehash: 5c0ab3579fcb9633c435305a8b02b0c3f73d7a6f
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825710"
---
# <a name="opt-optimizations"></a>/OPT (İyileştirmeler)

LINK öğesinin bir yapı sırasında gerçekleştirdiği iyileştirmeleri denetler.

## <a name="syntax"></a>Sözdizimi

> **/OPT:**{**ref** | **NOREF**} \
> **/OPT:**{**ICF**[**=**_yinelemeler_] | **NOICF**} \
> **/OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>Bağımsız Değişkenler

**Başvuru** &#124; **NOREF**

**/OPT: ref** hiçbir şekilde başvurulmayan işlevleri ve verileri ortadan kaldırır; **/OPT: NOREF** hiçbir şekilde başvurulmayan işlevleri ve verileri tutar.

/OPT: REF etkinleştirildiğinde bağlantı, başvurulmayan paketlenmiş işlevleri ve verileri, *Compts*olarak bilinen verileri kaldırır. Bu iyileştirme, geçişli COMDAT eleme olarak bilinir. **/OPT: ref** seçeneği artımlı bağlamayı de devre dışı bırakır.

Satır içine alınmış işlevler ve bir sınıf bildiriminde tanımlanan üye işlevleri her zaman Comtts ' dir. Bir nesne dosyasındaki tüm işlevler, [/GY](gy-enable-function-level-linking.md) seçeneği kullanılarak derlenmişse COMDAT 'lar içine yapılır. COMDAT 'a **const** verileri yerleştirmek için kullanarak `__declspec(selectany)`bunu bildirmeniz gerekir. Kaldırma veya katlama için veri belirtme hakkında daha fazla bilgi için bkz. [selectany](../../cpp/selectany.md).

/OPT: **NOREF** veya [/Debug](debug-generate-debug-info.md) belirtilmediği takdirde, varsayılan olarak, **/OPT: ref** bağlayıcı tarafından etkinleştirilir. Bu varsayılanı geçersiz kılmak ve başvurulmayan Comnts 'yi programda tutmak için **/OPT: NOREF**belirtin. Belirli bir sembolün kaldırılmasını geçersiz kılmak için [/Include](include-force-symbol-references.md) seçeneğini kullanabilirsiniz.

[/Debug](debug-generate-debug-info.md) belirtilirse, **/opt** Için varsayılan değer **NOREF**' dir ve tüm işlevler görüntüde korunur. Bu varsayılanı geçersiz kılmak ve bir hata ayıklama derlemesini iyileştirmek için **/OPT: ref**belirtin. Bu, yürütülebilir dosyanızın boyutunu azaltabilir ve hata ayıklama yapılarında bile yararlı bir iyileştirme olabilir. Hata ayıklama yapılarında özdeş işlevleri korumak için **/OPT: NOıCF** belirtmenizi öneririz. Bu yığın izlemelerini okumayı ve aksi takdirde birlikte katlanacak işlevlerde kesme noktalarını ayarlamayı kolaylaştırır.

**ICF**\[ICF**=**_yinelemeleri_] **NOICF** &#124;

Aynı COMDAT katlamayı gerçekleştirmek için **ICF**\[**=**_yinelemelerini_kullanın]. Fazlalık COMDAT'lar bağlayıcı çıktısından kaldırılabilir. İsteğe bağlı *yineleme* parametresi, simgelerin yineleme için kaç kez gezeceği sayısını belirtir. Varsayılan yineleme sayısı 1 ' dir. Ek yinelemeler, bir önceki yinelemede katlama sırasında kapsamda olmayan birden çok yineleme bulabilir.

/OPT: **NOICF** veya [/Debug](debug-generate-debug-info.md) belirtilmediği takdirde, varsayılan olarak, **/OPT: ICF** bağlayıcı tarafından etkinleştirilir. Bu varsayılanı geçersiz kılmak ve Comnts 'nin programa katlanmasını engellemek için **/OPT: NOıCF**belirtin.

Bir hata ayıklama derlemesinde, COMDAT katlamayı etkinleştirmek için açıkça **/OPT: ICF** belirtmeniz gerekir. Ancak, **/OPT: ICF** özdeş verileri veya işlevleri birleştirebildiğinden, yığın izlemelerinde görünen işlev adlarını değiştirebilir. Ayrıca, belirli işlevlerde kesme noktalarını ayarlamayı veya hata ayıklayıcıdaki bazı verileri incelemenizi olanaksız hale getirir ve kodunuzda tek adım ilerlemenizin sizi beklenmedik işlevlere götürebilirler. Kodun davranışı aynıdır, ancak hata ayıklayıcı sunumu çok karmaşık olabilir. Bu nedenle, küçük kodun avantajları bu dezavantajların avantajlarından yararlanmadığı müddetçe hata ayıklama yapılarında **/OPT: ICF** kullanmanızı önermiyoruz.

> [!NOTE]
> **/OPT: ICF** aynı adresin farklı işlevlere veya salt okunabilir veri üyelerine (yani, **/GY**kullanılarak derlendiğinde **const** değişkenlerine) atanmasına neden olabileceğinden, işlevler veya salt okuma veri üyeleri için benzersiz adreslere bağlı olan bir programı bozabilir. Daha fazla bilgi için bkz. [/GY (Işlev düzeyi bağlamayı etkinleştir)](gy-enable-function-level-linking.md).

**LBR** &#124; **NOLBR**

**/OPT: LBR** ve **/OPT: NOLBR** seçenekleri yalnızca ARM ikilileri için geçerlidir. Belirli ARM işlemci dal yönergeleri sınırlı aralığa sahip olduğundan, bağlayıcı Aralık dışı bir adrese bir atmayı algılarsa, dal yönergesinin hedef adresini, gerçek hedefi hedefleyen bir dal yönergesi içeren "Adası" kodunun adresiyle değiştirir. Genel kod boyutunu en aza indirmek için uzun dal yönergelerinin algılanmasını ve ara kod Adaları yerleştirmesini iyileştirmek için **/OPT: LBR** kullanabilirsiniz. **/OPT: NOLBR** bağlayıcının, karşılaştığı ve en iyi duruma getirme olmadan uzun dal yönergeleri için kod Adaları oluşturmasını söyler.

Varsayılan olarak, **/OPT: LBR** seçeneği artımlı bağlama etkin olmadığında ayarlanır. Artımsal olmayan bir bağlantı istiyorsanız ancak uzun dal iyileştirmelerine sahip değilseniz, **/OPT: NOLBR**değerini belirtin. **/OPT: LBR** seçeneği artımlı bağlamayı devre dışı bırakır.

## <a name="remarks"></a>Açıklamalar

Komut satırında kullanıldığında, bağlayıcı varsayılan olarak **/OPT: ref, ICF, LBR**olur. **/Debug** belirtilirse, varsayılan olarak **/OPT: NOREF, NOıCF, NOLBR**olur.

**/Opt** iyileştirmeleri genellikle görüntü boyutunu azaltır ve program hızını artırır. Bu geliştirmeler, daha büyük programlar için, perakende derlemeler için varsayılan olarak etkinleştirilmeleriyle ilgili önemli ölçüde olabilir.

Bağlayıcı iyileştirmesi daha fazla zaman alır, ancak en iyi duruma getirilmiş kod, bağlayıcının düzeltilmesi ve daha küçük bir son görüntü oluşturması için daha az sayıda yeniden konumlandırmaya sahip olması ve daha az hata ayıklama bilgisi olduğunda PDB 'ye yazılması durumunda daha da fazla zaman kazandırır. En iyi duruma getirme etkinleştirildiğinde analizin daha hızlı bir bağlantı süresine neden olabilir. Bu, analiz halindeki küçük ek maliyet, bağlayıcının daha küçük ikili dosyalar üzerinde geçiş yaptığı süre içindeki tasarruflara göre uzaklığa göre daha fazla olabilir.

**/Opt** bağımsız değişkenleri, virgülle ayrılmış olarak birlikte belirtilebilir. Örneğin, **/OPT: ref/OPT: NOıCF**yerine **/OPT: ref, NOICF**belirtebilirsiniz.

**/OPT: ref** tarafından kaldırılan işlevleri ve **/OPT: ICF**tarafından katlanmış işlevleri görmek için [/verbose](verbose-print-progress-messages.md) bağlayıcı seçeneğini kullanabilirsiniz.

**/Opt** bağımsız değişkenleri genellikle VISUAL Studio IDE 'Deki **Yeni proje** iletişim kutusu kullanılarak oluşturulan projeler için ayarlanır ve genellikle hata ayıklama ve yayın yapılandırmalarına yönelik farklı değerlere sahiptir. Projenizdeki bu bağlayıcı seçenekleri için herhangi bir değer ayarlanmamışsa, bu durumda proje varsayılanlarını alabilir ve bu, komut satırında bağlayıcı tarafından kullanılan varsayılan değerlerden farklı olabilir.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:ICF veya OPT:REF bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **iyileştirme** özellik sayfasını seçin.

1. Bu özelliklerden birini değiştirin:

   - **COMDAT Katlamasını Etkinleştir**

   - **Başvurular**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:LBR bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler**' de seçeneği girin:

   `/opt:lbr` veya `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> . <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> ve Özellikler.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC Bağlayıcı Seçenekleri](linker-options.md)
