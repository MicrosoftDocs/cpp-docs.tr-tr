---
title: 2.7.2.2 firstprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d3e6ad966f4cf895da9374798f6c9a4079ccc2f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400971"
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