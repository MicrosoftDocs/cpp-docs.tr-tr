---
title: / OPT (iyileştirmeler) | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc9f7f66b9bd0ee2c0da65d17eac33e1cbc8c316
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34463111"
---
# <a name="opt-optimizations"></a>/OPT (İyileştirmeler)

LINK öğesinin bir yapı sırasında gerçekleştirdiği iyileştirmeleri denetler.

## <a name="syntax"></a>Sözdizimi

> **/ OPT:**{**REF** | **NOREF**}<br/>
> **/ OPT:**{**ICF**[**=**_yineleme_] | **NOICF**}<br/>
> **/ OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>Arguments

**REF** &AMP;#124; **NOREF**

**/OPT:REF** işlevler ve hiçbir zaman başvurulan; veri ortadan kaldırır **/OPT:NOREF** işlevleri ve hiçbir zaman başvurulan verileri tutar.

/OPT:ref etkinleştirildiğinde, başvurulmayan paketlenmiş işlevler ve verileri, bilinen bağlantıyı kaldırır *COMDATs*. Bu iyileştirme, geçişli COMDAT eleme olarak bilinir. **/OPT:REF** seçeneği de devre dışı bırakır artımlı bağlama.

Satır içi işlevler ve üye işlevleri sınıf bildirimi içinde tanımlanan her zaman COMDATs olur. Derlenmiş kullanarak ise tüm işlevleri bir nesne dosyasına COMDATs yapılan [/Gy](../../build/reference/gy-enable-function-level-linking.md) seçeneği. Yerleştirmek için **const** COMDATs verilerin, bildirmelidir onu kullanarak `__declspec(selectany)`. Verileri kaldırma veya Katlama belirtme hakkında daha fazla bilgi için bkz: [selectany](../../cpp/selectany.md).

Varsayılan olarak, **/OPT:REF** bağlayıcı tarafından sürece etkindir **/OPT:NOREF** veya [/DEBUG](../../build/reference/debug-generate-debug-info.md) belirtilir. Bu varsayılanı geçersiz kılabilir ve programa başvurulmayan COMDATs tutmak için belirtmeniz **/OPT:NOREF**. Kullanabileceğiniz [/dahil](../../build/reference/include-force-symbol-references.md) belirli bir sembol kaldırılmasını geçersiz kılmak için seçeneği.

Varsa [/DEBUG](../../build/reference/debug-generate-debug-info.md) belirtilirse, varsayılan **/OPT** olan **NOREF**, ve tüm işlevler görüntüde korunur. Bu varsayılanı geçersiz kılabilir ve hata ayıklama derlemesi en iyi duruma getirmek için belirtmeniz **/OPT:REF**. Bu yürütülebilir dosyanın boyutunu küçültebilirsiniz ve yararlı bir iyileştirme hata ayıklama bile derlemeler olabilir. Ayrıca belirttiğiniz öneririz **/OPT:NOICF** aynı korumak için hata ayıklama işlevlerde oluşturur. Bu yığın izlemelerini okumayı ve aksi takdirde birlikte katlanacak işlevlerde kesme noktalarını ayarlamayı kolaylaştırır.

**ICF**\[**=**_yineleme_] &#124; **NOICF**

Kullanım **ICF**\[**=**_yineleme_] aynı comdat'ı Katlama gerçekleştirmek için. Fazlalık COMDAT'lar bağlayıcı çıktısından kaldırılabilir. İsteğe bağlı *yineleme* parametresi, yinelemeleri simgelerini çapraz geçiş sayısı belirtir. Yineleme varsayılan sayısı 1'dir. Ek yinelemeler, bir önceki yinelemede katlama sırasında kapsamda olmayan birden çok yineleme bulabilir.

Varsayılan olarak, **/OPT:ICF** bağlayıcı tarafından sürece etkindir **/OPT:NOICF** veya [/DEBUG](../../build/reference/debug-generate-debug-info.md) belirtilir. Bu varsayılanı geçersiz kılabilir ve programa Katlanmış COMDATs önlemek için belirtmek **/OPT:NOICF**.

Bir hata ayıklama derlemesi, açıkça belirtmelisiniz **/OPT:ICF** comdat'ı Katlama etkinleştirmek için. Ancak, çünkü **/OPT:ICF** özdeş veriler veya İşlevler birleştirebilirsiniz, Yığın izlemeleri görünür işlev adlarını değiştirebilirsiniz. Ayrıca, belirli işlevlerde kesme noktalarını ayarlayın veya hata ayıklayıcısında bazı verileri incelemek için mümkün hale getirebilir ve beklenmeyen işlevlerini alabilir olduğunda, tek adımlı kodunuz. Kod davranışını aynıdır, ancak hata ayıklayıcı sunu çok kafa karıştırıcı olabilir. Bu nedenle, kullanmanızı öneririz değil **/OPT:ICF** içinde hata ayıklama derlemeleri sürece bu olumsuzlukları küçük kod avantajlarından daha ağır basar.

