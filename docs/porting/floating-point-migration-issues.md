---
title: Kayan nokta geçiş sorunları
ms.date: 05/17/2017
ms.assetid: 36a1b552-2f2b-4919-bc9d-c17f42434954
ms.openlocfilehash: 0a84b764d395063f38cae299cff75437318b024e
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626988"
---
# <a name="floating-point-migration-issues"></a>Kayan nokta geçiş sorunları

Bazen projelerinizi Visual Studio 'nun daha yeni bir sürümüne yükselttiğinizde, belirli kayan nokta işlemleri sonuçlarının değiştiğini fark edebilirsiniz. Bu durum genellikle iki nedenden biri için gerçekleşir: kullanılabilir işlemcinin daha iyi avantajlarından yararlanan kod oluşturma değişiklikleri ve hata düzeltmeleri veya C çalışma zamanı kitaplığı 'ndaki (CRT) matematik işlevlerinde kullanılan algoritmalarda yapılan değişiklikler. Genel olarak, yeni sonuçlar dil standardı tarafından belirtilen sınırlar dahilinde doğru olur. Nelerin değiştiğini öğrenmek için ' i okuyun ve önemli ise işlevlerinizin daha önce aldığı sonuçları elde edin.

## <a name="new-math-functions-and-universal-crt-changes"></a>Yeni matematik işlevleri ve Evrensel CRT değişiklikleri

Çoğu CRT matematik işlevi, Visual Studio 'da yıl için sunulmaktadır, ancak Visual Studio 2013 başlayarak ISO C99 için gereken tüm işlevler dahil edilmiştir. Bu işlevler, performansı doğruluk altına alacak şekilde uygulanır. Her durumda doğru bir şekilde yuvarlanmış sonucun üretilmesi, canlı bir şekilde elde edilebilir hale gelebilir, bu işlevler doğru bir şekilde yuvarlanmış sonuca yakın bir şekilde bir kapatma sağlamak üzere tasarlanmıştır. Çoğu durumda, üretilen sonuç, doğru bir şekilde yuvarlanmış en az duyarlık veya *ULP*birimi olmak üzere, doğru yuvarlatılmış sonucun içinde, ancak daha fazla doğruluk olduğu durumlar olabilir. Bu işlevleri daha önce almak için farklı bir matematik kitaplığı kullanıyorsanız, sonuçlarınızda değişiklik yapmaktan uygulama farklılıkları sorumlu olabilir.

Matematik işlevleri Visual Studio 2015 ' de Universal CRT 'a taşındığında, bazı yeni algoritmalar kullanılmıştır ve Visual Studio 2013 yeni olan işlevlerin uygulanmasında birkaç hata düzeltildi. Bu değişiklikler, bu işlevleri kullanan kayan nokta hesaplamaları sonuçlarında algılanabilir farklılıklara yol açabilir. Hata sorunları olan işlevler HATAİŞLEV, exp2, geri kalan, remquo, scalbln ve scalbümn ve bu kişilerin float ve uzun çift çeşitleri vardı.  Visual Studio 2015 ' deki diğer değişiklikler, kayan nokta durum sözcüğünü ve özel durum bilgilerini _clear87, _clearfp, fegetenv, fesetenv ve feholdexcept işlevlerinde koruyan sorunlar düzeltildi.

## <a name="processor-differences-and-compiler-flags"></a>İşlemci farklılıkları ve derleyici bayrakları

Kayan nokta matematik kitaplığı işlevlerinin birçoğu, farklı CPU mimarileri için farklı uygulamalara sahiptir. Örneğin, 32 bit x86 CRT, 64 bit x64 CRT 'den farklı bir uygulamaya sahip olabilir. Ayrıca, bazı işlevlerden belirli bir CPU mimarisi için birden çok uygulama olabilir. En verimli uygulama, CPU tarafından desteklenen yönerge kümelerine bağlı olarak çalışma zamanında dinamik olarak seçilir. Örneğin, 32 bit x86 CRT 'de, bazı işlevlerde hem x87 uygulama hem de bir SSE2 uygulama vardır. SSE2 destekleyen bir CPU üzerinde çalışırken, daha hızlı SSE2 uygulama kullanılır. SSE2 desteklemeyen bir CPU üzerinde çalışırken, daha yavaş x87 uygulama kullanılır. Varsayılan x86 derleyici mimarisi seçeneği Visual Studio 2012 ' de [/Arch: SSE2](../build/reference/arch-x86.md) olarak değiştirildiğinden, eski kodu geçirirken bunu görebilirsiniz. Matematik kitaplığı işlevlerinin farklı uygulamaları, sonuçlarını oluşturmak için farklı CPU yönergeleri ve farklı algoritmalar kullanabileceğinden, işlevler farklı platformlarda farklı sonuçlar üretebilir. Çoğu durumda, sonuçlar doğru bir şekilde yuvarlanmış sonucu +/-1 ULP içinde, ancak gerçek sonuçlar CPU 'larda farklılık gösterebilir.

Visual Studio 'daki farklı kayan nokta modlarında kod oluşturma doğruluğu iyileştirmeleri, eski kod aynı derleyici bayraklarını kullanırken bile yeni kodla karşılaştırıldığı zaman kayan nokta işlemlerinin sonuçlarını da etkileyebilir. Örneğin, [/FP: kesin](../build/reference/fp-specify-floating-point-behavior.md) (varsayılan) veya `/fp:strict` belirtildiğinde, Visual Studio 2010 tarafından oluşturulan kod, deyimler aracılığıyla aradaki sayı olmayan (NaN) değerleri doğru bir biçimde yaymayabilir. Bu nedenle, eski derleyicilerde sayısal bir sonuç veren bazı ifadeler artık doğru bir NaN sonucu üretebilir. Ayrıca, `/fp:fast` için etkinleştirilmiş kod iyileştirmeleri artık daha fazla işlemci özelliğinden yararlandığından farklar görebilirsiniz. Bu iyileştirmeler daha az yönerge kullanabilir, ancak daha önce görünür olan bazı ara işlemler kaldırılmış olduğundan oluşturulan sonuçları etkileyebilir.

## <a name="how-to-get-identical-results"></a>Özdeş sonuçlar nasıl alınır?

Çoğu durumda, en yeni derleyicilerde ve kitaplıklarda kayan nokta değişiklikleri daha hızlı veya daha doğru davranışa veya her ikisine de neden olacak. SSE2 yönergeleri x87 yönergelerini değiştirse bile daha iyi işlemci güç performansı görebilirsiniz. Ancak, eski bir derleyicinin kayan nokta davranışını tam olarak çoğaltmanız gereken bir kodunuz varsa, Visual Studio Native multi-hedefleme yeteneklerini kullanmayı düşünün ve etkilenen projeyi eski araç takımı ile derleyin. Daha fazla bilgi için bkz. [Eski projeler oluşturmak Için Visual Studio 'da yerel çoklu sürüm kullanımını kullanma](use-native-multi-targeting.md).

## <a name="see-also"></a>Ayrıca bkz.

[Projeleri Visual 'ın önceki sürümlerinden yükseltmeC++](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)