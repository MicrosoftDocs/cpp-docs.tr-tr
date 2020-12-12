---
description: 'Hakkında daha fazla bilgi edinin: Ileti Işleme ve eşleme'
title: İleti İşleme ve Eşleme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
ms.openlocfilehash: 50a55f4718b47054690325e882177fa9acad2f46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203204"
---
# <a name="message-handling-and-mapping"></a>İleti İşleme ve Eşleme

Bu makalede, iletilerin ve komutların MFC çerçevesi tarafından nasıl işlendiği ve bunların işleyici işlevlerine nasıl bağlanacağı açıklanmaktadır.

Windows için geleneksel programlarda Windows iletileri, bir pencere yordamındaki büyük bir switch ifadesinde işlenir. Bunun yerine MFC, doğrudan iletileri ayrı sınıf üye işlevlerine eşlemek için [ileti haritaları](message-categories.md) kullanır. İleti haritaları bu amaçla sanal işlevlerden daha verimlidir ve iletilerin en uygun C++ nesnesi (uygulama, belge, görünüm vb.) tarafından işlenmesine izin verir. Tek bir iletiyi veya bir ileti aralığını, komut kimliklerini veya denetim kimliklerini eşleyebilirsiniz.

Genellikle menüler, araç çubuğu düğmeleri veya Hızlandırıcılar tarafından oluşturulan WM_COMMAND iletileri de ileti eşleme mekanizmasını kullanır. MFC, programınızdaki uygulama, çerçeve penceresi, görünüm ve etkin belgeler arasında komut iletilerinin standart bir [yönlendirmesini](command-routing.md) tanımlar. Gerekirse, bu yönlendirmeyi geçersiz kılabilirsiniz.

İleti haritaları Ayrıca, Kullanıcı arabirimi nesnelerini (menüler ve araç çubuğu düğmeleri gibi) güncelleştirmek, bunları geçerli bağlama uyacak şekilde etkinleştirmek veya devre dışı bırakmak için bir yol sağlar.

Windows 'daki iletiler ve ileti kuyrukları hakkında genel bilgi için, Windows SDK [ileti ve Ileti kuyrukları](/windows/win32/winmsg/messages-and-message-queues) ' ne bakın.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Çerçevede iletiler ve komutlar](messages-and-commands-in-the-framework.md)

- [Çerçeve bir ileti işleyicisini nasıl çağırır](how-the-framework-calls-a-handler.md)

- [Çerçeve Ileti eşlemelerini nasıl arar](how-the-framework-searches-message-maps.md)

- [Ileti Işleyici Işlevlerini bildirme](declaring-message-handler-functions.md)

- [Iletileri IŞLEVLERE eşleme](reference/mapping-messages-to-functions.md)

- [Durum çubuğunda komut bilgilerini görüntüleme](how-to-display-command-information-in-the-status-bar.md)

- [Kullanıcı arabirimi nesnelerinin dinamik güncelleştirmesi](how-to-update-user-interface-objects.md)

- [Nasıl yapılır: bir şablon sınıfı için Ileti eşlemesi oluşturma](how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](mfc-concepts.md)<br/>
[Genel MFC konuları](general-mfc-topics.md)<br/>
[CWnd sınıfı](reference/cwnd-class.md)<br/>
[CCmdTarget sınıfı](reference/ccmdtarget-class.md)
