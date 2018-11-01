---
title: İleti İşleme ve Eşleme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
ms.openlocfilehash: 1b109a3f85ffd3311d08c3d749d543b1e625e77c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628624"
---
# <a name="message-handling-and-mapping"></a>İleti İşleme ve Eşleme

Bu makalede ailesi, iletiler ve komutlar MFC çerçevesinde nasıl işlendiğini ve nasıl, bunları bunların işleyici işlevlerine nasıl bağlanacağını açıklar.

Windows için geleneksel programlarda, Windows iletileri pencere yordamını büyük switch deyiminde işlenir. Bunun yerine bir MFC kullanmadığı [ileti eşlemeleri](../mfc/message-categories.md) ayrı bir sınıf üyesi işlevleri için doğrudan ileti eşlemesi için. İleti eşlemeleri sanal İşlevler ' daha verimli bu amaçla ve bunlar en uygun bir C++ nesnesi tarafından işlenmek üzere iletilere izin ver-uygulama, belge, Görünüm ve benzeri. Kimlikleri denetimi veya tek bir iletiyi veya iletileri, komut kimlikleri, bir dizi eşleyin.

WM_COMMAND iletileri — genellikle menüler, düğmeler veya Hızlandırıcılar tarafından oluşturulan — ayrıca ileti eşleme mekanizmasını kullanın. MFC bir standardı tanımlar [yönlendirme](../mfc/command-routing.md) pencere, Görünüm ve programınızdaki etkin belgeler komut iletileri arasında uygulama çerçevesi. Gerekirse bu yönlendirme geçersiz kılabilirsiniz.

İleti eşlemeleri (örneğin, menüleri ve araç çubuğu düğmeleri) kullanıcı arabirimi nesnelerini güncelleştirme için bir yol da belirtmeniz geçerli bağlam uyacak şekilde devre dışı bırakma veya etkinleştirme.

İletileri ve ileti kuyrukları Windows hakkında genel bilgi için bkz. [iletileri ve ileti kuyruklarındaki](https://msdn.microsoft.com/library/windows/desktop/ms632590) Windows SDK.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

- [Framework'ün ileti işleyici çağırması](../mfc/how-the-framework-calls-a-handler.md)

- [Framework'ün İleti Eşlemelerini Araması](../mfc/how-the-framework-searches-message-maps.md)

- [İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)

- [İletileri İşlevlere Eşleme](../mfc/reference/mapping-messages-to-functions.md)

- [Durum çubuğunda komut bilgilerini görüntüleme](../mfc/how-to-display-command-information-in-the-status-bar.md)

- [Dinamik kullanıcı arabirimi nesnelerini güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

- [Nasıl yapılır: Bir Şablon Sınıfı için İleti Eşlemesi Oluşturma](../mfc/how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CWnd Sınıfı](../mfc/reference/cwnd-class.md)<br/>
[CCmdTarget Sınıfı](../mfc/reference/ccmdtarget-class.md)
