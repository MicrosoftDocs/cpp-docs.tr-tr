---
title: "Bağlayıcı araçları uyarısı LNK4001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ecc78fe50fd34a0c6f583bf103d368e23f19f2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4001"></a>Bağlayıcı Araçları Uyarısı LNK4001
Nesne dosyaları belirtilen; kullanılan kitaplıkları  
  
 Bağlayıcı, bir veya daha fazla .lib dosyaları, ancak hiçbir .obj dosyaları geçirildi.  
  
 Bağlayıcı .obj dosyasında erişim olanağına sahip bir .lib dosyasındaki bilgilere erişmesi mümkün olduğundan bu uyarı diğer bağlayıcı seçenekleri açıkça belirtmeniz gerekecektir gösterir. Örneğin, belirtmek zorunda kalabilirsiniz [/makine](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), veya [/Entry](../../build/reference/entry-entry-point-symbol.md) seçenekleri.