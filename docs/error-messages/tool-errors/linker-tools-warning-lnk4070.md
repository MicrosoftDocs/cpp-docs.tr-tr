---
title: Bağlayıcı araçları uyarısı LNK4070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4070
dev_langs:
- C++
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e4599e96552f1b98ef0b1af8d38995ebbe5a83e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302509"
---
# <a name="linker-tools-warning-lnk4070"></a>Bağlayıcı Araçları Uyarısı LNK4070
/OUT:filename yönergesinde. EXP çıktı dosyası adını 'filename'; ' farklıdır göz ardı yönergesi  
  
 `filename` Belirtilen [adı](../../build/reference/name-c-cpp.md) veya [Kitaplığı](../../build/reference/library.md) .exp dosyasını oluştururken deyimi farklı çıktısını `filename` , varsayılan olarak kabul veya ilebelirtilen[/OUT](../../build/reference/out-output-file-name.md) seçeneği.  
  
 Geliştirme ortamında ve burada projenin .def dosyası güncelleştirilmedi bir çıktı dosyası adını değiştirirseniz, bu uyarıyı görürsünüz. Bu uyarıyı çözümlemek için .def dosyası el ile güncelleştirin.  
  
 Sonuçta elde edilen DLL kullanan bir istemci programı sorunlarla karşılaşabilirsiniz.