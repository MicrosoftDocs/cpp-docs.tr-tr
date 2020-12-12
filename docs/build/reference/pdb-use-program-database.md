---
description: Daha fazla bilgi edinin:/PDB (program veritabanını kullan)
title: /PDB (Program Veritabanını Kullan)
ms.date: 11/04/2016
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
ms.openlocfilehash: 221d5d81dc3578e99751334b2e0a0a61aaaed356
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226109"
---
# <a name="pdb-use-program-database"></a>/PDB (Program Veritabanını Kullan)

```
/PDB:filename
```

## <a name="arguments"></a>Arguments

*filename*<br/>
Bağlayıcının oluşturduğu program veritabanı (PDB) için Kullanıcı tarafından belirtilen bir ad. Varsayılan adı değiştirir.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [/Debug](debug-generate-debug-info.md) belirtildiğinde, bağlayıcı hata ayıklama bilgilerini tutan bir program VERITABANı (pdb) oluşturur. PDB için varsayılan dosya adı programın temel adına ve. pdb uzantısına sahiptir.

PDB dosyasının adını belirtmek için/PDB:*filename* komutunu kullanın. /DEBUG belirtilmemişse,/PDB seçeneği yok sayılır.

PDB dosyası en fazla 2 GB olabilir.

Daha fazla bilgi için [bağlayıcı girişi olarak. pdb dosyaları](dot-pdb-files-as-linker-input.md)bölümüne bakın.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Hata ayıklama** Özellik sayfasına tıklayın.

1. **Program veritabanı dosyası oluştur** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
