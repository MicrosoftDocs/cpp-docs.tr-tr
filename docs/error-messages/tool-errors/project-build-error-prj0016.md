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
ms.openlocfilehash: ceb004cba243d6e2e9c44aadcaa40670ef7a0bbb
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890263"
---
# <a name="project-build-error-prj0016"></a>Proje Derleme Hatası PRJ0016

Kullanıcının güvenlik ayarları, işlemin oluşturulmasını önleyin. Bu ayarlar, derleme için gereklidir.

Bir işlem kullanarak işlemleri oluşturma izinlerine sahip olmayan bir kullanıcı olarak oturum açtınız. Bu kullanıcı hesabı için izin düzeylerini değiştirin veya hesap yöneticinize başvurun.

Aşağıdaki kayıt defteri anahtarını ayarlanmışsa bu hatayı da meydana gelebilir:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Bu hatayı gidermek için RestrictRun anahtarı silin. Bu kayıt defteri anahtarı gerekli olursa, ekleme **vcspawn.exe** anahtar girişlerinde listesi.

Bu hata başka bir nedeni, ilke ayarını VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun kayıt defteri anahtarı altında bu kullanıcı hesabı için izin verilen bir pencere program içermediğinden ' dir.

Ek bilgi için bkz: [uymak için Sistem İlkesi ayarları](https://msdn.microsoft.com/library/aa372139), içindeki "Yalnızca izin verilen Windows uygulamaları Çalıştır" bölümü.