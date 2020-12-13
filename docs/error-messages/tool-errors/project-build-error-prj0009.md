---
description: 'Hakkında daha fazla bilgi edinin: proje derleme hatası PRJ0009'
title: Proje Derleme Hatası PRJ0009
ms.date: 11/04/2016
f1_keywords:
- PRJ0009
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
ms.openlocfilehash: 28a7a9ce1a4fa5f1b5b95ba208739b7172f0ac6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343892"
---
# <a name="project-build-error-prj0009"></a>Proje Derleme Hatası PRJ0009

Derleme günlüğü yazma için açılamadı.

**Dosyanın başka bir işlem tarafından açık olmadığından ve yazma korumalı olmadığından emin olun.**

**Derleme günlüğü** özelliğini **Evet** olarak ayarlayıp bir derlemeyi veya yeniden derlemeyi gerçekleştirdikten sonra, Visual C++ Derleme günlüğünü özel modda açamadı.

**Seçenekler** iletişim kutusunu açıp ( **Araçlar** menüsünde, **Seçenekler** komutu ' na tıklayın) ve ardından **Projeler** klasöründe **VC + + Build** ' i seçerek **Yapı günlüğü** ayarını inceleyin. Yapı dosyası BuildLog.htm olarak adlandırılır ve ara dizine $ (IntDir) yazılır.

Bu hatanın olası nedenleri:

- Visual C++ iki işlem çalıştırıyorsunuz ve aynı projede aynı yapılandırmayı aynı anda oluşturmaya çalışıyorsunuz.

- Derleme günlüğü dosyası dosyayı kilitleyen bir işlemde açılır.

- Kullanıcının dosya oluşturma izni yok.

- Geçerli kullanıcının dosya BuildLog.htm yazma erişimi yok.
