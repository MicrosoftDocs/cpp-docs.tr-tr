---
title: NMAKE Çalıştırma
ms.date: 09/05/2018
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
ms.openlocfilehash: 81f38792893955b476dfc7eda91ed00603924a8f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646218"
---
# <a name="running-nmake"></a>NMAKE Çalıştırma

## <a name="syntax"></a>Sözdizimi

> **NMAKE** [*seçeneği* ...] [*makroları* ...] [*hedefleri* ...] [**\@**<em>commandfile</em> ...]

## <a name="remarks"></a>Açıklamalar

NMAKE derleme yalnızca belirtilen *hedefleri* veya belirtilmezse, derleme görevleri dosyasında ilk hedef. Derleme görevleri dosyası birinci hedef olabilir bir [pseudotarget](../build/pseudotargets.md) , diğer hedefleri oluşturur. NMAKE /F ile belirtilen derleme görevleri dosyalarını kullanır. /F belirtilmemişse, geçerli dizin derleme görevleri dosyası kullanır. Hiçbir derleme görevleri dosyası belirtilmezse, çıkarım kuralları komut satırı oluşturmak için kullandığı *hedefleri*.

*Commandfile* metin dosyası (veya yanıt dosyası) komut satırı girişi içeriyor. Diğer girişler önünde veya izleyin \@ *commandfile*. Bir yol izin verilir. İçinde *commandfile*, satır sonları boşluk olarak kabul edilir. Makro tanımları, bunlar boşluk içeriyorsa tırnak içine alın.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[NMAKE seçenekleri](../build/nmake-options.md)

[Tools.ini ve NMAKE](../build/tools-ini-and-nmake.md)

[NMAKE çıkış kodları](../build/exit-codes-from-nmake.md)

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Başvurusu](../build/nmake-reference.md)