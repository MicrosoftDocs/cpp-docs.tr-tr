---
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
ms.openlocfilehash: c3b4ecb38054748f36d75ca43e32d6447d3d2428
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299925"
---
# <a name="specifying-levels-of-functionality"></a>İşlevsellik Düzeylerini Belirtme

Bu makalede aşağıdaki işlevsellik düzeylerini eklemeyi açıklar, [CObject](../mfc/reference/cobject-class.md)-türetilmiş sınıf:

- Çalışma zamanı sınıf bilgileri

- Dinamik oluşturma desteği

- Serileştirme desteği

Genel bir açıklamasını `CObject` işlevselliği makaleye göz atın [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md).

## <a name="to-add-run-time-class-information"></a>Çalışma zamanı sınıf bilgileri eklemek için

1. Öğesinden, bir sınıf türetin `CObject`anlatılan şekilde [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md) makalesi.

1. DECLARE_DYNAMIC makrosu, burada gösterildiği gibi sınıfı bildiriminde kullanın:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. Implement_dynamıc makrosu uygulama dosyasında kullanın (. CPP) sınıfınızın. Bu makro bağımsız değişken olarak sınıfı ve temel sınıfın adını aşağıdaki gibi alır:

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
> Her zaman uygulama dosyasında ımplement_dynamıc yerleştirin (. CPP) sınıfınız için. Implement_dynamıc makrosu derleme sırasında yalnızca bir kez değerlendirilir ve bu nedenle bir arabirim dosyasında kullanılmamalıdır (. H), büyük olasılıkla birden fazla dosyasına dahil.

## <a name="to-add-dynamic-creation-support"></a>Dinamik oluşturma desteği eklemek için

1. Öğesinden, bir sınıf türetin `CObject`.

1. DECLARE_DYNCREATE makrosu, sınıf bildirimi içinde kullanın.

1. Bir oluşturucu bağımsız değişken olmadan (varsayılan bir oluşturucu) tanımlayın.

1. IMPLEMENT_DYNCREATE makrosu sınıf uygulama dosyasında kullanın.

## <a name="to-add-serialization-support"></a>Serileştirme desteği eklemek için

1. Öğesinden, bir sınıf türetin `CObject`.

1. Geçersiz kılma `Serialize` üye işlevi.

   > [!NOTE]
   > Eğer `Serialize` doğrudan diğer bir deyişle, istemediğiniz çok biçimli bir işaretçiyle nesneyi serileştirmek 3 ile 5 arasındaki adımları atlayın.

1. Declare_serıal makrosu, sınıf bildirimi içinde kullanın.

1. Bir oluşturucu bağımsız değişken olmadan (varsayılan bir oluşturucu) tanımlayın.

1. Implement_serıal makrosu sınıf uygulama dosyasında kullanın.

> [!NOTE]
> Bir sınıfın bir nesnesi için bir "çok biçimli işaretçinin" işaret (çağrısından A) veya bir (örneğin, B) türetilmiş sınıfın bir nesnesi. Çerçevesi çok biçimli bir işaretçi ile seri hale getirmek için bazı temel sınıftan (A) herhangi bir sınıfın bir nesnesi olabileceğinden, (B) serileştiren bir nesnenin çalışma zamanı sınıfının belirlemeniz gerekir.

Öğesinden, bir sınıf türetin olduğunda serileştirme etkinleştirme hakkında daha fazla ayrıntı için `CObject`, makalelere göz atın [MFC'deki dosyalar](../mfc/files-in-mfc.md) ve [serileştirme](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CObject'ten Sınıf Türetme](../mfc/deriving-a-class-from-cobject.md)
