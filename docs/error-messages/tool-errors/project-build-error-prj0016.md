---
title: Proje Derleme Hatası PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: ada89b074fd8e0c2bfc75ba833e9c5966a145312
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359429"
---
# <a name="project-build-error-prj0016"></a>Proje Derleme Hatası PRJ0016

Kullanıcının güvenlik ayarları, işlemin oluşturulmasını önleyin. Bu ayarlar, derleme için gereklidir.

Bir işlem kullanarak işlemleri oluşturma izinlerine sahip olmayan bir kullanıcı olarak oturum açtınız. Bu kullanıcı hesabı için izin düzeylerini değiştirin veya hesap yöneticinize başvurun.

Aşağıdaki kayıt defteri anahtarını ayarlanmışsa bu hatayı da meydana gelebilir:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Bu hatayı gidermek için RestrictRun anahtarı silin. Bu kayıt defteri anahtarı gerekli olursa, ekleme **vcspawn.exe** anahtar girişlerinde listesi.

Bu hata başka bir nedeni, ilke ayarını VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun kayıt defteri anahtarı altında bu kullanıcı hesabı için izin verilen bir pencere program içermediğinden ' dir.

Ek bilgi için bkz: [uymak için Sistem İlkesi ayarları](https://msdn.microsoft.com/library/aa372139), içindeki "Yalnızca izin verilen Windows uygulamaları Çalıştır" bölümü.