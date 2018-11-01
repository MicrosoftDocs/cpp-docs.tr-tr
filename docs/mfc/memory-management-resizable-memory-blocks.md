---
title: 'Bellek Yönetimi: Yeniden Boyutlandırılabilir Bellek Blokları'
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: 499e2d4a99152e08f50159c4c952eb882c9fd425
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481152"
---
# <a name="memory-management-resizable-memory-blocks"></a>Bellek Yönetimi: Yeniden Boyutlandırılabilir Bellek Blokları

**Yeni** ve **Sil** makalesinde açıklanan işleçleri [bellek yönetimi: örnekler](../mfc/memory-management-examples.md), ayırma ve sabit boyutlu bellek blokları serbest bırakılıyor için uygundur ve nesneleri. Bazen, uygulamanızı yeniden boyutlandırılabilir bellek blokları gerekebilir. Standart C çalışma zamanı kitaplık işlevleri kullanmalıdır [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), ve [ücretsiz](../c-runtime-library/reference/free.md) yeniden boyutlandırılabilir bellek blokları yığında yönetmek için.

> [!IMPORTANT]
>  Karıştırma **yeni** ve **Sil** işleçleri ile aynı bellek bloğu üzerinde yeniden boyutlandırılabilir bellek ayırma işlevleri MFC hata ayıklama sürümü bozuk bellek neden olur. Kullanmamalısınız **realloc** ile ayrılmış bir bellek bloğu üzerinde **yeni**. Benzer şekilde, bir bellek bloğu ile ayırmanız gerekir değil **yeni** işleci ve ile silebilirsiniz **ücretsiz**, veya **Sil** ileayrılanbellekbloğunuişletmeni**malloc**.

## <a name="see-also"></a>Ayrıca Bkz.

[Bellek Yönetimi: Öbek Ayırma](../mfc/memory-management-heap-allocation.md)

