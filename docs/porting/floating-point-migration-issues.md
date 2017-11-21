---
title: "Kayan nokta geçiş sorunları | Microsoft Docs"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 36a1b552-2f2b-4919-bc9d-c17f42434954
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e922872f302e6a6fb00170878a5033ba75e6b8a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="floating-point-migration-issues"></a>Kayan nokta geçiş sorunları  
  
Bazen projelerinizi Visual Studio'nun daha yeni bir sürüme yükselttiğinizde, kayan nokta belirli işlemlerin sonuçlarını değiştiğini fark edebilirsiniz. Bu genellikle iki nedenlerden biri gerçekleşir: kod oluşturma daha iyi faydalanan kullanılabilir işlemci değiştirir ve hata düzeltmeleri veya matematik işlevleri C çalışma zamanı kitaplığı (CRT) kullanılan algoritmalar değişir. Genel olarak, yeni sonuçları doğru standart dili tarafından belirlenen sınırlar içinde. Değiştirilenler ve önemli olup olmadığını öğrenmek okuma, önce işlevlerinizi aynı sonuçları almak nasıl aldı.  

## <a name="new-math-functions-and-universal-crt-changes"></a>Yeni matematik işlevleri ve evrensel CRT değişiklikleri  
  
Çoğu CRT matematik işlevleri için Visual Studio'da kullanılabilir yıldır ancak Visual Studio 2013'ten başlayarak, tüm ISO C99 tarafından gerekli işlevleri dahil edilir. Bu işlevler, performans doğruluk ile dengelemek için uygulanır. Her durumda doğru yuvarlatılmış sonuç üretme şekilde basımı karşılamayacak kadar pahalı olabilir çünkü bu işlevler verimli bir şekilde doğru yuvarlatılmış sonucu yaklaşık üretmek için tasarlanmıştır. Çoğu durumda, üretilen sonuç içinde 1 en az duyarlık birimidir veya *ulp*, doğru yuvarlatılmış sonucu, ancak durumlar olabilir büyük yanlış bilgi olduğu. Bu işlevler önce almak için farklı math kitaplığı kullanıyorsanız, uygulama farklılıkları sonuçlarınızı değişikliği sorumlu olabilir.   
    
Matematik işlevleri, Visual Studio 2015'te Evrensel CRT taşındı, bazı yeni algoritmaları kullanıldı ve Visual Studio 2013'te yeni işlevler uygulamasında çeşitli hatalar düzeltilmiştir. Bu değişiklikler bu işlevleri kullanma kayan nokta hesaplamaların sonuçlarını algılanabilir farklılıkları neden olabilir. Hata sorunları olan işlevler erf, exp2, kalan, remquo, scalbln, scalbn ve bunların float ve uzun çift çeşitleri yoktu.  Visual Studio 2015'te diğer değişiklikler kayan nokta durum word ve özel durum durumu bilgilerini _clear87, _clearfp, fegetenv, fesetenv ve feholdexcept işlevlerinde koruma sorunları sabit.  
  
## <a name="processor-differences-and-compiler-flags"></a>İşlemci farklar ve derleyici bayrakları  
  
Kayan birçok noktasının matematik kitaplık işlevleri sahip farklı uygulamalar farklı CPU mimari için. Örneğin, 32-bit x86 CRT 64-bit x64 daha farklı bir uygulama olabilir CRT. Ayrıca, bazı işlevler belirli bir CPU mimarisi için birden çok uygulamaları olabilir. En verimli uygulama CPU tarafından desteklenen yönerge kümeleri bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32-bit x86 içinde CRT, bazı işlevler sahip hem bir x87 uygulama ve SSE2 uygulaması. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulama kullanılır. SSE2, uygulama kullanılan yavaş x87 desteklemeyen bir CPU üzerinde çalışırken. Varsayılan x86 derleyici mimarisi seçeneği için değiştiğinden, bu eski kod geçirilirken görebilirsiniz [/arch:SSE2](../build/reference/arch-x86.md) Visual Studio 2012'de. Matematik kitaplığı işlevlerin farklı uygulamalar farklı CPU yönergeleri ve farklı algoritmalar sonuçları üretmek için kullanılıyor olabileceğinden, İşlevler farklı platformlarda farklı sonuçlar doğurabilir. Çoğu durumda, doğru yuvarlatılmış sonuç 1 ulp +/-içinde sonucu olan, ancak gerçek sonuçları CPU'lar arasında değişebilir.  
  
Eski kod yeni kod, aynı derleyici bayrakları kullanırken bile karşılaştırıldığında farklı kayan nokta modları Visual Studio'da kod oluşturma doğruluk yenilikleri kayan nokta işlemlerinin sonuçlarını da etkileyebilir. Örneğin, Visual Studio 2010 tarafından oluşturulan kodu zaman [/fp: kesin](../build/reference/fp-specify-floating-point-behavior.md) (varsayılan) veya **/fp: katı** belirtildi Ara bir sayı değil (NaN) değerler ifadeleri aracılığıyla dağıtıldıktan değil doğru. Bu nedenle, eski derleyicileri içinde sayısal bir sonuç verdi bazı ifadeleri artık doğru NaN sonuç üretebilir. Kod iyileştirmeler için etkinleştirilmiş olduğundan farkları da görebilirsiniz **/fp:fast** artık daha fazla işlemci özelliklerden yararlanabilir. Bu en iyi duruma getirme, daha az yönergeleri kullanabilirsiniz, ancak daha önce görünen bazı Ara işlemleri kaldırıldığı için oluşturulan sonuçları etkileyebilir.  
  
## <a name="how-to-get-identical-results"></a>Aynı sonuçları alma  
  
Çoğu durumda, daha hızlı veya daha doğru davranış veya her ikisine de kitaplıkları ve en yeni derleyicileri kayan nokta değişiklikleri neden. SSE2 yönergeleri x87 değiştirdiğinizde, daha iyi işlemci gücü performans bile görebilirsiniz yönergeler. Tam olarak gerekir kodu varsa, ancak kayan çoğaltmak noktası eski derleyici davranışı, Visual Studio yerel çoklu sürüm desteği özelliklerini kullanarak göz önünde bulundurun ve eski araç takımı ile etkilenen projeyi oluşturun. Daha fazla bilgi için bkz: [yerel çoklu sürüm desteği eski projeler derlemek için Visual Studio'da kullanın](use-native-multi-targeting.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
  
[Visual C++'ın önceki sürümlerinden yükseltme projeleri](upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
[Olası yükseltme sorunlarını (Visual C++) genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)  
[Visual C++ değişiklik geçmişini 2003 2015](visual-cpp-change-history-2003-2015.md)  
