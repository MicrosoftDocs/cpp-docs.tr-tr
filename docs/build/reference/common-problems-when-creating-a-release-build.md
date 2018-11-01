---
title: Yayın Derlemesi Oluşturmadaki Genel Sorunlar
ms.date: 11/04/2016
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
ms.openlocfilehash: a19eabc7b3e334f4a2a6d967d2bfc81b080c0054
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546587"
---
# <a name="common-problems-when-creating-a-release-build"></a>Yayın Derlemesi Oluşturmadaki Genel Sorunlar

Geliştirme sırasında genellikle derleme ve projenizin hata ayıklama derlemesi ile test edin. Daha sonra uygulamanızı bir yayın yapısı için oluşturma, erişim ihlali alabilirsiniz.

Aşağıdaki listede bir hata ayıklama ve yayın (nondebug) derleme arasındaki temel farklar gösterilmektedir. Diğer farklar vardır, ancak hata ayıklama yapısında çalışırken, bir yayın yapıda uygulamanın başarısız olmasına neden farklar aşağıda verilmiştir.

- [Yığın düzeni](#_core_heap_layout)

- [Derleme](#_core_compilation)

- [İşaretçi desteği](#_core_pointer_support)

- [En iyi duruma getirme](#_core_optimizations)

Bkz: [/GZ (Catch yayın derleme hatalarını hata ayıklama derleme içinde)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) derleyici seçeneği yayın catch hakkında bilgi için hata ayıklama yapılarında hata oluşturun.

##  <a name="_core_heap_layout"></a> Yığın düzeni

Yığın düzeni, uygulamanın hata ayıklama, ancak değil yayın çalışırken yaklaşık yüzde doksanı görünen sorunlara neden olacaktır.

Hata ayıklama için projenizi yapılandırdığınızda, hata ayıklama bellek ayırıcısı kullanıyor. Bu, tüm bellek ayırmaları etrafında yerleştirilen guard bayt olduğu anlamına gelir. Bu koruma bayt belleğin üzerine yazma algılayın. Yığın düzeni yayınlama ve hata ayıklama arasında farklı olduğundan sürümleri, belleğin üzerine yazma sorunları, hata ayıklama derlemesinde oluşturmayabilir, ancak bir sürüm yapıda yıkıcı etkileri olabilir.

Daha fazla bilgi için [denetlemek için bellek üzerine](../../build/reference/checking-for-memory-overwrites.md) ve [bellek üzerine yazmak için hata ayıklama derleme denetleyin kullanın](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md).

##  <a name="_core_compilation"></a> Derleme

MFC makroları ve çoğu için yayın oluşturma sırasında MFC uygulaması değişikliklerin birçoğu. Özellikle, ASSERTs içinde bulunan bir kodu hiçbiri yürütülecek şekilde ASSERT makrosu derleme, hiçbir şey için değerlendirir. Daha fazla bilgi için [ASSERT deyimleri inceleyin](../../build/reference/using-verify-instead-of-assert.md).

Yüksek hızda sürüm oluşturma için bazı işlevleri yapılırlar. İyileştirmeler genellikle bir yayın yapısı içinde etkinleştirilir. Farklı bellek ayırıcı da kullanılıyor.

##  <a name="_core_pointer_support"></a> İşaretçi desteği

Hata ayıklama bilgilerini eksikliği doldurmayı uygulamadan kaldırır. Bir yayın yapıda parazit işaretçileri hata ayıklama bilgilerini işaret eden yerine başlatılmamış belleği işaret eden, büyük şansına sahip olabilirsiniz.

##  <a name="_core_optimizations"></a> En iyi duruma getirme

Bazı kod parçalarını doğasına bağlı olarak, beklenmeyen bir kod iyileştirici derleyiciyi üretebilir. Yayın derlemesi sorunlarını az olası nedeni budur ancak bu durum ortaya çıkar. Bir çözüm için bkz: [kodunuzu en iyi duruma getirme](../../build/reference/optimizing-your-code.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Yayın Derlemeleri](../../build/reference/release-builds.md)<br/>
[Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)