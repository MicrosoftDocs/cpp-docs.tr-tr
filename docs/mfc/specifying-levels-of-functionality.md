---
description: 'Hakkında daha fazla bilgi edinin: Işlev düzeylerini belirtme'
title: İşlevsellik Düzeylerini Belirtme
ms.date: 11/06/2018
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
ms.openlocfilehash: 1b016cd5a41d3e09790f678a2d49d88df33d9782
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216853"
---
# <a name="specifying-levels-of-functionality"></a>İşlevsellik Düzeylerini Belirtme

Bu makalede, [CObject](../mfc/reference/cobject-class.md)ile türetilmiş Sınıfınıza aşağıdaki işlev düzeylerinin nasıl ekleneceği açıklanmaktadır:

- Çalışma zamanı sınıf bilgileri

- Dinamik oluşturma desteği

- Serileştirme desteği

İşlevlerin genel bir açıklaması için `CObject` , [CObject 'Ten bir sınıf türeten](../mfc/deriving-a-class-from-cobject.md)makale bölümüne bakın.

## <a name="to-add-run-time-class-information"></a>Çalışma zamanı sınıf bilgileri eklemek için

1. `CObject`' Yi, [CObject 'Ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md) makalesindeki bölümünde açıklandığı gibi sınıfından türetebilirsiniz.

1. Sınıf bildirimindeki DECLARE_DYNAMIC makrosunu burada gösterildiği gibi kullanın:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. Uygulama dosyasında IMPLEMENT_DYNAMIC makrosunu kullanın (. CPP). Bu makro, aşağıdaki gibi, sınıfının ve temel sınıfının adını bağımsız değişken olarak alır:

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
> IMPLEMENT_DYNAMIC uygulama dosyasında her zaman Yerleştir (. CPP). IMPLEMENT_DYNAMIC makro, derleme sırasında yalnızca bir kez değerlendirilmeli ve bu nedenle bir arabirim dosyasında kullanılmamalıdır (. H) büyük olasılıkla birden fazla dosyaya eklenebilir.

## <a name="to-add-dynamic-creation-support"></a>Dinamik oluşturma desteği eklemek için

1. Sınıfınızı ' dan türet `CObject` .

1. Sınıf bildiriminde DECLARE_DYNCREATE makrosunu kullanın.

1. Bağımsız değişken içermeyen bir Oluşturucu tanımlayın (Varsayılan Oluşturucu).

1. Sınıf uygulama dosyasında IMPLEMENT_DYNCREATE makrosunu kullanın.

## <a name="to-add-serialization-support"></a>Serileştirme desteği eklemek için

1. Sınıfınızı ' dan türet `CObject` .

1. `Serialize`Üye işlevini geçersiz kılın.

   > [!NOTE]
   > Doğrudan çağrı yaparsanız, `Serialize` diğer bir deyişle, nesneyi polimorfik bir işaretçi aracılığıyla seri hale getirmek istemiyorsanız 3 ile 5 arasındaki adımları atlayın.

1. Sınıf bildiriminde DECLARE_SERIAL makrosunu kullanın.

1. Bağımsız değişken içermeyen bir Oluşturucu tanımlayın (Varsayılan Oluşturucu).

1. Sınıf uygulama dosyasında IMPLEMENT_SERIAL makrosunu kullanın.

> [!NOTE]
> "Polimorfik işaretçi" bir sınıfın bir nesnesine işaret eder (bunu çağırın) veya bir (deyin, B) sınıfından türetilmiş herhangi bir sınıfın nesnesine işaret eder. Polimorfik bir işaretçi aracılığıyla seri hale getirmek için Framework, bir temel sınıftan (A) türetilmiş herhangi bir sınıfın bir nesnesi olabileceğinden, serileştirmekte olduğu nesnenin çalışma zamanı sınıfını (B) belirlemelidir.

Sınıfınızı sınıfından türettiğinizde serileştirmenin nasıl etkinleştirileceği hakkında daha fazla bilgi için `CObject` MFC ve [serileştirme](../mfc/serialization-in-mfc.md)içindeki makaleler [dosyalarına](../mfc/files-in-mfc.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject 'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md)
