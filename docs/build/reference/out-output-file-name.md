---
title: /OUT (Çıktı Dosyası Adı)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
ms.openlocfilehash: be5fe929bdcf52be19955a5bc2d7aa093e194f45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320077"
---
# <a name="out-output-file-name"></a>/OUT (Çıktı Dosyası Adı)

```
/OUT:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Bir kullanıcı tarafından belirtilen çıkış dosyasının adı. Varsayılan adını değiştirir.

## <a name="remarks"></a>Açıklamalar

/ Out seçeneği varsayılan adını ve bağlayıcının oluşturduğu program konumunu geçersiz kılar.

Varsayılan olarak, bağlayıcı ilk .obj dosyası belirtilmedi ve uygun bir uzantı (.exe veya .dll) temel adını kullanarak dosya adı oluşturur.

Bu .mapfile veya içeri aktarma kitaplığı için varsayılan taban adı seçeneği. Ayrıntılar için bkz [eşlem dosyası oluştur](map-generate-mapfile.md) (/ MAP) ve [/IMPLIB](implib-name-import-library.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **genel** özellik sayfası.

1. Değiştirme **çıkış dosyası** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
