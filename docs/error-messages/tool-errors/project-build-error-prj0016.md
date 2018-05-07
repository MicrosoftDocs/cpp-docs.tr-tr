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
ms.openlocfilehash: 6184e5bb251a2b74e8500cc195a38f2d814c1b5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0016"></a>Proje Derleme Hatası PRJ0016
Kullanıcının güvenlik ayarları işlemi oluşturulmasını engeller. Bu ayarlar, yapı için gereklidir.  
  
 Bir işlemi kullanarak işlemleri oluşturmak için izinlere sahip olmayan bir kullanıcı olarak kaydedilir. Bu kullanıcı hesabı için izin düzeylerini değiştirme veya hesap yöneticinize başvurun.  
  
 Bu hata ayrıca aşağıdaki kayıt defteri anahtarını ayarlayın oluşabilir:  
  
 \\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun  
  
 Bu hatayı gidermek için RestrictRun anahtarını silin. Bu kayıt defteri anahtarı gerekiyorsa, append **vcspawn.exe** anahtar girişlerinde listesi.  
  
 Bu hata başka bir nedeni, ilke ayarını VCSpawn.exe altındaki kayıt defteri anahtarının HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun bu kullanıcı hesabı için izin verilen bir pencere program içermediğine olmasıdır.  
  
 Ek bilgi için bkz:  
  
-   Kullanılabilen 324153, Bilgi Bankası makalesi [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Sistem İlkesi ayarları uymak](http://msdn.microsoft.com/library/aa372139), "Yalnızca izin verilen Windows uygulamalarını çalıştır" üzerindeki bölümü.