---
title: Belleğin Üzerine Yazma Denetimi için Hata Ayıklama Derlemesini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 42e3a7f1f1c34ba5a263adfca7496c24e162ab5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314292"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Belleğin Üzerine Yazma Denetimi için Hata Ayıklama Derlemesini Kullanma

Bellek üzerine yazmayı denetlemek üzere hata ayıklama derlemesini kullanmak için, önce projenizi hata ayıklama için yeniden oluşturmanız gerekir. Ardından, uygulamanızın `InitInstance` işlevinin en başına bölümüne gidin ve aşağıdaki satırı ekleyin:

```
afxMemDF |= checkAlwaysMemDF;
```

Hata ayıklama belleği ayırıcısı, tüm bellek ayırmalarının her türlü koruma baytlarını koyar. Ancak, bu koruma baytları değiştirilip değiştirilmediğini (bir belleğin üzerine yazma olduğunu gösterir) kontrol etmediğiniz takdirde hiçbir şey yapmayın. Aksi takdirde, bunun aslında bir bellek üzerine yazma ile uzaklaşabilme olanağı sağlayan bir arabellek sağlar.

`checkAlwaysMemDF`Öğesini etkinleştirerek, her **Yeni** veya **silme** çağrısı yapıldığında MFC 'yi `AfxCheckMemory` işleve bir çağrı yapmaya zorlarsınız. Bellek üzerine yazma algılanırsa, aşağıdakine benzer bir Izleme iletisi oluşturacaktır:

```
Damage Occurred! Block=0x5533
```

Bu iletilerden birini görürseniz, hasarın nerede oluştuğunu öğrenmek için kodunuzda ileretmeniz gerekir. Bellek üzerine yazma gerçekleştiği yerde daha kesin bir şekilde yalıtmak için `AfxCheckMemory` kendinize açık çağrılar yapabilirsiniz. Örneğin:

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

İlk onaylama başarılı olursa ikinci bir tane başarısız olursa, iki çağrı arasındaki işlevde bellek üzerine yazma oluşması gerektiği anlamına gelir.

Uygulamanızın yapısına bağlı olarak, programınızın hatta test için çok yavaş çalışmasına `afxMemDF` neden olduğunu fark edebilirsiniz. Değişken `afxMemDF` , New `AfxCheckMemory` ve delete için her çağrı için çağrılmasına neden olur. Bu durumda, yukarıda gösterildiği gibi kendi çağrılarınızı () `AfxCheckMemory`için bir dağılım yapmanız ve bellek üzerine yazmayı bu şekilde yalıtmak için denemeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Yayın Derlemesi Sorunlarını Giderme](fixing-release-build-problems.md)
