---
title: /MANIFESTINPUT (Bildirim Girişini Belirt)
ms.date: 07/24/2019
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: d7c8351c915f5666ada9939df686c81c86ab89ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337498"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (Bildirim Girişini Belirt)

Görüntüye katışdırılmış bildirime dahil etmek üzere bir bildirim girişi dosyası belirtir.

## <a name="syntax"></a>Sözdizimi

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Katıştılmış bildirime dahil edilen bildirim dosyası.

## <a name="remarks"></a>Açıklamalar

**/MANIFESTINPUT** seçeneği, yürütülebilir bir görüntüde gömülü bildirimi oluşturmak için kullanılacak bir giriş dosyasının yolunu belirtir. Birden çok bildirim giriş dosyanız varsa, her giriş dosyası için bir kez anahtarlanızı birden çok kez kullanın. Bildirim giriş dosyaları katıştırılmış bildirimi oluşturmak için birleştirilir. Bu seçenek **/MANIFEST:EMBED** seçeneğini gerektirir.

Bu seçenek doğrudan Visual Studio'da ayarlanamaz. Bunun yerine, ek bildirim dosyaları eklemek için projenin **Ek Bildirim Dosyaları** özelliğini kullanın. Daha fazla bilgi [için, Bkz. Manifest Araç Özelliği Sayfaları.](manifest-tool-property-pages.md)

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
