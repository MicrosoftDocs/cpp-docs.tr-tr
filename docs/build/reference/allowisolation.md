---
description: Daha fazla bilgi edinin:/ALLOWıSOLATION
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION_EDITBIN
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 7d935bc122b5f32bb8f1193feae58b5fc61e7faa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179596"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Bildirim arama için davranışı belirtir.

## <a name="syntax"></a>Syntax

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/Allowısolation** , işletim sisteminin bildirim aramalarını ve yüklemelerini sağlar.

**/Allowisolation** varsayılandır.

**/Allowisolation: Hayır** , yürütülebilir dosyaların hiçbir bildirim olmadığı gibi yüklendiğini belirtir ve [editbin başvurusunun](editbin-reference.md) `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` isteğe bağlı üst bilgi alanında biti ayarlamaya neden olur `DllCharacteristics` .

Bir yürütülebilir dosya için yalıtım devre dışı bırakıldığında, Windows yükleyicisi yeni oluşturulan işlem için bir uygulama bildirimi bulmaya çalışır. Yeni işlem, yürütülebilir dosyada bir bildirim olsa veya çalıştırılabilir *-Name*. exe. manifest adına sahip bir bildirim varsa bile varsayılan etkinleştirme bağlamına sahip değildir.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)<br/>
[/ALLOWISOLATION (bildirim arama)](allowisolation-manifest-lookup.md)<br/>
[Bildirim dosyaları başvurusu](/windows/win32/SbsCs/manifest-files-reference)
