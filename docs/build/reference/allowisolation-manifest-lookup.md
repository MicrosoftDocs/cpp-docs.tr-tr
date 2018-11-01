---
title: /ALLOWISOLATION (Bildirim Arama)
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
ms.openlocfilehash: 7b2cb4160a0d25aa65d2c5eb345ba1bc08b1c6b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428099"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Bildirim Arama)

Bildirim arama davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/ALLOWISOLATION:No** DLL'ler yüklü hiçbir bildirim olduysa olarak gösterir ve ayarlamak bağlayıcı neden `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` isteğe bağlı üst bilgisinde ait bit `DllCharacteristics` alan.

**/ ALLOWISOLATION** aramalar ve yükleri bildirim işletim sisteminin neden olur.

**/ ALLOWISOLATION** varsayılandır.

Bir yürütülebilir dosya için yalıtım devre dışı bırakıldığında, yeni oluşturulan işlem için bir uygulama bildirimi bulmak Windows Yükleyici denemez. Yeni işlem olsa bile bir bildirim yürütülebilir veya yürütülebilir dosya adı ile aynı dizine yerleştirilmiştir içinde varsayılan etkinleştirme bağlamı olmaz <em>yürütülebilir dosya adı</em>**. exe.manifest**.

Daha fazla bilgi için [bildirim dosyaları başvuru](/windows/desktop/SbsCs/manifest-files-reference).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **bildirim dosyası** özellik sayfası.

1. Değiştirme **izin yalıtım** özelliği.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
