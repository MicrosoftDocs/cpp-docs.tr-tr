---
title: Kullanıcı Grubu Üyesi Olarak Çalıştırma
ms.date: 11/04/2016
helpviewer_keywords:
- Users Group [C++]
- security [C++], Users Group
- Windows accounts [C++]
- non administrator users [C++]
- user accounts [C++]
- administrator (not running as) [C++]
ms.assetid: e48a03ec-d345-49f6-809a-1a291eecbc81
ms.openlocfilehash: 117ef426950fc9aff5ae41e894f0d7ae898369cd
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445435"
---
# <a name="running-as-a-member-of-the-users-group"></a>Kullanıcı Grubu Üyesi Olarak Çalıştırma

Bu konu, Windows Kullanıcı hesaplarının, Kullanıcı grubunun bir üyesi olarak nasıl yapılandırılacağı açıklanmaktadır (Yöneticiler grubunun aksine) kötü amaçlı kodla bulaşma olasılığını azaltarak güvenliği artırır.

## <a name="security-risks"></a>Güvenlik riskleri

Yönetici olarak çalıştırıldığında, sisteminiz "Truva atı" ve "arabellek taşması" gibi çeşitli güvenlik saldırılarına karşı savunmasız olur. Bir Internet sitesinden indirilen kötü amaçlı kod bilgisayarınıza saldırmak için, bir yönetici olarak yalnızca bir Internet sitesini ziyaret edebilirsiniz. Başarılı olursa, yönetici izinlerinizi devralır ve daha sonra tüm dosyalarınızı silme, sabit sürücünüzü yeniden biçimlendirme ve yönetim erişimi olan yeni bir kullanıcı hesabı oluşturma gibi eylemler gerçekleştirebilir.

## <a name="non-administrator-user-groups"></a>Yönetici olmayan kullanıcı grupları

Geliştiricilerin normalde kullandığı Windows Kullanıcı hesapları, kullanıcılar ya da uzman kullanıcılar gruplarına eklenmelidir. Geliştiriciler de hata ayıklama grubuna eklenmelidir. Kullanıcılar grubunun bir üyesi olmak, çalışan programlar ve bilgisayarınızı gereksiz riske sokmadan Internet sitelerini ziyaret eden rutin görevleri gerçekleştirmenize olanak tanır. Power Users grubunun bir üyesi olarak, uygulama yükleme, yazıcı yükleme ve çoğu Denetim Masası işlemi gibi görevleri de gerçekleştirebilirsiniz. İşletim sistemini yükseltme veya sistem parametrelerini yapılandırma gibi yönetim görevleri gerçekleştirmeniz gerekiyorsa, yönetim görevini gerçekleştirmek için yeterince uzun bir yönetici hesabında oturum açmanız gerekir. Alternatif olarak, Windows **runas** komutu, yönetim erişimi olan belirli uygulamaları başlatmak için kullanılabilir.

## <a name="exposing-customers-to-security-risks"></a>Müşterileri güvenlik risklerine sunma

Yöneticiler grubunun parçası değil geliştiriciler için özellikle önemlidir çünkü geliştirme makinelerini korumaya ek olarak, geliştiricilerin müşterilerin Yöneticiler grubuna katılması gereken kodu yanlışlıkla yazmasını engeller. Geliştirdiğiniz uygulamaları yürütmek için sıralama. Geliştirme sırasında yönetici erişimi gerektiren kod tanıtıldığında, çalışma zamanında başarısız olur ve uygulamanızın artık müşterilerin yönetici olarak çalıştırılmasını gerektirdiğini size uyarır.

## <a name="code-that-requires-administrator-privileges"></a>Yönetici ayrıcalıkları gerektiren kod

Bazı kodlar yürütmek için yönetici erişimi gerektirir. Mümkünse, bu kodun alternatifleri yapılmalıdır. Yönetici erişimi gerektiren kod işlemlerine örnek olarak şunlar verilebilir:

- Dosya sisteminin Windows veya program dosyaları dizinleri gibi korumalı bölümlerine yazma

- Kayıt defterinin korunan bölümlerine yazma (örneğin, HKEY_LOCAL_MACHINE)

- Bütünleştirilmiş kodları genel derleme önbelleğinde (GAC) yükleme

Genellikle, bu eylemlerin uygulama yükleme programlarıyla sınırlı olması gerekir. Bu, kullanıcıların yalnızca geçici olarak yönetici durumunu kullanmasına izin verir.

## <a name="debugging"></a>Hata ayıklama

Hata ayıklama grubunun bir parçası haline getirerek, Visual Studio içinde (yerel ve yönetilmeyen), yönetici olmayan tüm uygulamalarda hata ayıklaması yapabilirsiniz. Bu, Işleme Iliştir komutunu kullanarak çalışan bir uygulamaya ekleme olanağını içerir. Ancak, farklı bir kullanıcı tarafından başlatılan yerel veya yönetilen uygulamaların hatalarını ayıklamak için yönetici grubunun bir parçası olması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[En Iyi güvenlik uygulamaları](security-best-practices-for-cpp.md)
