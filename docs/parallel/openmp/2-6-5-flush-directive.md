---
title: 2.6.5 flush yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d67453b636d50fcb78092318ebb76f5192817548
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442740"
---
# <a name="265-flush-directive"></a>2.6.5 flush Yönergesi

**Temizleme** yönergesi, açık veya zımni, olup olmadığını belirtir uygulama takım tüm iş parçacıklarının belirli nesneleri (aşağıda belirtilen) tutarlı bir görünümünü sağlamak için gereken bir "iş parçacıkları arası" dizi noktası bellek. Bu nesneleri başvurmak ifadeleri önceki değerlendirme tamamlandıktan sonraki değerlendirmeler henüz değil başlamıştır anlamına gelir. Örneğin, derleyiciler nesneleri değerlerini kayıtları için bellek geri yüklemeniz gerekir ve donanım yazma arabelleklerini belleğe ve değerlerini bellekten nesneleri yeniden yüklemeniz gerekebilir.

Söz dizimi **Temizleme** yönerge aşağıdaki gibidir:

```
#pragma omp flush [(variable-list)]  new-line
```

Eşitleme iste nesneleri tüm değişkenleri tarafından belirlenebilir sonra değişkenlere isteğe bağlı olarak belirtilebilir. *değişken listesi*. Mevcut bir işaretçi ise *değişken listesi*işaretçi Temizlenen, işaretçiyi nesnenin değil başvuruyor.

A **Temizleme** yönerge olmadan bir *değişken listesi* erişilemeyen nesneleri hariç tüm paylaşılan nesneleri otomatik depolama süresi ile eşitler. (Daha fazla yüke sahip büyük olasılıkla budur bir **Temizleme** ile bir *değişken listesi*.) A **Temizleme** yönerge olmadan bir *değişken listesi* için aşağıdaki yönergeleri kapsanan:

- `barrier`

- Giriş ve çıkış ' **kritik**

- Giriş ve çıkış ' `ordered`

- Giriş ve çıkış ' **paralel**

- AT çıkış alanından **için**

- AT çıkış alanından **bölümleri**

- AT çıkış alanından **tek**

- Giriş ve çıkış ' **için paralel**

- Giriş ve çıkış ' **paralel bölümleri**

Yönergesi, kullanılmaz bir `nowait` yan tümcesi varsa. Not edilmesi gereken, **Temizleme** yönergesi değil kapsanıyor aşağıdakilerden biri:

- Giriş, **için**

- Giriş veya çıkış ' **ana**

- Giriş, **bölümleri**

- Giriş, **tek**

Bir geçici nitelikli türe sahip bir nesne değeri erişen bir başvuru yokmuş gibi davranan bir **Temizleme** yönergesi bu nesnede önceki bir dizi noktası belirtme. Bir geçici nitelikli türe sahip bir nesne değerini değiştiren bir başvuru yokmuş gibi davranan bir **Temizleme** yönergesi bu nesnede izleyen bir dizi noktası belirtme.

Dikkat edin çünkü **Temizleme** yönergesi, bir C dili deyimi sözdizimi bir parçası olarak sahip değil, bir program içindeki yerleşimi bazı kısıtlamalar vardır. Bkz: [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) resmi dilbilgisi için. Aşağıdaki örnek bu kısıtlamaları gösterir.

```
/* ERROR - The flush directive cannot be the immediate
*          substatement of an if statement.
*/
if (x!=0)
   #pragma omp flush (x)
...

/* OK - The flush directive is enclosed in a
*      compound statement
*/
if (x!=0) {
   #pragma omp flush (x)
}
```

Kısıtlamaları **Temizleme** yönerge aşağıdaki gibidir:

- Belirtilen bir değişken bir **Temizleme** yönergesi değil bir başvuru türü olmalıdır.