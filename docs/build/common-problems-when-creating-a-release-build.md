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
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
ms.openlocfilehash: 9bd1cafe40417872d42f2e9e1427e5f2eccad7a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328863"
---
# <a name="common-problems-when-creating-a-release-build"></a>Yayın Derlemesi Oluşturmadaki Genel Sorunlar

Geliştirme sırasında, genellikle projenizin hata ayıklama yapısıyla oluşturur ve sınarsınız. Daha sonra bir sürüm oluşturma için uygulama oluşturursanız, bir erişim ihlali alabilirsiniz.

Aşağıdaki liste, hata ayıklama ve sürüm (nondebug) yapısı arasındaki birincil farkları gösterir. Başka farklılıklar da vardır, ancak hata ayıklama yapısında çalıştığında bir uygulamanın sürüm yapısında başarısız olmasına neden olacak birincil farklar şunlardır.

- [Yığın Düzeni](#_core_heap_layout)

- [Derleme](#_core_compilation)

- [İşaretçi Desteği](#_core_pointer_support)

- [İyileştirmeler](#_core_optimizations)

Hata ayıklama yapılarında sürüm oluşturma hatalarını nasıl yakalayacağınız hakkında bilgi için [/GZ (Hata Ayıklama Yapısında Sürüm Oluşturma Hatalarını Yakala)](reference/gz-enable-stack-frame-run-time-error-checking.md) derleyici seçeneğine bakın.

## <a name="heap-layout"></a><a name="_core_heap_layout"></a>Yığın Düzeni

Yığın düzeni, bir uygulama hata ayıklamada çalıştığında görünen sorunların yaklaşık yüzde doksanının nedeni olur, ancak yayımlanmaz.

Projenizi hata ayıklama için oluşturduğunuzda, hata ayıklayıcı bellek ayırıcısını kullanırsınız. Bu, tüm bellek ayırmalarının etrafına koruma baytları yerleştirildiği anlamına gelir. Bu koruma baytları bir belleğin üzerine yazı yazdığını algılar. Yığın düzeni sürüm ve hata ayıklama sürümleri arasında farklı olduğundan, bir bellek üzerine yazma hata ayıklama yapısında herhangi bir sorun oluşturmayabilir, ancak bir sürüm yapısında yıkıcı etkileri olabilir.

Daha fazla bilgi için bkz: [Memory Overwrite için denetle](checking-for-memory-overwrites.md) ve [Hata Ayıklama Yapısını Kullanarak Bellek Üzerine Yaz'ı Denetleyin.](using-the-debug-build-to-check-for-memory-overwrite.md)

## <a name="compilation"></a><a name="_core_compilation"></a>Derleme

Serbest bırakılması için oluşturduğunuzda MFC makrolarının çoğu ve MFC uygulamasının çoğu değişir. Özellikle, ASSERT makrosu bir sürüm yapısında hiçbir şeyi değerlendirmez, bu nedenle ASSERT'lerde bulunan kodun hiçbiri yürütülmez. Daha fazla bilgi için [bkz.](using-verify-instead-of-assert.md)

Bazı işlevler sürüm yapısında artan hız için inlined vardır. Optimizasyonlar genellikle bir sürüm yapısında açık. Farklı bir bellek ayırıcı sı da kullanılıyor.

## <a name="pointer-support"></a><a name="_core_pointer_support"></a>İşaretçi Desteği

Hata ayıklama bilgilerinin olmaması, dolguyu uygulamanızdan kaldırır. Sürüm oluşturmada, başıboş işaretçilerin hata ayıklama bilgilerini işaret etmek yerine başharflere getirilmemiş belleğe işaret etme şansı daha yüksektir.

## <a name="optimizations"></a><a name="_core_optimizations"></a>Iyileştirme

Belirli kod segmentlerinin yapısına bağlı olarak, en iyi duruma ürün derleyici beklenmeyen kod oluşturabilir. Bu sürüm oluşturma sorunlarının en az olası nedenidir, ancak zaman zaman ortaya çıkar. Bir çözüm için [kodunuzu optimize etme](optimizing-your-code.md)'ye bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Yayın Derlemeleri](release-builds.md)<br/>
[Yayın Derlemesi Sorunlarını Giderme](fixing-release-build-problems.md)
