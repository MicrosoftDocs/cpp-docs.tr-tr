---
description: :/MANIFEST hakkında daha fazla bilgi edinin (yan yana derleme bildirimi oluşturma)
title: /MANIFEST (Yan Yana Derleme Bildirimi Oluşturma)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
ms.openlocfilehash: 6ab5dd0c0ae04a6ac5377c1c9ee0015f8c64ad54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190711"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (Yan Yana Derleme Bildirimi Oluşturma)

```
/MANIFEST[:{EMBED[,ID=#]|NO}]
```

## <a name="remarks"></a>Açıklamalar

/MANIFEST bağlayıcının yan yana bildirim dosyası oluşturması gerektiğini belirtir. Bildirim dosyaları hakkında daha fazla bilgi için bkz. [bildirim dosyaları başvurusu](/windows/win32/SbsCs/manifest-files-reference).

Varsayılan değer/MANIFESTDıR.

/MANIFEST: EMBED seçeneği, bağlayıcının bildirim dosyasını RT_MANIFEST türünde bir kaynak olarak görüntüye katıştırması gerektiğini belirtir. İsteğe bağlı `ID` parametre, bildirim için kullanılacak kaynak kimliğidir. Yürütülebilir dosya için 1 değerini kullanın. Özel bağımlılıklar belirtmesini sağlamak için bir DLL için 2 değerini kullanın. `ID`Parametresi belirtilmemişse,/DLL seçeneği ayarlandıysa varsayılan değer 2 ' dir; Aksi takdirde varsayılan değer 1 ' dir.

Visual Studio 2008 ile başlayarak, yürütülebilir dosyalar için bildirim dosyaları, Kullanıcı hesabı denetimi (UAC) bilgilerini belirten bir bölüm içerir. /MANIFEST belirtirseniz ancak ne [/Bildiriduyak AC](manifestuac-embeds-uac-information-in-manifest.md) ne de [/DLL](dll-build-a-dll.md)belirtirseniz, UAC düzeyi *' nin varsayılan* bir UAC parçası bildirime eklenir. UAC düzeyleri hakkında daha fazla bilgi için bkz. [/bildirimini estuac (BILDIRIMDEKI UAC bilgilerini katıştırır)](manifestuac-embeds-uac-information-in-manifest.md).

UAC için varsayılan davranışı değiştirmek üzere aşağıdakilerden birini yapın:

- /, Estuac seçeneğini belirtin ve UAC düzeyini istenen değere ayarlayın.

- Ya da bildirimde bir UAC parçası oluşturmak istemiyorsanız/BILDIRIMINI estuac: NO seçeneğini belirtin.

/MANIFEST belirtmezseniz ancak [/Manifestdependency](manifestdependency-specify-manifest-dependencies.md) açıklamalarını belirtirseniz, bir bildirim dosyası oluşturulur. /MANIFEST: NO belirtirseniz bir bildirim dosyası oluşturulmaz.

/MANIFEST belirtirseniz, bildirim dosyasının adı, çıkış dosyanızın adıyla aynıdır, ancak. manifest ile dosya adına eklenir. Örneğin, çıkış dosyanızın adı MyFile.exe ise, bildirim dosya adı MyFile.exe. manifest olur.  /MANIFESTFILE:*adı* belirtirseniz, bildirimin adı *ad* bölümünde belirttiğiniz şeydir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Bağlayıcı** düğümünü genişletin.

1. **Bildirim dosyası** özellik sayfasını seçin.

1. **Bildirim oluştur** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
