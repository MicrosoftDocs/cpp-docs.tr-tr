---
title: Yön Bayrağı
description: Microsoft C çalışma zamanı işlevlerinde CPU yönü bayrağının etkisini açıklar.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
ms.openlocfilehash: ce4198abd944d538261b9d89bfa9ecea6129a991
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514713"
---
# <a name="direction-flag"></a>Yön Bayrağı

Yön bayrağı, tüm Intel x86 uyumlu CPU 'Lara özgü bir CPU bayrağıdır. MOVS, MOVSD, MOVSW ve diğerleri gibi REP (Repeat) önekini kullanan tüm derleme yönergeleri için geçerlidir. Yön bayrağı silinirse, uygulanabilir yönergelere girilen adresler artar.

C çalışma zamanı yordamları, yön bayrağının temizlenmiş olduğunu varsayar. C çalışma zamanı işlevleri ile başka işlevler kullanıyorsanız, diğer işlevlerin yön bayrağını tek başına bırakması veya özgün durumuna geri yüklemeniz gerekir. Girişte yön bayrağının açık olması beklenirken, çalışma zamanı kodu daha hızlı ve daha verimli olur.

Dize işleme ve arabellek işleme yordamları gibi C Run-Time kitaplığı işlevleri, yön bayrağının açık olmasını bekler.

## <a name="see-also"></a>Ayrıca bkz.

[C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
