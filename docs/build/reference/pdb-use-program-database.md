---
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
ms.openlocfilehash: ddcf83cafd5f499158f3116f04e40397b7f8d0a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320090"
---
# <a name="pdb-use-program-database"></a>/PDB (Program Veritabanını Kullan)

```
/PDB:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Bir kullanıcı tarafından belirtilen ad bağlayıcının oluşturduğu program veritabanı (PDB). Varsayılan adını değiştirir.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, zaman [/DEBUG](debug-generate-debug-info.md) belirtildiğinde, bağlayıcı, hata ayıklama bilgilerini tutan bir program veritabanı (PDB) oluşturur. Varsayılan dosya adı PDB için temel programının adını ve .pdb uzantısına sahiptir.

/ Pdb kullanın:*filename* PDB dosyasının adını belirtmek için. / Pdb seçeneği/Debug belirtilmezse, yoksayılır.

Bir PDB dosyası 2 GB'a kadar olabilir.

Daha fazla bilgi için [bağlayıcı girişi olarak .pdb dosyaları](dot-pdb-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **hata ayıklama** özellik sayfası.

1. Değiştirme **Program veritabanı dosyası oluştur** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
