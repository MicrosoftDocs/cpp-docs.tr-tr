---
title: Bağlayıcı Araçları Uyarısı LNK4001
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: 75ca9ec92bbba1c15efc11a731b3894ea03e33dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298795"
---
# <a name="linker-tools-warning-lnk4001"></a>Bağlayıcı Araçları Uyarısı LNK4001

nesne dosyası belirtilmedi; kitaplıklar kullanıldı

Bağlayıcı, bir veya daha fazla .lib dosyaları, ancak hiçbir .obj dosyaları geçirildi.

Bağlayıcı bilgilerini bir .obj dosyasına erişim yetkisine sahip bir .lib dosyasına erişmek mümkün olmadığından, bu uyarı, açıkça diğer bağlayıcı seçenekleri belirtmek zorunda kalacaksınız gösterir. Örneğin, belirtmeniz gerekebilir [/makine](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), veya [/Entry](../../build/reference/entry-entry-point-symbol.md) seçenekleri.