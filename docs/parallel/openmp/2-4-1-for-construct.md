---
title: "2.4.1 yapı için | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 27d2cbce-786b-4819-91d3-d55b2cc57a5e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd861da77b549a73edf9aeface714b0066d88344
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="241-for-construct"></a>2.4.1 Yapı için
**İçin** yönergesi ilişkili döngü yinelemelerini paralel olarak yürütülecek belirten bir yinelemeli iş paylaşım yapısıyla tanımlar. Yinelemelerini **için** döngü bağlar, paralel yapı yürütme grupta zaten iş parçacıkları arasında dağıtılır. Söz dizimi **için** yapı aşağıdaki gibidir:  
  
```  
#pragma omp for [clause[[,] clause] ... ] new-linefor-loop  
```  
  
 Yan tümcesi aşağıdakilerden biridir:  
  
 **Özel (** *değişken listesi* **)**  
  
 **firstprivate (** *değişken listesi* **)**  
  
 **lastprivate (** *değişken listesi* **)**  
  
 **azaltma (** *işleci* **:** *değişken listesi***)**  
  
 **sıralı**  
  
 **zamanlama (** *türü*[, *chunk_size*]**)**  
  
 **nowait**  
  
 **İçin** yönergesi yerleştirir kısıtlamaları ilgili yapısına **için** döngü. Özellikle, karşılık gelen **için** döngü kurallı şekli olması gerekir:  
  
 **için (** *init expr* **;** *var op mantıksal b*; *incr expr***)**  
  
 *Init ifade*  
 Aşağıdakilerden biri:  
  
 *var* = *lb*  
  
 *tamsayı türü var* = *lb*  
  
 *incr ifade*  
 Aşağıdakilerden biri:  
  
 ++*var*  
  
 *var* ++  
  
 -- *var*  
  
 *var* --  
  
 *var* += *incr*  
  
 *var* -= *incr*  
  
 *var* = *var* + *incr*  
  
 *var* = *incr* + *var*  
  
 *var* = *var* - *incr*  
  
 *var*  
 İmzalı tamsayı değişken. Bu değişken aksi paylaşılan, bu örtük olarak özel süresince yapılır **için**.   Bu değişken gövdesi içinde değiştirilmemelidir **için** deyimi. Değişkeni belirtilmediği sürece **lastprivate**, döngü belirsiz sonra değeri.  
  
 *op mantıksal*  
 Aşağıdakilerden biri:  
  
 <  
  
 \<=  
  
 >  
  
 \>=  
  
 *lb*, *b*, ve *incr*  
 Tamsayı sabit ifadeleri döngüsü. Bu deyimler değerlendirmesi sırasında eşitleme yoktur. Bu nedenle, değerlendirilen herhangi yan etkileri belirsiz sonuçlar.  
  
 Kurallı biçimi döngüsüne girişteki hesaplanacak döngü yineleme sayısını izin verildiğini unutmayın. Bu hesaplama türü değerleri ile gerçekleştirilen *var*, tamsayı yükseltmeleri sonra. Özellikle, değeri *b* - *lb* + *incr* sonuç türü belirsiz olması gösterilemez. Daha fazla, eğer *op mantıksal* olan < veya \<sonra = *incr expr* neden gerekir *var* her döngü tekrarında üzerinde artırmak için.   Varsa *op mantıksal* olan > veya > = then *incr expr* neden gerekir *var* her döngü tekrarında üzerinde azaltmak için.  
  
 **Zamanlama** yan tümcesi belirtir nasıl yinelemelerini **için** döngü takım iş parçacıkları arasında bölünür. Bir program doğruluğunu hangi iş parçacığı belirli bir yineleme yürütür bağımlı olmamalıdır. Değeri *chunk_size*, belirtilmişse, pozitif bir değer içeren bir döngü sabit tamsayı ifade olmalıdır. Bu ifade değerlendirmesi sırasında eşitleme yoktur. Bu nedenle, değerlendirilen herhangi yan etkileri belirsiz sonuçlar. Zamanlama *türü* şunlardan biri olabilir:  
  
 Tablo 2-1 **zamanlama** yan tümcesi *türü* değerleri  
  
