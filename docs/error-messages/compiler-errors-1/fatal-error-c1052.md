---
description: 'Daha fazla bilgi edinin: önemli hata C1052'
title: Önemli hata C1052
ms.date: 05/08/2017
f1_keywords:
- C1052
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
ms.openlocfilehash: 818210cc4c3658167de30b9e666c600695389330
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251745"
---
# <a name="fatal-error-c1052"></a>Önemli hata C1052

> '*filename*' program veritabanı dosyası bağlayıcı tarafından/Debug: fastlink ile oluşturuldu; derleyici bu tür PDB dosyalarını güncelleştiremez; Lütfen bu dosyayı silin veya/fd kullanarak farklı bir PDB dosya adı belirtin

Derleyici [/Debug: fastlink](../../build/reference/debug-generate-debug-info.md) seçeneği belirtildiğinde bağlayıcı tarafından oluşturulan aynı program VERITABANı (pdb) dosyalarını güncelleştiremez. Normalde derleyicinin ürettiği PDB dosyaları ve bağlayıcı tarafından oluşturulan PDB dosyaları farklı adlara sahiptir. Ancak, aynı adları kullanacak şekilde ayarlandıysa, bu hata oluşabilir.

Bu sorunu onarmak için, yeniden derlemeden önce PDB dosyalarını açıkça silebilir veya derleyicinin ürettiği ve bağlayıcı tarafından oluşturulan PDB dosyaları için farklı adlar oluşturabilirsiniz.

Derleyici tarafından oluşturulan PDB dosya adını komut satırında belirtmek için [/FD](../../build/reference/fd-program-database-file-name.md) derleyici seçeneğini kullanın. IDE 'de derleyici tarafından oluşturulan pdb dosya adını belirtmek için, projeniz için **Özellik sayfaları** iletişim kutusunu açın ve **yapılandırma özellikleri**, **C/C++**, **çıkış dosyaları** sayfasında, **Program veritabanı dosya adı** özelliğini ayarlayın. Varsayılan olarak, bu özellik `$(IntDir)vc$(PlatformToolsetVersion).pdb` .

Alternatif olarak, bağlayıcı tarafından oluşturulan PDB dosya adını da ayarlayabilirsiniz. Komut satırında bağlayıcı tarafından oluşturulan PDB dosya adını belirtmek için [/pdb](../../build/reference/pdb-use-program-database.md) bağlayıcı seçeneğini kullanın. IDE 'de bağlayıcı tarafından oluşturulan PDB dosya adını belirtmek için, projeniz için **Özellik sayfaları** iletişim kutusunu açın ve **yapılandırma özellikleri**, **bağlayıcı**, **hata ayıklama** sayfasında **Program veritabanı dosyası oluştur** özelliğini ayarlayın. Varsayılan olarak, bu özellik olarak ayarlanır `$(OutDir)$(TargetName).pdb` .
