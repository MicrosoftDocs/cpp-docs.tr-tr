---
title: -PDB (Program veritabanını kullan) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
dev_langs:
- C++
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8717be9ee8f754f4e61dbed0211360a0b4f4f780
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717251"
---
# <a name="pdb-use-program-database"></a>/PDB (Program Veritabanını Kullan)

```
/PDB:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Bir kullanıcı tarafından belirtilen ad bağlayıcının oluşturduğu program veritabanı (PDB). Varsayılan adını değiştirir.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, zaman [/DEBUG](../../build/reference/debug-generate-debug-info.md) belirtildiğinde, bağlayıcı, hata ayıklama bilgilerini tutan bir program veritabanı (PDB) oluşturur. Varsayılan dosya adı PDB için temel programının adını ve .pdb uzantısına sahiptir.

/ Pdb kullanın:*filename* PDB dosyasının adını belirtmek için. / Pdb seçeneği/Debug belirtilmezse, yoksayılır.

Bir PDB dosyası 2 GB'a kadar olabilir.

Daha fazla bilgi için [bağlayıcı girişi olarak .pdb dosyaları](../../build/reference/dot-pdb-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **hata ayıklama** özellik sayfası.

1. Değiştirme **Program veritabanı dosyası oluştur** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)