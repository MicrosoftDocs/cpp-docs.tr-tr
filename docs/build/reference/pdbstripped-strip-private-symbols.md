---
title: -PDBSTRIPPED (özel simgeleri) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
dev_langs:
- C++
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0680f265214849c2e46c4ceb23dcb71bdff61c3f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710846"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (Özel Simgeleri Çıkart)

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>Arguments

*pdb_file_name*<br/>
Bir kullanıcı tarafından belirtilen ad bağlayıcının oluşturduğu kesilmiş program veritabanı (PDB).

## <a name="remarks"></a>Açıklamalar

Bir PDB dosyası üretmek seçenekleri herhangi bir derleyici veya bağlayıcı ile program görüntüsünü oluşturduğunuzda/pdbstrıpped seçeneği, ikinci program veritabanı (PDB) dosyası oluşturur. ([/DEBUG](../../build/reference/debug-generate-debug-info.md), [/z7](../../build/reference/z7-zi-zi-debug-information-format.md), / ZD, veya /Zi). Bu ikinci PDB dosyası, size gönderilen müşterilerinize istemezsiniz sembolleri atar. İkinci PDB dosyası yalnızca içerir:

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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **hata ayıklama** özellik sayfası.

1. Değiştirme **özel sembolleri sök** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)