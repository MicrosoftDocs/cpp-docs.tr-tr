---
title: /MANIFEST (Yan Yana Derleme Bildirimi Oluşturma)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
ms.openlocfilehash: 9a3ca3980a9cdff4e67885b2ad47ffa2385b0774
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321650"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (Yan Yana Derleme Bildirimi Oluşturma)

```
/MANIFEST[:{EMBED[,ID=#]|NO}]
```

## <a name="remarks"></a>Açıklamalar

/ MANIFEST, bağlayıcının yan yana bildirim dosyası oluşturması gerektiğini belirtir. Bildirim dosyaları hakkında daha fazla bilgi için bkz: [bildirim dosyaları başvuru](/windows/desktop/SbsCs/manifest-files-reference).

/MANIFEST varsayılandır.

/MANIFEST: ekleme seçeneği, bağlayıcı bildirim dosyası görüntüde bir rt_manıfest türü kaynağı olarak gömülü belirtir. İsteğe bağlı `ID` parametredir bildirim için kullanılacak kaynak kimliği. Yürütülebilir dosya için 1 değerini kullanın. Özel bağımlılıklarını belirtmek etkinleştirmek için bir DLL için 2 değeri kullanın. Varsa `ID` parametresi belirtilmezse, varsayılan değer olan 2/dll seçenek ayarlanırsa; Aksi takdirde, varsayılan değer 1'dir.

Yürütülebilir dosyalar için bildirim dosyalarını, Visual Studio 2008'den itibaren kullanıcı hesabı denetimi (UAC) bilgisinin belirten bir bölümü içermelidir. /MANIFEST belirtir, ancak bunların hiçbiri belirtin [/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md) ya da [/dll](dll-build-a-dll.md), UAC düzeyinde ayarlanmış bir varsayılan UAC parça *asInvoker* bildirimine eklenir. UAC düzeyleri hakkında daha fazla bilgi için bkz. [/MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır)](manifestuac-embeds-uac-information-in-manifest.md).

UAC için varsayılan davranışı değiştirmek için aşağıdakilerden birini yapın:

- /MANIFESTUAC seçeneğini belirtin ve UAC düzeyi istenen değere ayarlayın.

- Veya bildiriminde UAC parçası oluşturmak istemiyorsanız: No seçeneğini belirtin.

/MANIFEST belirtmeyin ancak belirtin [/MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md) yorumları, bir bildirim dosyası oluşturulur. /MANIFEST:NO belirtirseniz bir bildirim dosyası oluşturulmaz.

/MANIFEST belirtirseniz, bildirim dosyasının adı, çıkış dosyasının, ancak dosya adına .manifest adı ile aynıdır. Örneğin, çıktı dosyanızın adı MyFile.exe ise, bildirim dosyası adı MyFile.exe.manifest ' dir.  /MANIFESTFILE belirtirseniz:*adı*, içinde belirttiğiniz addır bildirimin *adı*.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **bildirim dosyası** özellik sayfası.

1. Değiştirme **oluşturma bildirimi** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
