---
title: 2.7.2.1 private
ms.date: 11/04/2016
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
ms.openlocfilehash: c1a2560eb80c848605698c435e3a0f0f7e66b75a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536961"
---
# <a name="2721-private"></a>2.7.2.1 private

`private` Yan tümcesi bir takım içindeki her iş parçacığı için özel olarak değişken listesi değişkenlerinde bildirir. Söz dizimi `private` yan tümcesi şu şekildedir:

```
private(variable-list)
```

Belirtilen değişken davranışını bir `private` yan tümcesi aşağıdaki gibidir. Otomatik depolama süresine sahip yeni bir nesne için yapı ayrılır. Boyutu ve hizalama yeni nesnenin değişken türüne göre belirlenir. Bu ayırma, takım içindeki her iş parçacığı için bir kez gerçekleşir ve sınıf nesnesi için gerekirse bir varsayılan oluşturucu çağrılır. Aksi takdirde ilk belirsiz değerdir.  Değişkeni tarafından başvurulan özgün nesne girişte yapısı için belirsiz bir değere sahip, yapı dinamik kapsam içinde değiştirilmemelidir ve yapı gelen Çıkışta belirsiz bir değere sahip.

Yönerge yapısı sözcük kapsamını, iş parçacığı tarafından ayrılan yeni özel nesne değişkeni başvuruyor.

Kısıtlamaları `private` yan tümcesi aşağıdaki gibidir:

- Belirtilen sınıf türüne sahip bir değişken bir `private` yan tümcesi bir erişilebilir, açık bir varsayılan oluşturucusu olmalıdır.

- Belirtilen bir değişken bir `private` yan tümcesi değil olmalıdır bir **const**-yetkili türü tür bir sınıf sahip olmadığı sürece bir `mutable` üyesi.

- Belirtilen bir değişken bir `private` yan tümcesi eksik bir türü veya bir başvuru türü değil olmalıdır.

- Görünen değişkenleri `reduction` yan tümcesi bir **paralel** yönergesi belirtilemez bir `private` iş paylaşım için paralel yapı bağlayan bir yönerge yan tümcesi.