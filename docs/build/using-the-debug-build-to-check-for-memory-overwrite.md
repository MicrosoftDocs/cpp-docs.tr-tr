---
description: 'Hakkında daha fazla bilgi edinin: bellek üzerine yazmayı denetlemek için hata ayıklama derlemesini kullanma'
title: Belleğin Üzerine Yazma Denetimi için Hata Ayıklama Derlemesini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 03981696a0314632aebb959d6fa1d986145c087c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199070"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Belleğin Üzerine Yazma Denetimi için Hata Ayıklama Derlemesini Kullanma

Bellek üzerine yazmayı denetlemek üzere hata ayıklama derlemesini kullanmak için, önce projenizi hata ayıklama için yeniden oluşturmanız gerekir. Ardından, uygulamanızın işlevinin en başına bölümüne gidin `InitInstance` ve aşağıdaki satırı ekleyin:

```
afxMemDF |= checkAlwaysMemDF;
```

Hata ayıklama belleği ayırıcısı, tüm bellek ayırmalarının her türlü koruma baytlarını koyar. Ancak, bu koruma baytları değiştirilip değiştirilmediğini (bir belleğin üzerine yazma olduğunu gösterir) kontrol etmediğiniz takdirde hiçbir şey yapmayın. Aksi takdirde, bunun aslında bir bellek üzerine yazma ile uzaklaşabilme olanağı sağlayan bir arabellek sağlar.

`checkAlwaysMemDF`Öğesini etkinleştirerek, `AfxCheckMemory` her bir çağrı **`new`** yapıldığında veya yapıldığında, MFC 'yi işleve bir çağrı yapmaya zorlarsınız **`delete`** . Bellek üzerine yazma algılanırsa, aşağıdakine benzer bir Izleme iletisi oluşturacaktır:

```
Damage Occurred! Block=0x5533
```

Bu iletilerden birini görürseniz, hasarın nerede oluştuğunu öğrenmek için kodunuzda ileretmeniz gerekir. Bellek üzerine yazma gerçekleştiği yerde daha kesin bir şekilde yalıtmak için kendinize açık çağrılar yapabilirsiniz `AfxCheckMemory` . Örneğin:

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

İlk onaylama başarılı olursa ikinci bir tane başarısız olursa, iki çağrı arasındaki işlevde bellek üzerine yazma oluşması gerektiği anlamına gelir.

Uygulamanızın yapısına bağlı olarak, `afxMemDF` programınızın hatta test için çok yavaş çalışmasına neden olduğunu fark edebilirsiniz. `afxMemDF`Değişken, `AfxCheckMemory` New ve delete için her çağrı için çağrılmasına neden olur. Bu durumda, yukarıda gösterildiği gibi kendi çağrılarınızı () için bir dağılım yapmanız `AfxCheckMemory` ve bellek üzerine yazmayı bu şekilde yalıtmak için denemeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Yayın derleme sorunlarını giderme](fixing-release-build-problems.md)
