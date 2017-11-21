---
title: "Kullanıcılar grubunun bir üyesi olarak çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PRJ0050
- VCD0047
dev_langs: C++
helpviewer_keywords:
- Users Group [C++]
- security [C++], Users Group
- Windows accounts [C++]
- non administrator users [C++]
- user accounts [C++]
- administrator (not running as) [C++]
ms.assetid: e48a03ec-d345-49f6-809a-1a291eecbc81
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 0535848630fbb32171d4f48ca8e227b7112f0744
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="running-as-a-member-of-the-users-group"></a>Kullanıcı Grubu Üyesi Olarak Çalıştırma
Bu konuda nasıl (aksine, Yöneticiler grubu) Users grubunun bir üyesi olarak Windows kullanıcı hesaplarını yapılandırma güvenlik kötü amaçlı kod bulaşması olasılığını azaltarak artırır açıklanmaktadır.  
  
## <a name="security-risks"></a>Güvenlik riskleri  
 Bir yönetici olarak çalışan sisteminizi "Truva atı" ve "arabellek taşması." gibi güvenlik saldırısı çeşitli türlerde karşı savunmasız hale getirir Bir yönetici sisteme zarar verebilir gibi yalnızca ziyaret bir Internet sitesini bir Internet sitelerinden indirilen kötü amaçlı kod olarak bilgisayarınıza saldırmak. Başarılı olursa, yönetici izinlerinizi devralır ve tüm dosyaları sildikten, sabit diskinize yeniden biçimlendirme ve yeni bir kullanıcı hesapları yönetici erişimine sahip oluşturma gibi eylemleri gerçekleştirebilir.  
  
## <a name="non-administrator-user-groups"></a>Yönetici olmayan kullanıcı grupları  
 Geliştiricilerin normalde kullandığı Windows kullanıcı hesapları kullanıcıların veya Power Users Groups ile eklenmesi gerekir. Geliştiriciler ayrıca hata ayıklama grubuna eklenmesi gerekir. Users grubunun üyesi olma çalışan programlar ve bilgisayarınızı gereksiz riske sokmadan Internet siteleri ziyaret gibi rutin görevleri gerçekleştirmenizi sağlar. Power Users grubunun bir üyesi olarak uygulama yüklemesi, yazıcı yükleme ve çoğu Denetim Masası işlemleri gibi görevleri de gerçekleştirebilirsiniz. İşletim sistemini yükseltme veya sistem parametrelerini yapılandırma gibi yönetim görevlerini gerçekleştirmek gerekiyorsa, bir yönetici hesabı süre için yönetim görevi gerçekleştirmek için yeterli oturum açmanız gerekir. Alternatif olarak, Windows **runas** komutu, yönetim erişimi olan belirli uygulamaları başlatmak için kullanılabilir.  
  
## <a name="exposing-customers-to-security-risks"></a>Güvenlik riskleri müşterilere gösterme  
 Geliştirme makineleri korumaya ek olarak, geliştiriciler Yöneticiler grubuna katılmak müşteriler gerektiren kod yanlışlıkla yazma engellediğinden, Administrators grubunun bir parçası olmadığı geliştiriciler için özellikle önemlidir Sipariş uygulamalarını yürütmek için geliştirme. Yönetici erişimi gerektiren kod geliştirme sırasında kullanılırsa, uygulamanızın yönetici olarak çalıştırmak müşteriler gerektirdiğini konusunda sizi uyarmayı zamanında başarısız olur.  
  
## <a name="code-that-requires-administrator-privileges"></a>Yönetici ayrıcalıkları gerektiren kod  
 Biraz kod yürütmek için yönetici erişimi gerektirir. Mümkünse, bu kodun alternatifleri takip edilmelidir. Yönetici erişimi gerektiren kod işlemleri örnekleri şunlardır:  
  
-   Windows veya Program dosyaları gibi dosya sisteminin korumalı alanlarına dizinleri yazma  
  
-   Kayıt defteri HKEY_LOCAL_MACHINE gibi korumalı alanlarına yazma  
  
-   Derlemeleri Genel Derleme Önbelleği'ne (GAC) yükleme  
  
 Genellikle, bu eylemleri için uygulama yükleme programları sınırlı olması gerekir. Bu, kullanıcıların yönetici durumu yalnızca geçici olarak kullanmasına izin verir.  
  
## <a name="debugging"></a>Hata Ayıklama  
 Hata ayıklama Grubu'nun parçası olma tarafından yönetici olmayan Visual Studio içinde (yerel ve yönetilmeyen) başlatma herhangi bir uygulama ayıklayabilirsiniz. Bu işleme Ekle komutu kullanarak çalışan bir uygulama ekleme özelliği içerir. Ancak, farklı bir kullanıcı tarafından başlatılan yerel veya yönetilen uygulamalarda hata ayıklamak için yönetici grubunun bir parçası olması gereklidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [En iyi güvenlik uygulamaları](security-best-practices-for-cpp.md)