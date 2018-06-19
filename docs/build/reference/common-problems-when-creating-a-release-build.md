---
title: Yayın derlemesi oluşturma genel sorunlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- unexpected code generation
- debugging [MFC], release builds
- release builds, troubleshooting
- stray pointers
- debug builds, difference from release builds
- MFC [C++], release builds
- heap layout problems
- pointers, stray
- release builds, building applications
- debug memory allocator
- optimization [C++], compiler
- projects [C++], debug configuration
- troubleshooting Visual C++
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8860783a2cf9fb88b28e24e0bc16eb16c0dd5d77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373172"
---
# <a name="common-problems-when-creating-a-release-build"></a>Yayın Derlemesi Oluşturmadaki Genel Sorunlar
Geliştirme sırasında genellikle derleme ve projenizin hata ayıklama derlemesi ile test. Ardından, uygulamanız yayın derlemesi için yapılandırdıysanız, bir erişim ihlali alabilirsiniz.  
  
 Aşağıdaki liste bir hata ayıklama ve yayın (nondebug) derlemesi arasındaki birincil farklılıklar gösterir. Diğer farklar vardır, ancak bir hata ayıklama derlemesi çalışırken, bir yayın derleme bir uygulama başarısız olmasına neden olur farklılıklar şunlardır.  
  
-   [Yığın düzeni](#_core_heap_layout)  
  
-   [Derleme](#_core_compilation)  
  
-   [İşaretçi desteği](#_core_pointer_support)  
  
-   [En iyi duruma getirme](#_core_optimizations)  
  
 Bkz: [/GZ (Catch yayın derleme hatalarını hata ayıklama yapı içinde)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) derleyici seçeneği yayın catch hakkında bilgi için hata ayıklama derlemelerinde hataları oluşturun.  
  
##  <a name="_core_heap_layout"></a> Yığın düzeni  
 Uygulama hata ayıklama, ancak değil yayın çalışırken yığın düzeni belirgin sorunları yaklaşık yüzde doksanına neden olur.  
  
 Hata ayıklama için projeyi derlerken hata ayıklama bellek ayırıcısı kullanıyor. Bu, tüm bellek ayırmaları etrafında yerleştirilen koruma bayt olduğu anlamına gelir. Bu koruma bayt algılamak belleğin üzerine yazma. Yığın düzeni hata ayıklama ve yayın arasında farklı olduğu için sürümler, belleğin üzerine yazma sorunları bir hata ayıklama derlemesi oluşturmayabilir, ancak bir yayın derleme yıkıcı iş etkisi.  
  
 Daha fazla bilgi için bkz: [denetleyin bellek üzerine yazmak için](../../build/reference/checking-for-memory-overwrites.md) ve [hata ayıklama yapı denetleyin bellek üzerine yazmak için kullanın](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md).  
  
##  <a name="_core_compilation"></a> Derleme  
 MFC makroları ve çoğu sürüm için derlerken MFC uygulaması değişiklikleri çoğunu. Özellikle, ASSERTs içinde bulunan kod hiçbiri yürütülecek şekilde ASSERT makrosu Nothing bir sürümde yapıdaki değerlendirir. Daha fazla bilgi için bkz: [ASSERT deyimleri inceleyin](../../build/reference/using-verify-instead-of-assert.md).  
  
 Bazı işlevler sürümde yapıdaki daha yüksek hız için satır içi. En iyi duruma getirme genellikle bir yayın yapı içinde etkinleştirilir. Farklı bellek ayırıcısı de kullanılıyor.  
  
##  <a name="_core_pointer_support"></a> İşaretçi desteği  
 Hata ayıklama bilgilerini eksikliği doldurma uygulamanızdan kaldırır. Bir yayın derleme parazit işaretçileri hata ayıklama bilgileri işaret eden yerine başlatılmamış bellek işaret eden, büyük şansına sahip olabilirsiniz.  
  
##  <a name="_core_optimizations"></a> En iyi duruma getirme  
 Bazı kod parçalarını yapısına bağlı en iyi duruma getirme derleyici beklenmeyen kodu oluşturabilir. Yayın derlemesi sorunlarını az olası nedeni budur ancak bazen kaynaklanır. Bir çözüm için bkz: [kodunuzu en iyi duruma getirme](../../build/reference/optimizing-your-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yayın derlemeleri](../../build/reference/release-builds.md)   
 [Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)