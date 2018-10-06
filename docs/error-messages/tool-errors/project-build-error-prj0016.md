---
title: Proje derleme hatası PRJ0016 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0016
dev_langs:
- C++
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01610f888d8afe275b0e52b86e4f4c678f896c9f
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820483"
---
# <a name="project-build-error-prj0016"></a>Proje Derleme Hatası PRJ0016

Kullanıcının güvenlik ayarları, işlemin oluşturulmasını önleyin. Bu ayarlar, derleme için gereklidir.

Bir işlem kullanarak işlemleri oluşturma izinlerine sahip olmayan bir kullanıcı olarak oturum açtınız. Bu kullanıcı hesabı için izin düzeylerini değiştirin veya hesap yöneticinize başvurun.

Aşağıdaki kayıt defteri anahtarını ayarlanmışsa bu hatayı da meydana gelebilir:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Bu hatayı gidermek için RestrictRun anahtarı silin. Bu kayıt defteri anahtarı gerekli olursa, ekleme **vcspawn.exe** anahtar girişlerinde listesi.

Bu hata başka bir nedeni, ilke ayarını VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun kayıt defteri anahtarı altında bu kullanıcı hesabı için izin verilen bir pencere program içermediğinden ' dir.

Ek bilgi için bkz:

- Kullanılabilir olan 324153, Bilgi Bankası makalesi [ http://support.microsoft.com/default.aspx?scid=kb; 324153](http://support.microsoft.com/default.aspx?scid=kb;324153).

- [Sistem İlkesi ayarları için bağlılığı](https://msdn.microsoft.com/library/aa372139), "Yalnızca izin verilen Windows uygulamaları Çalıştır" bölümü.