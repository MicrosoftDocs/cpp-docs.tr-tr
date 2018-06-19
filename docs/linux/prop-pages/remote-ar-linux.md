---
title: Uzak arşivi özellikler (C++ Linux) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
author: mikeblome
ms.author: mblome
f1_keywords: []
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 004e015b7e5ad8a99b3bea2bf21b7b598f2fedbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328659"
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
