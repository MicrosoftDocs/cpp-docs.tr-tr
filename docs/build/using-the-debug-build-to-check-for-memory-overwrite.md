---
title: Belleğin Üzerine Yazma Denetimi için Hata Ayıklama Derlemesini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 42e3a7f1f1c34ba5a263adfca7496c24e162ab5d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823650"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Belleğin Üzerine Yazma Denetimi için Hata Ayıklama Derlemesini Kullanma

Belleğin üzerine yazma için kontrol etmek için hata ayıklama derlemesini kullanmak için önce projenizin hata ayıklama için yeniden oluşturmanız gerekir. Ardından, çok uygulamanızın başlangıcına geçin `InitInstance` işlev ve aşağıdaki satırı ekleyin:

```
afxMemDF |= checkAlwaysMemDF;
```

Hata ayıklama bellek ayırıcısı guard bayt tüm bellek ayırmaları geçici bir çözüm getirir. Ancak, bunlar bayt koruyucu (hangi belleğin üzerine yazma gösterir) değiştirildikten olup olmadığını denetlemeden herhangi iyi desteklemez. Aksi takdirde, bu yalnızca, bir belleğin üzerine yazma ile almasını aslında izin verebilir bir arabellek sağlar.

Etkinleştirerek `checkAlwaysMemDF`, çağrı yapmak için MFC zorlayacak `AfxCheckMemory` her işlev çağrısı **yeni** veya **Sil** yapılır. Belleğin üzerine yazma algılandı, aşağıdakine benzer bir izleme iletisi oluşturur:

```
Damage Occurred! Block=0x5533
```

Şu iletilerden birini görürseniz, hasarı nerede oluştuğunu belirlemek için kodunuzda adım adım ilerleyin gerekir. Belleğin üzerine yazma oluştuğu daha kesin bir şekilde yalıtmak için yapılan açık çağrıları yapabilir `AfxCheckMemory` kendiniz. Örneğin:

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

İlk ASSERT başarılı olur ve ikincisi başarısız olursa, belleğin üzerine yazma, iki çağrı arasında işlevde oluşan gerektiğini anlamına gelir.

Uygulamanızı doğasına bağlı olarak, size, gelebilir `afxMemDF` programınızı bile test etmek için çok yavaş çalışmasına neden olur. `afxMemDF` Değişkeni neden `AfxCheckMemory` silin ve yeni yapılan her çağrı için çağrılabilir. Kendi çağrısına bu durumda, dağılım `AfxCheckMemory`böylece üzerine yukarıda da gösterildiği gibi () ve bellek ayırmak için deneyin.

## <a name="see-also"></a>Ayrıca bkz.

[Yayın Derlemesi Sorunlarını Giderme](fixing-release-build-problems.md)
