---
description: Daha fazla bilgi edinin:/MANIFESTıNPUT (bildirim girişini belirt)
title: /MANIFESTINPUT (Bildirim Girişini Belirt)
ms.date: 07/24/2019
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: e4c5561779f41074a1c52593a62dd7d32ca32801
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137936"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (Bildirim Girişini Belirt)

Görüntüye gömülü bildirime dahil edilecek bir bildirim giriş dosyasını belirtir.

## <a name="syntax"></a>Sözdizimi

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Katıştırılmış bildirime dahil edilecek bildirim dosyası.

## <a name="remarks"></a>Açıklamalar

**/Manifestınput** seçeneği, bir çalıştırılabilir görüntüde gömülü bildirimi oluşturmak için kullanılacak bir giriş dosyasının yolunu belirtir. Birden çok bildirim giriş dosyanız varsa, her giriş dosyası için bir kez olmak üzere anahtarı birden çok kez kullanın. Bildirim giriş dosyaları, katıştırılmış bildirimi oluşturmak için birleştirilir. Bu seçenek **/manifest: embed** seçeneğini gerektirir.

Bu seçenek doğrudan Visual Studio 'da ayarlanamaz. Bunun yerine, dahil edilecek ek bildirim dosyalarını belirtmek için projenin **ek bildirim dosyaları** özelliğini kullanın. Daha fazla bilgi için bkz. [bildirim aracı özellik sayfaları](manifest-tool-property-pages.md).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
