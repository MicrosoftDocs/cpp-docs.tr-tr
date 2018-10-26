---
title: 'OLE arka planı: Uygulama stratejileri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae49db47905f38c4b614609a7a4b73c4597292e3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075917"
---
# <a name="ole-background-implementation-strategies"></a>OLE Arka Planı: Uygulama Stratejileri

Uygulamanızın bağlı olarak, dört olası uygulama stratejileri OLE desteği ekleme vardır:

- Yeni bir uygulama yazıyorsunuz.

   Bu durum genellikle en az gerektirir çalışır. MFC Uygulama Sihirbazı'nı çalıştırın ve Gelişmiş Özellikler veya bileşik belge desteği iskelet bir uygulama oluşturulacağını seçin. Bu seçeneklerin ve ne hakkında daha fazla bilgi için bkz [bir MFC EXE Program oluşturma](../mfc/reference/mfc-application-wizard.md).

- Microsoft Foundation Class Kitaplığı ile sürüm 2.0 veya üstü OLE desteklemiyor bir program var.

   MFC Uygulama Sihirbazı daha önce belirtildiği gibi yeni bir uygulama oluşturun ve daha sonra kopyalayın ve yeni uygulama kodunu mevcut uygulamanıza yapıştırın. Bu sunucular, kapsayıcıları veya otomatik uygulamalar için çalışır. MFC bkz [KARALAMA](../visual-cpp-samples.md) örnek bu strateji ilişkin bir örnek.

- OLE sürüm 1.0 desteği uygulayan Microsoft Foundation Class Kitaplığı programı var.

   Bkz: [MFC Teknik Notu 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) bu dönüştürme stratejisi.

- Sahip olduğunuz bir uygulama, Microsoft Foundation sınıfları kullanarak yazılmadı ve olabilir veya OLE desteği uygulanmadı.

   Bu durum, en fazla iş gerektirir. Bir ilk strateji, olduğu gibi yeni bir uygulama oluşturun ve ardından kopyalayıp mevcut kod içine bir yaklaşımdır. Mevcut kodunuzu C yazılmışsa, C++ kodu olarak derle şekilde değiştirmeniz gerekebilir. Ardından, C kodu Windows API çağırırsa, Microsoft Foundation sınıfları kullanmak için değiştirmeniz gerekmez. Büyük olasılıkla bu yaklaşım bazı sürümleri 2.0 ve üzeri Microsoft Foundation sınıfları tarafından kullanılan belge/görünüm mimarisi desteği için programınızın alanlarını yeniden yapılandırma gerektirir. Bu mimari hakkında daha fazla bilgi için bkz. [Teknik Not 25](../mfc/tn025-document-view-and-frame-creation.md).

Bir stratejisi verdikten sonra her iki okuma gereken [kapsayıcıları](../mfc/containers.md) veya [sunucuları](../mfc/servers.md) makaleler (yazdığınız uygulama türünü bağlı olarak) veya örnek programlardan veya her ikisi de inceleyin. MFC OLE örnekleri [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md) nasıl kapsayıcılar ve sunucular, çeşitli yönlerini sırasıyla uygulandığını göstermektedir. Bu makaleler boyunca çeşitli noktalarda belirli işlevlere Bu örnekte açıklanan teknikleri örnekleri olarak anılacaktır.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE Arka Planı](../mfc/ole-background.md)<br/>
[Kapsayıcılar: Bir Kapsayıcı Uygulama](../mfc/containers-implementing-a-container.md)<br/>
[Sunucular: Sunucu Uygulama](../mfc/servers-implementing-a-server.md)<br/>
[MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)

