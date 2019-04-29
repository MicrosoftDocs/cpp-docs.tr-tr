---
title: Proje Derleme Hatası PRJ0009
ms.date: 11/04/2016
f1_keywords:
- PRJ0009
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
ms.openlocfilehash: 963b7c861f9e8ee7105ebdc23afff08c4be46465
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359507"
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