---
title: Bağlayıcı Araçları Uyarısı LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: aaa26393f1ce76d3e1bc40e5ba4978d1bcdb4fc9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193764"
---
# <a name="linker-tools-warning-lnk4237"></a>Bağlayıcı Araçları Uyarısı LNK4237

' Dll 'den içeri aktarılırken/SUBSYSTEM: NATIVE belirtildi; /SUBSYSTEM: CONSOLE veya/SUBSYSTEM: WINDOWS kullanın.

[/Subsystem: NATIVE](../../build/reference/subsystem-specify-subsystem.md) , aşağıdakilerden birini veya daha fazlasını doğrudan kullanan bir Windows (Win32) uygulaması oluşturulurken belirtildi:

- paketindeki

- Gdi32.dll

- user32.dll

- Msvcrt\* dll 'lerden biri.

**/Subsystem: NATIVE**belirtilmeden bu uyarıyı çözün.
