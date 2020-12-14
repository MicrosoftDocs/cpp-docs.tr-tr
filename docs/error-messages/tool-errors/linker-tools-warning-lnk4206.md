---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4206'
title: Bağlayıcı Araçları Uyarısı LNK4206
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: 40d7a8f18a835721ff747293696d0499c0a94ef3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294151"
---
# <a name="linker-tools-warning-lnk4206"></a>Bağlayıcı Araçları Uyarısı LNK4206

> önceden derlenmiş tür bilgileri bulunamadı; '*filename*' bağlı değil veya üzerine yazıldı; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

[/Rivc](../../build/reference/yc-create-precompiled-header-file.md)kullanılarak derlenen *filename* nesne dosyası, bağlantı komutunda belirtilmemiş veya üzerine yazıldı.

Bu uyarı için yaygın bir senaryo,/Rivc ile derlenen. obj bir kitaplıkta ve kodunuzda bu. obj öğesine hiçbir sembol başvurusunun olmadığı yerdir.  Bu durumda bağlayıcı,. obj dosyasını kullanmaz (veya hatta görmeyecektir).  Bu durumda, kodunuzu yeniden derlemeniz ve [/yu](../../build/reference/yu-use-precompiled-header-file.md)kullanarak derlenen nesneler için [/rivl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) kullanmanız gerekir.
