---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4070'
title: Bağlayıcı Araçları Uyarısı LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: 188c8d88fa4fec332dad80fd5afee346f6099fca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210185"
---
# <a name="linker-tools-warning-lnk4070"></a>Bağlayıcı Araçları Uyarısı LNK4070

/OUT: filename yönergesi içinde. EXP, ' filename ' çıkış dosya adından farklı; yönerge yoksayılıyor

`filename`. Exp dosyası oluşturulduğu sırada [ad](../../build/reference/name-c-cpp.md) veya [kitaplık](../../build/reference/library.md) ifadesinde belirtilen, `filename` Varsayılan olarak kabul edilen veya [/Out](../../build/reference/out-output-file-name.md) seçeneğiyle belirtilen çıktıdan farklıdır.

Geliştirme ortamında bir çıkış dosyasının adını değiştirirseniz ve projenin. def dosyasının güncel olmadığı durumlarda bu uyarıyı görürsünüz. Bu uyarıyı çözmek için. def dosyasını el ile güncelleştirin.

Ortaya çıkan DLL 'yi kullanan bir istemci program sorunlarla karşılaşabilir.
