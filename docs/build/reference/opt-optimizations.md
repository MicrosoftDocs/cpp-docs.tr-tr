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
ms.openlocfilehash: fb59b861bc46c93a3f5fa1b6c6b8d1b73ddefc66
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818303"
---
# <a name="opt-optimizations"></a>/OPT (İyileştirmeler)

LINK öğesinin bir yapı sırasında gerçekleştirdiği iyileştirmeleri denetler.

## <a name="syntax"></a>Sözdizimi

> **/ OPT:**{**REF** | **NOREF**}<br/>
> **/ OPT:**{**ICF**[**=**_yinelemeler_] | **NOICF**}<br/>
> **/OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>Arguments

**REF** &#124; **NOREF**

**/ OPT: ref** işlevleri ve hiçbir zaman başvurulmayan; verileri ortadan kaldırır. **Elenmesini** işlevleri ve hiçbir zaman başvurulmayan verileri tutar.

/ OPT: ref etkin olduğunda, LINK başvurulmayan paketlenmiş işlevleri ve verileri, bilinen kaldırır *comdat'ları*. Bu iyileştirme, geçişli COMDAT eleme olarak bilinir. **/OPT: ref** seçeneği de devre dışı bırakır artımlı bağlama.

Her zaman satır içine alınmış işlevleri ve üye işlevleri sınıf bildirimi içinde tanımlanmış comdat'ları olur. Kullanarak derlenmişse tüm işlevlerin bir nesne dosyası comdat'ları yapılan [/Gy](gy-enable-function-level-linking.md) seçeneği. Yerleştirmek için **const** comdat'ları verileri, size bildirmelidir bunu kullanarak `__declspec(selectany)`. Kaldırma veya Katlama için veri belirtme hakkında daha fazla bilgi için bkz: [selectany](../../cpp/selectany.md).

Varsayılan olarak, **/OPT: ref** bağlayıcı tarafından sürece etkin **elenmesini** veya [/DEBUG](debug-generate-debug-info.md) belirtilir. Bu varsayılanı geçersiz kılmak ve başvurulmayan comdat'ları programda tutmak için bu seçeneği belirtin **elenmesini**. Kullanabileceğiniz [/INCLUDE](include-force-symbol-references.md) belirli bir sembolün kaldırılmasını geçersiz kılmak için seçeneği.

Varsa [/DEBUG](debug-generate-debug-info.md) belirtilirse, varsayılan **/OPT** olduğu **NOREF**, ve tüm işlevler görüntüde korunur. Bu varsayılanı geçersiz kılmak ve bir hata ayıklama derlemesini en iyileştirmek için belirtin **/OPT: ref**. Bu yürütülebilir dosyanızın boyutunu azaltabilir ve bir kullanışlı iyileştirme bile hata ayıklama yapıları olabilir. De belirtmenizi öneririz **noıcf** aynı korumak için hata ayıklama işlevlerini oluşturur. Bu yığın izlemelerini okumayı ve aksi takdirde birlikte katlanacak işlevlerde kesme noktalarını ayarlamayı kolaylaştırır.

**ICF**\[**=**_iterations_] &#124; **NOICF**

Kullanım **ICF**\[**=**_yinelemeler_] eşdeğer COMDAT katlaması gerçekleştirmek için. Fazlalık COMDAT'lar bağlayıcı çıktısından kaldırılabilir. İsteğe bağlı *yinelemeler* parametresi defa geçirileceğini yinelemeler için simgelerin sayısını belirtir. Varsayılan yineleme sayısı 1'dir. Ek yinelemeler, bir önceki yinelemede katlama sırasında kapsamda olmayan birden çok yineleme bulabilir.

Varsayılan olarak, **/OPT: ICF** bağlayıcı tarafından sürece etkin **noıcf** veya [/DEBUG](debug-generate-debug-info.md) belirtilir. Bu varsayılanı geçersiz kılmak ve comdat'ları programda Katlanmış önlemek için belirtin **noıcf**.

Hata ayıklama yapısında, açıkça belirtmeniz gerekir **/OPT: ICF** COMDAT katlamayı etkinleştirmek için. Ancak, çünkü **/OPT: ICF** aynı verileri ve işlevleri birleştirebildiği, yığın izlemelerinde görünen işlev adlarını değiştirebilirsiniz. Ayrıca, belirli işlevlerde kesme noktalarını ayarlayın veya hata ayıklayıcı bazı verileri incelemek için imkansız zorlaştırabilir ve beklemediğiniz işlevlere götürebilir olduğunda, tek adımlı kodunuza. Kod davranışını aynıdır, ancak hata ayıklayıcı sunu çok kafa karıştırıcı olabilir. Bu nedenle, kullanmanızı öneririz değil **/OPT: ICF** hata ayıklama yapılarında daha küçük bir kodun avantajları bu dezavantajların üstünde olmadığı sürece.

