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
ms.openlocfilehash: 8c07de9e766b7c2126d0ce4c8d1daed631a8355c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194746"
---
# <a name="project-build-error-prj0016"></a>Proje Derleme Hatası PRJ0016
Kullanıcının güvenlik ayarları, işlemin oluşturulmasını önleyin. Bu ayarlar, derleme için gereklidir.  
  
 Bir işlem kullanarak işlemleri oluşturma izinlerine sahip olmayan bir kullanıcı olarak oturum açtınız. Bu kullanıcı hesabı için izin düzeylerini değiştirin veya hesap yöneticinize başvurun.  
  
 Aşağıdaki kayıt defteri anahtarını ayarlanmışsa bu hatayı da meydana gelebilir:  
  
 \\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun  
  
 Bu hatayı gidermek için RestrictRun anahtarı silin. Bu kayıt defteri anahtarı gerekli olursa, ekleme **vcspawn.exe** anahtar girişlerinde listesi.  
  
 Bu hata başka bir nedeni, ilke ayarını VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun kayıt defteri anahtarı altında bu kullanıcı hesabı için izin verilen bir pencere program içermediğinden ' dir.  
  
 Ek bilgi için bkz:  
  
-   Kullanılabilir olan 324153, Bilgi Bankası makalesi [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Sistem İlkesi ayarları için bağlılığı](https://msdn.microsoft.com/library/aa372139), "Yalnızca izin verilen Windows uygulamaları Çalıştır" bölümü.