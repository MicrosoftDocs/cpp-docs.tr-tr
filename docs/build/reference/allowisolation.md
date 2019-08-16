---
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 359a68d5ec0a8c7390b5f0343530864e880a057c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493127"
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

**/Allowisolation: Hayır** , yürütülebilir dosyaların hiçbir bildirim olmadığı gibi yüklendiğini belirtir ve [editbin başvurusunun](editbin-reference.md) isteğe bağlı üst bilgi `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` `DllCharacteristics` alanında biti ayarlamaya neden olur.

Bir yürütülebilir dosya için yalıtım devre dışı bırakıldığında, Windows yükleyicisi yeni oluşturulan işlem için bir uygulama bildirimi bulmaya çalışır. Yeni işlem, yürütülebilir dosyada bir bildirim olsa veya çalıştırılabilir *-Name*. exe. manifest adına sahip bir bildirim varsa bile varsayılan etkinleştirme bağlamına sahip değildir.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)<br/>
[/ALLOWISOLATION (Bildirim Arama)](allowisolation-manifest-lookup.md)<br/>
[Bildirim dosyaları başvurusu](/windows/win32/SbsCs/manifest-files-reference)
