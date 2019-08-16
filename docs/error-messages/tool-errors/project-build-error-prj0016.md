---
title: Proje Derleme Hatası PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: 6733ef1f390f2ff377356dda3f7cd3ebfe10cc2b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509875"
---
# <a name="project-build-error-prj0016"></a>Proje Derleme Hatası PRJ0016

Kullanıcının güvenlik ayarları, işlemin oluşturulmasını engelliyor. Bu ayarlar, oluşturma için gereklidir.

İşlem kullanarak işlem oluşturma izni olmayan bir kullanıcı olarak oturum açtınız. Bu Kullanıcı hesabı için izin düzeylerini değiştirmeniz veya hesap yöneticinize başvurmanız gerekir.

Bu hata, aşağıdaki kayıt defteri anahtarı ayarlanmışsa de oluşabilir:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Bu hatayı çözmek için, Kısıttrun anahtarını silin. Bu kayıt defteri anahtarı gerekliyse, anahtar içindeki giriş listesine **vcspiyonu. exe** ' yi ekleyin.

Bu hatanın başka bir nedeni de Ilke ayarınız, bu kullanıcı hesabı için izin verilen bir pencere programı olarak HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun kayıt defteri anahtarı altında Vcspiyonu. exe ' yi içermez.

Daha fazla bilgi için, "yalnızca izin verilen Windows uygulamalarını çalıştır" bölümündeki [sistem Ilkesi ayarlarına bağlanma](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)bölümüne bakın.