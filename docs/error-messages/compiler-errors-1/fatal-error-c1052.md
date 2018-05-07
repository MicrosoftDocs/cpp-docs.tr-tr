---
title: Önemli hata C1052 | Microsoft Docs
ms.custom: ''
ms.date: 05/08/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8d272b71a527763245ccf7c8d69bd11a915eab7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1052"></a>Önemli hata C1052

> Program veritabanı dosyası, '*filename*', /DEBUG:fastlink ile; bağlayıcı tarafından üretildi derleyici tür PDB dosyaları güncelleştirilemiyor; Lütfen silin veya farklı bir PDB dosya adı belirtmek için /Fd kullanın

Derleme bağlayıcı tarafından oluşturulan aynı program veritabanı (PDB) dosyaları güncelleştirilemiyor zaman [/DEBUG:fastlink](../../build/reference/debug-generate-debug-info.md) seçeneği belirtildi. Normalde derleyicinin ürettiği PDB dosyalarını ve bağlayıcı oluşturulan PDB dosyalarını farklı adlara sahip. Ancak, aynı adı kullanmak üzere ayarlanmışsa, bu hataya neden olabilir.

Bu sorunu gidermek için açıkça PDB dosyalarını yeniden derleme veya derleyici tarafından üretilen ve bağlayıcı oluşturulan PDB dosyaları için farklı adlar oluşturabilmeniz için önce silebilirsiniz.

Komut satırında derleyicinin ürettiği PDB dosya adı belirtmek için kullanın [/Fd](../../build/reference/fd-program-database-file-name.md) derleyici seçeneği. IDE içinde derleyicinin ürettiği PDB dosya adı belirtmek için açık **özellik sayfaları** iletişim ve projeniz için **yapılandırma özellikleri**, **C/C++**,  **Çıkış dosyaları** sayfasında **Program veritabanı dosya adı** özelliği. Bu özellik varsayılan olarak açık `$(IntDir)vc$(PlatformToolsetVersion).pdb`.

Alternatif olarak, bağlayıcı oluşturulan PDB dosya adına ayarlayabilirsiniz. Komut satırında bağlayıcı oluşturulan PDB dosya adı belirtmek için kullanın [/pdb](../../build/reference/pdb-use-program-database.md) bağlayıcı seçeneği. IDE içinde bağlayıcı oluşturulan PDB dosya adı belirtmek için açık **özellik sayfaları** iletişim ve projeniz için **yapılandırma özellikleri**, **bağlayıcı**,  **Hata ayıklama** sayfasında **Program veritabanı dosya oluşturmak** özelliği. Varsayılan olarak, bu özelliği ayarlamak `$(OutDir)$(TargetName).pdb`.
