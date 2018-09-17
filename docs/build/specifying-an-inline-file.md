---
title: Satır içi dosya belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73983094f10088920100b4fbbb8d870aee13f05e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720570"
---
# <a name="specifying-an-inline-file"></a>Satır İçi Dosya Belirtme

İki açılı ayraçlar belirtin (<<) komutta burada *filename* görünecektir. Açılı ayraçlar, bir makro genişletmesinin olamaz.

## <a name="syntax"></a>Sözdizimi

```
<<[filename]
```

## <a name="remarks"></a>Açıklamalar

Komutu çalıştırdığınızda, açılı ayraçlar tarafından değiştirilir *filename*, belirtilmişse veya NMAKE tarafından oluşturulan benzersiz bir ad. Belirtilmişse *filename* açılı ayraçlar boşluk veya sekme olmadan izlemeniz gerekir. Bir yol izin verilir. Hiçbir uzantı gerekli veya varsayılır. Varsa *filename* belirtilirse, dosyayı geçerli oluşturan veya belirtilen dizin, dosya bu adla herhangi bir mevcut üzerine; Aksi takdirde TMP dizininde oluşturulur (veya geçerli dizin, TMP ortam değişkeni tanımlı değil). Bir önceki varsa *filename* olan yeniden kullanılabilir NMAKE önceki dosyanın yerini alır.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](../build/inline-files-in-a-makefile.md)