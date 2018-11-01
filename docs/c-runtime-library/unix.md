---
title: UNIX
ms.date: 11/04/2016
f1_keywords:
- unix
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
ms.openlocfilehash: d7f0cc1f9bbbfb1f950c7efc1371587d805d1e9e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480190"
---
# <a name="unix"></a>UNIX

Programlarınızın UNIX bağlantı noktası planlıyorsanız, aşağıdaki yönergeleri izleyin:

- Üst bilgi dosyaları, SYS alt dizinden kaldırmayın. Yalnızca UNIX programlarınıza taşımanın planlamıyorsanız SYS üst bilgi dosyaları başka bir yere yerleştirebilirsiniz.

- UNIX-uyumlu yol sınırlayıcısını yollarını ve dosya adlarını bağımsız değişken olarak temsil eden bir dize olması yordamlarını kullanın. UNIX, yalnızca ileri eğik çizgi (/) bu amaçla, Win32 işletim sistemleri için iki eğik çizgi destek desteklerken (\\) ve eğik çizgi (/). Bu nedenle bu belgede yol ayırıcıları olarak UNIX uyumlu eğik kullanılır `#include` deyimleri, örneğin. (Ancak, Windows işletim sistemi komut kabuğunda, cmd EXE desteklemiyor eğik komut isteminde girdiğiniz komutlarda.)

- Yollar ve doğru büyük küçük harfe duyarlı olduğu UNIX içinde çalışması dosya adlarını kullanın. Win32 işletim sistemlerinde dosya ayırma tablosu (FAT) dosya sistemi büyük/küçük harfe duyarlı değildir; NTFS dosya sistemi çalışması için dizin listesinde korur, ancak dosya aramaları ve diğer sistem işlemleri durumda yok sayar.

    > [!NOTE]
    >  Visual C++'ın bu sürümünde, işlev tanımlamalardan UNIX uyumluluk bilgileri kaldırıldı.

## <a name="see-also"></a>Ayrıca Bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)