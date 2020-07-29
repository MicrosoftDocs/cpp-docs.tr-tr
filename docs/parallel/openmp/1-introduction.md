---
title: 1. Giriş
ms.date: 01/16/2019
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
ms.openlocfilehash: 60a5090814b722cc0d9f6e51ab9038e697a4ed2a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231656"
---
# <a name="1-introduction"></a>1. Giriş

Bu belge, C ve C++ programlarında paylaşılan bellek paralelliğini belirtmek için kullanabileceğiniz bir derleyici yönergeleri, kitaplık işlevleri ve ortam değişkenlerinin koleksiyonunu belirtir. Bu belgede açıklanan işlevsellik, her topluca *OpenMP C/C++ uygulama programı arabirimi (API)* olarak bilinir. Bu belirtimin amacı, bir programın farklı satıcıların paylaşılan bellek mimarilerine taşınabilmesini sağlayan paralel programlama için bir model sağlamaktır. Birçok satıcının derleyicileri, OpenMP C/C++ API 'sini destekler. OpenMP *FORTRAN uygulama programı arabirimi*de dahil olmak üzere OpenMP hakkında daha fazla bilgi aşağıdaki Web sitesinde bulunabilir:

[https://www.openmp.org](https://www.openmp.org)

Bu belgede tanımlanan yönergeler, kitaplık işlevleri ve ortam değişkenleri, taşınmalarına izin verirken paralel programlar oluşturmanıza ve yönetmenize olanak sağlar. Yönergeler, tek program birden çok veri (SPMD) yapıları, çalışma paylaşımı yapıları ve eşitleme yapıları ile C ve C++ sıralı programlama modelini genişletir. Ayrıca, verilerin paylaşılması ve limanların de desteklenir. OpenMP C ve C++ API 'sini destekleyen derleyiciler, tüm OpenMP derleyicisi yönergelerinin yorumlanmasını etkinleştiren ve bu derleyiciye izin veren bir komut satırı seçeneği içerir.

## <a name="11-scope"></a>1.1 Kapsam

Bu belirtim, yalnızca derleyicinin ve çalışma zamanı sisteminin, programı paralel olarak yürütmek için hangi eylemleri yaptığını açıkça tanımladığınız, Kullanıcı tarafından yönlendirilen paralelleştirme özelliğini ele alır. OpenMP C ve C++ uygulamaları, bağımlılıkları, çakışmaları, kilitlenmeleri, yarış koşullarını veya hatalı program yürütmeye neden olan diğer sorunları denetlemek için gerekli değildir. OpenMP C ve C++ API yapılarını kullanan uygulamanın doğru şekilde yürütüldüğünü sağlamaktan siz sorumlusunuz. Bu belgede paralelleştirme konusunda yardımcı olmak için derleyicinin ürettiği otomatik paralelleştirme ve yönergeler derleyici tarafından ele alınmıştır.

## <a name="12-definition-of-terms"></a>1,2 terim tanımı

Bu belgede aşağıdaki terimler kullanılır:

- barrier

  Bir ekipteki tüm iş parçacıklarının ulaşması gereken bir eşitleme noktası.  Her bir iş parçacığı, ekipteki tüm iş parçacıklarının bu noktaya gelmesini bekler. Uygulama tarafından oluşturulan yönergeler ve örtük engelleri tarafından tanımlanan açık engelleri vardır.

- oluşturma

  Yapı bir ifadedir. Bir yönergeden oluşur ve ardından yapısal bir blok gelir. Bazı yönergeler bir yapının parçası değildir. (Bkz. [Ek C](c-openmp-c-and-cpp-grammar.md)'de *OpenMP-Directive* ).

- deki

  Bir C veya C++ `#pragma` sonrasında `omp` tanımlayıcı, diğer metin ve yeni bir satır. Yönerge program davranışını belirtir.

- dinamik kapsam

  *Sözcük*temelli olmayan tüm deyimler ve bir işlev içindeki deyimler, sözcük temelli kapsam içindeki deyimlerin yürütülmesi sonucu olarak yürütülür. Bir dinamik kapsam, *bölge*olarak da adlandırılır.

- sözcük temelli kapsam

  *Yapılandırılmış bir blok*içinde Sözcüksel olarak tutulan deyimler.

- Ana iş parçacığı

  Bir *paralel bölge* girildiğinde ekip oluşturan iş parçacığı.

- paralel bölge

  Bir OpenMP paralel yapısına bağlanan ve birçok iş parçacığı tarafından yürütülebilecek deyimler.

- private

  Özel değişken, başvuruyu yapan iş parçacığına özgü bir depolama bloğu adlandırır. Bir değişkenin özel olduğunu belirtmek için birkaç yol vardır: bir paralel bölge, yönerge,,,, veya yan tümce içindeki bir tanım veya `threadprivate` `private` `firstprivate` `lastprivate` `reduction` değişkenin **`for`** **`for`** bir veya yönergesinin hemen ardından bir döngüsünde döngü denetim değişkeni olarak kullanılması `for` `parallel for` .

- region

  Dinamik bir uzantı.

- seri bölge

  Yalnızca *ana iş parçacığı* tarafından, herhangi bir *paralel bölgenin*dinamik kapsamı dışında yürütülen deyimler.

- Serialize

  Paralel bir yapıyı şu ile yürütmek için:

  - yalnızca tek bir iş parçacığından oluşan iş parçacığı ekibi (Bu paralel yapının ana iş parçacığı),

  - yapılandırılmış blok içindeki deyimler için seri yürütme sırası (bloğun bir paralel yapının parçası olmadığı sıra) ve

  - tarafından döndürülen değer üzerinde hiçbir etkisi yoktur `omp_in_parallel()` (iç içe geçmiş paralel yapıların etkileri dışında).

- shared

  Paylaşılan değişken, tek bir depolama bloğunu adlandırır. Bu değişkene erişen bir ekipteki tüm iş parçacıkları bu tek depolama bloğuna de erişir.

- yapılandırılmış blok

  Yapısal bir blok, tek bir giriş ve tek bir çıkış içeren bir ifadedir (tek veya bileşik). Bir deyimin içine veya dışına atlanmak için, bu deyim yapılandırılmış bir bloğudur. (Bu kural bir öğesine `longjmp` çağrı içerir (3C) veya kullanımı `throw` , bir çağrısına `exit` izin verilse de.) Yürütmesi her zaman açılışında başlıyorsa `{` ve her zaman kapanışda sona erdiğinde `}` , bileşik bir ifade yapısal bir bloğudur. **`try`** Karşılık gelen bileşik deyimin içinde yer aldığı `{` ve `}` yapılandırılmış bir blok olması halinde, bir ifade deyimi, seçim deyimi, yineleme deyimi veya blok yapısal bir bloğudur. Bir sıçrama bildirimi, etiketli deyim veya bildirim bildirimi yapısal bir blok değildir.

- ekip

  Bir veya daha fazla iş parçacığı bir yapının yürütülmesinde birlikte çalışıyor.

- thread

  Bir yürütme varlığı, denetimin seri akışı, özel değişkenler kümesi ve paylaşılan değişkenlere erişim.

- değişken

  İsteğe bağlı olarak, bir nesneyi isimleyen ad alanı adlarıyla nitelenmiş bir tanımlayıcı.

## <a name="13-execution-model"></a>1,3 yürütme modeli

OpenMP, paralel yürütmenin çatal-JOIN modelini kullanır. Bu çatal ekleme modeli çeşitli sorunları çözmek için yararlı olabilir, ancak büyük dizi tabanlı uygulamalar için tasarlanmıştır. OpenMP, paralel programlar (birçok yürütmenin iş parçacığı ve tam bir OpenMP destek kitaplığı) gibi doğru şekilde yürütülen programları desteklemek için tasarlanmıştır. Ayrıca, sıralı programlar olarak doğru şekilde yürütülen programlar için (yönergeler yok sayılır ve basit bir OpenMP saplamaları kitaplığı). Ancak, sıralı olarak yürütüldüğünde düzgün davranmeyen bir program geliştirmeye izin verilir ve bu mümkündür. Ayrıca, sayısal işlemlerin ilişkilendirmesinde yapılan değişiklikler nedeniyle paralellik derecenin farklı dereceleri farklı sayısal sonuçlara neden olabilir. Örneğin, bir seri ek azaltma, paralel bir azaltmaya göre farklı bir ek ilişkilendirme düzenine sahip olabilir. Bu farklı ilişkilendirmeler kayan nokta ekleme sonuçlarını değiştirebilir.

OpenMP C/C++ API 'SI ile yazılmış bir program yürütmeye, *ana iş parçacığı*adlı tek bir yürütme iş parçacığı olarak başlar. Ana iş parçacığı, ilk paralel yapı ile karşılaşana kadar bir seri bölgede yürütülür. OpenMP C/C++ API 'sinde, `parallel` yönerge paralel bir yapı oluşturur. Paralel bir yapı ile karşılaşıldığında, ana iş parçacığı bir iş parçacığı grubu oluşturur ve ana ekip ekibi ana haline gelir. Ekipteki her iş parçacığı, iş paylaşımı yapıları dışında, bir paralel bölgenin dinamik kapsamı içinde deyimleri yürütür. Ekipteki tüm iş parçacıkları aynı sırada iş paylaşımı yapıları ile karşılaşmalıdır ve bir veya daha fazla iş parçacığı ilişkili yapılandırılmış blok içinde deyimleri yürütür. Bir yan tümce olmadan iş paylaşımı yapısının sonunda örtülü olan engeli, `nowait` ekipteki tüm iş parçacıkları tarafından yürütülür.

Bir iş parçacığı paylaşılan bir nesneyi değiştirirse, yalnızca kendi yürütme ortamını değil, programdaki diğer iş parçacıklarını da etkiler. Değişiklik, başka bir iş parçacığının görünüm noktasından, bir sonraki dizi noktasında (temel dilde tanımlandığı şekilde), yalnızca nesnenin geçici olarak bildirildiği durumlarda tamamlanma garantisi vardır. Aksi takdirde, değişikliğin ilk değişiklik parçacığından sonra tamamlanmasını garanti edilir. Diğer iş parçacıkları daha sonra (veya eşzamanlı olarak) `flush` nesneyi belirten bir yönerge (örtük veya açık olarak) görürsünüz. `flush`Diğer OpenMP yönergeleri tarafından kapsanan yönergeler yan etkilerin doğru sıralamasını garanti etmez, bu, ek ve açık yönergeler sağlamak için programcının sorumluluğundadır `flush` .

Paralel yapıyı tamamladıktan sonra ekipteki iş parçacıkları örtük bir engelde eşitlenir ve yalnızca ana iş parçacığı yürütmeye devam eder. Tek bir programda herhangi bir sayıda paralel yapı belirtilebilir. Sonuç olarak, bir program yürütme sırasında birçok kez çatalla katılabilir.

OpenMP C/C++ API 'SI, programcıların paralel yapıların içinden çağrılan işlevlerde yönergeler kullanmasına izin verir. Paralel bir yapının sözcük temelli kapsamı içinde görünmeyen ancak dinamik ölçüde yer alan yönergeler *yalnız bırakılmış* yönergeler olarak adlandırılır. Yalnız bırakılmış yönergeler sayesinde, programcılar programın büyük kısımlarını paralel olarak yürütebilir ve yalnızca en az sayıda sıralı programda değişiklik yapabilir. Bu işlevle, program çağrı ağacının en üst düzeylerinde paralel yapılar kodlayabilirsiniz ve çağrılan işlevlerde yürütmeyi denetlemek için yönergeleri kullanabilirsiniz.

Aynı dosyaya yazılan C ve C++ çıkış işlevlerine yönelik eşitlenmemiş çağrılar, farklı iş parçacıkları tarafından yazılan verilerin belirleyici olmayan sırada göründüğü çıkışlara neden olabilir. Benzer şekilde, aynı dosyadan okunan giriş işlevlerine yönelik eşitlenmemiş çağrılar, verileri belirleyici olmayan sırada okuyabilir. Her iş parçacığı farklı bir dosyaya eriştiği için, uyumsuz g/ç kullanımı, g/ç işlevlerinin seri yürütmesi ile aynı sonuçları üretir.

## <a name="14-compliance"></a>1.4 Uyumluluk

*OpenMP c* /C++ API 'sinin uygulanması, Bölüm 1, 2, 3, 4 ve ek C 'de düzenlendiği şekilde, bu belirtimin tüm öğelerinin semantiğini algılayıp korur. Appendıces A, B, D, E ve F yalnızca bilgi amaçlıdır ve belirtimin bir parçası değildir. API 'nin yalnızca bir alt kümesini içeren uygulamalar OpenMP uyumlu değildir.

OpenMP C ve C++ API 'SI, bir uygulama tarafından desteklenen temel dilin uzantısıdır. Temel dil, bu belgede görüntülenen bir dil yapısını veya uzantıyı desteklemiyorsa, bunu desteklemek için OpenMP uygulamasının gerekli değildir.

Tüm standart C ve C++ kitaplığı işlevleri ve yerleşik işlevler (derleyicinin belirli bir bilgisine sahip olduğu işlevler) iş parçacığı açısından güvenli olmalıdır. Bir paralel bölgedeki farklı iş parçacıkları tarafından iş parçacığı güvenli işlevlerinin eşitlenmemiş bir şekilde kullanılması tanımsız bir davranış oluşturmaz. Ancak, davranış bir seri bölge ile aynı olmayabilir. (Rastgele sayı oluşturma işlevi bir örnektir.)

OpenMP C/C++ API 'SI, belirli bir davranışın *uygulama tanımlı* olduğunu belirtir. Bu durumlarda davranışını tanımlamak ve belgelemek için uyumlu bir OpenMP uygulamasının olması gerekir. Uygulama tanımlı davranışların bir listesi için bkz. [ek E](e-implementation-defined-behaviors-in-openmp-c-cpp.md).

## <a name="15-normative-references"></a>1,5 normatif başvurular

- ISO/ıEC 9899:1999, *bilgi teknolojisi-programlama dilleri-C*. Bu OpenMP API 'SI belirtimi, C99 olarak ISO/ıEC 9899:1999 anlamına gelir.

- ISO/ıEC 9899:1990, *bilgi teknolojisi-programlama dilleri-C*. Bu OpenMP API 'SI belirtimi, C90 olarak ISO/ıEC 9899:1990 anlamına gelir.

- ISO/ıEC 14882:1998, *bilgi teknolojisi-programlama dilleri-C++*. Bu OpenMP API 'SI belirtimi, C++ olarak ISO/ıEC 14882:1998 anlamına gelir.

Bu OpenMP API 'SI belirtiminin C 'ye başvurduğu, uygulama tarafından desteklenen temel dile başvuru yapılır.

## <a name="16-organization"></a>1.6 Organizasyon

- [Çalışma zamanı kitaplık işlevleri](3-run-time-library-functions.md)
- [Ortam değişkenleri](4-environment-variables.md)
- [OpenMP C/C++’daki uygulama tanımlı davranışlar](e-implementation-defined-behaviors-in-openmp-c-cpp.md)
- [OpenMP C/C++ sürüm 2,0 ' deki yeni özellikler](f-new-features-and-clarifications-in-version-2-0.md)
