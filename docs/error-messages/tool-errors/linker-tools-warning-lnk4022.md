---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4022'
title: Bağlayıcı Araçları Uyarısı LNK4022
ms.date: 11/04/2016
f1_keywords:
- LNK4022
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
ms.openlocfilehash: f0f968bf8e562d87e2227fb67f7a37b450c813b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331946"
---
# <a name="linker-tools-warning-lnk4022"></a>Bağlayıcı Araçları Uyarısı LNK4022

' symbol ' sembolü için benzersiz eşleşme bulunamıyor

BAĞLANTı veya LıB, belirtilen açıklanmayan sembol için birden fazla eşleşme buldu ve belirsizlik çözümlenemedi. Çıkış dosyası (. exe,. dll,. exp veya. lib) üretilmez. Bu uyarı, her bir yinelenen sembol için bir uyarı [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) ve son olarak önemli hata [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md)tarafından izlenir.

Bu uyarıyı engellemek için, sembolü düzenlenmiş biçimde belirtin. Düzenlenmiş adları görmek için nesnede [dumpbin](../../build/reference/dumpbin-options.md) ' i çalıştırın.
