---
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
ms.openlocfilehash: 289812ce8c6167a82204946c0a362ccad6896a39
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642643"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (MS-DOS Saplama Dosyası Adı)

```
/STUB:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
MS-DOS uygulama.

## <a name="remarks"></a>Açıklamalar

/ Stub seçeneği, MS-DOS saplama programını Win32 programına iliştirir.

Dosya MS-DOS yürütülürse saplama programını çağrılır. Genellikle, uygun bir mesaj görüntüler; Ancak, geçerli bir MS-DOS uygulama saplama programını olabilir.

Belirtin bir *filename* saplama programı sonra komut satırında iki nokta (:). Bağlayıcı denetimleri *filename* ve dosyayı yürütülebilir bir dosya değil, bir hata iletisi verir. Program bir .exe dosyası olmalıdır; için bir saplama programını .com dosyası geçersiz.

Bu seçenek kullanılırsa, bağlayıcı aşağıdaki ileti işler varsayılan bir saplama programı ekler:

```
This program cannot be run in MS-DOS mode.
```

Bir sanal cihaz sürücüsü oluştururken *filename* (WINNT içinde tanımlanan. bir IMAGE_DOS_HEADER yapı içeren bir dosya adı belirtin izin verir H) varsayılan üstbilgi yerine VXD kullanılacak.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)