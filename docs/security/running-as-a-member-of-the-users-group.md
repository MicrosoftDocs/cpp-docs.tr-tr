---
title: Kullanıcılar grubunun bir üyesi olarak çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- PRJ0050
- VCD0047
dev_langs:
- C++
helpviewer_keywords:
- Users Group [C++]
- security [C++], Users Group
- Windows accounts [C++]
- non administrator users [C++]
- user accounts [C++]
- administrator (not running as) [C++]
ms.assetid: e48a03ec-d345-49f6-809a-1a291eecbc81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fd9d0deded3180529bfa714519a9b8d415c6b15
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586328"
---
# <a name="running-as-a-member-of-the-users-group"></a>Kullanıcı Grubu Üyesi Olarak Çalıştırma
Bu konu nasıl (aksine, Yöneticiler grubu) Users grubunun bir üyesi olarak Windows kullanıcı hesapları yapılandırılıyor kötü amaçlı kod bulaşması olasılığını azaltarak güvenliğini açıklar.  
  
## <a name="security-risks"></a>Güvenlik riskleri  
 Bir yönetici olarak, sistem güvenlik saldırısı, "Truva atı" ve "arabellek taşması." gibi çeşitli türlerde karşı savunmasız hale getirir Bir yönetici sisteme zarar olarak yalnızca sitesini ziyaret ederek bir Internet sitesini bir Internet sitesinden indirilen kötü amaçlı kod olarak bilgisayarınızı saldırı. Başarılı olursa, yönetici izinleri devralır ve tüm dosyaları sildikten, sabit yeniden biçimlendirme ve yeni bir kullanıcı, yönetici erişimine sahip hesapları oluşturma gibi eylemler gerçekleştirebilir.  
  
## <a name="non-administrator-user-groups"></a>Yönetici olmayan kullanıcı grupları  
 Geliştiriciler normalde kullandığı Windows kullanıcı hesapları, kullanıcıları veya güç kullanıcı grupları için eklenmelidir. Geliştiriciler ayrıca hata ayıklama grubuna eklenmesi gerekir. Kullanıcılar grubunun bir üyesi olduğundan çalışan programlar ve gereksiz risk bilgisayarınıza sokmadan Internet siteleri ziyaret dahil olmak üzere, rutin görevleri gerçekleştirmenize olanak tanır. Power Users grubunun bir üyesi olarak uygulama yükleme, yazıcı yükleme ve çoğu Denetim Masası işlemleri gibi görevleri gerçekleştirebilirsiniz. İşletim sistemini yükseltmeyi veya sistem parametrelerini yapılandırma gibi yönetim görevlerini gerçekleştirmek gerekiyorsa, içinde bir yönetici hesabı süre için yönetim görevi gerçekleştirmek için yeterli oturum açmanız gerekir. Alternatif olarak, Windows **runas** komutu, belirli uygulamaları yönetici erişimi ile başlatmak için kullanılabilir.  
  
## <a name="exposing-customers-to-security-risks"></a>Müşterilerin güvenlik risklerine gösterme  
 Geliştirme makineleri korumaya ek olarak, geliştiriciler Yöneticiler grubuna katılın müşterilere gerektiren kod yanlışlıkla yazmasını engeller, Yöneticiler grubunun bir parçası olmadığı geliştiriciler için özellikle önemlidir çünkü Sipariş uygulamalarını yürütmek için geliştirdiğiniz. Yönetici erişimi gerektiren kod geliştirme sırasında ortaya çıkan, uygulamanızın yönetici olarak çalıştırmak müşterilerin gerektirdiğini için uyarı, çalışma zamanında başarısız olur.  
  
## <a name="code-that-requires-administrator-privileges"></a>Yönetici ayrıcalıkları gerektiren kod  
 Bazı kod yürütmek için yönetici erişimi gerektirir. Mümkünse, bu kod alternatifleri takip edilmelidir. Yönetici erişimi gerektiren kod işlem örnekleri şunlardır:  
  
-   Dosya sistemi, Windows veya Program Files dizini gibi korumalı alanlarına yazma  
  
-   Kayıt defterinde HKEY_LOCAL_MACHINE gibi korumalı alanlarına yazma  
  
-   Derlemeleri Genel Derleme Önbelleği'ne (GAC) yükleme  
  
 Genellikle, bu eylemleri uygulama yükleme programları için sınırlı olmalıdır. Bu yönetici durumu yalnızca geçici olarak kullanmasına olanak tanır.  
  
## <a name="debugging"></a>Hata Ayıklama  
 Hata ayıklama grubunun parçası olma tarafından yönetici olmayan Visual Studio içinden (yerel ve yönetilmeyen) başlatma uygulamalarda hata ayıklama yapabilirsiniz. Bu işlem komut işleme İliştir çalışan bir uygulamayı ekleme özelliği içerir. Ancak, farklı bir kullanıcı tarafından başlatılan yerel veya yönetilen uygulamalarda hata ayıklamak için yönetici grubunun bir parçası olması gereklidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [En iyi güvenlik uygulamaları](security-best-practices-for-cpp.md)