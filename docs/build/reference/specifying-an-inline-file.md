---
description: 'Hakkında daha fazla bilgi edinin: satır Içi dosya belirtme'
title: Satır İçi Dosya Belirtme
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
ms.openlocfilehash: 461bf507f707512aa690e81dc5752a97d0c1c4ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224614"
---
# <a name="specifying-an-inline-file"></a>Satır İçi Dosya Belirtme

*Dosya adının* görüneceği komutta iki açılı ayraçlar (<<) belirtin. Açılı ayraçlar bir makro genişletmesi olamaz.

## <a name="syntax"></a>Syntax

```
<<[filename]
```

## <a name="remarks"></a>Açıklamalar

Komut çalıştırıldığında, açılı ayraçlar, belirtilmişse *dosya adı* ile veya benzersiz bir NMAKE üretilmiş adı ile değiştirilmiştir. Belirtilmişse *dosya adı* , boşluk veya sekme olmadan açılı ayraçları izlemelidir. Bir yola izin verilir. Uzantı gerekmez veya varsayıldı. Dosya *adı* belirtilmişse, dosya geçerli veya belirtilen dizinde oluşturulur ve bu adla var olan dosyaların üzerine yazılır; Aksi takdirde, bu, TMP dizininde (veya TMP ortam değişkeni tanımlanmamışsa geçerli dizin) oluşturulur. Önceki bir *dosya adı* yeniden kullanılırsa NMAKE önceki dosyanın yerini alır.

## <a name="see-also"></a>Ayrıca bkz.

[Derleme görevleri dosyasındaki satır içi dosyalar](inline-files-in-a-makefile.md)
