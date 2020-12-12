---
description: 'Şu konuda daha fazla bilgi edinin: kapsayıcılar: bir kapsayıcı uygulama'
title: 'Kapsayıcılar: Bir Kapsayıcı Uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
ms.openlocfilehash: 24e3c7f7d4546ebe9b103af0e9ca0d9694b25d2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310333"
---
# <a name="containers-implementing-a-container"></a>Kapsayıcılar: Bir Kapsayıcı Uygulama

Bu makalede bir kapsayıcı uygulama yordamı özetlenmektedir ve kapsayıcıları uygulama hakkında daha ayrıntılı açıklamalar sağlayan diğer makalelere işaret eder. Ayrıca, uygulamak isteyebileceğiniz bazı isteğe bağlı OLE özelliklerini ve bu özellikleri açıklayan makaleleri de listeler.

#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp türetilmiş sınıfınızı hazırlamak için

1. Üye işlevini çağırarak OLE kitaplıklarını başlatın `AfxOleInit` `InitInstance` .

1. Yerleşik `CDocTemplate::SetContainerInfo` `InitInstance` bir öğe yerinde etkinleştirildiğinde kullanılan menü ve Hızlandırıcı kaynaklarını atamak için ' i çağırın. Bu konu hakkında daha fazla bilgi için bkz. [etkinleştirme](activation-cpp.md).

Bu özellikler, bir kapsayıcı uygulaması oluşturmak için MFC Uygulama Sihirbazı 'nı kullandığınızda sizin için otomatik olarak sağlanır. Bkz. [MFC exe programı oluşturma](reference/mfc-application-wizard.md).

#### <a name="to-prepare-your-view-class"></a>Görünüm sınıfınızı hazırlamak için

1. Seçili öğelere birden çok seçimi desteklerken, bir işaretçiyi veya işaretçiler listesini tutarak seçili öğeleri izleyin. `OnDraw`İşleviniz tüm OLE öğelerini çizmelidir.

1. `IsSelected`Geçirilen öğenin şu anda seçili olup olmadığını denetlemek için geçersiz kılın.

1. `OnInsertObject` **Nesne Ekle** iletişim kutusunu göstermek için bir ileti işleyicisi uygulayın.

1. `OnSetFocus`Görünümden odağı yerinde bir ETKIN OLE Embedded öğesine aktarmak için bir ileti işleyicisi uygulayın.

1. Bir `OnSize` OLE Embedded öğesine, kendisini içeren görünümün boyutunu yansıtacak şekilde değiştirmek için ihtiyacı olan bir OLE katıştırılmış öğesini bilgilendirmek üzere bir ileti işleyicisi uygulayın.

Bu özelliklerin uygulanması, bir uygulamadan bir sonrakine önemli bir şekilde değiştiğinden, uygulama Sihirbazı yalnızca temel bir uygulama sağlar. Büyük olasılıkla uygulamanızın düzgün çalışmasını sağlamak için bu işlevleri özelleştirmeniz gerekecektir. Buna bir örnek için bkz. [kapsayıcı](../overview/visual-cpp-samples.md) örneği.

#### <a name="to-handle-embedded-and-linked-items"></a>Katıştırılmış ve bağlantılı öğeleri işlemek için

1. [Colet Clienentidıtem](reference/coleclientitem-class.md)öğesinden bir sınıf türet. Bu sınıfın nesneleri, içine eklenmiş veya OLE belgenize bağlanmış öğeleri temsil eder.

1. `OnChange`, `OnChangeItemPosition` , Ve geçersiz kılın `OnGetItemPosition` . Bu işlevler, katıştırılmış ve bağlantılı öğeleri boyutlandırmayı, konumlandırmayı ve değiştirmeyi işler.

Uygulama Sihirbazı, sınıfı sizin için türetecektir, ancak `OnChange` önceki yordamda 2. adımdaki diğer işlevleri de geçersiz kılmanız gerekir. Bu işlevler, bir uygulamadan sonrakine farklı şekilde uygulandığından, çatı uygulamalarının çoğu uygulama için özelleştirilmesinin olması gerekir. Bunun örnekleri için bkz. MFC örnekleri [DRAWCLI](../overview/visual-cpp-samples.md) ve [CONTAINER](../overview/visual-cpp-samples.md).

OLE 'yi desteklemek için kapsayıcı uygulamanın menü yapısına bir dizi öğe eklemeniz gerekir. Bunlar hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: kapsayıcı eklemeleri](menus-and-resources-container-additions.md).

Ayrıca, kapsayıcı uygulamanızda aşağıdaki özelliklerden bazılarını desteklemek isteyebilirsiniz:

- Katıştırılmış bir öğeyi düzenlediğinizde yerinde etkinleştirme.

   Daha fazla bilgi için bkz. [etkinleştirme](activation-cpp.md).

- Bir sunucu uygulamasından seçim sürükleyip bırakarak OLE öğeleri oluşturma.

   Daha fazla bilgi için bkz. [OLE sürükle ve bırak](drag-and-drop-ole.md).

- Gömülü nesnelerin veya birleşim kapsayıcı/sunucu uygulamalarının bağlantıları.

   Daha fazla bilgi için bkz. [kapsayıcılar: Gelişmiş Özellikler](containers-advanced-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](containers.md)<br/>
[Kapsayıcılar: Istemci öğeleri](containers-client-items.md)
