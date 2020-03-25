---
title: Proje Derleme Hatası PRJ0009
ms.date: 11/04/2016
f1_keywords:
- PRJ0009
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
ms.openlocfilehash: d02325504b04a13cd15dee0bd70891bf5a63b62e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192971"
---
# <a name="project-build-error-prj0009"></a>Proje Derleme Hatası PRJ0009

Derleme günlüğü yazma için açılamadı.

**Dosyanın başka bir işlem tarafından açık olmadığından ve yazma korumalı olmadığından emin olun.**

**Derleme günlüğü** özelliğini **Evet** olarak ayarlayıp derleme veya yeniden oluşturma işlemi gerçekleştirdikten sonra Visual C++ , Derleme günlüğünü özel modda açamadı.

**Seçenekler** iletişim kutusunu açıp ( **Araçlar** menüsünde, **Seçenekler** komutu ' na tıklayın) ve ardından **Projeler** klasöründe **VC + + Build** ' i seçerek **Yapı günlüğü** ayarını inceleyin. Yapı dosyası BuildLog. htm olarak adlandırılır ve ara dizinine $ (IntDir) yazılır.

Bu hatanın olası nedenleri:

- İki görsel C++ işlem çalıştırıyorsunuz ve aynı projede aynı yapılandırmayı aynı anda oluşturmaya çalışıyorsunuz.

- Derleme günlüğü dosyası dosyayı kilitleyen bir işlemde açılır.

- Kullanıcının dosya oluşturma izni yok.

- Geçerli kullanıcının BuildLog. htm dosyasına yazma erişimi yok.
