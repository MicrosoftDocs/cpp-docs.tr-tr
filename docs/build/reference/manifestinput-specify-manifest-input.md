---
title: -MANIFESTINPUT (bildirim girişini belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5259df2216a8c844123c308ece7ac6b0b650ab39
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705173"
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

Bu seçenek, doğrudan Visual Studio'nun içinde olacak şekilde ayarlanamaz. Bunun yerine, **ek bildirim dosyaları** dahil etmek için ek bildirim dosyaları belirtmek için projenin özelliği. Daha fazla bilgi için [girdi ve çıktı, bildirim aracı, yapılandırma özellikleri, \<Projectname > özellik sayfaları iletişim kutusu](../../ide/input-and-output-manifest-tool.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)