---
title: Tools.ini ve NMAKE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84406886c9aa0c0053ed7c183912bf8a7f1f4771
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723586"
---
# <a name="toolsini-and-nmake"></a>Tools.ini ve NMAKE

Derleme görevleri dosyalarını, okumadan önce /R kullanılmadığı sürece NMAKE Tools.ini okur. Tools.ini için önce geçerli dizinde, ardından INIT ortam değişkeni tarafından belirtilen dizindeki görünüyor. NMAKE ayarlarında başlatma dosyası bölümü ile başlayan `[NMAKE]` ve herhangi bir derleme görevleri dosyası bilgi içerebilir. Sayı işareti ile ayrı satırda başlayan bir açıklama belirtin (#).

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Çalıştırma](../build/running-nmake.md)