---
title: "Önemli hata C1052 | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1052
dev_langs: C++
helpviewer_keywords: C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a64caf82dcc99a26d7eb46d6e27465b0a8976edb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1052"></a>Önemli hata C1052  
  
> Program veritabanı dosyası, '*filename*', /DEBUG:fastlink ile; bağlayıcı tarafından üretildi derleyici tür PDB dosyaları güncelleştirilemiyor; Lütfen silin veya farklı bir PDB dosya adı belirtmek için /Fd kullanın  
  
Derleme bağlayıcı tarafından oluşturulan aynı program veritabanı (PDB) dosyaları güncelleştirilemiyor zaman [/DEBUG:fastlink](../../build/reference/debug-generate-debug-info.md) seçeneği belirtildi. Normalde derleyicinin ürettiği PDB dosyalarını ve bağlayıcı oluşturulan PDB dosyalarını farklı adlara sahip. Ancak, aynı adı kullanmak üzere ayarlanmışsa, bu hataya neden olabilir.  
  
Bu sorunu gidermek için açıkça PDB dosyalarını yeniden derleme veya derleyici tarafından üretilen ve bağlayıcı oluşturulan PDB dosyaları için farklı adlar oluşturabilmeniz için önce silebilirsiniz.  
  
Komut satırında derleyicinin ürettiği PDB dosya adı belirtmek için kullanın [/Fd](../../build/reference/fd-program-database-file-name.md) derleyici seçeneği. IDE içinde derleyicinin ürettiği PDB dosya adı belirtmek için açık **özellik sayfaları** iletişim ve projeniz için **yapılandırma özellikleri**, **C/C++**,  **Çıkış dosyaları** sayfasında **Program veritabanı dosya adı** özelliği. Bu özellik varsayılan olarak açık `$(IntDir)vc$(PlatformToolsetVersion).pdb`.  
  
Alternatif olarak, bağlayıcı oluşturulan PDB dosya adına ayarlayabilirsiniz. Komut satırında bağlayıcı oluşturulan PDB dosya adı belirtmek için kullanın [/pdb](../../build/reference/pdb-use-program-database.md) bağlayıcı seçeneği. IDE içinde bağlayıcı oluşturulan PDB dosya adı belirtmek için açık **özellik sayfaları** iletişim ve projeniz için **yapılandırma özellikleri**, **bağlayıcı**,  **Hata ayıklama** sayfasında **Program veritabanı dosya oluşturmak** özelliği. Varsayılan olarak, bu özelliği ayarlamak `$(OutDir)$(TargetName).pdb`.  
