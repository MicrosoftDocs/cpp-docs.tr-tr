---
title: 'Kapsayıcılar: bir kapsayıcı uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46fa8b115dd01a9ee11442a0701cd719cc6d389e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394367"
---
# <a name="containers-implementing-a-container"></a>Kapsayıcılar: Bir Kapsayıcı Uygulama

Bu makalede, bir kapsayıcı uygulama yordamı özetler ve açıklamalar kapsayıcılar uygulama hakkında daha ayrıntılı sağlayan diğer makalelere gösterir. Ayrıca, uygulamak istediğiniz bazı isteğe bağlı OLE özellikleri ve bu özellikleri açıklayan makaleleri listeler.

#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp türetilmiş sınıfınızın hazırlamak için

1. Çağırarak OLE kitaplıklarını Başlat `AfxOleInit` içinde `InitInstance` üye işlevi.

1. Çağrı `CDocTemplate::SetContainerInfo` içinde `InitInstance` gömülü bir öğe olduğunda kullanılan kaynakları yerinde etkin menü ve Hızlandırıcı atamak için. Bu konu hakkında daha fazla bilgi için bkz. [etkinleştirme](../mfc/activation-cpp.md).

Bu özellikler, MFC Uygulama Sihirbazı kapsayıcılı bir uygulama oluşturmak için kullandığınızda sizin için otomatik olarak sağlanır. Bkz: [MFC EXE Program oluşturma](../mfc/reference/mfc-application-wizard.md).

#### <a name="to-prepare-your-view-class"></a>Görünüm sınıfınıza hazırlamak için

1. Seçilen öğeleri bir işaretçi tutarak izlemek veya listesinde seçilen öğeler için birden fazla seçimi destekler, işaretçiler. `OnDraw` İşlevi, tüm OLE öğelerini çizmek gerekir.

1. Geçersiz kılma `IsSelected` geçirilen öğe şu anda seçili olup olmadığını denetlemek için.

1. Uygulama bir `OnInsertObject` görüntülenecek ileti işleyicisi **Nesne Ekle** iletişim kutusu.

1. Uygulama bir `OnSetFocus` ileti işleyicisi odak görünümünden bir yerinde active OLE aktarmak için katıştırılmış öğesi.

1. Uygulama bir `OnSize` , kendi dikdörtgeni içeren görünümündeki boyutundaki değişikliği yansıtacak şekilde değiştirmek için gerekli bir OLE bildirmek için ileti işleyicisi öğesi katıştırılmış.

Uygulama bu özelliklerin bir uygulamadan diğerine önemli ölçüde değişir olduğundan, Uygulama Sihirbazı'nı yalnızca temel bir uygulamasını sağlar. Büyük olasılıkla uygulamanızı düzgün çalışması için bu işlevleri özelleştirmek gerekecektir. Bu örnek için bkz [KAPSAYICI](../visual-cpp-samples.md) örnek.

#### <a name="to-handle-embedded-and-linked-items"></a>Katıştırılmış ve bağlantılı öğeler işlemek için

1. Öğesinden bir sınıf türetin [Coleclientıtem](../mfc/reference/coleclientitem-class.md). Bu sınıfın nesneleri, gömülü veya bağlantılı OLE belgenize öğelerini temsil eder.

1. Geçersiz kılma `OnChange`, `OnChangeItemPosition`, ve `OnGetItemPosition`. Bu işlevler, katıştırılmış ve bağlantılı iş öğelerini değiştirme boyutlandırma ve konumlandırma işleyin.

Uygulama Sihirbazı'nı sizin için sınıf derleyeceği fakat geçersiz kılmak büyük olasılıkla gerekir `OnChange` ve diğer işlevler önceki yordamdaki 2. adımda birlikte listelenir. Bu işlevleri farklı bir uygulamadan diğerine uygulanır nedeniyle iskelet uygulamaları çoğu uygulama için özelleştirilmiş gerekir. Bu örnekler için bkz. MFC örnekleri [DRAWCLI](../visual-cpp-samples.md) ve [KAPSAYICI](../visual-cpp-samples.md).

OLE desteklemek için kapsayıcı uygulama menüsü yapısı birçok öğe eklemeniz gerekir. Bunlar hakkında daha fazla bilgi için bkz: [menüler ve kaynaklar: kapsayıcı ekleme](../mfc/menus-and-resources-container-additions.md).

Aşağıdaki özelliklerden bazıları kapsayıcı uygulamanızı desteklemek isteyebilirsiniz:

- Gömülü bir öğe düzenlenirken yerinde etkinleştirme.

     Daha fazla bilgi için [etkinleştirme](../mfc/activation-cpp.md).

- Bir sunucu uygulamasından bir seçim sürükleyip bırakarak oluşturma OLE öğeleri.

     Daha fazla bilgi için [sürükleme ve bırakma (OLE)](../mfc/drag-and-drop-ole.md).

- Katıştırılmış nesneler ya da birlikte kapsayıcı/sunucu uygulamaları bağlar.

     Daha fazla bilgi için [kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Kapsayıcılar: İstemci Öğeleri](../mfc/containers-client-items.md)

