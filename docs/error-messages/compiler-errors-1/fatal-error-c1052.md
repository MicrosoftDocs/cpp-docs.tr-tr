---
title: "Önemli hata C1052 | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b9d7cc04fa863d30829c5484b328effc55125e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1052"></a>Önemli hata C1052  
  
> Program veritabanı dosyası, '*filename*', /DEBUG:fastlink ile; bağlayıcı tarafından üretildi derleyici tür PDB dosyaları güncelleştirilemiyor; Lütfen silin veya farklı bir PDB dosya adı belirtmek için /Fd kullanın  
  
Derleme bağlayıcı tarafından oluşturulan aynı program veritabanı (PDB) dosyaları güncelleştirilemiyor zaman [/DEBUG:fastlink](../../build/reference/debug-generate-debug-info.md) seçeneği belirtildi. Normalde derleyicinin ürettiği PDB dosyalarını ve bağlayıcı oluşturulan PDB dosyalarını farklı adlara sahip. Ancak, aynı adı kullanmak üzere ayarlanmışsa, bu hataya neden olabilir.  
  
Bu sorunu gidermek için açıkça PDB dosyalarını yeniden derleme veya derleyici tarafından üretilen ve bağlayıcı oluşturulan PDB dosyaları için farklı adlar oluşturabilmeniz için önce silebilirsiniz.  
  
Komut satırında derleyicinin ürettiği PDB dosya adı belirtmek için kullanın [/Fd](../../build/reference/fd-program-database-file-name.md) derleyici seçeneği. IDE içinde derleyicinin ürettiği PDB dosya adı belirtmek için açık **özellik sayfaları** iletişim ve projeniz için **yapılandırma özellikleri**, **C/C++**,  **Çıkış dosyaları** sayfasında **Program veritabanı dosya adı** özelliği. Bu özellik varsayılan olarak açık `$(IntDir)vc$(PlatformToolsetVersion).pdb`.  
  
Alternatif olarak, bağlayıcı oluşturulan PDB dosya adına ayarlayabilirsiniz. Komut satırında bağlayıcı oluşturulan PDB dosya adı belirtmek için kullanın [/pdb](../../build/reference/pdb-use-program-database.md) bağlayıcı seçeneği. IDE içinde bağlayıcı oluşturulan PDB dosya adı belirtmek için açık **özellik sayfaları** iletişim ve projeniz için **yapılandırma özellikleri**, **bağlayıcı**,  **Hata ayıklama** sayfasında **Program veritabanı dosya oluşturmak** özelliği. Varsayılan olarak, bu özelliği ayarlamak `$(OutDir)$(TargetName).pdb`.  
