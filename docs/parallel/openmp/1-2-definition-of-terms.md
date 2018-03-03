---
title: "1.2 terimlerin tanımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: fcaa8eb8-bbbf-4a24-ad0e-e299c442db79
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab188c32c633092efc562d0432ebb7c5662b5ff8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="12-definition-of-terms"></a>1.2 Terimlerin Tanımı
Bu belgede aşağıdaki terimler kullanılır:  
  
 barrier  
 Bir takım tüm iş parçacıklarının erişilmesi gereken bir eşitleme noktası.  Her iş parçacığı, tüm iş parçacıklarının ekipteki bu noktada gelmesini bekler. Açık engelleri yönergeleri ve uygulama tarafından oluşturulan örtük engelleri tarafından tanımlanan vardır.  
  
 Yapı  
 Bir deyim bir yapıdır. Bir yönerge ve sonraki yapılandırılmış blok oluşur. Bazı yönergeleri bir yapı parçası değildir. (Bkz *openmp yönergesi* içinde [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)).  
  
 Yönergesi  
 C veya C++ **#pragma** arkasından **omp** tanımlayıcısı, başka bir metin ve yeni bir satır. Yönergesi program davranışını belirtir.  
  
 dinamik kapsam  
 Tüm tablolarda *sözcük ölçüde*, deyimleri sözcük kapsam içinde yürütme sonucu olarak yürütülen bir işlev içinde herhangi bir deyimle artı. Dinamik kapsam olarak da adlandırılan bir *bölge*.  
  
 sözcük kapsamı  
 Deyimleri sözcüksel olarak kapsamında yer alan bir *yapılandırılmış blok*.  
  
 Ana iş parçacığı  
 Bir takım oluşturur iş parçacığı olduğunda bir *paralel bölge* girilir.  
  
 Paralel bölge  
 Bir OpenMP paralel bağlamak deyimleri oluşturun ve birden çok iş parçacığı tarafından yürütülen.  
  
 private  
 Özel bir değişken başvuru yapma iş parçacığı için benzersizdir depolama bloğu adları. Bir değişkeni özel olduğunu belirtmek için çeşitli yollar olduğuna dikkat edin: tanımını paralel bir bölge içindeki bir **threadprivate** yönergesi, bir **özel**, **firstprivate**, **lastprivate**, veya **azaltma** yan tümcesi veya kullanımı değişkeni olarak bir **için**for döngüsü denetim değişkeni olarak bir **için** döngü hemen bir **için** veya **için paralel** yönergesi.  
  
 bölge  
 Dinamik bir uzantı.  
  
 Seri bölge  
 Yalnızca tarafından yürütülen deyimleri *ana iş parçacığı* herhangi dinamik kapsam dışında *paralel bölge*.  
  
 Serileştirme  
 Bir grup (Bu ana iş parçacığı, paralel yapı için) yalnızca bir tek iş parçacığı, seri yürütme sırasını içeren deyimleri yapılandırılmış bloğu içinde oluşan iş parçacığı ile paralel yapı yürütmek için (blok yüklenmemiş gibi aynı sipariş bölümü bir paralel yapıyı) ve tarafından döndürülen değer üzerinde hiçbir etkisi olmadan **omp_in_parallel()** (paralel yapıları iç içe etkilerini herhangi dışında).  
  
 shared  
 Paylaşılan bir değişken tek bir blok depolama adları. Bu değişken erişen tüm iş parçacıkları, bir takım bu tek bir blok depolama erişir.  
  
 yapılandırılmış bloğu  
 Yapılandırılmış bir blok tek bir giriş ve tek bir çıkış vardır (tek veya bileşik) bir açıklamadır. Giriş / Çıkış bu deyim bir atlama ise yapılandırılmış bir blok deyimi yok. (bir çağrı dahil olmak üzere **longjmp**(3 C) veya kullanımını **throw**, ancak bir çağrı **çıkmak** izin verilir). Bileşik deyim, her zaman bir açılış yapıyoruz yürütülmeye yapılandırılmış bir blok ise **{** ve kapatma sırasında her zaman biter **}**. İfade deyimi, seçim deyimi, yineleme deyimi veya **deneyin** bloğu kapsayan tarafından karşılık gelen bileşik deyim alırsa, yapılandırılmış bir blok **{** ve **}** yapılandırılmış bir blok olacaktır. Atlama deyimi, etiketli deyim veya bildirimi deyimi yapılandırılmış bloğu değil.  
  
 Takım  
 Bir yapı yürütme içinde birlikte çalışan bir veya daha fazla iş parçacığı sayısı.  
  
 thread  
 Seri akış denetimi, bir dizi özel değişkenler ve erişim paylaşılan değişkenlere sahip bir yürütme varlık.  
  
 değişken  
 Ad alanı adları ile isteğe bağlı olarak tam bir tanımlayıcı, bir nesne adları.