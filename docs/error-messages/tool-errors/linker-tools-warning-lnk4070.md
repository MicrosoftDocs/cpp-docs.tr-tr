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
ms.openlocfilehash: 9cfb4ae1c5440742c491d9615a2b4929a9b04f66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106966"
---
# <a name="linker-tools-warning-lnk4070"></a>Bağlayıcı Araçları Uyarısı LNK4070

/ Out: filename yönergesi. EXP farklı çıkış dosya 'filename'; yönerge yoksayılıyor

`filename` Belirtilen [adı](../../build/reference/name-c-cpp.md) veya [Kitaplığı](../../build/reference/library.md) .exp dosyası oluşturulurken deyimi farklı çıktısı `filename` , varsayılan olarak veya ilebelirtilen[/OUT](../../build/reference/out-output-file-name.md) seçeneği.

Geliştirme ortamındaki ve burada projenin .def dosyasında güncelleştirilmedi bir çıktı dosyası adını değiştirirseniz, bu uyarıyı görürsünüz. Bu uyarıyı çözümlemek için .def dosyasının el ile güncelleştirin.

Ortaya çıkan DLL'yi kullanan bir istemci programı sorunlarla karşılaşabilirsiniz.