---
title: /MANIFESTINPUT (Bildirim Girişini Belirt)
ms.date: 11/04/2016
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: bf192664a7a2402b06621167d91dff67ce0741a9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814235"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (Bildirim Girişini Belirt)

Görüntüde gömülü bildirimi eklemek için bildirim giriş dosyasını belirtir.

## <a name="syntax"></a>Sözdizimi

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Katıştırılmış bildirime dahil edilecek bildirim dosyası.

## <a name="remarks"></a>Açıklamalar

**/MANIFESTINPUT** seçeneği, yürütülebilir bir görüntüde gömülü bildirimi oluşturmak için kullanılacak bir girdi dosyasının yolunu belirtir. Giriş dosyalarını, birden çok kez anahtar kullanmak birden çok bildirim varsa — her giriş dosyası için bir kez. Bildirim giriş dosyaları katıştırılmış bildirim oluşturmak üzere birleştirilir. Bu seçenek gerektirir **/MANIFEST: ekleme** seçeneği.

Bu seçenek, doğrudan Visual Studio'nun içinde olacak şekilde ayarlanamaz. Bunun yerine, **ek bildirim dosyaları** dahil etmek için ek bildirim dosyaları belirtmek için projenin özelliği. Daha fazla bilgi için [girdi ve çıktı, bildirim aracı, yapılandırma özellikleri, \<Projectname > özellik sayfaları iletişim kutusu](input-and-output-manifest-tool.md).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
