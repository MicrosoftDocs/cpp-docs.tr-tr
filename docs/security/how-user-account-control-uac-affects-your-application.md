---
title: Kullanıcı Hesabı Denetimi (UAC) uygulamanızı nasıl etkiler? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23266ca4b4d32146ed8627c6ce3ab1cc878d59cd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600658"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Kullanıcı Hesabı Denetimi (UAC) Uygulamanızı Nasıl Etkiler
Kullanıcı Hesabı Denetimi (UAC), Windows Vista'nın, kullanıcı hesaplarının ayrıcalıkları sınırlı bir özelliktir. Bu sitelerdeki UAC hakkında ayrıntılı bilgi bulabilirsiniz:  
  
-   [Windows Vista kullanıcı hesabı denetimi adım adım kılavuzu](http://go.microsoft.com/fwlink/p/?linkid=53781)  
  
-   [Geliştirici en iyi ve en az ayrıcalıklı bir ortamda uygulamalar için yönergeler](http://go.microsoft.com/fwlink/p/?linkid=82444)  
  
-   [Anlama ve Windows Vista kullanıcı hesabı denetimi yapılandırma](http://go.microsoft.com/fwlink/p/?linkid=82445)  
  
## <a name="building-projects-after-enabling-uac"></a>UAC etkinleştirdikten sonra proje oluşturma  
 Windows Vista'da UAC devre dışıyken Visual C++ projesi oluşturun ve daha sonra UAC'yi etkinleştirmek, temizleme ve bunun düzgün çalışması projeyi yeniden derleyin.  
  
## <a name="applications-that-require-administrative-privileges"></a>Yönetici ayrıcalıkları gerektiren uygulamalar  
 Varsayılan olması, Visual C++ bağlayıcı UAC parçası yürütme düzeyi uygulama bildirimine katıştırır `asInvoker`. Uygulamanıza (örneğin, kayıt defteri HKLM düğümünün değiştiriyorsa veya Windows dizini gibi diskin korumalı alanlarına yazıyorsa) doğru bir şekilde çalıştırmak için yönetici ayrıcalıkları gerekiyorsa, uygulamanızı değiştirmeniz gerekir.  
  
 İlk seçenek yürütme düzeyini değiştirmek için UAC parçasında değiştirmektir *requireAdministrator'a*. Çalıştırılmadan önce uygulamayı daha sonra kullanıcıdan yönetimsel kimlik bilgilerini ister. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [/MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 İkinci seçenek UAC parçası bildirime belirterek ekleme değil, `/MANIFESTUAC:NO` bağlayıcı seçeneği. Bu durumda, uygulamanızı sanallaştırılmış çalıştırılır. Uygulamanızı sona erdikten sonra kayıt defteri veya dosya sistemine yaptığınız tüm değişiklikler kalıcı olmaz.  
  
 Aşağıdaki akış çizelgesi, uygulamanızın nasıl çalışacağını tanımlar UAC etkin olup olmadığını ve uygulama UAC bildirim olup bağlı olarak:  
  
 ![Windows Vista yükleyici davranışı](media/uacflowchart.png "UACflowchart")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [En iyi güvenlik uygulamaları](security-best-practices-for-cpp.md)