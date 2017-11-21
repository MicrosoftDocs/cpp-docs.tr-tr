---
title: "Uzak arşivi özellikler (C++ Linux) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.Ar.CreateIndex
- VC.Project.Ar.CreateThinArchive
- VC.Project.Ar.NoWarnOnCreate
- VC.Project.Ar.TruncateTimestamp
- VC.Project.Ar.SuppressStartupBanner
- VC.Project.Ar.Verbose
- vc.project.AdditionalOptionsPage
- VC.Project.Ar.OutputFile
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 402fa1f752b311014c828027e45a92a3dc6a2917
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="remote-archive-properties-c-linux"></a>Uzak arşivi özellikler (C++ Linux)

Özellik | Açıklama
--- | ---
Bir arşiv dizini oluşturma | Bir arşiv dizini (cf. ranlib) oluşturun.  Bu bağlantı hızı ve kendi kitaplığında bağımlılık azaltın.
İnce arşiv oluşturma | Basit bir arşiv oluşturun.  Basit bir arşiv nesneleri yerine nesnelere relativepaths içerir.  İnce ve Normal arasında geçiş yapma, varolan kitaplık silinmesi gerektirir.
Herhangi bir uyarı oluştur | Kitaplık oluşturulduğunda, uyarma.
Truncate zaman damgası | Zaman damgaları ve uıd'leri/GID için sıfır değerini kullanın.
Başlangıç başlığını gösterme | Engelle sürüm numarasını gösterir.
Ayrıntılı | Ayrıntılı
Ek Seçenekler | Ek Seçenekler.
Çıkış dosyası | Varsayılan ad ve konum lib oluşturur programın /OUT seçeneğini geçersiz kılar.
Archiver | Statik nesneleri veya uzak sistem üzerindeki archiver yoluna bağlama sırasında çağırmak için program belirtir.
Archiver zaman aşımı | Uzak archiver, milisaniye cinsinden zaman aşımı.
Kopya çıktı | Derleme çıktı dosyası Uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir.
