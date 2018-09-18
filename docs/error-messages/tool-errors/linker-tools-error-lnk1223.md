---
title: Bağlayıcı araçları hatası LNK1223 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1223
dev_langs:
- C++
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8639919c74559829367108b36d62594e2a83a91a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067999"
---
# <a name="linker-tools-error-lnk1223"></a>Bağlayıcı Araçları Hatası LNK1223

dosya geçersiz veya bozuk: dosya geçersiz .pdata katılımları içeriyor

Derleyici sıralanmamış girişleri .pdata bölüme yayılan, pdata kullanan RISC platformlar için bu hata oluşur.

Bu sorunu gidermek için olmadan derlemeyi deneyin [/GL (bütün Program iyileştirmesi)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) etkin. Boş işlev gövdeleri bazı durumlarda bu hataya neden olabilir.