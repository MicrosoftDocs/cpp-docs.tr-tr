---
title: Bağlayıcı araçları uyarısı LNK4001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f684e85233c4df777a53f03f07936137c425946e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070425"
---
# <a name="linker-tools-warning-lnk4001"></a>Bağlayıcı Araçları Uyarısı LNK4001

nesne dosyası belirtilmedi; kitaplıklar kullanıldı

Bağlayıcı, bir veya daha fazla .lib dosyaları, ancak hiçbir .obj dosyaları geçirildi.

Bağlayıcı bilgilerini bir .obj dosyasına erişim yetkisine sahip bir .lib dosyasına erişmek mümkün olmadığından, bu uyarı, açıkça diğer bağlayıcı seçenekleri belirtmek zorunda kalacaksınız gösterir. Örneğin, belirtmeniz gerekebilir [/makine](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), veya [/Entry](../../build/reference/entry-entry-point-symbol.md) seçenekleri.