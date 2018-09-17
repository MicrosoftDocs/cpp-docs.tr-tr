---
title: -ALLOWISOLATION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ALLOWISOLATION
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12ee07a0ea6dbe2c3bea21aaa6b394b4c3e6f156
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704099"
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
[/ ALLOWISOLATION (bildirim arama)](../../build/reference/allowisolation-manifest-lookup.md)
[bildirimi başvuru dosyaları](/windows/desktop/SbsCs/manifest-files-reference)