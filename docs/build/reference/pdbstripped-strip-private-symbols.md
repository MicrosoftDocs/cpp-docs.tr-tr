---
description: Daha fazla bilgi edinin:/PDBÇıKARıLDı (özel sembolleri çıkar)
title: /PDBSTRIPPED (Özel Simgeleri Çıkart)
ms.date: 11/04/2016
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
ms.openlocfilehash: 27e70281ad12f4401ad6557ead9be11a38684472
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226044"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (Özel Simgeleri Çıkart)

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>Arguments

*pdb_file_name*<br/>
Bağlayıcı tarafından oluşturulan, kesilmiş program veritabanı (PDB) için Kullanıcı tarafından belirtilen bir ad.

## <a name="remarks"></a>Açıklamalar

/PDBÇıKARıLDı seçeneği, bir PDB dosyası ([/Debug](debug-generate-debug-info.md), [/Z7](z7-zi-zi-debug-information-format.md),/ZD veya/Zi) oluşturan derleyici veya bağlayıcı seçeneklerinden herhangi biriyle program görüntünüzü oluştururken ıkıncı program veritabanı (pdb) dosyası oluşturur. Bu ikinci PDB dosyası, müşterilerinize göndermek istemediğiniz sembolleri atlar. İkinci PDB dosyası yalnızca şunları içerir:

- Ortak semboller

- Nesne dosyalarının listesi ve katkıda bulundukları yürütülebilirin bölümleri

- Yığında geçiş yapmak için kullanılan çerçeve işaretçisi iyileştirmesi (!) hata ayıklama kayıtları

Atılmış PDB dosyası şunları içermez:

- Tür bilgileri

- Satır numarası bilgileri

- İşlevler, Yereller ve statik veriler gibi nesne başına dosya Kodugörünümü sembolleri

Tam PDB dosyası,/pdbçabappedkullandığınızda yine de oluşturulacaktır.

PDB dosyası oluşturmaması durumunda/PDBÇıKARıLDı yok sayılır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Hata ayıklama** Özellik sayfasına tıklayın.

1. **Strip özel sembolleri** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
