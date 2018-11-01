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
ms.openlocfilehash: ab07e3ac3f8c154ffa62a25ab8bad967b255e2e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604980"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Bildirim arama davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/ ALLOWISOLATION** aramalar ve yükleri bildirim işletim sisteminin neden olur.

**/ ALLOWISOLATION** varsayılandır.

**/ALLOWISOLATION:No** yokmuş gibi hiçbir bildirim ve nedenleri yürütülebilir dosyaları yüklendiğini gösteren [EDITBIN başvurusu](../../build/reference/editbin-reference.md) ayarlanacak `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` isteğe bağlı üst bilgisinde ait bit `DllCharacteristics` alan.

Bir yürütülebilir dosya için yalıtım devre dışı bırakıldığında, Windows Yükleyicisi için yeni oluşturulan işlemi bir uygulama bildirimi bulmak dener. Yeni işlem yürütülebilir bildiriminde yok ya da bir bildirim yoksa, adına sahip olsa bile varsayılan etkinleştirme bağlamı yok *yürütülebilir dosya adı*. exe.manifest.

## <a name="see-also"></a>Ayrıca Bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)<br/>
[/ALLOWISOLATION (Bildirim Arama)](../../build/reference/allowisolation-manifest-lookup.md)<br/>
[Bildirim dosyaları başvurusu](/windows/desktop/SbsCs/manifest-files-reference)