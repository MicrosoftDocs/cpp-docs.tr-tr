---
title: /VERSION (Sürüm Bilgileri)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
ms.openlocfilehash: 3e24a5307b8c4f60f29de390d38d9694f1cacf29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529707"
---
# <a name="version-version-information"></a>/VERSION (Sürüm Bilgileri)

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>Arguments

*Ana* ve *küçük*<br/>
İstediğiniz .exe veya .dll dosyasının üst bilgisinde sürüm numarası.

## <a name="remarks"></a>Açıklamalar

/ VERSION seçeneği .exe veya .dll dosyasının üst bilgisinde sürüm numarası put söyler. DUMPBIN kullanma [OPTIONAL ](../../build/reference/headers.md) /VERSION etkisini görmek için isteğe bağlı üstbilgi değerleri alanının görüntü sürümünü görmek için.

*Ana* ve *küçük* bağımsız değişkenler 0 ile 65.535 aralığındaki ondalık sayı. Varsayılan değer 0,0 sürümüdür.

/ VERSION ile belirtilen bilgileri dosya Gezgini'nde özelliklerini görüntülerken bir uygulama için görüntülenen sürüm bilgilerini etkilemez. Bu sürüm bilgileri, uygulama oluşturmak için kullanılan bir kaynak dosyasından gelir. Bkz: [sürüm bilgileri Düzenleyicisi](../../windows/version-information-editor.md) daha fazla bilgi için.

Bir sürüm numarası eklemek için başka bir yöntem, [sürüm](../../build/reference/version-c-cpp.md) modül-tanımlama bildirimi.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **genel** özellik sayfası.

1. Değiştirme **sürüm** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)