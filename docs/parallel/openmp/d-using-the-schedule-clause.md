---
title: D. Zamanlama yan tümcesi
ms.date: 01/22/2019
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
ms.openlocfilehash: 89e011784c5cccedc4a75f38d553458ea2e5d7e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362887"
---
# <a name="d-the-schedule-clause"></a>D. Zamanlama yan tümcesi

Bir paralel bölgenin sonuna en az bir engel olan ve başka engelleri içindeki olabilir. Her engel diğer takım üyelerinin gelmesi son iş parçacığı için beklemeniz gerekir. Böylece engel yaklaşık aynı zamanda tüm iş parçacıklarının ulaşırsınız bu bekleme süresi en aza indirmek için paylaşılan iş dağıtılmalıdır. Paylaşılan bazıları iş bulunan `for` oluşturur, `schedule` yan tümcesi bu amaç için kullanılabilir.

Zamanlama için seçtiğiniz aynı nesneleri yinelenen başvurular olduğunda bir `for` yapısı temelde önbellekler ve bellek erişim zamanları Tekdüzen olup boyutunu ve durum gibi bellek sisteminin özelliklerine göre belirlenemedi veya nonuniform. Bu tür konular bazı iş parçacıkları bazı döngüler görece daha az iş atanmış olsa bile her bir iş parçacığı aynı döngüleri, bir dizi bir dizinin öğeleri kümesini tutarlı bir şekilde başvurmak için tercih yapabilir. Bu ayar kullanılarak yapılabilir `static` döngüler için aynı sınırları ile zamanlama. Aşağıdaki örnekte, sıfır olarak ikinci döngüsünde, alt sınır olsa bile kullanılan `k` zamanlama önemli değilse daha doğal olacaktır.

```cpp
#pragma omp parallel
{
#pragma omp for schedule(static)
  for(i=0; i<n; i++)
    a[i] = work1(i);
#pragma omp for schedule(static)
  for(i=0; i<n; i++)
    if(i>=k) a[i] += work2(i);
}
```

Kalan örneklerde, bu bellek kabul erişimi baskın göz önünde bulundurarak değil. Aksi belirtilmediği sürece, tüm iş parçacıklarının karşılaştırılabilir hesaplama kaynaklarını alır. Bu gibi durumlarda, zamanlama için tercih ettiğiniz bir `for` yapısı, en yakın önceki arasında gerçekleştirilecek olan paylaşılan iş bağlıdır ve süreçlerinin önündeki engelleri örtük kapanış engel veya varsa yaklaşan engel en yakın bir `nowait` yan tümcesi. Zamanlamayı her tür için bu zamanlama türü nasıl en iyi seçenek olabilir kısa bir örnek gösterir. Kısa bir açıklama her bir örnek aşağıda verilmiştir.

`static` Zamanlama en basit durum için tek bir içeren bir paralel bölgenin uygun ayrıca `for` , aynı iş miktarı her bir yineleme oluşturun.

```cpp
#pragma omp parallel for schedule(static)
for(i=0; i<n; i++) {
  invariant_amount_of_work(i);
}
```

`static` Zamanlama özelliklerine göre nitelenen, her iş parçacığının yaklaşık aynı sayıda yineleme başka bir iş parçacığı alır ve her bir iş parçacığı atanmış yinelemeleri bağımsız olarak belirleyebilirsiniz. Bu nedenle eşitleme işi dağıtmak için gereklidir ve her yinelemede aynı miktarda iş gerektirdiğini varsayım altında tüm iş parçacıkları, aynı anda ancak ondan haberdar tamamlanmalıdır.

Bir takımın *p* iş parçacıkları, izin *ceiling(n/p)* tamsayı olması *q*, hangi karşılayan *n p =\*q - r* ile*0 < = r < p*. Bir adet `static` Bu örnek atadığınız için zamanlamasını *q* ilk yinelemelere *p-1* iş parçacıklarını ve *q-r* yinelemelere son iş parçacığı.  Kabul edilebilir başka bir uygulama atadığınız *q* ilk yinelemelere *p-r* iş parçacıklarını ve *q-1* kalan için yineleme *r*iş parçacıkları. Bu örnekte, bir program, belirli bir uygulama ayrıntıları güvenmemelisiniz neden gösterilmektedir.

`dynamic` Zamanlama durumu için uygun bir `for` değişen veya hatta beklenmeyen sayıda işin gerektiren yinelemeler oluşturun.

