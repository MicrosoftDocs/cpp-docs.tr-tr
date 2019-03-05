---
title: 'Bellek Yönetimi: Yeniden boyutlandırılabilir bellek blokları'
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: 124a2599e1523d5393fcf6255c88de0fd8cd72cd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281752"
---
# <a name="memory-management-resizable-memory-blocks"></a>Bellek Yönetimi: Yeniden boyutlandırılabilir bellek blokları

**Yeni** ve **Sil** makalesinde açıklanan işleçleri [bellek yönetimi: Örnekler](../mfc/memory-management-examples.md), ayırma ve sabit boyutlu bellek blokları ve nesneleri serbest bırakma için uygundur. Bazen, uygulamanızı yeniden boyutlandırılabilir bellek blokları gerekebilir. Standart C çalışma zamanı kitaplık işlevleri kullanmalıdır [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), ve [ücretsiz](../c-runtime-library/reference/free.md) yeniden boyutlandırılabilir bellek blokları yığında yönetmek için.

> [!IMPORTANT]
>  Karıştırma **yeni** ve **Sil** işleçleri ile aynı bellek bloğu üzerinde yeniden boyutlandırılabilir bellek ayırma işlevleri MFC hata ayıklama sürümü bozuk bellek neden olur. Kullanmamalısınız **realloc** ile ayrılmış bir bellek bloğu üzerinde **yeni**. Benzer şekilde, bir bellek bloğu ile ayırmanız gerekir değil **yeni** işleci ve ile silebilirsiniz **ücretsiz**, veya **Sil** ileayrılanbellekbloğunuişletmeni**malloc**.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Yönetimi: Yığın ayırma](../mfc/memory-management-heap-allocation.md)
