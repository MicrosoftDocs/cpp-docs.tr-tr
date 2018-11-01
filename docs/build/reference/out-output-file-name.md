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
ms.openlocfilehash: f5ba323b830b9d06956d88d957206e3f73c15418
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497195"
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

Bu .mapfile veya içeri aktarma kitaplığı için varsayılan taban adı seçeneği. Ayrıntılar için bkz [eşlem dosyası oluştur](../../build/reference/map-generate-mapfile.md) (/ MAP) ve [/IMPLIB](../../build/reference/implib-name-import-library.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **genel** özellik sayfası.

1. Değiştirme **çıkış dosyası** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)