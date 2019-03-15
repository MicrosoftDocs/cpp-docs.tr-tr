---
title: Dosya Adı Makroları
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
ms.openlocfilehash: 54527c6f06bee396fdc7419647c607f8979c6a38
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823683"
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

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE Makroları](special-nmake-macros.md)
