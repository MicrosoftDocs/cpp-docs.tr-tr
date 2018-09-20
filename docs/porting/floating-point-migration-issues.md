---
title: Kayan nokta geçiş sorunları | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 36a1b552-2f2b-4919-bc9d-c17f42434954
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e204e8dcc0d846294393edf9bf73b86360b40de2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421992"
---
# <a name="floating-point-migration-issues"></a>Kayan nokta geçiş sorunları  

  
Bazen projelerinizi Visual Studio'nun daha yeni bir sürüme yükseltme yaptığınızda, belirli bir kayan nokta işlemlerinin sonuçlarını değiştiğini fark edebilirsiniz. Bu genellikle iki nedenlerden biri gerçekleşir: kod oluşturma, daha iyi faydalanan kullanılabilir işlemci değiştirir ve hata düzeltmeleri veya matematik işlevleri (CRT) C Çalışma Zamanı Kitaplığı'nda kullanılan algoritmalar değiştirir. Genel olarak, yeni sonuçlar dil standardı tarafından belirlenen sınırlar içinde doğru olur. İşlevlerinizi aynı sonuçları almak nasıl, ne değiştirilir ve önemli olup olmadığını öğrenmek okuma, önce alındı.  

## <a name="new-math-functions-and-universal-crt-changes"></a>Yeni matematik işlevleri ve evrensel CRT değişiklikleri  
  
Çoğu CRT matematik işlevleri için Visual Studio'da kullanılabilen yıldır, ancak Visual Studio 2013 itibariyle, tüm ISO C99 tarafından gerekli işlevleri dahil edilir. Bu işlevler, doğruluk açısından performans dengelemek için uygulanır. Her durumda doğru yuvarlatılmış sonuç oluşturmayı fazla vakit pahalı olabileceği için bu işlevleri verimli bir şekilde doğru yuvarlatılmış sonuca Kapat bir yaklaştırma üretmek için tasarlanmıştır. Çoğu durumda olan +/-1 birim en az duyarlılık sonucu içinde veya *ulp*, doğru yuvarlatılmış sonucu, ancak durumlar olabilir büyük yanlışlığı olduğu. Bu işlevler önce almak için farklı matematik kitaplığı kullanıyorsanız, uygulama farklılıkları sonuçlarınızı değişiklik sorumlu olabilir.   
    
Matematik işlevleri için Visual Studio 2015'te Evrensel CRT taşınan, kullanılan bazı yeni algoritmaları ve Visual Studio 2013'te yeni işlevler uygulaması olarak bazı hatalar düzeltilmiştir. Bu değişiklikleri bu işlevleri kayan nokta hesaplamalarının sonuçlarını algılanabilir farklılıkları neden olabilir. Hata sorunlar yaşadım işlevleri erf, exp2, kalan, remquo, scalbln ve scalbn ve bunların float ve uzun çift çeşitleri olmuştur.  Visual Studio 2015'te diğer değişiklikler, kayan nokta durum word ve özel durum durumu bilgilerini _clear87, _clearfp fegetenv fesetenv ve feholdexcept işlevlerde koruma sorunlarını düzelttik.  
  
## <a name="processor-differences-and-compiler-flags"></a>İşlemci farkları ve derleyici bayrakları  
  
Birçok kayan nokta matematik kitaplığı işlevi farklı CPU mimarileri için farklı uygulamaları vardır. Örneğin, 32-bit x86 CRT 64-bit x64 değerinden farklı bir uygulama olabilir CRT. Ayrıca, bazı işlevler belirli bir CPU mimarisi için birden çok uygulamaları olabilir. En verimli uygulama CPU tarafından desteklenen komut kümelerini bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32-bit x86, CRT, bazı işlevler, hem x x87 sahip uygulama ve SSE2 uygulaması. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulaması kullanılır. SSE2, uygulama kullanılan daha yavaş x87 desteklemeyen bir CPU üzerinde çalışırken. Varsayılan x86 derleyici mimari seçeneği için değiştiğinden, bu eski kod geçişi sırasında görebilirsiniz [/arch: SSE2](../build/reference/arch-x86.md) Visual Studio 2012. Matematik kitaplığı işlevi, farklı uygulamalar farklı CPU yönergeleri ve farklı algoritmalar sonuçları üretmek için kullanılıyor olabileceğinden, İşlevler, farklı platformlarda farklı sonuçlar üretebilir. Çoğu durumda, sonuçlar içinde +/-1 ulp yuvarlatılmış doğru sonucu olan, ancak gerçek sonuçların CPU'lar arasında değişebilir.  
  
Eski kodu yeni kodu için aynı derleyici bayraklarına kullanırken bile karşılaştırılır, farklı kayan nokta modları Visual Studio'da kod üretimi doğruluk geliştirmeleri kayan nokta işlemlerinin sonuçlarını da etkileyebilir. Örneğin, Visual Studio 2010 tarafından oluşturulan kodu olduğunda [/FP: precise](../build/reference/fp-specify-floating-point-behavior.md) (varsayılan) veya `/fp:strict` belirtildi ifadeler üzerinden Ara bir sayı değil (NaN) değerler doğru yayıldıktan değil. Bu nedenle, eski derleyicilerde sayısal bir sonuç getirdi bazı ifadelerin artık doğru bir NaN sonuç üretebilir. Ayrıca kod iyileştirmeler etkinleştirilmiş olduğundan değişiklikleriyle karşılaşabileceğinizi `/fp:fast` artık daha fazla işlemci özelliklerini yararlanın. Bu iyileştirmeler, daha az yönergeleri kullanabilirsiniz, ancak daha önce görünen bazı Ara işlem kaldırıldığı için oluşturulan sonuç etkileyebilir.  
  
## <a name="how-to-get-identical-results"></a>Aynı sonuçları elde etme  
  
Çoğu durumda, daha hızlı veya daha doğru davranış veya her ikisi en yeni derleyicileri ve kitaplıkları kayan nokta değişiklikleri neden. SSE2 yönergelerini x87 değiştirdiğinizde, işlemci gücü için daha iyi performans bile görebilirsiniz yönergeleri. Tam olarak gerekir kodunuz varsa ancak kayan çoğaltma noktası daha eski bir derleyici davranışını, Visual Studio yerel çoklu sürüm desteği özelliklerini kullanmayı göz önünde bulundurun ve eski araç takımıyla etkilenen projeyi derleyin. Daha fazla bilgi için [yerel çoklu sürüm desteğinin Visual Studio'da eski projeleri oluşturmak için kullanmak](use-native-multi-targeting.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
  
[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)  