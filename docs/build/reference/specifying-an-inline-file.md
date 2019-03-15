---
title: Satır İçi Dosya Belirtme
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
ms.openlocfilehash: 7eb123ef3f2115df5c65d266630bded8cb54baae
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824151"
---
# <a name="specifying-an-inline-file"></a>Satır İçi Dosya Belirtme

İki açılı ayraçlar belirtin (<<) komutta burada *filename* görünecektir. Açılı ayraçlar, bir makro genişletmesinin olamaz.

## <a name="syntax"></a>Sözdizimi

```
<<[filename]
```

## <a name="remarks"></a>Açıklamalar

Komutu çalıştırdığınızda, açılı ayraçlar tarafından değiştirilir *filename*, belirtilmişse veya NMAKE tarafından oluşturulan benzersiz bir ad. Belirtilmişse *filename* açılı ayraçlar boşluk veya sekme olmadan izlemeniz gerekir. Bir yol izin verilir. Hiçbir uzantı gerekli veya varsayılır. Varsa *filename* belirtilirse, dosyayı geçerli oluşturan veya belirtilen dizin, dosya bu adla herhangi bir mevcut üzerine; Aksi takdirde TMP dizininde oluşturulur (veya geçerli dizin, TMP ortam değişkeni tanımlı değil). Bir önceki varsa *filename* olan yeniden kullanılabilir NMAKE önceki dosyanın yerini alır.

## <a name="see-also"></a>Ayrıca bkz.

[Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](inline-files-in-a-makefile.md)
