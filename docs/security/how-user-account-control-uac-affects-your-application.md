---
title: Kullanıcı Hesabı Denetimi (UAC) uygulamanızı nasıl etkiler | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 020a7a16e38ee40c99a7a5b77c88002e3135bfa1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Kullanıcı Hesabı Denetimi (UAC) Uygulamanızı Nasıl Etkiler
Kullanıcı Hesabı Denetimi (UAC), Windows Vista'nın kullanıcı hesapları sınırlı ayrıcalıklarına sahip bir özelliktir. Aşağıdaki sitelerde UAC hakkında ayrıntılı bilgi bulabilirsiniz:  
  
-   [Windows Vista kullanıcı hesabı denetimi adım adım kılavuzu](http://go.microsoft.com/fwlink/p/?linkid=53781)  
  
-   [Geliştirici en iyi yöntemler ve en az ayrıcalıklı ortamındaki uygulamalar için yönergeler](http://go.microsoft.com/fwlink/p/?linkid=82444)  
  
-   [Anlama ve Windows Vista'da kullanıcı hesabı denetimi yapılandırma](http://go.microsoft.com/fwlink/p/?linkid=82445)  
  
## <a name="building-projects-after-enabling-uac"></a>UAC etkinleştirdikten sonra proje oluşturma  
 Windows Vista UAC devre dışıyken Visual C++ projesi oluşturun ve daha sonra UAC etkinleştirirseniz, temizleyin ve doğru çalışması için projeyi yeniden derleyin.  
  
## <a name="applications-that-require-administrative-privileges"></a>Yönetici ayrıcalıkları gerektiren uygulamalar  
 Varsayılan olması, Visual C++ bağlayıcı UAC parçası bir uygulama bildirimi yürütme düzeyi ile katıştırır `asInvoker`. Uygulamanız doğru bir şekilde (örneğin, kayıt defteri HKLM düğümünün değiştirir veya Windows dizini gibi disk korumalı alanlarına yazıyorsa) çalıştırmak için yönetici ayrıcalıkları gerektiriyorsa, uygulamanızın değiştirmeniz gerekir.  
  
 İlk seçenek bildirimin UAC parçasında yürütme düzeyini değiştirmek değiştirmektir *requireAdministrator'a*. Çalıştırılmadan önce uygulamayı daha sonra kullanıcı için yönetici kimlik bilgilerini ister. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [/MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 İkinci seçenek UAC parçası bildirimine belirterek katıştırmak değil, **/MANIFESTUAC:NO** bağlayıcı seçeneği. Bu durumda, uygulamanızın sanallaştırılmış çalışır. Uygulamanızı sona erdikten sonra kayıt defterine veya dosya sistemine yaptığınız tüm değişiklikler kalıcı olmaz.  
  
 Aşağıdaki akış çizelgesi, uygulamanızın nasıl çalışacağını tanımlar UAC etkinleştirilip etkinleştirilmediği ve uygulama UAC bildirim olup bağlı olarak:  
  
 ![Windows Vista yükleyici davranışı](media/uacflowchart.png "UACflowchart")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [En iyi güvenlik uygulamaları](security-best-practices-for-cpp.md)