---
title: "Bağlayıcı araçları uyarısı LNK4070 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4070
dev_langs: C++
helpviewer_keywords: LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca0a31fb3512b7b11150984fc3d15013cb75c0e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4070"></a>Bağlayıcı Araçları Uyarısı LNK4070
/OUT:filename yönergesinde. EXP çıktı dosyası adını 'filename'; ' farklıdır göz ardı yönergesi  
  
 `filename` Belirtilen [adı](../../build/reference/name-c-cpp.md) veya [Kitaplığı](../../build/reference/library.md) .exp dosyasını oluştururken deyimi farklı çıktısını `filename` , varsayılan olarak kabul veya ilebelirtilen[/OUT](../../build/reference/out-output-file-name.md) seçeneği.  
  
 Geliştirme ortamında ve burada projenin .def dosyası güncelleştirilmedi bir çıktı dosyası adını değiştirirseniz, bu uyarıyı görürsünüz. Bu uyarıyı çözümlemek için .def dosyası el ile güncelleştirin.  
  
 Sonuçta elde edilen DLL kullanan bir istemci programı sorunlarla karşılaşabilirsiniz.