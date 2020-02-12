---
title: 'Kapsayıcılar: Bir Kapsayıcı Uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
ms.openlocfilehash: ed95324b8df978a6ab2f7582c0ddf626a45e7fe1
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127926"
---
# <a name="containers-implementing-a-container"></a>Kapsayıcılar: Bir Kapsayıcı Uygulama

Bu makalede bir kapsayıcı uygulama yordamı özetlenmektedir ve kapsayıcıları uygulama hakkında daha ayrıntılı açıklamalar sağlayan diğer makalelere işaret eder. Ayrıca, uygulamak isteyebileceğiniz bazı isteğe bağlı OLE özelliklerini ve bu özellikleri açıklayan makaleleri de listeler.

#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp türetilmiş sınıfınızı hazırlamak için

1. `InitInstance` üye işlevindeki `AfxOleInit` çağırarak OLE kitaplıklarını başlatın.

1. Yerleşik bir öğe yerinde etkinleştirildiğinde kullanılan menü ve Hızlandırıcı kaynaklarını atamak için `InitInstance` `CDocTemplate::SetContainerInfo` çağırın. Bu konu hakkında daha fazla bilgi için bkz. [etkinleştirme](../mfc/activation-cpp.md).

Bu özellikler, bir kapsayıcı uygulaması oluşturmak için MFC Uygulama Sihirbazı 'nı kullandığınızda sizin için otomatik olarak sağlanır. Bkz. [MFC exe programı oluşturma](../mfc/reference/mfc-application-wizard.md).

#### <a name="to-prepare-your-view-class"></a>Görünüm sınıfınızı hazırlamak için

1. Seçili öğelere birden çok seçimi desteklerken, bir işaretçiyi veya işaretçiler listesini tutarak seçili öğeleri izleyin. `OnDraw` işleviniz tüm OLE öğelerini çizmelidir.

1. Geçirilen öğenin şu anda seçili olup olmadığını denetlemek için `IsSelected` geçersiz kılın.

1. **Nesne Ekle** iletişim kutusunu göstermek için bir `OnInsertObject` ileti işleyicisi uygulayın.

1. Görünümden odağı yerinde bir etkin OLE Embedded öğesine aktarmak için bir `OnSetFocus` ileti işleyicisi uygulayın.

1. Bir OLE Embedded öğesine, kendisini içeren görünümün boyutunu yansıtacak şekilde değiştirmek için ihtiyaç duyması gerektiğini bildirmek üzere bir `OnSize` ileti işleyicisi uygulayın.

Bu özelliklerin uygulanması, bir uygulamadan bir sonrakine önemli bir şekilde değiştiğinden, uygulama Sihirbazı yalnızca temel bir uygulama sağlar. Büyük olasılıkla uygulamanızın düzgün çalışmasını sağlamak için bu işlevleri özelleştirmeniz gerekecektir. Buna bir örnek için bkz. [kapsayıcı](../overview/visual-cpp-samples.md) örneği.

#### <a name="to-handle-embedded-and-linked-items"></a>Katıştırılmış ve bağlantılı öğeleri işlemek için

1. [Colet Clienentidıtem](../mfc/reference/coleclientitem-class.md)öğesinden bir sınıf türet. Bu sınıfın nesneleri, içine eklenmiş veya OLE belgenize bağlanmış öğeleri temsil eder.

1. `OnChange`, `OnChangeItemPosition`ve `OnGetItemPosition`geçersiz kılın. Bu işlevler, katıştırılmış ve bağlantılı öğeleri boyutlandırmayı, konumlandırmayı ve değiştirmeyi işler.

Uygulama Sihirbazı, sınıfı sizin için türetecektir, ancak önceki yordamda adım 2 ' de bulunan `OnChange` ve diğer işlevleri büyük olasılıkla geçersiz kılmanız gerekir. Bu işlevler, bir uygulamadan sonrakine farklı şekilde uygulandığından, çatı uygulamalarının çoğu uygulama için özelleştirilmesinin olması gerekir. Bunun örnekleri için bkz. MFC örnekleri [DRAWCLI](../overview/visual-cpp-samples.md) ve [CONTAINER](../overview/visual-cpp-samples.md).

OLE 'yi desteklemek için kapsayıcı uygulamanın menü yapısına bir dizi öğe eklemeniz gerekir. Bunlar hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: kapsayıcı eklemeleri](../mfc/menus-and-resources-container-additions.md).

Ayrıca, kapsayıcı uygulamanızda aşağıdaki özelliklerden bazılarını desteklemek isteyebilirsiniz:

- Katıştırılmış bir öğeyi düzenlediğinizde yerinde etkinleştirme.

   Daha fazla bilgi için bkz. [etkinleştirme](../mfc/activation-cpp.md).

- Bir sunucu uygulamasından seçim sürükleyip bırakarak OLE öğeleri oluşturma.

   Daha fazla bilgi için bkz. [OLE sürükle ve bırak](../mfc/drag-and-drop-ole.md).

- Gömülü nesnelerin veya birleşim kapsayıcı/sunucu uygulamalarının bağlantıları.

   Daha fazla bilgi için bkz. [kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Kapsayıcılar: İstemci Öğeleri](../mfc/containers-client-items.md)
