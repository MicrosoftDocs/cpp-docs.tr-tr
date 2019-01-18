---
title: 1. Giriş
ms.date: 01/16/2019
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
ms.openlocfilehash: 99020e9cf8c38bcfaeefdf5c31663b3e66352556
ms.sourcegitcommit: 2ebbf8093fadb9a1b78a4381439bcd5c01a89267
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2019
ms.locfileid: "54397309"
---
# <a name="1-introduction"></a>1. Giriş

Bu belge, derleyici yönergeleri, kitaplık işlevleri ve paylaşılan bellek paralellik C ve C++ programlarında belirtmek için kullanabileceğiniz ortam değişkenleri koleksiyonu belirtir. Bu belgede açıklanan işlevselliğini toplu olarak bilinen *OpenMP C/C++ uygulama programı arabirimi (API)*. Bu belirtim paralel, programlama için bir model sağlamak için bir program, farklı satıcıların paylaşılan bellek mimariler arasında taşınabilir olarak tanır hedefidir. OpenMP C/C++ API birçok satıcılardan derleyiciler destekler. OpenMP hakkında daha fazla bilgi dahil olmak üzere *OpenMP Fortran uygulaması Program arabirimi*, aşağıdaki web sitesinde bulunabilir:

[https://www.openmp.org](https://www.openmp.org)

Yönergeleri, kitaplık işlevleri ve bu belgede tanımlanan ortam değişkenleri oluşturma ve paralel programlar taşınabilirlik verirken yönetmenize olanak sağlar. Yönergeleri C ve C++ sıralı programlama modeli (SPMD) birden çok veri yapıları tek programı, iş paylaşım yapıları ve eşitleme yapılarını genişletin. Bunlar ayrıca paylaşım ve veri privatization destekler. OpenMP C ve C++ API destekleyen derleyiciler etkinleştirir ve tüm OpenMP derleyici yönergeleri yorumu sağlayan derleyici komut satırı seçeneği içerir.

## <a name="11-scope"></a>1.1 Kapsam

Bu belirtim hangi eylemleri açıkça tanımlar burada görüntülerle yalnızca kullanıcı yönlendirilmiş paralelleştirme, derleyici kapsar ve çalışma zamanı sistemi gerçekleştirin program paralel olarak yürütmek için. OpenMP C ve C++ uygulamaları, bağımlılıkları, çakışmaları, kilitlenmeleri, yarış durumları veya yanlış programın yürütülmesine neden başka sorunlar olup olmadığını denetlemek için gerekli değildir. OpenMP C ve C++ API yapıları kullanarak uygulamanın düzgün çalıştığından emin olmak sizin sorumluluğunuzdadır. Derleyici tarafından oluşturulan otomatik paralelleştirme ve derleyici yönergeleri gibi paralelleştirme yardımcı olması için bu belgede ele alınan değildir.

## <a name="12-definition-of-terms"></a>1.2 tanımı koşulları

Bu belgede aşağıdaki terimler kullanılır:

- barrier

  Takım tüm iş parçacıklarının ulaşması gereken bir eşitleme noktası.  Her iş parçacığı, takımın tüm iş parçacıkları bu noktada geldiğinde bekler. Yönergeleri ve uygulama tarafından oluşturulan örtük engelleri tarafından tanımlanan açık engelleri vardır.

- Yapısı

  Bir deyimi bir yapıdır. Bir yönergesi, oluşan bir yapılandırılmış bloğu tarafından izlenen. Yönergelerden bazıları bir yapısı dahil değildir. (Bkz *openmp yönergesi* içinde [ek C](c-openmp-c-and-cpp-grammar.md)).

- Yönergesi

  Bir C veya C++ `#pragma` ardından `omp` tanımlayıcısı, diğer metin ve yeni bir satır. Yönerge, programın davranışını belirtir.

- dinamik kapsam

  Tüm deyimlerinde *sözcük kapsamı*, sözcük kapsamı içindeki deyimler yürütme sonucu olarak çalıştırılan bir işlev içinde herhangi bir deyimle artı. Dinamik kapsam olarak da adlandırılan bir *bölge*.

- sözcük kapsamı

  Deyimleri içinde sözcüksel olarak tutulan bir *yapısal bloğunun*.

- Ana iş parçacığı

  Bir ekip oluşturan iş parçacığı, bir *paralel bölgenin* girilir.

- Paralel bölgenin

  Bir OpenMP paralel yapı bağlayın ve birçok iş parçacığı tarafından yürütülen deyimleri.

- private

  Özel bir değişken başvurusu yapılmalıdır iş parçacığı için benzersiz olan depolama bloğu adları. Bir değişkeni özel olduğunu belirtmek için birkaç yolu vardır: bir paralel bölgenin içinde tanımını bir `threadprivate` yönergesi, bir `private`, `firstprivate`, `lastprivate`, veya `reduction` yan tümcesi veya değişken olarak kullanıldığında bir `for`döngü denetim değişkeni olarak bir `for` hemen döngü bir `for` veya `parallel for` yönergesi.

- bölge

  Dinamik bir uzantı.

- Seri bölge

  Yalnızca yürütülen deyimleri *ana iş parçacığı* herhangi dinamik kapsam dışında *paralel bölgenin*.

- Seri hale getirme

  Paralel bir yapısı ile çalıştırmak için:

  - bir takım (ana iş parçacığını paralel bu yapı için olan) yalnızca tek bir iş parçacığı oluşan bir iş parçacığı sayısı

  - Seri (aynı sıralama blok bir paralel yapısı parçası yokmuş gibi) yapılandırılmış bloğundaki ifadeler için yürütme sırasını ve

  - tarafından döndürülen değer üzerinde hiçbir etkisi `omp_in_parallel()` (paralel yapılar iç içe herhangi etkileri dışında).

- shared

  Tek bir blok depolama paylaşılan bir değişken adı. Bu değişken erişen tüm iş parçacıklarının bir takım da bu tek bir blok depolama erişin.

- Yapısal bloğunun

  Bir yapısal bloğunun tek bir giriş ve tek bir çıkış (tek veya bileşik) bir ifadedir. Bir atlama içine veya dışına bir deyimi varsa, bu deyimi bir yapılandırılmış taşıdır. (Bu kural bir çağrı içerdiğine `longjmp`(3C) veya kullanımını `throw`, çağrı ancak `exit` izin verilir.) Her zaman yürütme sırasında açma başlıyorsa `{` ve kapatma sırasında her zaman sona eren `}`, bileşik deyim yapılandırılmış bir bloğudur. Bir ifade deyimi, seçim deyimi, yineleme deyiminin veya `try` bloğu yapısal bloğunun karşılık gelen bileşik deyim, kapsayan tarafından aldıysanız `{` ve `}` yapısal bloğunun olacaktır. Atlama deyimi, etiketli deyim veya bildirim deyimi bir yapısal bloğunun değildir.

- Takım

  Bir yapı içinde yürütülmesini kurduğuna ilişkin bir veya daha fazla iş parçacığı.

- thread

  Bir yürütme seri bir denetim akışını, bir dizi özel değişkenleri ve paylaşılan değişkenlerine erişimi olan varlık.

- değişken

  İsteğe bağlı olarak ad alanı adları, tam bir tanımlayıcı, bir nesne adları.

## <a name="13-execution-model"></a>1.3 yürütme modeli

OpenMP Paralel yürütme çatal katılım modelini kullanır. Bu çatal katılım modeli çeşitli sorunları çözmek için yararlı olabilir, ancak büyük dizi tabanlı uygulamalar için uygun hale getirilir. OpenMP, hem paralel programlar (kitaplığını birçok iş parçacığı yürütme ve tam bir OpenMP desteği) olarak doğru bir şekilde yürütülen programlar desteklemek üzere tasarlanmıştır. Ayrıca, doğru olarak sıralı programlar (yönergeleri yok sayıldı ve basit bir OpenMP saptamalar kitaplık) yürütülen programlar için bir hizmettir. Ancak mümkündür ve sıralı olarak çalıştırıldığında doğru şekilde davranmaz değil bir program geliştirmek için izin verilir. Ayrıca, farklı bir paralellik derecesi sayısal işlemlerinin İlişkilendirmedeki değişiklikler nedeniyle farklı sayısal sonuçlar neden olabilir. Örneğin, bir seri toplama azaltma ayrıca ilişkilerinin paralel azaltma değerinden farklı bir desen olabilir. Bu farklı ilişkilendirmeleri, kayan nokta ekleme sonuçlarını değişebilir.

OpenMP C/C++ API ile yazılmış bir program yürütme adlı tek bir iş parçacığı olarak yürütülmesine başlar *ana iş parçacığı*. İlk paralel yapısıyla karşılaştı kadar ana iş parçacığını bir seri bölgede yürütür. OpenMP C/C++ API `parallel` yönergesi, paralel bir yapı oluşturur. Bir paralel yapısıyla karşılaştı, iş parçacıklarının takım ana iş parçacığı oluşturur ve ana ekibi ana sunucunuz olur. Takım her bir iş parçacığı dinamik kapsamını iş paylaşım yapıları dışında bir paralel bölgenin içinde deyimleri yürütür. Takım tüm iş parçacıklarının iş paylaşım yapıları aynı sırada karşılaşırsanız gerekir ve bir veya daha fazla iş parçacığı ilişkili yapılandırılmış bloğundaki ifadeleri çalıştırır. Bir iş paylaşımı yapısı sonunda kapsanan engel bir `nowait` yan tümcesi, takımın tüm iş parçacıkları tarafından yürütülür.

Bir iş parçacığı paylaşılan bir nesnenin değiştirirse, yalnızca kendi yürütme ortamı, aynı zamanda bu programın diğer iş parçacıklarını etkiler. Değiştirme, nesne geçici olarak bildirilirse (temel dilinde tanımlandığı şekilde), açısından sonraki dizisi noktasına başka bir iş parçacığının tamamlanması sağlanır. Aksi takdirde, değişiklik ilk değiştirme iş parçacığı sonra tamamlanması sağlanır. Diğer iş parçalarının sonra (veya aynı anda) bkz bir `flush` nesneyi (örtük veya açık olarak) belirtir. yönergesi. Zaman `flush` diğer OpenMP yönergeleri tarafından kapsanan yönergeleri yan etkilerini doğru sıralama garanti yoktur, bu ek, açıkça sağlamak için programcının sorumluluğundadır `flush` yönergeleri.

Paralel yapı tamamlandıktan sonra takım iş parçacıkları örtük bir engel eşitleyebilir ve yalnızca ana iş parçacığını yürütmeye devam eder. Tek bir programda herhangi bir sayıda paralel yapılar belirtilebilir. Sonuç olarak, bir program çatalını oluşturmanız ve yürütme sırasında birçok kez katılın.

OpenMP C/C++ API yönergeleri içinde paralel yapılar çağrılır işlevleri kullanmak programcılar sağlar. Paralel bir yapı içindeki sözcük kapsamı görünmez, ancak dinamik kapsam şekilde yönergeleri çağrılır *yalnız bırakılmış* yönergeleri. Yalnız bırakılmış yönergeleri ile paralel olarak sıralı program sadece küçük değişiklikler, programın önemli bölümleri programcılar yürütebilir. Bu işlevsellik ile program çağrısı ağacında üst düzeylerinde paralel yapılar kod ve çağrılan işlevlerin hiçbirinde yürütmesini denetlemek için yönergeleri kullanın.

C ve C++ eşitlenmemiş çağrıları, aynı dosyaya yazmak işlevleri farklı iş parçacıkları tarafından yazılan veriler belirleyici olmayan bir sırada göründüğü çıkış sonuçlanabilir çıktı. Benzer şekilde, aynı dosyadan okunan işlevleri giriş eşitlenmemiş çağrıları belirleyici olmayan bir sırada veri okuyabilirsiniz. Her iş parçacığı farklı bir dosyaya erişen şekilde eşitlenmemiş g/ç kullanımını aynı sonuçları seri yürütme g/ç işlevleri üretir.

## <a name="14-compliance"></a>1.4 Uyumluluk

OpenMP C/C++ API uygulamasıdır *OpenMP uyumlu* tanır ve bu belirtim tüm öğelerini semantiği olarak bölümlerde 1, 2, 3, 4, normal bir kutudur korur ve ek c ek A, B, D, E ve F içindir bilgiler yalnızca amacıyla ve belirtiminin parçası değildir. Yalnızca bir API alt kümesini içeren uygulamalar OpenMP ile uyumlu değildir.

OpenMP C ve C++ API uygulaması tarafından desteklenen temel dil için bir uzantısıdır. Temel dil dil yapısı veya görüntülenen uzantısı desteklemiyorsa ve bu belgede OpenMP uygulaması bunu desteklemek için gerekli değildir.

Tüm standart C ve C++ Kitaplığı işlevleri ve yerleşik işlevler (diğer bir deyişle, İşlevler derleyici belirli bilgi olduğu) iş parçacığı açısından güvenli olması gerekir. Bir paralel bölgenin içinde farklı iş parçacıkları tarafından iş parçacığı açısından güvenli işlevlerin eşitlenmemiş kullanımını tanımsız davranış oluşturmuyor. Ancak, davranışı seri bir bölge ile aynı olmayabilir. (Bir rastgele sayı oluşturma işlevi, örnek verilebilir.)

OpenMP C/C++ API belirli bir davranış belirtir *uygulama tanımlı.* Uyumlu bir OpenMP uygulama tanımlamak ve bu gibi durumlarda davranışını belge için gereklidir. Uygulama tanımlı davranışlar bir listesi için bkz. [ek E](e-implementation-defined-behaviors-in-openmp-c-cpp.md).

## <a name="15-normative-references"></a>1.5 örnek oluşturan başvurular

- ISO/IEC 9899:1999 *bilgi teknolojisi - programlama dilleri - C*. Bu OpenMP API belirtimi için ISO/IEC 9899:1999 C99 ifade eder.

- ISO/IEC 9899:1990 *bilgi teknolojisi - programlama dilleri - C*. Bu OpenMP API belirtimi için ISO/IEC 9899:1990 C90 ifade eder.

- ISO/IEC 14882:1998 *bilgi teknolojisi - programlama dilleri - C++*. Bu OpenMP API belirtimine C++ için ISO/IEC 14882:1998 ifade eder.

Bu OpenMP API belirtimine C'ye başvuran olduğunda, uygulama tarafından desteklenen temel dil için başvuru yapılır.

## <a name="16-organization"></a>1.6 Organizasyon

- [Çalışma zamanı kitaplık işlevleri](3-run-time-library-functions.md)
- [Ortam değişkenleri](4-environment-variables.md)
- [OpenMP C/C++'daki uygulama tanımlı davranışlar](e-implementation-defined-behaviors-in-openmp-c-cpp.md)
- [OpenMP C/C++ sürüm 2.0 yenilikleri](f-new-features-and-clarifications-in-version-2-0.md)
