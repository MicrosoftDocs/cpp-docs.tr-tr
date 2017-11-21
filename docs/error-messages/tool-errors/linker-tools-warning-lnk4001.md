---
title: "Bağlayıcı araçları uyarısı LNK4001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4001
dev_langs: C++
helpviewer_keywords: LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cfb73e0c62a49fe5190103987277483d29af71fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4001"></a>Bağlayıcı Araçları Uyarısı LNK4001
Nesne dosyaları belirtilen; kullanılan kitaplıkları  
  
 Bağlayıcı, bir veya daha fazla .lib dosyaları, ancak hiçbir .obj dosyaları geçirildi.  
  
 Bağlayıcı .obj dosyasında erişim olanağına sahip bir .lib dosyasındaki bilgilere erişmesi mümkün olduğundan bu uyarı diğer bağlayıcı seçenekleri açıkça belirtmeniz gerekecektir gösterir. Örneğin, belirtmek zorunda kalabilirsiniz [/makine](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), veya [/Entry](../../build/reference/entry-entry-point-symbol.md) seçenekleri.