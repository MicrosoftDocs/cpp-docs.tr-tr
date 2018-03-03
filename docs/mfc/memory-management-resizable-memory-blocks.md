---
title: "Bellek Yönetimi: Yeniden boyutlandırılabilir bellek blokları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fce06d27a091ad1740c882367358cf69a6dc3e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-resizable-memory-blocks"></a>Bellek Yönetimi: Yeniden Boyutlandırılabilir Bellek Blokları
**Yeni** ve **silmek** makalede açıklanan işleçleri [bellek yönetimi: örnekler](../mfc/memory-management-examples.md), ayırma ve serbest bırakma sabit boyutlu bellek blokları için uygun olduğuna ve nesneleri. Bazen, uygulamanızın yeniden boyutlandırılabilir bellek blokları gerekebilir. Standart C çalışma zamanı kitaplığı işlevleri kullanmalısınız [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), ve [ücretsiz](../c-runtime-library/reference/free.md) yeniden boyutlandırılabilir bellek blokları yığında yönetmek için.  
  
> [!IMPORTANT]
>  Karıştırma **yeni** ve **silmek** aynı bellek bloğu yeniden boyutlandırılabilir bellek ayırma işlevlere işleçlerle MFC hata ayıklama sürümü bozuk bellek neden olur. Kullanılamaz `realloc` bir bellek bloğu ile ayrılmış **yeni**. Benzer şekilde, bir bellek bloğu ile ayırmanız gerekir değil **yeni** işleci ve onunla silme **ücretsiz**, veya **silmek** ileayrılmışbellekbloğuişlecinin`malloc`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek Yönetimi: Öbek Ayırma](../mfc/memory-management-heap-allocation.md)

