---
title: İletişim Kutusu Çubukları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
ms.openlocfilehash: 3a3276e9b5d0e1ab8d8e77fae983d24ff1e4b4e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557416"
---
# <a name="dialog-bars"></a>İletişim Kutusu Çubukları

Bir iletişim çubuğu bir araç, bir tür olduğundan, [denetim çubuğu](../mfc/control-bars.md) herhangi bir denetim türü içerebilir. Modsuz iletişim kutusu, özelliklerine sahip olduğu bir [CDialogBar](../mfc/reference/cdialogbar-class.md) nesnesi, daha güçlü bir araç sağlar.

Araç çubuğu arasında bazı önemli farklılıklar vardır ve bir `CDialogBar` nesne. A `CDialogBar` nesnesi, Visual C++ iletişim kutusu Düzenleyicisi ile oluşturabileceğiniz ve herhangi bir Windows Denetim türü içerebilecek bir iletişim şablonunu kaynaktan, oluşturulur. Kullanıcı denetiminden denetlemek için sekmesinde. Ve bir hizalama Stili iletişim çubuğu ana çerçeve penceresinin herhangi bir bölümü ile hizalamak için veya hatta bunu yerinde bırakmanız üst boyutlandırılırsa belirtebilirsiniz. Aşağıdaki şekilde bir iletişim çubuğu çeşitli denetimleri gösterir.

![VC iletişim çubuğu](../mfc/media/vc378t1.gif "vc378t1") bir iletişim çubuğu

İle çalışma, diğer bakımdan bir `CDialogBar` nesnedir modsuz iletişim kutusu ile çalışmak gibidir. Tasarım ve iletişim kaynağını oluşturma iletişim kutusu düzenleyicisini kullanın.

İletişim kutusu çubukları, virtues düğmeleri dışında denetimleri içerebilir biridir.

Kendi iletişim sınıflarından normal olsa `CDialog`, genellikle bir iletişim çubuğu için kendi sınıfınızı türetilen değil. İletişim kutusu çubukları olan ana pencere ve herhangi bir iletişim çubuğu denetim bildirimi iletileri için uzantıları gibi **BN_CLICKED** veya **EN_CHANGE**, çubuk, ana pencereyi iletişim kutusunun üst gönderilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[Örnek](../visual-cpp-samples.md)

