---
title: Proje Derleme Hatası PRJ0008
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 696b77e9906b231a680027a3faaf23e53d8fb6e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525912"
---
# <a name="project-build-error-prj0008"></a>Proje Derleme Hatası PRJ0008

'Dosya' dosyası silinemedi.

**Dosya başka bir işlem tarafından açık olmadığından ve yazma korumalı olmadığından emin olun.**

Bir yeniden oluşturma sırasında veya temizleyen, Visual C++ derleme için tüm bilinen Ara ve Çıkış dosyalarını yanı sıra, joker karakter belirtimleri karşılayan tüm dosyaları siler. **uzantıları temizlemede** özelliğinde [genel Yapılandırma ayarları özellik sayfası](../../ide/general-property-page-project.md).

Visual C++ bir dosyayı silmek mümkün değilse bu hata iletisiyle karşılaşırsınız. Hatayı gidermek için dosya ve alt dizin yazılabilir derleme yapan kullanıcı için olun.