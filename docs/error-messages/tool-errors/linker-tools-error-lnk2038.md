---
title: "Bağlayıcı araçları hatası LNK2038 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2038
dev_langs: C++
helpviewer_keywords: LNK2038
ms.assetid: b8d0fb35-eee6-4f52-b3c4-239cb4f65656
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 73694359c3fbcaa16455be3ce1197ba99fce56c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2038"></a>Bağlayıcı Araçları Hatası LNK2038
uyumsuzluğu algıladı '\<adı >': değer '\<değeri 1 >' değerle eşleşmiyor '\<değeri 2 >' ın \<filename.obj >  
  
 Bağlayıcı tarafından bir simge uyuşmazlığı algılandı. Bu hata, bu farklı belirtir. bir uygulama bölümlerini — bu kitaplıkları veya uygulama bağlandığı diğer nesne kodu içerir — simgenin çakışan tanımları kullanır. [Uyuşmazlığı algılamak](../../preprocessor/detect-mismatch.md) pragma çakışan değerlerine algılamak ve bu tür simgeleri tanımlamak için kullanılır.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Projenizdeki bir nesne dosyası güncel olduğunda bu hata oluşabilir. Bu hata için diğer çözümleri denemeden önce nesne dosyaları geçerli olduğundan emin olmak için temiz bir yapı gerçekleştirin.  
  
-   Visual Studio çalışma zamanı hataları veya diğer beklenmeyen davranışlara neden olabilir. uyumsuz kod bağlama önlemek için aşağıdaki simgelerden tanımlar.  
  
     `_MSC_VER`  
     Bir uygulama ya da kitaplığı oluşturmak için kullanılan Visual C++ Derleyici birincil ve ikincil sürüm numaralarını gösterir. Visual C++ derleyicisi bir sürümünü kullanarak derlenmiş kod farklı birincil ve ikincil sürüm numarası olan bir sürümünü kullanarak derlenmiş kod ile uyumlu değil. Daha fazla bilgi için bkz: `_MSC_VER` içinde [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).  
  
     Kullanmakta olduğunuz ve alma veya kitaplık uyumlu bir sürümü yapı Visual C++ Derleyici sürümü ile uyumlu olmayan bir kitaplığına bağlanıyorsanız, derleyici önceki bir sürümünü projenizi derleme için kullanabileceğiniz — yalnızca değiştirme **Platform araç takımı** projesinin özelliği. Daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
     `_ITERATOR_DEBUG_LEVEL`  
     Güvenlik ve hata ayıklama C++ Standart Kitaplığı'nda etkin özellikleri düzeyini gösterir. Bu özellikler belirli C++ Standart Kitaplığı nesneleri gösterimini değiştirin ve böylece onları olanlar uyumlu bu kullanım farklı güvenlik ve hata ayıklama özellikleri yapın. Daha fazla bilgi için bkz: [_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md).  
  
     `RuntimeLibrary`  
     Bir uygulama veya kitaplığı tarafından kullanılan C++ Standart Kitaplığı ve C çalışma zamanı sürümü gösterir. C++ Standart kitaplığı veya C çalışma zamanı bir sürümünü kullanan kodu farklı bir sürümünü kullanan kodu ile uyumlu değil. Daha fazla bilgi için bkz: [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
     `_PPLTASKS_WITH_WINRT`  
     Kullanan kodu gösterir [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) için farklı bir ayar kullanarak derlenmiş nesnelere bağlı [/ZW](../../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği. (**/ZW** destekleyen C + +/ CX.) PPL'de üzerinde bağlıdır veya kullanan kodu aynı kullanarak derlenmelidir **/ZW** uygulama geri kalanı kullanılan ayar.  
  
     Bu simgeleri değerlerini projeleri tutarlı olduğundan emin olun, Visual Studio çözümünüz ve bu da bunlar uygulamanızı bağlandığı kodu ve kitaplıkları ile tutarlı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı araçları hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)