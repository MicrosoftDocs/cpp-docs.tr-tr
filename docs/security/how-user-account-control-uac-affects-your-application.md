---
title: Kullanıcı Hesabı Denetimi (UAC) Uygulamanızı Nasıl Etkiler
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 8c283e86a71092bb510892b6361f3d0fddc2abb6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510148"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Kullanıcı Hesabı Denetimi (UAC) Uygulamanızı Nasıl Etkiler

Kullanıcı hesabı denetimi (UAC), Kullanıcı hesaplarının sınırlı ayrıcalıklara sahip olduğu bir Windows Vista özelliğidir. Bu sitelerde UAC hakkında ayrıntılı bilgi bulabilirsiniz:

- [En az ayrıcalıklı bir ortamdaki uygulamalar için En Iyi geliştirici uygulamaları ve yönergeleri](/windows/win32/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>UAC etkinleştirildikten sonra projeler oluşturma

Windows Vista 'da UAC 'yi devre C++ dışı bırakılmış bir Visual Studio projesi derleyebilir ve daha sonra UAC 'yi etkinleştirirseniz, projenin doğru çalışması için projeyi temizlemeniz ve yeniden oluşturmanız gerekir.

## <a name="applications-that-require-administrative-privileges"></a>Yönetici ayrıcalıkları gerektiren uygulamalar

Varsayılan olarak, görsel C++ bağlayıcı, yürütme düzeyi `asInvoker`olan bir uygulamanın bildirimine bir UAC parçası katıştırır. Uygulamanız için yönetici ayrıcalıklarının doğru şekilde çalışmasını gerektiriyorsa (örneğin, kayıt defterinin HKLM düğümünü değiştirirse veya Windows dizini gibi, diskin korunan bölümlerine yazıyorsa), uygulamanızı değiştirmeniz gerekir.

İlk seçenek, bildirimin UAC parçasını, yürütme düzeyini *requireAdministrator*olarak değiştirecek şekilde değiştirmektir. Daha sonra uygulama, kullanıcıdan çalıştırılmadan önce yönetici kimlik bilgilerini ister. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [/bildirimini estuac (BILDIRIMDEKI UAC bilgilerini katıştırır)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).

İkinci seçenek, `/MANIFESTUAC:NO` bağlayıcı seçeneğini belirterek bir UAC parçasını bildirime katıştırmamalıdır. Bu durumda, uygulamanız sanallaştırılmış olarak çalışır. Kayıt defterinde veya dosya sisteminde yaptığınız tüm değişiklikler, uygulamanız sona erdikten sonra devam etmez.

Aşağıdaki akış çizelgesi, uygulamanızın UAC 'nin etkinleştirilip etkinleştirilmeyeceğini ve uygulamanın bir UAC bildirimine sahip olup olmadığına bağlı olarak nasıl çalışacağını açıklar:

![Windows Yükleyici davranışı](media/uacflowchart.png "Windows Yükleyici davranışı")

## <a name="see-also"></a>Ayrıca bkz.

[En Iyi güvenlik uygulamaları](security-best-practices-for-cpp.md)
