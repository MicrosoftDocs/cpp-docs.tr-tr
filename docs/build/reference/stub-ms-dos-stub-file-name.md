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
ms.openlocfilehash: 7150d4ff8f35b00d96caa21fd5ea3754fec76030
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317880"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
