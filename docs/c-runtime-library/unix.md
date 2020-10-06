---
title: UNIX
description: Programınızı UNIX 'e taşıma yönergeleri.
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- unix
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
ms.openlocfilehash: 3975db2407943b329fa7eded0d72d63524428210
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765225"
---
# <a name="unix"></a>UNIX

Programlarınızın UNIX 'e bağlantı noktasını düşünüyorsanız, aşağıdaki yönergeleri izleyin:

- SYS alt dizininden üst bilgi dosyalarını kaldırmayın. Yalnızca programlarınızı UNIX 'e taşımayı planlamıyorsanız SYS üstbilgi dosyalarını başka bir yere yerleştirebilirsiniz.

- Yolları ve dosya adlarını bağımsız değişken olarak temsil eden dizelerdeki UNIX uyumlu yol sınırlayıcısını kullanın. UNIX, bu amaçla yalnızca eğik çizgi (/) destekler, ancak Win32 işletim sistemleri hem ters eğik çizgi () hem de eğik \\ çizgi (/) destekler. Bu belge `#include` , örneğin, ifadelerde yol sınırlayıcıları olarak UNIX uyumlu eğik çizgiler kullanır. (Ancak, Windows işletim sistemi komut kabuğu CMD.EXE, komut istemine girilen komutlarda eğik çizgiyi desteklemez.)

- Büyük/küçük harfe duyarlı olan UNIX 'te doğru şekilde çalışan yolları ve dosya adlarını kullanın. Win32 işletim sistemlerindeki dosya ayırma tablosu (FAT) dosya sistemi büyük/küçük harfe duyarlı değildir. NTFS dosya sistemi, Dizin listelerinin durumunu korur, ancak dosya aramalarındaki ve diğer sistem işlemlerinde büyük/küçük harf durumunu yoksayar.

> [!NOTE]
> Bu Visual C++ sürümünde, UNIX uyumluluk bilgileri işlev açıklamalarından kaldırılmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)
