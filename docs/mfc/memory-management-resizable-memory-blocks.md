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
ms.openlocfilehash: 308b5aa00aeb1f0e7887ad90bad79a28b361d7c7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217928"
---
# <a name="memory-management-resizable-memory-blocks"></a>Bellek Yönetimi: Yeniden Boyutlandırılabilir Bellek Blokları

**`new`** **`delete`** [Bellek yönetimi: örnekler](memory-management-examples.md)bölümünde açıklanan ve işleçleri, sabit boyutlu bellek blokları ve nesneleri ayırmak ve ayırmayı yapmak için uygundur. Bazen, uygulamanız yeniden boyutlandırılabilir bellek bloklarına ihtiyaç duyar. Yığın üzerinde yeniden boyutlandırılabilir bellek bloklarını yönetmek için [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md)ve [Free](../c-runtime-library/reference/free.md) standart C çalışma zamanı kitaplığı işlevlerini kullanmanız gerekir.

> [!IMPORTANT]
> **`new`** Ve **`delete`** işleçlerini aynı bellek bloğunda yeniden boyutlandırılabilir bellek ayırma işlevleriyle KARıŞTıRMAK, MFC 'Nin hata ayıklama sürümünde bozulmuş bellek oluşmasına neden olur. İle ayrılmış bir bellek bloğunda **realloc** kullanmamalısınız **`new`** . Benzer şekilde, bir bellek bloğunu **`new`** işleçle ayırmamalıdır ve **ücretsiz**olarak silmelisiniz veya **`delete`** **malloc**ile ayrılmış bir bellek bloğunda işlecini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek yönetimi: yığın ayırma](memory-management-heap-allocation.md)
