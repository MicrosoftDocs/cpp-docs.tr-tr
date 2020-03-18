---
title: Yön Bayrağı
ms.date: 11/04/2016
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
ms.openlocfilehash: 04e096c6a62f806f4c214745a8401b1730eda3a6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443385"
---
# <a name="direction-flag"></a>Yön Bayrağı

Yön bayrağı, tüm Intel x86 uyumlu CPU 'Lara özgü bir CPU bayrağıdır. MOVS, MOVSD, MOVSW ve diğerleri gibi REP (Repeat) önekini kullanan tüm derleme yönergeleri için geçerlidir. Yön bayrağı silinirse, uygulanabilir yönergelere girilen adresler artar.

C çalışma zamanı yordamları, yön bayrağının temizlenmiş olduğunu varsayar. C çalışma zamanı işlevleri ile başka işlevler kullanıyorsanız, diğer işlevlerin yön bayrağını tek başına bırakması veya özgün durumuna geri yüklemeniz gerekir. Girişte yön bayrağının açık olması beklenirken, çalışma zamanı kodu daha hızlı ve daha verimli olur.

Dize işleme ve arabellek işleme yordamları gibi C çalışma zamanı kitaplığı işlevleri, yön bayrağının açık olmasını bekler.

## <a name="see-also"></a>Ayrıca bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
