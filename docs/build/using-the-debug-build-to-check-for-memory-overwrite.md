---
title: Belleğin Üzerine Yazma Denetimi için Hata Ayıklama Derlemesini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 152f72749d2ebdacd46dd3e4db671bc5705d4b6a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213755"
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

Bu iletilerden birini görürseniz, hasarın nerede oluştuğunu öğrenmek için kodunuzda ileretmeniz gerekir. Bellek üzerine yazma gerçekleştiği yerde daha kesin bir şekilde yalıtmak için kendinize açık çağrılar yapabilirsiniz `AfxCheckMemory` . Örnek:

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

İlk onaylama başarılı olursa ikinci bir tane başarısız olursa, iki çağrı arasındaki işlevde bellek üzerine yazma oluşması gerektiği anlamına gelir.

Uygulamanızın yapısına bağlı olarak, `afxMemDF` programınızın hatta test için çok yavaş çalışmasına neden olduğunu fark edebilirsiniz. `afxMemDF`Değişken, `AfxCheckMemory` New ve delete için her çağrı için çağrılmasına neden olur. Bu durumda, yukarıda gösterildiği gibi kendi çağrılarınızı () için bir dağılım yapmanız `AfxCheckMemory` ve bellek üzerine yazmayı bu şekilde yalıtmak için denemeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Yayın derleme sorunlarını giderme](fixing-release-build-problems.md)
