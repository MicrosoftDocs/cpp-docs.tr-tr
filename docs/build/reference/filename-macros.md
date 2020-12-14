---
description: 'Daha fazla bilgi için: filename makroları'
title: Dosya Adı Makroları
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
ms.openlocfilehash: 2b10d021d27eedf008a143472715ee8e0cbecde5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200578"
---
# <a name="filename-macros"></a>Dosya Adı Makroları

Dosya adı makroları, bağımlılıkta belirtilen dosya adları olarak önceden tanımlanmıştır (diskte tam dosya adı belirtimleri değildir). Bu makroların çağrıldığında parantez içine alınması gerekmez; gösterildiği gibi yalnızca bir $ belirtin.

|Makroya|Anlamı|
|-----------|-------------|
|**$\@**|Geçerli hedefin tam adı (yol, taban adı, uzantı), şu anda belirtilmiş.|
|**$$\@**|Geçerli hedefin tam adı (yol, taban adı, uzantı), şu anda belirtilmiş. Yalnızca bir bağımlılıktan bağımsız olarak geçerlidir.|
|**$&#42;**|Geçerli hedefin yolu ve taban adı eksi dosya uzantısı.|
|**$&#42;&#42;**|Geçerli hedefin tüm bağımlıları.|
|**$?**|Tüm bağımlılar geçerli hedeften daha sonraki bir zaman damgasına sahip.|
|**$<**|Geçerli hedeften daha sonra zaman damgasıyla bağımlı dosya. Yalnızca çıkarım kurallarındaki komutlarda geçerlidir.|

Önceden tanımlanmış bir dosya adı makrosunun bir bölümünü belirtmek için bir makro değiştiricisi ekleyin ve değiştirilmiş makroyu parantez içine alın.

|Değiştirici|Sonuçta elde edilen dosya adı bölümü|
|--------------|-----------------------------|
|**TID**|Sürücü Plus dizini|
|**B**|Taban adı|
|**Vadeli**|Taban adı artı uzantısı|
|**R**|Sürücü Plus dizini artı temel adı|

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE makroları](special-nmake-macros.md)
