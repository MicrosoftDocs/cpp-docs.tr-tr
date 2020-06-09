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
ms.openlocfilehash: 74ae94146b1ec711b586ea1fecbbc89a47b40b5e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626273"
---
# <a name="memory-management-resizable-memory-blocks"></a>Bellek Yönetimi: Yeniden Boyutlandırılabilir Bellek Blokları

[Bellek yönetimi: örnekler](memory-management-examples.md)bölümünde açıklanan **New** ve **Delete** işleçleri, sabit boyutlu bellek blokları ve nesnelerinin ayrılmasına ve ayrılmasına yönelik bir seçimdir. Bazen, uygulamanız yeniden boyutlandırılabilir bellek bloklarına ihtiyaç duyar. Yığın üzerinde yeniden boyutlandırılabilir bellek bloklarını yönetmek için [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md)ve [Free](../c-runtime-library/reference/free.md) standart C çalışma zamanı kitaplığı işlevlerini kullanmanız gerekir.

> [!IMPORTANT]
> **Yeni** ve **silme** işleçlerini aynı bellek bloğunda yeniden boyutlandırılabilir bellek AYıRMA işlevleriyle karıştırmak, MFC 'nin hata ayıklama sürümünde bozulmuş bellek oluşmasına neden olur. **Yeni**ile ayrılmış bir bellek bloğunda **realloc** kullanmamalısınız. Benzer şekilde, **Yeni** işleçle bir bellek bloğu ayırmamalıdır ve **ücretsiz**olarak silmelisiniz ya da **malloc**ile ayrılmış bir bellek bloğunda **Delete** işlecini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Yönetimi: Öbek Ayırma](memory-management-heap-allocation.md)
