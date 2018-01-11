---
title: "D. Zamanlamayı yan tümcesini kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b51eeb36a4cffafde0e90586fec08d28b9672e5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="d-using-the-schedule-clause"></a>D. Zamanlama yan tümcesini kullanma
Paralel bir bölge, sonunda en az bir engel olan ve başka engelleri içindeki sahip olabilir. Her engel bir takım üyeleri gelmesi son iş parçacığı için beklemeniz gerekir. Böylece engel yaklaşık aynı zamanda, tüm iş parçacıklarının gelmesini bu bekleme süresini en aza indirmek için paylaşılan iş dağıtılmalıdır. Paylaşılan bazıları iş yer **için** oluşturur, `schedule` yan tümcesi bu amaç için kullanılabilir.  
  
 Zamanlama için seçimi aynı nesnelere yinelenen başvurular olduğunda bir **için** yapı öncelikle, durum ve boyutunu önbellekleri ve belleğe mi erişim gibi bellek sistem özelliklerine göre belirlenemedi kez Tekdüzen veya düzensiz olur. Bu tür konular bazı iş parçacıkları döngüler bazıları görece daha az iş atanan olsa bile her iş parçacığı döngüler, bir dizi dizi öğelerini aynı kümesini tutarlı bir şekilde başvurmak için tercih yapabilirsiniz. Bu kullanılarak yapılabilir **statik** zamanlama tüm döngüler için aynı sınır ile. Aşağıdaki örnekte, unutmayın sıfır kullanılır ikinci Döngüdeki alt sınırı olarak rağmen **k** zamanlama önemli olsalar daha doğal olacaktır.  
  
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
  
 Kalan örneklerde, belleğin varsayılır erişim baskın göz önünde bulundurarak, değil ve aksi belirtilmedikçe, tüm iş parçacıklarının karşılaştırılabilir hesaplama kaynaklarını alırsınız. Bu durumda, zamanlamasını seçimine bir **için** yakın önceki arasında gerçekleştirilmesi gereken tüm paylaşılan iş bağımlı yapı engel ve örtük kapanış engel veya varsa sonraki engel en yakın bir `nowait` yan tümcesi. Zamanlama her tür için bu zamanlama türü nasıl en iyi seçenek büyük olasılıkla kısa bir örnek gösterir. Kısa bir tartışma her bir örnek aşağıda verilmiştir.  
  
 **Statik** zamanlama basit çalışması için tek bir içeren paralel bir bölge uygun de **için** , iş ile aynı miktarda her bir yineleme oluşturun.  
  
```  
#pragma omp parallel for schedule(static)  
for(i=0; i<n; i++) {  
  invariant_amount_of_work(i);  
}  
```  
  
 **Statik** zamanlama özellikleri tarafından işlemleri, her iş parçacığının yaklaşık aynı sayıda yineleme başka bir iş parçacığı alır ve her iş parçacığı bağımsız olarak kendisine atanmış yineleme belirleyebilirsiniz. Böylece iş dağıtmak için eşitleme gereklidir ve her bir yineleme iş ile aynı miktarda gerektirdiği varsayılarak altında tüm iş parçacıklarının en hakkında aynı anda tamamlanmalıdır.  
  
 Bir ekibin `p` iş parçacıklarını izin *ceiling(n/p)* tamsayı olması *q*, hangi karşılayan *n = p\*q - r* ile *0 < = r < p* . Bir uyarlamasını **statik** Bu örnek atadığınız için zamanlama *q* ilk yinelemelere *p-1* iş parçacıklarını ve *q-r* Son iş parçacığı yinelemelere.  Başka bir kabul edilebilir uygulama atadığınız *q* ilk yinelemelere *p-r* iş parçacıklarını ve *q-1* kalan için yineleme *r*iş parçacığı sayısı. Bir program belirli bir uygulama ayrıntılarını güvenmemelisiniz neden bu gösterilmektedir.  
  
 **Dinamik** zamanlamadır harf kullanımı için uygun bir **için** iş değişen veya hatta beklenmeyen miktarda gerektiren yineleme ile oluşturun.  
  
