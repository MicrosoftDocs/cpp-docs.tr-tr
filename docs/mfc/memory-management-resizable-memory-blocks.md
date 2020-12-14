---
description: 'Daha fazla bilgi edinin: bellek yönetimi: yeniden boyutlandırılabilir bellek blokları'
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
ms.openlocfilehash: bcca5617a0d59a7dd5c6a1f9c9f82cb5876f1ef5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248885"
---
# <a name="memory-management-resizable-memory-blocks"></a>Bellek Yönetimi: Yeniden Boyutlandırılabilir Bellek Blokları

**`new`** **`delete`** [Bellek yönetimi: örnekler](memory-management-examples.md)bölümünde açıklanan ve işleçleri, sabit boyutlu bellek blokları ve nesneleri ayırmak ve ayırmayı yapmak için uygundur. Bazen, uygulamanız yeniden boyutlandırılabilir bellek bloklarına ihtiyaç duyar. Yığın üzerinde yeniden boyutlandırılabilir bellek bloklarını yönetmek için [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md)ve [Free](../c-runtime-library/reference/free.md) standart C çalışma zamanı kitaplığı işlevlerini kullanmanız gerekir.

> [!IMPORTANT]
> **`new`** Ve **`delete`** işleçlerini aynı bellek bloğunda yeniden boyutlandırılabilir bellek ayırma işlevleriyle KARıŞTıRMAK, MFC 'Nin hata ayıklama sürümünde bozulmuş bellek oluşmasına neden olur. İle ayrılmış bir bellek bloğunda **realloc** kullanmamalısınız **`new`** . Benzer şekilde, bir bellek bloğunu **`new`** işleçle ayırmamalıdır ve **ücretsiz** olarak silmelisiniz veya **`delete`** **malloc** ile ayrılmış bir bellek bloğunda işlecini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek yönetimi: yığın ayırma](memory-management-heap-allocation.md)
