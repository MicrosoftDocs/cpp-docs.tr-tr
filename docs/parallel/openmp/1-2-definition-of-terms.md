---
title: 1.2 Terimlerin Tanımı
ms.date: 11/04/2016
ms.assetid: fcaa8eb8-bbbf-4a24-ad0e-e299c442db79
ms.openlocfilehash: cd8bcc47a7fc9d1d0683c220ccd5ef1edac2b4e9
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326036"
---
# <a name="12-definition-of-terms"></a>1.2 Terimlerin Tanımı

Bu belgede aşağıdaki terimler kullanılır:

- barrier

   Takım tüm iş parçacıkları tarafından erişilmesi gereken bir eşitleme noktası.  Her iş parçacığı, takımın tüm iş parçacıkları bu noktada geldiğinde bekler. Yönergeleri ve uygulama tarafından oluşturulan örtük engelleri tarafından tanımlanan açık engelleri vardır.

- Yapısı

   Bir deyimi bir yapıdır. Bu, bir yönerge ve sonraki yapısal bloğunun oluşur. Yönergelerden bazıları bir yapısının parçası olmadığını unutmayın. (Bkz *openmp yönergesi* içinde [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)).

- Yönergesi

   Bir C veya C++ **#pragma** ardından **omp** tanımlayıcısı, diğer metin ve yeni bir satır. Yönerge, programın davranışını belirtir.

- dinamik kapsam

   Tüm deyimlerinde *sözcük kapsamı*, sözcük kapsamı içindeki deyimler yürütme sonucu olarak çalıştırılan bir işlev içinde herhangi bir deyimle artı. Dinamik kapsam olarak da adlandırılan bir *bölge*.

- sözcük kapsamı

   Sözcüksel olarak içindeki deyimler bir *yapısal bloğunun*.

- Ana iş parçacığı

   Bir ekip oluşturan iş parçacığı, bir *paralel bölgenin* girilir.

- Paralel bölgenin

   Bir OpenMP paralel yapı bağlayın ve birden çok iş parçacığı tarafından yürütülen deyimleri.

- private

   Özel bir değişken başvurusu yapılmalıdır iş parçacığı için benzersiz olan depolama bloğu adları. Bir değişkeni özel olduğunu belirtmek için çeşitli yollar olduğunu unutmayın: tanımını bir paralel bölgenin içinde bir **threadprivate** yönergesi, bir **özel**, **firstprivate**, **lastprivate**, veya **azaltma** yan tümcesi veya değişken olarak kullanıldığında bir **için**döngü denetim değişkeni olarak bir **için** döngü hemen bir **için** veya **için paralel** yönergesi.

- bölge

   Dinamik bir uzantı.

- Seri bölge

   Yalnızca yürütülen deyimleri *ana iş parçacığı* herhangi dinamik kapsam dışında *paralel bölgenin*.

- Seri hale getirme

   İş parçacığı (ana iş parçacığını paralel bu yapı için olan) yalnızca bir tek iş parçacığı, seri yapılandırılmış bloğundaki ifadeler için yürütme sırasını ile oluşan bir ekip ile paralel bir yapısı yürütülecek (blok yokmuş gibi aynı sıralama bölümü yapısının bir paralel) ve döndürdüğü değerin üzerinde hiçbir etkisi olmadan **omp_in_parallel()** (paralel yapılar iç içe herhangi etkileri dışında).

- shared

   Tek bir blok depolama paylaşılan bir değişken adı. Bu değişken erişen tüm iş parçacıklarının bir takım bu tek bir blok depolama erişim sağlar.

- Yapısal bloğunun

   Bir yapısal bloğunun tek bir giriş ve tek bir çıkış (tek veya bileşik) bir ifadedir. İçine veya dışına Sadeliği atlama ise herhangi bir deyimi bir yapısal bloğunun olur (çağrı dahil olmak üzere **longjmp**(3 C) veya kullanımını **throw**, ancak bir çağrı **çıkmak** izin verilir). Bileşik deyim, her zaman sol konumunda yürütülmeye yapısal bloğunun ise **{** ve kapatma sırasında her zaman sona eren **}**. Bir ifade deyimi, seçim deyimi, yineleme deyiminin veya **deneyin** bloğu yapısal bloğunun karşılık gelen bileşik deyim, kapsayan tarafından aldıysanız **{** ve **}**  yapısal bloğunun olacaktır. Atlama deyimi, etiketli deyim veya bildirim deyimi bir yapısal bloğunun değil.

- Takım

   Bir yapı içinde yürütülmesini kurduğuna ilişkin bir veya daha fazla iş parçacığı.

- thread

   Bir yürütme seri bir denetim akışını, bir dizi özel değişkenleri ve paylaşılan değişkenlerine erişimi olan varlık.

- değişken

   İsteğe bağlı olarak ad alanı adları, tam bir tanımlayıcı, bir nesne adları.
