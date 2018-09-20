---
title: D. Schedule yan tümcesini kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d40b22a5e724f8d8b587e2928d3d1305a7fa807a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446150"
---
# <a name="d-using-the-schedule-clause"></a>D. Schedule yan tümcesini kullanma

Bir paralel bölgenin sonuna en az bir engel olan ve başka engelleri içindeki olabilir. Her engel diğer takım üyelerinin gelmesi son iş parçacığı için beklemeniz gerekir. Böylece engel yaklaşık aynı zamanda tüm iş parçacıklarının ulaşırsınız bu bekleme süresi en aza indirmek için paylaşılan iş dağıtılmalıdır. Paylaşılan bazıları iş bulunan **için** oluşturur, `schedule` yan tümcesi bu amaç için kullanılabilir.

Zamanlama için seçtiğiniz aynı nesneleri yinelenen başvurular olduğunda bir **için** yapısı temelde önbellekler ve bellek olup olmadığını erişim boyutunu ve durum gibi bellek sisteminin özelliklerine göre belirlenemedi tek tip veya düzensiz kez. Bu tür konular bazı iş parçacıkları bazı döngüler görece daha az iş atanmış olsa bile her bir iş parçacığı aynı döngüleri, bir dizi bir dizinin öğeleri kümesini tutarlı bir şekilde başvurmak için tercih yapabilir. Bu kullanarak yapılabilir **statik** döngüler için aynı sınırları ile zamanlama. Aşağıdaki örnekte, dikkat sıfır olarak kullanılır ikinci Döngüdeki alt sınır olsa bile **k** zamanlama önemli değilse daha doğal olacaktır.

```
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

Kalan örneklerde, bu bellek varsayılır erişim baskın önemli noktalar değil ve aksi belirtilmedikçe, tüm iş parçacıklarının karşılaştırılabilir hesaplama kaynaklarını alır. Bu gibi durumlarda, zamanlama için tercih ettiğiniz bir **için** yapısı, en yakın önceki arasında gerçekleştirilecek olan paylaşılan iş bağlıdır ve süreçlerinin önündeki engelleri örtük kapanış engel veya varsa sonraki engel en yakın bir `nowait` yan tümcesi. Zamanlamayı her tür için bu zamanlama türü nasıl en iyi seçenek olabilir kısa bir örnek gösterir. Kısa bir açıklama her bir örnek aşağıda verilmiştir.

**Statik** zamanlama en basit durum için tek bir içeren bir paralel bölgenin uygun ayrıca **için** , aynı iş miktarı her bir yineleme oluşturun.

```
#pragma omp parallel for schedule(static)
for(i=0; i<n; i++) {
  invariant_amount_of_work(i);
}
```

**Statik** zamanlama özelliklerine göre nitelenen, her iş parçacığının yaklaşık aynı sayıda yineleme başka bir iş parçacığı alır ve her bir iş parçacığı atanmış yinelemeleri bağımsız olarak belirleyebilirsiniz. Bu nedenle eşitleme işi dağıtmak için gereklidir ve her yinelemede aynı miktarda iş gerektirdiğini varsayım altında tüm iş parçacıkları, aynı anda ancak ondan haberdar tamamlanmalıdır.

Bir takımın `p` iş parçacıkları, izin *ceiling(n/p)* tamsayı olması *q*, hangi karşılayan *n p =\*q - r* ile *0 < r = < p* . Bir adet **statik** Bu örnek atadığınız için zamanlamasını *q* ilk yinelemelere *p-1* iş parçacıklarını ve *q-r* Son iş parçacığı yinelemelere.  Kabul edilebilir başka bir uygulama atadığınız *q* ilk yinelemelere *p-r* iş parçacıklarını ve *q-1* kalan için yineleme *r*iş parçacıkları. Bir program, belirli bir uygulama ayrıntıları doğrulamamalısınız neden bunu göstermektedir.

**Dinamik** zamanlama durumu için uygun bir **için** değişen veya hatta beklenmeyen sayıda işin gerektiren yinelemeler oluşturun.

```
#pragma omp parallel for schedule(dynamic)
  for(i=0; i<n; i++) {
    unpredictable_amount_of_work(i);
}
```

**Dinamik** zamanlama daha uzun sürer, son yineleme yürütmek için başka bir iş parçacığı için iş parçacığı engel bekler özelliği göre nitelenen. Bu eşitleme her atama için kullanılabilir oldukça yinelemeler teker teker iş parçacığı atanmasını gerektirir. En düşük öbek boyutunu belirterek eşitleme ek yükü azaltılabilir *k* 1 ' den büyük iş parçacıkları kalmayacak şekilde *k* kadar kısa bir zaman *k* kalır. Bu iş parçacığı engel, kendi son öbeği (en fazla) yürütmek için başka bir iş parçacığı alan daha uzun bekler garanti eder *k* yineleme.

**Dinamik** zamanlama hesaplama kaynaklarını değişen iş parçacıklarının alırsanız yararlı olabilir, çok çeşitli sayıda işin her yineleme için aynı etkiye sahiptir. Benzer şekilde, dinamik zamanlamayı da iş parçacığı ulaşırsınız faydalı olabilir **için** bazı durumlarda karşın çeşitli zamanlarda oluşturmak **destekli** zamanlama tercih olabilir.

**Destekli** zamanlama, iş parçacıkları geldiğinde farklı zamanlarda ve çalışması için uygun bir **için** her yineleme aynı miktarda iş hakkında gerektiren ile oluşturun. Bu durum oluşabilir, örneğin, **için** yapısı bir veya daha fazla bölüm tarafından öncesinde veya **için** ile oluşturur `nowait` yan tümceleri.

```
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

