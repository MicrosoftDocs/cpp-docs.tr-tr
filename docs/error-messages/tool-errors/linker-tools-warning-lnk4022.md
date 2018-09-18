---
title: Bağlayıcı araçları uyarısı LNK4022 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 644e7a9ba26dab15e2bfa2a269f62c04f0510180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041005"
---
# <a name="linker-tools-warning-lnk4022"></a>Bağlayıcı Araçları Uyarısı LNK4022

'symbol' sembolü için benzersiz eşleşme bulunamıyor

BAĞLANTI veya birden çok bulunan LIB için belirli tamamlanmamış sembol eşleşir ve belirsizlik çözümlenemedi. Çıkış dosyası (.exe, .dll, .exp veya .lib) oluşturulur. Bu uyarı, bir uyarı tarafından izlenen [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) her biri için yinelenen sembol ve son olarak önemli bir hata tarafından izlenir [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).

Bu uyarıyı engellemek için düzenlenmiş hâli içinde Sembol belirtin. Çalıştırma [DUMPBIN](../../build/reference/dumpbin-options.md) görmek için bir nesnede düzenlenmiş adları.