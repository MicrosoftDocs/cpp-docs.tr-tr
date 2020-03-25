---
title: Bağlayıcı Araçları Uyarısı LNK4206
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: 1758fffb72e183e8a186d115b2b3f3b30c32e047
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193891"
---
# <a name="linker-tools-warning-lnk4206"></a>Bağlayıcı Araçları Uyarısı LNK4206

> önceden derlenmiş tür bilgileri bulunamadı; '*filename*' bağlı değil veya üzerine yazıldı; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

[/Rivc](../../build/reference/yc-create-precompiled-header-file.md)kullanılarak derlenen *filename* nesne dosyası, bağlantı komutunda belirtilmemiş veya üzerine yazıldı.

Bu uyarı için yaygın bir senaryo,/Rivc ile derlenen. obj bir kitaplıkta ve kodunuzda bu. obj öğesine hiçbir sembol başvurusunun olmadığı yerdir.  Bu durumda bağlayıcı,. obj dosyasını kullanmaz (veya hatta görmeyecektir).  Bu durumda, kodunuzu yeniden derlemeniz ve [/yu](../../build/reference/yu-use-precompiled-header-file.md)kullanarak derlenen nesneler için [/rivl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) kullanmanız gerekir.