> [!NOTE]
> Çünkü **/OPT: ICF** aynı adresin farklı işlevlere veya salt okunur veri üyelerine atanan neden olabilir (diğer bir deyişle, **const** kullanılarak derlendiğinde değişkenleri **/Gy**), Bu işlevlere veya salt okunur veri üyelerine için benzersiz adreslere bağlı bir programı bozabilir. Daha fazla bilgi için [/Gy (işlev düzeyi bağlamayı etkinleştir)](gy-enable-function-level-linking.md).

**LBR** &#124; **NOLBR**

**/OPT: LBR** ve **nolbr** seçenekleri, yalnızca ARM ikili dosyalar için geçerlidir. Belirli ARM işlemci dal yönergeleri sınırlı aralığa sahip olduğundan bağlayıcı, aralık dışı bir adrese atlandığını algılarsa dal yönergesinin hedef adresini, gerçek hedefe giden dal yönergesinin bulunduğu "ada" kodu adresiyle değiştirir. Kullanabileceğiniz **/OPT: LBR** uzun dal yönergeleri algılanmasını ve genel kod boyutunu en aza indirmek amacıyla Ara kod Adaları yerleşimini en iyi duruma getirme. **Nolbr** bağlayıcıyı iyileştirme yapmadan karşılaşılan uzun dal yönergeleri için kod Adaları oluşturma konusunda bilgilendirir.

Varsayılan olarak, **/OPT: LBR** seçeneği, artımlı bağlamayı etkinleştirilmediğinde ayarlanır. Uzun dal iyileştirmeleri değil, ancak artımlı olmayan bir bağlantı istiyorsanız, belirtin **nolbr**. **/OPT: LBR** seçeneği artımlı bağlamayı devre dışı bırakır.

## <a name="remarks"></a>Açıklamalar

Bağlayıcı komut satırına kullanıldığında varsayılan **/OPT: ref, ICF LBR**. Varsa **/DEBUG** belirtilirse, varsayılan **noref, NOICF, NOLBR**.

**/OPT** iyileştirmeler genellikle görüntü boyutunu azaltır ve program hızını artırır. Bu geliştirmeler perakende derlemeleri için varsayılan olarak etkin neden olan daha büyük programlarda, önemli olabilir.

Bağlayıcı en iyileştirme ek zaman Önden alır ancak en iyi duruma getirilmiş kod Ayrıca, bağlayıcı düzeltmek için daha az konum değiştirmeler içeriyor ve daha küçük bir son görüntü oluşturulur ve işlemek ve PDB yazmak için daha az hata ayıklama bilgileri olduğunda daha fazla zaman kaydeder zaman kazandırır. İyileştirme etkinleştirildiğinde, küçük bir ek maliyet analizi olması birden fazla olarak bağlayıcı tasarruf daha küçük ikili dosyaları geçirir zamanına göre uzaklığı, daha hızlı bağlantı saati, genel olarak, neden olabilir.

**/OPT** bağımsız değişken belirtilebilir birlikte, virgülle ayrılmış. Örneğin, yerine, **/OPT: ref noıcf**, belirtebileceğiniz **/OPT: ref, NOICF**.

Kullanabileceğiniz [/VERBOSE](verbose-print-progress-messages.md) tarafından kaldırılan işlevleri görmek için bağlayıcı seçeneği **/OPT: ref** ve tarafından katlanan işlevleri **/OPT: ICF**.

**/OPT** bağımsız değişkenler kullanılarak oluşturulan projeler için genellikle ayarlanır **yeni proje** iletişim kutusunda Visual Studio IDE ve genellikle hata ayıklama için farklı değerlere sahip ve yayın yapılandırmaları. Bu bağlayıcı seçenekleri, projenizdeki herhangi bir değer ayarlarsanız, komut satırında bağlayıcı tarafından kullanılan varsayılan değerleri farklı Proje Varsayılanları elde edebilirsiniz.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:ICF veya OPT:REF bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **iyileştirme** özellik sayfası.

1. Bu özelliklerden birini değiştirin:

   - **COMDAT katlamasını etkinleştir**

   - **Başvurular**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:LBR bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. De seçeneği girin **ek seçenekler**:

   `/opt:lbr` veya `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> özellikleri.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