> [!NOTE]
> Çünkü **/OPT:ICF** farklı işlevler veya salt okunur veri üyeleri için atanacak aynı adresini neden olabilir (diğer bir deyişle, **const** kullanarak derlendiğinde değişkenleri **/Gy**), benzersiz adresler işlevleri veya salt okunur veri üyeleri için bağımlı bir program bozulabilir. Daha fazla bilgi için bkz: [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md).

**LBR** &AMP;#124; **NOLBR**

**/OPT:LBR** ve **/OPT:NOLBR** seçenekleri, yalnızca ARM ikili dosyaları için geçerlidir. Belirli ARM işlemci dal yönergeleri sınırlı aralığa sahip olduğundan bağlayıcı, aralık dışı bir adrese atlandığını algılarsa dal yönergesinin hedef adresini, gerçek hedefe giden dal yönergesinin bulunduğu "ada" kodu adresiyle değiştirir. Kullanabileceğiniz **/OPT:LBR** uzun şube yönergeleri algılanmasını ve genel kod boyutu en aza indirmek için Ara kod Adaları yerleştirilmesi en iyi duruma getirme. **/OPT:NOLBR** kod Adaları uzun şube yönergeler için en iyi duruma getirme karşılaşılan oluşturmak için bağlayıcıya bildirir.

Varsayılan olarak, **/OPT:LBR** artımlı bağlama etkinleştirilmediğinde seçeneğini ayarlayın. Artımlı olmayan bir bağlantı ancak değil uzun şube iyileştirmeler istiyorsanız belirtin **/OPT:NOLBR**. **/OPT:LBR** seçeneğini artımlı bağlantılandırma devre dışı bırakır.

## <a name="remarks"></a>Açıklamalar

Komut satırında kullanıldığında, bağlayıcı için varsayılan olarak **/OPT:REF, ICF LBR**. Varsa **/DEBUG** belirtilmemişse, varsayılan **/OPT:NOREF, NOICR, NOLBR**.

**/OPT** iyileştirmeleri genellikle görüntü boyutunu küçültmek ve program hızını artırır. Bu geliştirmeler perakende yapıları için varsayılan olarak etkin neden olduğu daha büyük programlarda önemli olabilir.

Bağlayıcı iyileştirme fazladan Önden zaman, ancak en iyi duruma getirilmiş kod ayrıca zaman bağlayıcı düzeltmek için daha az relocatıons sahiptir ve daha küçük bir son resim oluşturur ve işlemek ve PDB yazmak için daha az hata ayıklama bilgileri olduğunda daha fazla zaman kazandırır zamandan tasarruf sağlar. İyileştirme etkinleştirildiğinde, küçük ek bir maliyet analizi olması birden fazla gibi bağlayıcı tasarruf küçük ikili dosyaları geçirir zamana göre uzaklığı, daha hızlı bağlantı saati, bir genel olarak, yol açabilir.

**/OPT** bağımsız değişkenleri belirtilebilir birlikte, virgülle ayrılmış. Örneğin, yerine, **/OPT:REF /OPT:NOICF**, belirleyebileceğiniz **/OPT:REF, NOICF**.

Kullanabileceğiniz [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) tarafından kaldırılır işlevleri görmek için bağlayıcı seçeneği **/OPT:REF** ve tarafından Katlanmış işlevleri **/OPT:ICF**.

**/OPT** bağımsız değişkenleri kullanılarak oluşturulan projeleri için genellikle ayarlanır **yeni proje** Visual Studio IDE içinde iletişim ve genellikle hata ayıklama için farklı değerlere sahip ve yapılandırmaları bırakın. Bu bağlayıcı seçenekleri projenizdeki için herhangi bir değer ayarlarsanız, komut satırında bağlayıcı tarafından kullanılan varsayılan değerlerle farklı olabilir Proje Varsayılanları elde edebilirsiniz.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:ICF veya OPT:REF bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **en iyi duruma getirme** özellik sayfası.

1. Bu özelliklerden birini değiştirin:

   - **Comdat'ı Katlama etkinleştir**

   - **Başvurular**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:LBR bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Seçenek girin **ek seçenekler**:

   `/opt:lbr` Veya `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> özellikleri.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
