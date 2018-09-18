---
title: Proje derleme hatası PRJ0009 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0009
dev_langs:
- C++
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efeb110823e801dd86a503a7069c4898f400769e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057190"
---
# <a name="project-build-error-prj0009"></a>Proje Derleme Hatası PRJ0009

Derleme günlük yazma için açılamadı.

**Dosya başka bir işlem tarafından açık olmadığından ve yazma korumalı olmadığından emin olun.**

Ayarlanmasından sonra **derleme günlüğü** özelliğini **Evet** ve derleme veya yeniden gerçekleştiriyorsa, Visual C++ derleme günlüğüne özel modda açamadı.

İnceleme **derleme günlüğü** açarak ayarlama **seçenekleri** iletişim kutusu (üzerinde **Araçları** menüsünde tıklayın **seçenekleri** komut) ve ardından seçme **VC ++ derleme** içinde **projeleri** klasör. Derleme dosyası BuildLog.htm adı verilir ve Ara dizin $(IntDir) yazılır.

Bu hata için olası nedenler:

- Visual C++'ın iki işlem çalıştırdığınız ve aynı anda hem de aynı projede aynı yapılandırmasını derlenmeye çalışılıyor.

- Derleme günlüğü dosyası dosya kilitleri bir işlem olarak açılır.

- Kullanıcı bir dosyayı oluşturma izni yok.

- Geçerli kullanıcının dosyaya BuildLog.htm yazma erişimi yok.