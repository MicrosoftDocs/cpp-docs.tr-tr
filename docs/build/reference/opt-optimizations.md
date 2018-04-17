---
title: -OPT (iyileştirmeler) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 928968803dc008eb39b3d0c52152c1f3b631a852
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="opt-optimizations"></a>/OPT (İyileştirmeler)
LINK öğesinin bir yapı sırasında gerçekleştirdiği iyileştirmeleri denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## <a name="arguments"></a>Arguments  
 **REF** &AMP;#124; **NOREF**  
 **/OPT:REF** işlevler ve hiçbir zaman başvurulan; veri ortadan kaldırır **/OPT:NOREF** işlevleri ve hiçbir zaman başvurulan verileri tutar.  
  
 /OPT:ref etkinleştirildiğinde, bağlantı başvurulmayan paketlenmiş işlevler ve verileri kaldırır. Kullanarak derlenen nesne paketlenmiş işlevler ve verileri (COMDATs) varsa, [/Gy](../../build/reference/gy-enable-function-level-linking.md) seçeneği. Bu iyileştirme, geçişli COMDAT eleme olarak bilinir. Varsayılan olarak, **/OPT:REF** olmayan hata ayıklama derlemelerinde etkinleştirilir. Bu varsayılanı geçersiz kılabilir ve programa başvurulmayan COMDATs tutmak için belirtmeniz **/OPT:NOREF**. Kullanabileceğiniz [/dahil](../../build/reference/include-force-symbol-references.md) belirli bir sembol kaldırılmasını geçersiz kılmak için seçeneği.  
  
 Zaman **/OPT:REF** açıkça ya da varsayılan olarak, sınırlı bir biçimini etkin **/OPT:ICF** etkin, aynı işlevleri Katlama. İsterseniz **/OPT:REF** ama **/OPT:ICF**, ya da belirtmeniz gerekir **/OPT:REF, NOICF** veya **/OPT:NOICF**.  
  
 Varsa [/DEBUG](../../build/reference/debug-generate-debug-info.md) belirtilirse, varsayılan **/OPT** olan **NOREF**, ve tüm işlevler görüntüde korunur. Bu varsayılanı geçersiz kılabilir ve hata ayıklama derlemeyi en iyi duruma getirmek için belirtmeniz **/OPT:REF**. Çünkü **/OPT:REF** gelir **/OPT:ICF**, aynı zamanda belirlediğiniz öneririz **/OPT:NOICF** hata ayıklama derlemeleri de aynı işlevleri korumak için. Bu yığın izlemelerini okumayı ve aksi takdirde birlikte katlanacak işlevlerde kesme noktalarını ayarlamayı kolaylaştırır. **/OPT:REF** seçeneğini artımlı bağlantılandırma devre dışı bırakır.  
  
 Açık olarak işaretlemek sahip `const` kullanın; bir comdat'ı olarak veri [__declspec(selectany)](../../cpp/selectany.md).  
  
 Belirtme **/OPT:ICF** etkinleştirmemeniz **/OPT:REF** seçeneği.  
  
 **ICF [=** `iterations` **] &AMP;#124; NOICF**   
 Kullanım **/OPT:ICF [=**`iterations`**]** aynı comdat'ı Katlama gerçekleştirmek için. Fazlalık COMDAT'lar bağlayıcı çıktısından kaldırılabilir. İsteğe bağlı `iterations` parametresi, yinelemeleri simgelerini çapraz geçiş sayısı belirtir. Varsayılan yineleme sayısı 2'dir. Ek yinelemeler, bir önceki yinelemede katlama sırasında kapsamda olmayan birden çok yineleme bulabilir.  
  
 Bağlayıcı farklı şekilde davranan zaman **/OPT:REF** belirtilen — ve **ICF** varsayılan olarak etkindir; ne zaman göründüğünden **/OPT:REF, ICF** açıkça belirtilen. Biçiminde **ICF** ile etkin **/OPT:REF** tek başına salt okunur verileri Katlama olmayan — bu .rdata, ve.xdata'yı ve sanal işlem bulunur içerir. Bu nedenle, daha az işlevleri için görüntüleri üretildiğinde Katlanmış [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] bu modüllerdeki işlevlerin salt okunur verileri hakkında daha fazla bağımlı olduğundan — Örneğin, ve.xdata'yı ve sanal işlem bulunur. Tam almak için **ICF** davranışı Katlama açıkça belirtmek **/OPT:ICF**.  
  
 İşlevler içinde COMDATs yerleştirmek için kullandığınız **/Gy** yerleştirmek için derleyici seçeneği; `const` veri bildirdiğiniz onu `__declspec(selectany)`. Katlama için veri belirtme hakkında daha fazla bilgi için bkz: [selectany](../../cpp/selectany.md).  
  
 Varsayılan olarak, **ICF** üzerinde ise **REF** açıktır. Varsa bu varsayılanı geçersiz kılmak için **REF** olduğu belirtilen kullanmak **NOICF**. Zaman **/OPT:REF** bir hata ayıklama derlemesi açıkça belirtmelisiniz belirtilmemiş **/OPT:ICF** comdat'ı Katlama etkinleştirmek için. Ancak, çünkü **/OPT:ICF** özdeş veriler veya İşlevler birleştirebilirsiniz, Yığın izlemeleri görünür işlev adlarını değiştirebilirsiniz. Ayrıca, belirli işlevlerde kesme noktalarını ayarlamayı ya da hata ayıklayıcıda bazı verileri incelemeyi imkansız hale getirebilir ve kod içinde tek adımla ilerlediğinizde sizi beklemediğiniz işlevlere götürebilir. Bu nedenle, kullanmanızı öneririz değil **/OPT:ICF** içinde hata ayıklama derlemeleri sürece bu olumsuzlukları küçük kod avantajlarından daha ağır basar.  
  