Gibi **dinamik**, **destekli** zamanlama engel son onun yinelemesini yürütmek için başka bir iş parçacığı alan daha uzun veya son iş parçacığı bekler garantileri *k* Öbek boyutu, yinelemeler *k* belirtilir. Bu tür zamanlamalar arasından **destekli** zamanlaması nitelenen özellik tarafından en az eşitlemeler gerektirir. Öbek boyutu için *k*, tipik bir uygulaması atar *q = ceiling(n/p)* ilk kullanılabilir iş parçacığı yinelemelere ayarlayın *n* büyüğü, *n-q* ve *p\*k*ve tüm yinelemelerle Atanana dek yineleyin.

En iyi zamanlaması seçimi Bu örneklerde olduğu gibi açık olmadığında **çalışma zamanı** zamanlama farklı zamanlamalar ve Öbek boyutları ile değiştirin ve programı yeniden derlemeniz gerekmeden denemek için kullanışlıdır. En iyi zamanlama program uygulandığı giriş verileri (bazı bilinebilen biçimde) bağlı olduğunda bu da yararlı olabilir.

Farklı zamanlamalar gereksinimlerimi karşılamama örneği görmek için 8 iş parçacığı arasında 1000 yineleme paylaşımı göz önünde bulundurun. Sabit bir miktarda her yineleme iş olduğunu varsayın ve bunu zaman birimi kullanabilirsiniz.

Tüm iş parçacıkları aynı anda başlatırsanız **statik** zamanlaması ile eşitleme 125 birimlerindeki yürütmek yapı neden olur. Ancak, bir iş parçacığı sonlarında ulaşan, 100 birimi olduğunu varsayın. Ardından kalan yedi iş parçacıkları engel 100 birimine bekleyin ve 225 için tüm yapı için yürütme süresini artırır.

Çünkü hem **dinamik** ve **destekli** zamanlamaları engel birimi birden fazla iş parçacığı bekler ve yürütme süreleri için yalnızca 138 artırmak yapı için Gecikmeli iş parçacığının neden emin olun birimleri, büyük olasılıkla eşitleme gecikmeleri artırılana. Böyle gecikmeler göz ardı edilebilir değilse, eşitleme sayısı için 1000 olduğunu önemli olur **dinamik** ancak için yalnızca 41 **destekli**, bir varsayılan öbek boyutu varsayılıyor. 25, öbek boyutu ile **dinamik** ve **destekli** hem 150 birimleri yanı sıra herhangi bir gecikme gerekli eşitlemeleri, hangi şimdi sayı yalnızca 40 ve 20 ' den sırasıyla son.