---
title: 2.7.2.2 firstprivate
ms.date: 11/04/2016
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
ms.openlocfilehash: f981c66fd3e0a2f42dcf731954f5054f96ed2973
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605978"
---
# <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

**Firstprivate** yan tümcesi tarafından sağlanan bir işlevselliğin sağlar **özel** yan tümcesi. Söz dizimi **firstprivate** yan tümcesi şu şekildedir:

```
firstprivate(variable-list)
```

Belirtilen değişkenler *değişken listesi* sahip **özel** açıklandığı yan tümcesi semantiğini [bölümü 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25. Yapı iş parçacığının yürütülmesini önce iş parçacığı başına bir kez yapıldığını gibi oluşturma ve başlatma gerçekleşir. İçin bir **firstprivate** paralel bir yapısı yan tümcesi, ilk yeni özel nesne değeri karşılaştığı iş parçacığı için paralel yapı hemen önce var olan orijinal nesnenin değeri. İçin bir **firstprivate** yan tümcesi bir iş paylaşımı yapısı, ilk iş paylaşımı yapısı yürütülen her bir iş parçacığı için yeni özel nesne değeri zaman içinde önceki bir noktaya var. orijinal nesnenin değeri, aynı iş parçacığında iş paylaşımı yapısı karşılaşır. Ayrıca, C++ nesneler için yeni özel her iş parçacığı için orijinal nesnenin kopya nesnedir.

Kısıtlamaları **firstprivate** yan tümcesi aşağıdaki gibidir:

- Belirtilen bir değişken bir **firstprivate** yan tümcesi eksik bir türü veya bir başvuru türü değil olmalıdır.

- Bir değişken olarak belirtilen sınıf türüyle **firstprivate** erişilebilir, açık bir kopya oluşturucuya sahip olmalıdır.

- Bir paralel bölgenin içinde özel olmayan veya, görünen değişkenleri **azaltma** yan tümcesi bir **paralel** yönergesi belirtilemez bir **firstprivate** yan tümcesi bir Paralel yapısı için bağlar iş paylaşım yönergesi.