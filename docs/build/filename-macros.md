---
title: Dosya adı makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc231dfb156460a2a0cc383b6d038a98c6e2015b
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894414"
---
# <a name="filename-macros"></a>Dosya Adı Makroları

Dosya adı makroları, bağımlılık (disk üzerinde değil tam dosya adı belirtimleri) içinde belirtilen dosya adları önceden tanımlanmıştır. Bu makrolar çağrıldığında parantez içine alınmış gerekmez; yalnızca bir $ gösterildiği gibi belirtin.

|Makrosu|Açıklama|
|-----------|-------------|
|**$\@**|Şu anda belirtilen geçerli hedefinin tam adı (yol, temel adı, uzantısı).|
|**$$\@**|Şu anda belirtilen geçerli hedefinin tam adı (yol, temel adı, uzantısı). Yalnızca bir bağımlılık bağımlıda olarak geçerlidir.|
|**$&#42;**|Geçerli hedefinin yolu ve temel adı eksi dosya uzantısı.|
|**$&#42;&#42;**|Tüm bağımlılıklar geçerli hedef.|
|**$?**|Tüm bağımlılıklar geçerli hedef daha sonraki bir zaman damgasına sahip.|
|**$<**|Bağımlı dosya geçerli hedef daha sonraki bir zaman damgasına sahip. Çıkarsama kurallarında komutlarda yalnızca geçerli.|

Filename önceden tanımlanmış makro bir parçası belirtmek için bir makro değiştiricisi Ekle ve değiştirilen makrosu ayraç içine alın.

|Değiştirici|Sonuçta elde edilen dosya adı bölümü|
|--------------|-----------------------------|
|**D**|Sürücü yanı sıra dizin|
|**B**|Taban adı|
|**F**|Temel adı ve uzantısı|
|**R**|Sürücü artı directory artı temel adı|

## <a name="see-also"></a>Ayrıca Bkz.

[Özel NMAKE Makroları](../build/special-nmake-macros.md)
