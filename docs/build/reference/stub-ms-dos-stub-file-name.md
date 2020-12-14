---
description: Şu konuda daha fazla bilgi edinin:/STUB (MS-DOS saplama dosyası adı)
title: /STUB (MS-DOS Saplama Dosyası Adı)
ms.date: 11/04/2016
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
ms.openlocfilehash: 34f3cd71ce66cb6695a58707fd84de79f7a14b1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230308"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (MS-DOS Saplama Dosyası Adı)

```
/STUB:filename
```

## <a name="arguments"></a>Arguments

*filename*<br/>
Bir MS-DOS uygulaması.

## <a name="remarks"></a>Açıklamalar

/STUB seçeneği bir MS-DOS saplama programını Win32 programına iliştirir.

Dosya MS-DOS ' da yürütüldüğünde bir saplama programı çağırılır. Genellikle uygun bir ileti görüntüler; Ancak, geçerli bir MS-DOS uygulaması bir saplama programı olabilir.

İki nokta üst üste sonra saplama programı için bir *dosya adı* belirtin (:) komut satırında. Bağlayıcı dosya *adını* denetler ve dosya yürütülebilir değilse bir hata iletisi verir. Program bir. exe dosyası olmalıdır; bir. com dosyası bir saplama programı için geçersizdir.

Bu seçenek kullanılmazsa, bağlayıcı aşağıdaki iletiyi veren bir varsayılan saplama programı ekler:

```
This program cannot be run in MS-DOS mode.
```

Bir sanal cihaz sürücüsü oluştururken *Dosya* adı, kullanıcının IMAGE_DOS_HEADER yapısını içeren bir dosya adı belirtmesini sağlar (WINNT içinde tanımlanmıştır). H) varsayılan üst bilgi yerine VXD 'de kullanılacak.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. Seçeneği **ek seçenekler** kutusuna yazın.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
