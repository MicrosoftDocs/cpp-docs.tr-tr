---
title: 1.3 Yürütme Modeli
ms.date: 11/04/2016
ms.assetid: 85ae8bc4-5bf0-45e0-a45f-02de9adaf716
ms.openlocfilehash: 291bf71159cc681916d19649cfa12298d0929cc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491581"
---
# <a name="13-execution-model"></a>1.3 Yürütme Modeli

OpenMP Paralel yürütme çatal katılım modelini kullanır. Bu çatal katılım modeli çeşitli sorunları çözmek için yararlı olabilir, ancak büyük dizi tabanlı uygulamalar için biraz uyarlanmıştır. OpenMP paralel programları (birden çok iş parçacığı yürütme ve tam bir OpenMP desteği kitaplık) gibi her ikisi de doğru şekilde yürütülecektir destek programları ve sıralı programlar (yönergeleri yok sayıldı ve basit bir OpenMP saptamalar kitaplık) olarak hazırlanmıştır. Ancak, mümkündür ve sıralı olarak çalıştırıldığında doğru şekilde davranmaz bir program geliştirmek için izin. Ayrıca, farklı bir paralellik derecesi sayısal işlemlerinin İlişkilendirmedeki değişiklikler nedeniyle farklı sayısal sonuçlar neden olabilir. Örneğin, bir seri toplama azaltma ayrıca ilişkilerinin paralel azaltma değerinden farklı bir desen olabilir. Bu farklı ilişkilendirmeleri, kayan nokta ekleme sonuçlarını değişebilir.

OpenMP C/C++ API ile yazılmış bir program yürütme adlı tek bir iş parçacığı olarak yürütülmesine başlar *ana iş parçacığı*. İlk paralel yapısıyla karşılaştı kadar ana iş parçacığını bir seri bölgede yürütür. OpenMP C/C++ API **paralel** yönergesi, paralel bir yapı oluşturur. Bir paralel yapısıyla karşılaştı, iş parçacıklarının takım ana iş parçacığı oluşturur ve ana ekibi ana sunucunuz olur. Takım her bir iş parçacığı dinamik kapsamını iş paylaşım yapıları dışında bir paralel bölgenin içinde deyimleri yürütür. Takım aynı sırada tüm iş parçacıkları tarafından iş paylaşım yapıları karşılaştı gerekir ve deyimleri ilişkili yapısal bloğunun içinde bir veya daha fazla iş parçacığı tarafından yürütülür. Bir iş paylaşımı yapısı sonunda kapsanan engel bir `nowait` yan tümcesi, takımın tüm iş parçacıkları tarafından yürütülür.

Bir iş parçacığı paylaşılan bir nesnenin değiştirirse, yalnızca kendi yürütme ortamı, aynı zamanda bu programın diğer iş parçacıklarını etkiler. Değiştirme, nesne geçici olarak bildirilirse (temel dilinde tanımlandığı şekilde), açısından bir başka iş parçacıklarının, sonraki bir dizi noktası tamamlanması sağlanır. Değişiklik Aksi takdirde, ilk değiştirme iş parçacığı sonra tamamlanması sağlanır ve ardından (veya aynı anda) diğer iş parçacıkları, karşılaştığınız bir **Temizleme** (örtük veya açık) nesneyi belirtir yönergesi. Dikkat edin **Temizleme** diğer OpenMP yönergeleri tarafından kapsanan yönergeleri yan etkilerini istenen sıralama emin olmak yeterli değildir, bu ek, açıkça sağlamak için programcının sorumluluğundadır  **Flush** yönergeleri.

Paralel yapı tamamlandıktan sonra takım iş parçacıkları örtük bir engel eşitleyebilir ve yalnızca ana iş parçacığını yürütmeye devam eder. Tek bir programda herhangi bir sayıda paralel yapılar belirtilebilir. Sonuç olarak, bir program çatalını oluşturmanız ve yürütme sırasında birçok kez katılın.

OpenMP C/C++ API yönergeleri içinde paralel yapılar çağrılır işlevleri kullanmak programcılar sağlar. Paralel bir yapı içindeki sözcük kapsamı görünmez, ancak dinamik kapsam şekilde yönergeleri çağrılır *yalnız bırakılmış* yönergeleri. Yalnız bırakılmış yönergeleri programcılar kendi programın önemli bölümleri, yalnızca küçük değişiklikler ile paralel sıralı program yürütme yeteneği verir. Bu işlevsellik ile kullanıcılar program çağrısı ağacında üst düzeylerinde paralel yapılar kod ve çağrılan işlevlerin hiçbirinde yürütmesini denetlemek için yönergeleri kullanın.

C ve C++ eşitlenmemiş çağrıları, aynı dosyaya yazmak işlevleri farklı iş parçacıkları tarafından yazılan veriler belirleyici olmayan bir sırada göründüğü çıkış sonuçlanabilir çıktı. Benzer şekilde, aynı dosyadan okunan işlevleri giriş eşitlenmemiş çağrıları belirleyici olmayan bir sırada veri okuyabilirsiniz. Her iş parçacığı farklı bir dosyaya erişen şekilde eşitlenmemiş g/ç kullanımını aynı sonuçları seri yürütme g/ç işlevleri üretir.