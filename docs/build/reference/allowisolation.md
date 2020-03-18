---
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION_EDITBIN
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 3dae8ee83e25492fab0ba2c6a55681728d5f3453
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440378"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Bildirim arama için davranışı belirtir.

## <a name="syntax"></a>Sözdizimi

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/Allowısolation** , işletim sisteminin bildirim aramalarını ve yüklemelerini sağlar.

**/Allowisolation** varsayılandır.

**/Allowisolation: Hayır** , yürütülebilir dosyaların hiçbir bildirim olmadığı gibi yüklendiğini ve [editbin başvurusunun](editbin-reference.md) , isteğe bağlı üstbilginin `DllCharacteristics` alanındaki `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bitini ayarlamaya neden olur.

Bir yürütülebilir dosya için yalıtım devre dışı bırakıldığında, Windows yükleyicisi yeni oluşturulan işlem için bir uygulama bildirimi bulmaya çalışır. Yeni işlem, yürütülebilir dosyada bir bildirim olsa veya çalıştırılabilir *-Name*. exe. manifest adına sahip bir bildirim varsa bile varsayılan etkinleştirme bağlamına sahip değildir.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)<br/>
[/ALLOWISOLATION (Bildirim Arama)](allowisolation-manifest-lookup.md)<br/>
[Bildirim dosyaları başvurusu](/windows/win32/SbsCs/manifest-files-reference)