> [!NOTE]
>  Çünkü **/OPT:ICF** farklı işlevler veya salt okunur veri üyeleri için atanacak aynı adresini neden olabilir (`const` kullanarak derlenmiş değişkenleri **/Gy**), bağımlı program bölünebilir benzersiz adresler işlevleri veya salt okunur veri üyeleri için. Daha fazla bilgi için bkz: [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md).  
  
 **LBR** &AMP;#124; **NOLBR**  
 **/OPT:LBR** ve **/OPT:NOLBR** seçenekleri, yalnızca ARM ikili dosyaları için geçerlidir. Belirli ARM işlemci dal yönergeleri sınırlı aralığa sahip olduğundan bağlayıcı, aralık dışı bir adrese atlandığını algılarsa dal yönergesinin hedef adresini, gerçek hedefe giden dal yönergesinin bulunduğu "ada" kodu adresiyle değiştirir. Kullanabileceğiniz **/OPT:LBR** uzun şube yönergeleri algılanmasını ve genel kod boyutu en aza indirmek için Ara kod Adaları yerleştirilmesi en iyi duruma getirme. **/OPT:NOLBR** kod Adaları uzun şube yönergeler için en iyi duruma getirme karşılaşılan oluşturmak için bağlayıcıya bildirir.  
  
 Varsayılan olarak, **/OPT:LBR** artımlı bağlama etkinleştirilmediğinde seçeneğini ayarlayın. Artımlı olmayan bir bağlantı ancak değil uzun şube iyileştirmeler istiyorsanız belirtin **/OPT:NOLBR**. **/OPT:LBR** seçeneğini artımlı bağlantılandırma devre dışı bırakır.  
  
## <a name="remarks"></a>Açıklamalar  
 İyileştirmeler genellikle görüntü boyutunu azaltır ve daha yüksek bağlantı süresi maliyetiyle program hızını artırır.  
  
 Kullanabileceğiniz [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) tarafından kaldırılır fonksiyonları görmek için seçeneği **/OPT:REF** ve tarafından Katlanmış işlevleri **/OPT:ICF**.  
  
### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:ICF veya OPT:REF bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Sol bölmede **yapılandırma özellikleri**, **bağlayıcı**, **en iyi duruma getirme**.  
  
3.  Bu özelliklerden birini değiştirin:  
  
    -   **Comdat'ı Katlama etkinleştir**  
  
    -   **Başvurular**  
  
### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki OPT:LBR bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Seçenek girin **ek seçenekler**:  
  
     `/opt:lbr`  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> özellikleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
