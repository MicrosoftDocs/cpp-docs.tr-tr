---
title: Profil temelli iyileştirme hatası PG0165
description: Profil temelli iyileştirme (PGO) verilerini okuma PG0165 hatalarını açıklar.
ms.date: 10/30/2019
f1_keywords:
- PG0165
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
ms.openlocfilehash: c5e5c5d37f8c70a6c2a3d9f7a43c13bb46d0e25a
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626797"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Profil temelli iyileştirme hatası PG0165

Profil temelli iyileştirme verileri okunurken bir hata oluştu. Bu hata, çeşitli formlarda görünebilir:

> '*Filename. pgd*' okunuyor: ' PGD sürümü desteklenmiyor (sürüm uyuşmazlığı) '.

PGD dosyaları belirli bir derleyici araç takımı için özeldir. Bu hata, *dosya adı. pgd*oluşturmak için kullanılandan farklı bir derleyici kullandığınızda oluşturulur. Hata, bu derleyici araç takımının geçerli programı iyileştirmek için *filename. pgd* dosyasından verileri kullanamayacağını gösterir. Bu sorunu çözmek için, geçerli derleyici araç takımını kullanarak *filename*. pgd ' yi yeniden oluşturun.

> '*Filename. pgd*' okunuyor: ' pgd dosyası salt okunurdur '.

Bu hata, PGD dosyası dosya sisteminde salt okunurdur olarak işaretlendiğinde görüntülenir. Bu sorunu çözmek için dosya özniteliklerini okuma-yazma olarak değiştirin.
