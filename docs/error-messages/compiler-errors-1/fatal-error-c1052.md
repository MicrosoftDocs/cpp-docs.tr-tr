---
title: Önemli hata C1052
ms.date: 05/08/2017
f1_keywords:
- C1052
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
ms.openlocfilehash: b381cc3cfe27d4c4a9d744a6b854a0e43727fe71
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479774"
---
# <a name="fatal-error-c1052"></a>Önemli hata C1052

> Program veritabanı dosyası, '*filename*', / Debug: fastlink ile; bağlayıcı tarafından oluşturulan derleyici olamaz tür PDB dosyalarını güncelleştiremez; Lütfen silin veya /Fd farklı bir PDB dosya adı belirtmek için kullanın

Derleyici, bağlayıcı tarafından oluşturulan aynı program veritabanı (PDB) dosyalarını güncelleştirilemiyor, [/Debug: fastlink](../../build/reference/debug-generate-debug-info.md) seçeneği belirtildi. Normalde derleyici tarafından oluşturulan PDB dosyalarını ve bağlayıcı tarafından oluşturulan PDB dosyalarını farklı adlara sahip. Ancak, aynı adları kullanmanız ayarı geçerliyse, bu hatayı neden olabilir.

Bu sorunu gidermek için açıkça PDB dosyalarını yeniden derleme veya derleyici tarafından oluşturulan ve bağlayıcı tarafından oluşturulan PDB dosyaları için farklı adlar oluşturabilmeniz için önce silebilirsiniz.

Komut satırında derleyici tarafından oluşturulan PDB dosya adı belirtmek için kullanın [/Fd](../../build/reference/fd-program-database-file-name.md) derleyici seçeneği. IDE'de derleyici tarafından oluşturulan PDB dosya adı belirtmek için açık **özellik sayfaları** iletişim ve projeniz için **yapılandırma özellikleri**, **C/C++**,  **Çıkış dosyalarını** sayfasında **Program veritabanı dosya adı** özelliği. Varsayılan olarak, bu özellik, `$(IntDir)vc$(PlatformToolsetVersion).pdb`.

Alternatif olarak, bağlayıcı tarafından oluşturulan PDB dosya adı ayarlayabilirsiniz. Komut satırında bağlayıcı tarafından oluşturulan PDB dosya adı belirtmek için kullanın [/pdb](../../build/reference/pdb-use-program-database.md) bağlayıcı seçeneği. IDE içinde bağlayıcı tarafından oluşturulan PDB dosya adı belirtmek için açık **özellik sayfaları** iletişim ve projeniz için **yapılandırma özellikleri**, **bağlayıcı**,  **Hata ayıklama** sayfasında **Program veritabanı dosyası oluştur** özelliği. Varsayılan olarak, bu özellik kümesine `$(OutDir)$(TargetName).pdb`.
