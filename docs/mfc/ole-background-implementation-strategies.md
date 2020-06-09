---
title: 'OLE Arka Planı: Uygulama Stratejileri'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
ms.openlocfilehash: 90517f9b37872dd7de0ce1a2d08da94c93e6f8f8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619893"
---
# <a name="ole-background-implementation-strategies"></a>OLE Arka Planı: Uygulama Stratejileri

Uygulamanıza bağlı olarak OLE desteği eklemek için dört olası uygulama stratejisi vardır:

- Yeni bir uygulama yazıyor.

   Bu durum genellikle en az iş gerektirir. Bir çatı uygulaması oluşturmak için MFC Uygulama Sihirbazı 'Nı çalıştırın ve gelişmiş özellikler ya da bileşik belge desteği ' ni seçin. Bu seçenekler ve ne yaptıkları hakkında daha fazla bilgi için, [MFC exe programı oluşturma](reference/mfc-application-wizard.md)makalesine bakın.

- Microsoft Foundation Class Kitaplığı sürüm 2,0 veya sonraki bir sürümü ile yazılmış bir programınız var ve OLE 'yi desteklemez.

   Daha önce belirtildiği gibi MFC Uygulama Sihirbazı ile yeni bir uygulama oluşturun ve ardından yeni uygulamadan kodu kopyalayıp mevcut uygulamanıza yapıştırın. Bu, sunucular, kapsayıcılar veya otomatikleştirilmiş uygulamalar için çalışacaktır. Bu stratejinin bir örneği için bkz. MFC [karalama](../overview/visual-cpp-samples.md) örneği.

- OLE sürüm 1,0 desteğini uygulayan bir Microsoft Foundation Class Kitaplığı programınız vardır.

   Bu dönüştürme stratejisi için bkz. [MFC teknik notunun 41](tn041-mfc-ole1-migration-to-mfc-ole-2.md) .

- Microsoft Foundation Sınıfları kullanılarak yazılmayan ve OLE desteği uygulanmamış veya uygulamamamış bir uygulamanız var.

   Bu durum, en çok iş gerektirir. Bir yaklaşım, İlk stratejide olduğu gibi yeni bir uygulama oluşturmak ve ardından var olan kodunuzu kopyalayıp içine yapıştırmaktır. Mevcut kodunuz C dilinde yazılmışsa, C++ kodu olarak derlemek için onu değiştirmeniz gerekebilir. C kodunuz Windows API 'sini çağırırsa, Microsoft Foundation sınıflarını kullanmak için bunu değiştirmeniz gerekmez. Bu yaklaşım büyük olasılıkla, 2,0 ve Microsoft Foundation Sınıfları üzeri sürümleri tarafından kullanılan belge/görünüm mimarisini desteklemek için programınızı yeniden yapılandırma gerektirir. Bu mimari hakkında daha fazla bilgi için bkz. [teknik nota 25](tn025-document-view-and-frame-creation.md).

Bir stratejiye karar verdikten sonra [kapsayıcıları](containers.md) veya [sunucu](servers.md) makalelerini (yazmakta olduğunuz uygulamanın türüne bağlı olarak) veya örnek programları ya da her ikisini birden okumanız gerekir. MFC OLE örnekleri [Oclient](../overview/visual-cpp-samples.md) ve [hiersvr](../overview/visual-cpp-samples.md) , kapsayıcılar ve sunucuların çeşitli yönlerini sırasıyla nasıl uygulanacağını gösterir. Bu makalelerin tamamında çeşitli noktalarda, ele alınan tekniklerin örnekleri olarak bu örneklerde belirli işlevlere bahsedilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[OLE arka planı](ole-background.md)<br/>
[Kapsayıcılar: Bir Kapsayıcı Uygulama](containers-implementing-a-container.md)<br/>
[Sunucular: Sunucu Uygulama](servers-implementing-a-server.md)<br/>
[MFC Uygulama Sihirbazı](reference/mfc-application-wizard.md)
