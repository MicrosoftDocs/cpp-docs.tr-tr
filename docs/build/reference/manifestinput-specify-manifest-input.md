---
title: /MANIFESTINPUT (Bildirim Girişini Belirt)
ms.date: 07/24/2019
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: 7b7bd54f98003d9158276fcf75fd61ffb5348585
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606465"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (Bildirim Girişini Belirt)

Görüntüye gömülü bildirime dahil edilecek bir bildirim giriş dosyasını belirtir.

## <a name="syntax"></a>Sözdizimi

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>Parametreler

*kısaltın*<br/>
Katıştırılmış bildirime dahil edilecek bildirim dosyası.

## <a name="remarks"></a>Açıklamalar

**/Manifestınput** seçeneği, bir çalıştırılabilir görüntüde gömülü bildirimi oluşturmak için kullanılacak bir giriş dosyasının yolunu belirtir. Birden çok bildirim giriş dosyanız varsa, her giriş dosyası için bir kez olmak üzere anahtarı birden çok kez kullanın. Bildirim giriş dosyaları, katıştırılmış bildirimi oluşturmak için birleştirilir. Bu seçenek **/manifest: embed** seçeneğini gerektirir.

Bu seçenek doğrudan Visual Studio 'da ayarlanamaz. Bunun yerine, dahil edilecek ek bildirim dosyalarını belirtmek için projenin **ek bildirim dosyaları** özelliğini kullanın. Daha fazla bilgi için bkz. [bildirim aracı özellik sayfaları](manifest-tool-property-pages.md).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