|||  
|-|-|  
|static|Zaman **zamanlama (statik,** *chunk_size***)** belirtilirse, yineleme tarafından belirlenen bir boyutta parçalara bölünür *chunk_size*. Öbek hepsini şekilde iş parçacığı sayısı sırasına göre takım iş parçacıklarında statik olarak atanmış. Durumlarda *chunk_size* belirtilirse, yineleme alanı, her iş parçacığı için atanan bir Öbek ile boyutu, yaklaşık olarak eşit olan parçalara bölünür.|  
|dinamik|Zaman **zamanlama (dinamik** *chunk_size***)** belirtilirse, yinelemeleri öbekleri, her içeren bir dizi bölünen *chunk_size* yineleme. Her öbek atama için bekleyen bir iş parçacığı atanır. İş parçacığı yineleme öbek yürütür ve atanacak hiçbir öbekleri kalana kadar sonraki ataması için bekler. Atanacak son öbek yineleme daha az sayıda gerekebileceğini unutmayın. Durumlarda *chunk_size* belirtilmemişse, varsayılan olarak, 1.|  
|Destekli|Zaman **zamanlama (Destekli,** *chunk_size***)** belirtilirse, yinelemeleri öbek boyutları azalan ile iş parçacıklarında atanır. Bir iş parçacığı, atanan öbek tekrar sona erdiğinde, hiçbiri kalana kadar dinamik olarak başka bir öbek atanır. İçin bir *chunk_size* 1, her öbek boyutu yaklaşık atanmamış yineleme iş parçacıklarını numarasına göre bölünmüş sayısıdır. Bu boyutları yaklaşık 1 katlanarak azaltın. İçin bir *chunk_size* değerle *k* 1 ' den büyük boyutları yaklaşık katlanarak çok azaltmak *k*, son öbek daha az olabilir ancak bu  *k* yineleme. Durumlarda *chunk_size* belirtilmemişse, varsayılan olarak, 1.|  
|çalışma zamanı|Zaman **schedule(runtime)** belirtilirse, ilgili planlama çalışma zamanına kadar ertelenmiş karar. Zamanlama *türü* ve öbek boyutunu seçilebilir çalışma zamanında ortam değişkenini ayarlayarak **OMP_SCHEDULE**. Bu ortam değişkeni ayarlanmamış ise, sonuçta elde edilen zamanlaması uygulama tanımlı değildir. Zaman **schedule(runtime)** belirtilirse, *chunk_size* belirtilmemelidir.|  
  
 İçinde açıkça tanımlanmış yokluğu **zamanlama** yan tümcesi, varsayılan **zamanlama** uygulama tanımlı değil.  
  
 OpenMP uyumlu bir program doğru yürütme için belirli bir zamanlama güvenmemelisiniz. Bir program bir zamanlamaya göre doğrulamamalısınız *türü* aynı zamanlamaya uygulamalarında Çeşitlemeler olmasını mümkün olduğundan tam olarak yukarıda verilen açıklama uyumludur *türü* arasında farklı derleyicileri. Açıklamaları, belirli bir durum için uygun olan zamanlamayı seçmek için kullanılabilir.  
  
 **Sıralı** yan tümcesi bulunmalıdır ne zaman **sıralı** yönergeleri bağlamak için **için** oluşturun.  
  
 Sonunda örtük bir engel olan bir **için** sürece oluşturmak bir **nowait** yan tümcesi belirtilir.  
  
 Kısıtlamaları **için** yönergesi aşağıdaki gibidir:  
  
-   **İçin** döngü, yapılandırılmış bir blok olmalıdır ve ayrıca, yürütülmesinin tarafından sonlandırılması gerekir değil bir **sonu** deyimi.  
  
-   Döngü değerlerini kontrol ifadelerin **için** döngü ile ilişkili bir **için** yönergesi ekibindeki tüm iş parçacıklarının için aynı olması gerekir.  
  
-   **İçin** döngü yineleme değişkeni imzalı tamsayı türü olması gerekir.  
  
-   Yalnızca tek bir **zamanlama** yan tümcesi görünebilir bir **için** yönergesi.  
  
-   Yalnızca tek bir **sıralı** yan tümcesi görünebilir bir **için** yönergesi.  
  
-   Yalnızca tek bir **nowait** yan tümcesi görünebilir bir **için** yönergesi.  
  
-   Belirtilmeyen IF veya ne sıklıkta içindeki tüm yan etkiler olan *chunk_size*, *lb*, *b*, veya *incr* ifadeleri oluşur.  
  
-   Değeri *chunk_size* ifadesi ekibindeki tüm iş parçacıklarının için aynı olmalıdır.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **özel**, **firstprivate**, **lastprivate**, ve **azaltma** yan tümceleri, bkz: [bölüm 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.  
  
-   **OMP_SCHEDULE** ortam değişkeni, bkz: [bölüm 4.1](../../parallel/openmp/4-1-omp-schedule.md) sayfasında 48.  
  
-   **Sıralı** oluşturmak için bkz: [bölüm 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) sayfasında 22.  
  
-   [Ek D](../../parallel/openmp/d-using-the-schedule-clause.md), sayfa 93, zamanlama yan tümcesinin kullanılması hakkında daha fazla bilgi sağlar.