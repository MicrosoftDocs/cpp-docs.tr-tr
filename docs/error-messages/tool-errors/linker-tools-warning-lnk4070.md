---
title: Bağlayıcı Araçları Uyarısı LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: 391a477625b51fd37eacc5d455801ce90d2abbc2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194011"
---
# <a name="linker-tools-warning-lnk4070"></a>Bağlayıcı Araçları Uyarısı LNK4070

/OUT: filename yönergesi içinde. EXP, ' filename ' çıkış dosya adından farklı; yönerge yoksayılıyor

. Exp dosyası oluşturulduğu sırada [ad](../../build/reference/name-c-cpp.md) veya [kitaplık](../../build/reference/library.md) ifadesinde belirtilen `filename`, varsayılan olarak kabul edilen veya [/out](../../build/reference/out-output-file-name.md) seçeneği ile belirtilen çıkış `filename` farklıdır.

Geliştirme ortamında bir çıkış dosyasının adını değiştirirseniz ve projenin. def dosyasının güncel olmadığı durumlarda bu uyarıyı görürsünüz. Bu uyarıyı çözmek için. def dosyasını el ile güncelleştirin.

Ortaya çıkan DLL 'yi kullanan bir istemci program sorunlarla karşılaşabilir.