```cpp
#pragma omp parallel for schedule(dynamic)
  for(i=0; i<n; i++) {
    unpredictable_amount_of_work(i);
}
```

`dynamic` Zamanlama daha uzun sürer, son yineleme yürütmek için başka bir iş parçacığı için iş parçacığı engel bekler özelliği göre nitelenen. Bu gereksinim, yinelemeler teker teker eşitleme her atama için kullanılabilir olduklarında iş parçacıkları atanmalarının gerekli olduğu anlamına gelir. En düşük öbek boyutunu belirterek eşitleme ek yükü azaltılabilir *k* 1 ' den büyük iş parçacıkları kalmayacak şekilde *k* kadar kısa bir zaman *k* kalır. Bu iş parçacığı engel, kendi son öbeği (en fazla) yürütmek için başka bir iş parçacığı alan daha uzun bekler garanti eder *k* yineleme.

`dynamic` Zamanlama hesaplama kaynaklarını değişen iş parçacıklarının alırsanız yararlı olabilir, çok çeşitli sayıda işin her yineleme için aynı etkiye sahiptir. Benzer şekilde, dinamik zamanlamayı da iş parçacığı ulaşırsınız faydalı olabilir `for` bazı durumlarda karşın çeşitli zamanlarda oluşturmak `guided` zamanlama tercih olabilir.

`guided` Zamanlama, iş parçacıkları geldiğinde farklı zamanlarda ve çalışması için uygun bir `for` her yineleme aynı miktarda iş hakkında gerektiren ile oluşturun. Bu durum oluşabilir, örneğin, `for` yapısı bir veya daha fazla bölüm tarafından öncesinde veya `for` ile oluşturur `nowait` yan tümceleri.

```cpp
#pragma omp parallel
{
  #pragma omp sections nowait
  {
    // ...
  }
  #pragma omp for schedule(guided)
  for(i=0; i<n; i++) {
    invariant_amount_of_work(i);
  }
}
```

Gibi `dynamic`, `guided` zamanlama engel son onun yinelemesini yürütmek için başka bir iş parçacığı alan daha uzun veya son iş parçacığı bekler garantileri *k* öbek boyutu, yinelemeler *k* belirtilir. Bu tür zamanlamalar arasından `guided` zamanlaması nitelenen özellik tarafından en az eşitlemeler gerektirir. Öbek boyutu için *k*, tipik bir uygulaması atar *q = ceiling(n/p)* ilk kullanılabilir iş parçacığı yinelemelere ayarlayın *n* büyüğü, *n-q* ve *p\*k*ve tüm yinelemelerle Atanana dek yineleyin.

En iyi zamanlaması seçimi Bu örneklerde olduğu gibi açık değilken, `runtime` zamanlama farklı zamanlamalar ve Öbek boyutları ile değiştirin ve programı yeniden derlemeniz gerekmeden denemek için kullanışlıdır. En iyi zamanlama program uygulandığı giriş verileri (bazı bilinebilen biçimde) bağlı olduğunda bu da yararlı olabilir.

Farklı zamanlamalar gereksinimlerimi karşılamama örneği görmek için sekiz iş parçacıkları arasında 1000 yineleme paylaşımı göz önünde bulundurun. Sabit bir miktarda her yineleme iş olduğunu varsayın ve bunu zaman birimi kullanabilirsiniz.

Tüm iş parçacıkları aynı anda başlatırsanız `static` zamanlaması ile eşitleme 125 birimlerindeki yürütmek yapı neden olur. Ancak, bir iş parçacığı sonlarında ulaşan, 100 birimi olduğunu varsayın. Ardından kalan yedi iş parçacıkları engel 100 birimine bekleyin ve 225 için tüm yapı için yürütme süresini artırır.

Çünkü hem `dynamic` ve `guided` zamanlamaları engel birimi birden fazla iş parçacığı bekler, bunların yürütme sürelerini büyük olasılıkla gecikmeler artırılana yalnızca 138 birimlerine artırmak yapı için Gecikmeli iş parçacığı neden olduğundan emin olun Eşitleme. Böyle gecikmeler göz ardı edilebilir değilse, eşitleme sayısı için 1000 olduğunu önemli olur `dynamic` ancak için yalnızca 41 `guided`, bir varsayılan öbek boyutu varsayılıyor. 25, öbek boyutu ile `dynamic` ve `guided` hem 150 birimleri yanı sıra herhangi bir gecikme gerekli eşitlemeleri, hangi şimdi sayı yalnızca 40 ve 20 ' den sırasıyla son.
