---
title: Proje Derleme Hatası PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: 0cab1e35a36ab78426923d60acafb5cdf2942469
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192750"
---
# <a name="project-build-error-prj0016"></a>Proje Derleme Hatası PRJ0016

Kullanıcının güvenlik ayarları, işlemin oluşturulmasını engelliyor. Bu ayarlar, oluşturma için gereklidir.

İşlem kullanarak işlem oluşturma izni olmayan bir kullanıcı olarak oturum açtınız. Bu Kullanıcı hesabı için izin düzeylerini değiştirmeniz veya hesap yöneticinize başvurmanız gerekir.

Bu hata, aşağıdaki kayıt defteri anahtarı ayarlanmışsa de oluşabilir:

\\\Hkcu\software\microsoft\windows\currentversion\policies\explorer\kısıttrun

Bu hatayı çözmek için, Kısıttrun anahtarını silin. Bu kayıt defteri anahtarı gerekliyse, anahtar içindeki giriş listesine **vcspiyonu. exe** ' yi ekleyin.

Bu hatanın başka bir nedeni, Ilke ayarınız, bu kullanıcı hesabı için izin verilen bir pencere programı olarak HKEY_CURRENT_USER \Software\microsoft\windows\currentversion\policies\kısıtlayıcı Trun kayıt defteri anahtarı altında Vcspiyonu. exe ' yi içermez.

Daha fazla bilgi için, "yalnızca izin verilen Windows uygulamalarını çalıştır" bölümündeki [sistem Ilkesi ayarlarına bağlanma](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)bölümüne bakın.
