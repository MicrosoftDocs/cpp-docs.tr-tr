---
title: 'Bellek Yönetimi: Yeniden boyutlandırılabilir bellek blokları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92582e4255c88b9cc78368a635b27772f2e51a30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443910"
---
# <a name="memory-management-resizable-memory-blocks"></a>Bellek Yönetimi: Yeniden Boyutlandırılabilir Bellek Blokları

**Yeni** ve **Sil** makalesinde açıklanan işleçleri [bellek yönetimi: örnekler](../mfc/memory-management-examples.md), ayırma ve sabit boyutlu bellek blokları serbest bırakılıyor için uygundur ve nesneleri. Bazen, uygulamanızı yeniden boyutlandırılabilir bellek blokları gerekebilir. Standart C çalışma zamanı kitaplık işlevleri kullanmalıdır [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), ve [ücretsiz](../c-runtime-library/reference/free.md) yeniden boyutlandırılabilir bellek blokları yığında yönetmek için.

> [!IMPORTANT]
>  Karıştırma **yeni** ve **Sil** işleçleri ile aynı bellek bloğu üzerinde yeniden boyutlandırılabilir bellek ayırma işlevleri MFC hata ayıklama sürümü bozuk bellek neden olur. Kullanmamalısınız **realloc** ile ayrılmış bir bellek bloğu üzerinde **yeni**. Benzer şekilde, bir bellek bloğu ile ayırmanız gerekir değil **yeni** işleci ve ile silebilirsiniz **ücretsiz**, veya **Sil** ileayrılanbellekbloğunuişletmeni**malloc**.

## <a name="see-also"></a>Ayrıca Bkz.

[Bellek Yönetimi: Öbek Ayırma](../mfc/memory-management-heap-allocation.md)

