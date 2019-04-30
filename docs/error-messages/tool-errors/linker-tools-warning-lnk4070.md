---
title: Bağlayıcı Araçları Uyarısı LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: e7139b21f053ea8633356c7194cd719a6a4aef35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410271"
---
# <a name="linker-tools-warning-lnk4070"></a>Bağlayıcı Araçları Uyarısı LNK4070

/ Out: filename yönergesi. EXP farklı çıkış dosya 'filename'; yönerge yoksayılıyor

`filename` Belirtilen [adı](../../build/reference/name-c-cpp.md) veya [Kitaplığı](../../build/reference/library.md) .exp dosyası oluşturulurken deyimi farklı çıktısı `filename` , varsayılan olarak veya ilebelirtilen[/OUT](../../build/reference/out-output-file-name.md) seçeneği.

Geliştirme ortamındaki ve burada projenin .def dosyasında güncelleştirilmedi bir çıktı dosyası adını değiştirirseniz, bu uyarıyı görürsünüz. Bu uyarıyı çözümlemek için .def dosyasının el ile güncelleştirin.

Ortaya çıkan DLL'yi kullanan bir istemci programı sorunlarla karşılaşabilirsiniz.