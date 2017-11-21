---
title: -(x86) arch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
caps.latest.revision: "33"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d1dd4689cf4e2ef4c4f6601396110327c74773b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="arch-x86"></a>/arch (x86)
X86 üzerinde kod oluşturma için Mimari belirtir. Ayrıca bkz. [/(x64) arch](../../build/reference/arch-x64.md) ve [/arch (ARM)](../../build/reference/arch-arm.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/arch:[IA32|SSE|SSE2|AVX|AVX2]  
```  
  
## <a name="arguments"></a>Arguments  
 **/arch:IA32**  
 Gelişmiş hiçbir yönerge ve ayrıca kayan nokta hesaplamalar için x87 belirtir.  
  
 **/arch:SSE**  
 SSE yönergeleri kullanımını etkinleştirir.  
  
 **/arch:SSE2**  
 SSE2 yönergeleri kullanımını etkinleştirir. Varsayılan yönerge x86 budur platformları yoksa **/arch** seçeneği belirtildi.  
  
 **/arch:AVX**  
 Intel Gelişmiş vektör uzantıları yönergeleri kullanımını etkinleştirir.  
  
 **/arch:AVX2**  
 Intel Gelişmiş vektör Extensions 2 yönergeleri kullanımını etkinleştirir.  
  
## <a name="remarks"></a>Açıklamalar  
 SSE ve SSE2 yönergeleri çeşitli Intel ve AMD işlemcileri üzerinde yok. AVX yönergeleri Intel Sandy köprüsü işlemciler ve AMD Bulldozer işlemciler üzerinde yok. AVX2 yönergeleri Intel Haswell ve Broadwell işlemciler ve AMD Excavator tabanlı işlemciler tarafından desteklenir.  
  
 `_M_IX86_FP`, `__AVX__` Ve `__AVX2__` makroları hangi belirtmek, varsa, **/arch** derleyici seçeneği kullanıldı. Daha fazla bilgi için bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md). **/Arch:AVX2** seçeneği ve `__AVX2__` makrosu, Visual Studio 2013 güncelleştirme 2 ', sürüm 12.0.34567.1 sunulmuştur.  
  
 İyileştirici SSE ve SSE2 yönergeleri kullanmak üzere nasıl ve ne zaman seçtiği zaman **/arch** belirtilir. SSE kullanır ve yığın SSE2 yönergeler SSE/SSE2 yönerge ve kayıtları kayan nokta x87 yerine kullanılacak hızlıdır olduğunu belirlediğinde, skaler bazı kayan nokta hesaplamaları için kaydolun. Sonuç olarak, kodunuzu x87 ve SSE/SSE2 bileşimi gerçekte kayan nokta hesaplamaları için kullanabilir. Ayrıca, ile **/arch:SSE2**, SSE2 yönergeleri bazı 64-bit tamsayı işlemleri için kullanılabilir.  
  
 SSE ve SSE2 yönergeleri kullanarak yanı sıra derleyici SSE ve SSE2 destekleyen işlemci düzeltmelerini mevcut olan diğer yönergeler de kullanır. İlk Intel işlemcileri Pentium Pro düzeltilmesi görünen CMOV yönerge örneğidir.  
  
 Derleyici oluşturur x86 SSE2 yönergeleri kullanan varsayılan kod olduğundan, belirtmelisiniz **/arch:IA32** SSE ve SSE2 yönergeleri oluşturma x86 için devre dışı bırakmak için işlemci.  
  
 **/ arch** etkiler kod oluşturmayı yerel işlevler için yalnızca. Kullandığınızda [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derlemek için **/arch** kod oluşturma için yönetilen işlevler üzerinde etkisi yoktur.  
  
 **/ arch** ve [/QIfist](../../build/reference/qifist-suppress-ftol.md) aynı derlenecek üzerinde kullanılamaz. Kullanmıyorsanız, özellikle `_controlfp` FP denetim sözcüğü sonra 53 bit çalışma zamanı başlangıç kümeleri x87 FPU denetim kodu word duyarlık denetim alana değiştirmek için. Bu nedenle, her float ve bir ifadede çift işlemi 53 bit significand ve 15 bit üs kullanır. Ancak, 24 bit significand ve 8 bit üs her SSE tek duyarlıklı işlemi kullanır ve 53 bit significand ve 11 bit üs SSE2 çift duyarlıklı işlemleri kullanın. Daha fazla bilgi için bkz: [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md). Bu farklılıklar, bir ifade ağacına, ancak kullanıcı ataması sonra her alt burada söz konusu değildir durumlarda mümkündür. Aşağıdakileri göz önünde bulundurun:  
  
```cpp  
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.  
```  
  
 Karşılaştırma:  
  
```cpp  
t = f1 * f2;   // Do f1 * f2, round to the type of t.  
r = t + d;     // This should produce the same overall result   
               // whether x87 stack is used or SSE/SSE2 is used.  
```  
  
### <a name="to-set-this-compiler-option-for-avx-avx2-ia32-sse-or-sse2-in-visual-studio"></a>Visual Studio'da Bu derleyici seçeneği AVX, AVX2, IA32, SSE veya SSE2 ayarlamak için  
  
1.  Açık **özellik sayfaları** projesi için iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **yapılandırma özellikleri**, **C/C++** klasör.  
  
3.  Seçin **kod oluşturma** özellik sayfası.  
  
4.  Değiştirme **etkinleştirmek gelişmiş yönerge kümesi** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)