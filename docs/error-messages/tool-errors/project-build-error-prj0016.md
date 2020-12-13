---
description: 'Hakkında daha fazla bilgi edinin: proje derleme hatası PRJ0016'
title: Proje Derleme Hatası PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: a34783e46bbe4c7b9979fe9b3d200cde4c228885
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343840"
---
# <a name="project-build-error-prj0016"></a>Proje Derleme Hatası PRJ0016

Kullanıcının güvenlik ayarları, işlemin oluşturulmasını engelliyor. Bu ayarlar, oluşturma için gereklidir.

İşlem kullanarak işlem oluşturma izni olmayan bir kullanıcı olarak oturum açtınız. Bu Kullanıcı hesabı için izin düzeylerini değiştirmeniz veya hesap yöneticinize başvurmanız gerekir.

Bu hata, aşağıdaki kayıt defteri anahtarı ayarlanmışsa de oluşabilir:

\\\Hkcu\software\microsoft\windows\currentversion\policies\explorer\kısıtlayıcı Trun

Bu hatayı çözmek için, Kısıttrun anahtarını silin. Bu kayıt defteri anahtarı gerekliyse, anahtardaki giriş listesine **vcspawn.exe** ekleyin.

Bu hatanın başka bir nedeni de Ilke ayarınız, bu kullanıcı hesabı için izin verilen bir pencere programı olarak HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun kayıt defteri anahtarı altında VCSpawn.exe içermez.

Daha fazla bilgi için, "yalnızca izin verilen Windows uygulamalarını çalıştır" bölümündeki [sistem Ilkesi ayarlarına bağlanma](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)bölümüne bakın.