```  
#pragma omp parallel for schedule(dynamic)  
  for(i=0; i<n; i++) {  
    unpredictable_amount_of_work(i);  
}  
```  
  
 **Dinamik** zamanlama son yineleme yürütmek için başka bir iş parçacığı daha uzun sürdüğü için hiçbir iş parçacığı engel bekler özelliği tarafından işlemleri. Bu, her bir atama için eşitleme çıktıklarında yineleme bir seferde bir iş parçacığı atanmasını gerektirir. Minimum öbek boyutunu belirterek eşitleme ek yükü azaltılabilir *k* 1 ' den büyük iş parçacığı kalmayacak şekilde *k* birer birer kadar az *k* kalır. Bu hiçbir iş parçacığı engel son öbeğini (en çok) yürütmek için başka bir iş parçacığı sürdüğünü daha uzun bekler garanti *k* yineleme.  
  
 **Dinamik** zamanlama hesaplama kaynaklarını değişen iş parçacıklarının alırsanız, yararlı olabilir, her bir yineleme için iş değişik miktarlardaki çok aynı etkiye sahiptir. Benzer şekilde, dinamik zamanlama da iş parçacıklarının en ulaşırsa yararlı olabilir **için** bazı bu gibi durumlarda karşın çeşitli zamanlarda oluşturmak **destekli** zamanlama tercih olabilir.  
  
 **Destekli** zamanlamadır, iş parçacıklarının gelmesini çeşitli zamanlarda çalışması için uygun bir **için** her yineleme iş ile aynı miktarda hakkında gerektiren ile oluşturun. Bu durum, örneğin, **için** yapı göre bir veya daha fazla bölümler öncesinde veya **için** ile oluşturur `nowait` yan tümceleri.  
  
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
  
 Gibi **dinamik**, **destekli** zamanlama hiçbir iş parçacığı engel son yineleme yürütmek için başka bir iş parçacığı sürdüğünü daha uzun veya son bekler garanti *k* Yineleme öbek boyutu, *k* belirtilir. Bu tür zamanlamalar arasından **destekli** zamanlaması işlemleri özelliği tarafından en az eşitlemeler gerektirir. Öbek boyutu için *k*, tipik bir uygulama atayacaktır *q ceiling(n/p) =* ilk kullanılabilir iş parçacığı yinelemelere ayarlamak  *n*  büyük için ,*n-q* ve *p\*k*ve tüm yinelemeleri atanan kadar yineleyin.  
  
 En iyi zamanlama seçimi Bu örnekler için olduğu gibi Temizle olmadığında **çalışma zamanı** zamanlaması farklı zamanlamalar ve Öbek boyutları ile değiştirin ve programı yeniden derleyin gerek kalmadan denemek için uygun değildir. En iyi zamanlama (bazı öngörülebilir bir yolla) programı uygulandığı giriş verilere bağlıdır da yararlı olabilir.  
  
 Dengelemeler farklı zamanlamalar arasında örneği görmek için 8 iş parçacığı arasında 1000 yineleme paylaşımı göz önünde bulundurun. Her bir yineleme iş sabit bir tutar olduğunu varsayın ve zaman birimi olarak kullanın.  
  
 Tüm iş parçacıklarının aynı anda, başlatırsanız **statik** zamanlaması ile eşitleme 125 birimlerindeki yürütmek yapı neden olur. Ancak bir iş parçacığı sonlarında ulaşan, 100 birim olduğunu varsayın. Engeli adresindeki 100 birimler için kalan yedi iş parçacığı bekleyin ve tüm yapı için yürütme süresi için 225 artırır.  
  
 Çünkü hem **dinamik** ve **destekli** zamanlamaları emin olun hiçbir iş parçacığı engel birden çok birimi bekler, Gecikmeli iş parçacığı yürütme zamanları yalnızca 138 artırmak yapı için neden olur. birimler, büyük olasılıkla gelen gecikmeler tarafından artar. Bu gibi gecikmeler düşünülerek emin değilseniz, eşitlemeler sayısı 1000 için olduğunu önemli hale **dinamik** ancak için yalnızca 41 **destekli**, bir varsayılan öbek boyutu varsayılarak. 25, öbek boyutu ile **dinamik** ve **destekli** her ikisi de 150 birimleri yanı sıra tüm gecikmeler gerekli eşitlemeler, hangi şimdi numarası yalnızca 40 ve 20 ' den sırasıyla son.