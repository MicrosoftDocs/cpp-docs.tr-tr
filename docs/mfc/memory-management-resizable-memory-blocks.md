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
ms.openlocfilehash: b048b60a5512ecc54750cb980ca67e2373e2c837
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364782"
---
# <a name="memory-management-resizable-memory-blocks"></a>Bellek Yönetimi: Yeniden Boyutlandırılabilir Bellek Blokları

Yeni **new** ve **silme** işleçleri, [makaleBellek Yönetimi açıklanan: Örnekler,](../mfc/memory-management-examples.md)ayırma ve sabit boyutlu bellek blokları ve nesneleri ayırmak için iyidir. Bazen, uygulamanızın yeniden boyutlandırılabilir bellek blokları gerekebilir. Standart C çalışma zamanı kitaplık işlevleri [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md) [ve](../c-runtime-library/reference/free.md) ücretsiz yığın üzerinde yeniden boyutlandırılabilir bellek blokları yönetmek için kullanmanız gerekir.

> [!IMPORTANT]
> **Yeni** ve **sil işleçlerini** aynı bellek bloğundaki yeniden boyutlandırılabilir bellek ayırma işlevleriyle karıştırmak, MFC'nin Hata Ayıklama sürümünde bozuk belleğe neden olur. Yeni **ile**ayrılmış bir bellek bloğunda **realloc** kullanmamalısınız. Aynı şekilde, **yeni** işleç ile bir bellek bloğu ayırmak ve **ücretsiz**olarak silmek gerekir , ya da **malloc**ile ayrılmış bellek bloğu üzerinde **silme** işleci kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Yönetimi: Öbek Ayırma](../mfc/memory-management-heap-allocation.md)
