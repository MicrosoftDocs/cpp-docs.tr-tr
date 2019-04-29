---
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
ms.openlocfilehash: 3ed36eca727a15a3c70bc51a07cd3c143d7f66da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320142"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (Özel Simgeleri Çıkart)

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>Arguments

*pdb_file_name*<br/>
Bir kullanıcı tarafından belirtilen ad bağlayıcının oluşturduğu kesilmiş program veritabanı (PDB).

## <a name="remarks"></a>Açıklamalar

Bir PDB dosyası üretmek seçenekleri herhangi bir derleyici veya bağlayıcı ile program görüntüsünü oluşturduğunuzda/pdbstrıpped seçeneği, ikinci program veritabanı (PDB) dosyası oluşturur. ([/DEBUG](debug-generate-debug-info.md), [/z7](z7-zi-zi-debug-information-format.md), / ZD, veya /Zi). Bu ikinci PDB dosyası, size gönderilen müşterilerinize istemezsiniz sembolleri atar. İkinci PDB dosyası yalnızca içerir:

- Ortak semboller

- Nesne dosyaları ve yürütülebilir katkıda bulundukları kısımları listesi

- Yığın geçirmek için kullanılan çerçeve işaretçisi iyileştirme (FPO) hata ayıklama kayıtlarını

Kesilmiş bir PDB dosyası içermez:

- Tür bilgileri

- Satır numarası bilgisi

- İşlevleri, Yereller ve statik veriler için olanlar gibi her nesne için dosya CodeView semboller

/ Pdbstrıpped kullandığınızda tam PDB dosyası yine de oluşturulur.

Bir PDB dosyası oluşturmazsanız/pdbstrıpped göz ardı edilir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **hata ayıklama** özellik sayfası.

1. Değiştirme **özel sembolleri sök** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
