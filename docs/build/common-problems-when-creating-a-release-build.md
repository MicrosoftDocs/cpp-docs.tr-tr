---
description: 'Hakkında daha fazla bilgi edinin: yayın derlemesi oluştururken sık karşılaşılan sorunlar'
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
ms.openlocfilehash: 7470b87a33b9dc0cb6f7e85b9cfa7b7c1216a936
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163099"
---
# <a name="common-problems-when-creating-a-release-build"></a>Yayın Derlemesi Oluşturmadaki Genel Sorunlar

Geliştirme sırasında, genellikle projenizin hata ayıklama derlemesini oluşturup test edersiniz. Uygulamanızı bir yayın derlemesi için derlemenize sonra bir erişim ihlali alabilirsiniz.

Aşağıdaki listede bir hata ayıklama ve sürüm (hata ayıklama) derlemesi arasındaki birincil farklılıklar gösterilmektedir. Başka farklar vardır ancak aşağıdakiler, bir uygulamanın bir hata ayıklama derlemesinde çalışırken yayın derlemesinde başarısız olmasına neden olacak birincil farklardır.

- [Yığın düzeni](#_core_heap_layout)

- [Derleme](#_core_compilation)

- [İşaretçi desteği](#_core_pointer_support)

- [İyileştirmeler](#_core_optimizations)

Hata ayıklama yapılarında yayın oluşturma hatalarının nasıl yakalayacağınız hakkında bilgi için bkz. [/gz (hata ayıklama derlemesinde hataları Release-Build yakala)](reference/gz-enable-stack-frame-run-time-error-checking.md) derleyici seçeneği.

## <a name="heap-layout"></a><a name="_core_heap_layout"></a> Yığın düzeni

Yığın düzeni, bir uygulama hata ayıklamada çalışırken, ancak serbest bırakmadığında, görünen sorunların yüzde 90 ' unun nedeni olacaktır.

Projenizi hata ayıklama için yapılandırdığınızda, hata ayıklama bellek ayırıcısını kullanıyorsunuz demektir. Bu, tüm bellek tahsisatlarının çevresinde yer alan koruma baytları olduğu anlamına gelir. Bu koruma baytları belleği üzerine yazmayı algılar. Yığın düzeni yayın ve hata ayıklama sürümleri arasında farklılık yaptığından, bir bellek üzerine yazma işlemi hata ayıklama derlemesinde herhangi bir sorun oluşturmayabilir, ancak yayın derlemesinde çok önemli etkileri olabilir.

Daha fazla bilgi için bkz. [bellek üzerine yazmayı denetleme](checking-for-memory-overwrites.md) ve [bellek üzerine yazmayı denetlemek Için hata ayıklama derlemesini kullanma](using-the-debug-build-to-check-for-memory-overwrite.md).

## <a name="compilation"></a><a name="_core_compilation"></a> Derleme

Yayın için derleme yaptığınızda MFC makrolarının birçoğu ve MFC uygulamasının çoğu değişir. Özellikle, onay makrosu bir yayın derlemesinde Nothing olarak değerlendirilir ve bu nedenle, onaylamalar içinde bulunmayan kodların hiçbiri yürütülür. Daha fazla bilgi için bkz. [onaylama deyimlerini İnceleme](using-verify-instead-of-assert.md).

Bazı işlevler, yayın derlemesinde daha fazla hız için satır içine alınır. İyileştirmeler, genellikle bir yayın derlemesinde açıktır. Farklı bir bellek ayırıcısı da kullanılıyor.

## <a name="pointer-support"></a><a name="_core_pointer_support"></a> İşaretçi desteği

Hata ayıklama bilgilerinin bulunmaması uygulamanızın doldurmasını kaldırır. Bir yayın derlemesinde, başıo işaretçilerin hata ayıklama bilgilerine işaret etmek yerine başlatılmamış belleği işaret eden daha büyük bir olasılığı vardır.

## <a name="optimizations"></a><a name="_core_optimizations"></a> İyileştirmeleri

Belirli kod segmentlerinin yapısına bağlı olarak, iyileştirmeli Derleyici beklenmeyen bir kod oluşturabilir. Bu, yayın derleme sorunlarının en büyük nedenidir, ancak bu durum bazen meydana gelir. Bir çözüm için bkz. [kodunuzu iyileştirme](optimizing-your-code.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yayın Derlemeleri](release-builds.md)<br/>
[Yayın derleme sorunlarını giderme](fixing-release-build-problems.md)
