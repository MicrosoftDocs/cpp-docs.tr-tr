---
title: Güncelleştirme İşleyicilerini Çağırma Zamanı
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
ms.openlocfilehash: 4a52c147d1abf02b7c5e89abf868f87a07ab32cc
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346069"
---
# <a name="when-update-handlers-are-called"></a>Güncelleştirme İşleyicilerini Çağırma Zamanı

Kullanıcı bir WM_INITMENUPOPUP iletisi oluşturmayacaktır Dosya menüsündeki fareye tıklayana varsayalım. Kullanıcı görebilmeniz menüsü açılır önce framework'ün güncelleştirme mekanizmasını Dosya menüsündeki tüm öğelerini topluca güncelleştirir.

Bunu yapmak için framework yolları komutları tüm menü öğelerinin açılan menüde boyunca standart komut yönlendirmeyi güncelleştirin. Komut hedefleri yönlendirme sahip menü öğeleri güncelleştirme komut uygun ileti eşleme girişi ile eşleştirerek güncelleştirme olanağı (form `ON_UPDATE_COMMAND_UI`) ve bir "Güncelleştirme işleyici" işlevi çağırma. Bu nedenle, altı menü öğeleri ile bir menü için altı güncelleştirme komutları gönderilir. Menü öğesinin komut kimliği için bir güncelleştirme işleyici zaten varsa, bir güncelleştirme yapmak için çağrılır. Aksi halde framework bir işleyici bu komut kimliği için bulunup bulunmadığını kontrol eder ve etkinleştirir veya uygun şekilde menü öğesi devre dışı bırakır.

Çerçeve bulunamadı, bir `ON_UPDATE_COMMAND_UI` otomatik olarak varsa kullanıcı arabirimi nesnesi etkinleştirir komut yönlendirme sırasında girdi, bir `ON_COMMAND` girişi yere aynı komut kimliği. Aksi takdirde, kullanıcı arabirimi nesnesi devre dışı bırakır. Bu nedenle, bir kullanıcı arabirimi nesnesi'nın etkinleştirildiğinden emin olmak için bir işleyici nesnesi oluşturur komut için sağlamak veya bir güncelleştirme işleyici için sağlayın. Şekil konusunda bkz [kullanıcı arabirimi nesneleri ve komut kimlikleri](../mfc/user-interface-objects-and-command-ids.md).

Varsayılan devre dışı kullanıcı arabirimi nesnelerini devre dışı bırakmak mümkündür. Daha fazla bilgi için [m_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable) sınıfının üyesi `CFrameWnd` içinde *MFC başvurusu*.

Menü başlatma framework uygulama WM_INITMENUPOPUP ileti aldığında gerçekleşen, otomatik olarak gerçekleşir. Boşta döngü sırasında öğesi menülerini gibi komut düğmesi güncelleştirme işleyicileri için çok aynı şekilde yönlendirme framework arar.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)
