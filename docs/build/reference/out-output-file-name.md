---
title: -OUT (çıktı dosyası adı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
dev_langs:
- C++
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c4bfc79a257424820bed5f784cb0a83daf016d5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725406"
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

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)