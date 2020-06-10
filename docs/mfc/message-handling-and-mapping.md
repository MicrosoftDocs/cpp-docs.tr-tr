---
title: İleti İşleme ve Eşleme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
ms.openlocfilehash: a27f8220055630873b02dd7ff975c04744ad9e8e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622401"
---
# <a name="message-handling-and-mapping"></a>İleti İşleme ve Eşleme

Bu makalede, iletilerin ve komutların MFC çerçevesi tarafından nasıl işlendiği ve bunların işleyici işlevlerine nasıl bağlanacağı açıklanmaktadır.

Windows için geleneksel programlarda Windows iletileri, bir pencere yordamındaki büyük bir switch ifadesinde işlenir. Bunun yerine MFC, doğrudan iletileri ayrı sınıf üye işlevlerine eşlemek için [ileti haritaları](message-categories.md) kullanır. İleti haritaları bu amaçla sanal işlevlerden daha verimlidir ve iletilerin en uygun C++ nesnesi (uygulama, belge, görünüm vb.) tarafından işlenmesine izin verir. Tek bir iletiyi veya bir ileti aralığını, komut kimliklerini veya denetim kimliklerini eşleyebilirsiniz.

Genellikle menüler, araç çubuğu düğmeleri veya Hızlandırıcılar tarafından oluşturulan WM_COMMAND iletileri de ileti eşleme mekanizmasını kullanır. MFC, programınızdaki uygulama, çerçeve penceresi, görünüm ve etkin belgeler arasında komut iletilerinin standart bir [yönlendirmesini](command-routing.md) tanımlar. Gerekirse, bu yönlendirmeyi geçersiz kılabilirsiniz.

İleti haritaları Ayrıca, Kullanıcı arabirimi nesnelerini (menüler ve araç çubuğu düğmeleri gibi) güncelleştirmek, bunları geçerli bağlama uyacak şekilde etkinleştirmek veya devre dışı bırakmak için bir yol sağlar.

Windows 'daki iletiler ve ileti kuyrukları hakkında genel bilgi için, Windows SDK [ileti ve Ileti kuyrukları](/windows/win32/winmsg/messages-and-message-queues) ' ne bakın.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Framework'teki İletiler ve Komutlar](messages-and-commands-in-the-framework.md)

- [Çerçeve bir ileti işleyicisini nasıl çağırır](how-the-framework-calls-a-handler.md)

- [Çerçeve Ileti eşlemelerini nasıl arar](how-the-framework-searches-message-maps.md)

- [İleti İşleyici İşlevlerini Bildirme](declaring-message-handler-functions.md)

- [İletileri İşlevlere Eşleme](reference/mapping-messages-to-functions.md)

- [Durum çubuğunda komut bilgilerini görüntüleme](how-to-display-command-information-in-the-status-bar.md)

- [Kullanıcı arabirimi nesnelerinin dinamik güncelleştirmesi](how-to-update-user-interface-objects.md)

- [Nasıl yapılır: Bir Şablon Sınıfı için İleti Eşlemesi Oluşturma](how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](mfc-concepts.md)<br/>
[Genel MFC Konuları](general-mfc-topics.md)<br/>
[CWnd Sınıfı](reference/cwnd-class.md)<br/>
[CCmdTarget sınıfı](reference/ccmdtarget-class.md)
