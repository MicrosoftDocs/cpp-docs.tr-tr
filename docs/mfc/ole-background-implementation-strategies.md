---
title: 'OLE arka planı: Uygulama stratejileri'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
ms.openlocfilehash: 83a1089ecaaaa9bd0dd1d928cd3d1869e5017a4a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774392"
---
# <a name="ole-background-implementation-strategies"></a>OLE arka planı: Uygulama stratejileri

Uygulamanızın bağlı olarak, dört olası uygulama stratejileri OLE desteği ekleme vardır:

- Yeni bir uygulama yazıyorsunuz.

   Bu durum genellikle en az gerektirir çalışır. MFC Uygulama Sihirbazı'nı çalıştırın ve Gelişmiş Özellikler veya bileşik belge desteği iskelet bir uygulama oluşturulacağını seçin. Bu seçeneklerin ve ne hakkında daha fazla bilgi için bkz [bir MFC EXE Program oluşturma](../mfc/reference/mfc-application-wizard.md).

- Microsoft Foundation Class Kitaplığı ile sürüm 2.0 veya üstü OLE desteklemiyor bir program var.

   MFC Uygulama Sihirbazı daha önce belirtildiği gibi yeni bir uygulama oluşturun ve daha sonra kopyalayın ve yeni uygulama kodunu mevcut uygulamanıza yapıştırın. Bu sunucular, kapsayıcıları veya otomatik uygulamalar için çalışır. MFC bkz [KARALAMA](../overview/visual-cpp-samples.md) örnek bu strateji ilişkin bir örnek.

- OLE sürüm 1.0 desteği uygulayan Microsoft Foundation Class Kitaplığı programı var.

   Bkz: [MFC Teknik Notu 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) bu dönüştürme stratejisi.

- Sahip olduğunuz bir uygulama, Microsoft Foundation sınıfları kullanarak yazılmadı ve olabilir veya OLE desteği uygulanmadı.

   Bu durum, en fazla iş gerektirir. Bir ilk strateji, olduğu gibi yeni bir uygulama oluşturun ve ardından kopyalayıp mevcut kod içine bir yaklaşımdır. Mevcut kodunuzu C yazılmışsa, C++ kodu olarak derle şekilde değiştirmeniz gerekebilir. Ardından, C kodu Windows API çağırırsa, Microsoft Foundation sınıfları kullanmak için değiştirmeniz gerekmez. Büyük olasılıkla bu yaklaşım bazı sürümleri 2.0 ve üzeri Microsoft Foundation sınıfları tarafından kullanılan belge/görünüm mimarisi desteği için programınızın alanlarını yeniden yapılandırma gerektirir. Bu mimari hakkında daha fazla bilgi için bkz. [Teknik Not 25](../mfc/tn025-document-view-and-frame-creation.md).

Bir stratejisi verdikten sonra her iki okuma gereken [kapsayıcıları](../mfc/containers.md) veya [sunucuları](../mfc/servers.md) makaleler (yazdığınız uygulama türünü bağlı olarak) veya örnek programlardan veya her ikisi de inceleyin. MFC OLE örnekleri [OCLIENT](../overview/visual-cpp-samples.md) ve [HIERSVR](../overview/visual-cpp-samples.md) nasıl kapsayıcılar ve sunucular, çeşitli yönlerini sırasıyla uygulandığını göstermektedir. Bu makaleler boyunca çeşitli noktalarda belirli işlevlere Bu örnekte açıklanan teknikleri örnekleri olarak anılacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE Arka Planı](../mfc/ole-background.md)<br/>
[Kapsayıcılar: Bir kapsayıcı uygulama](../mfc/containers-implementing-a-container.md)<br/>
[Sunucular: Sunucu uygulama](../mfc/servers-implementing-a-server.md)<br/>
[MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)
