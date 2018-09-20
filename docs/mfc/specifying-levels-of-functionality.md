---
title: İşlevsellik düzeylerini belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4b5ed392850fac97e8671774dee0905bf3417eb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375896"
---
# <a name="specifying-levels-of-functionality"></a>İşlevsellik Düzeylerini Belirtme

Bu makalede aşağıdaki işlevsellik düzeylerini eklemeyi açıklar, [CObject](../mfc/reference/cobject-class.md)-türetilmiş sınıf:

- [Çalışma zamanı sınıf bilgileri](#_core_to_add_run.2d.time_class_information)

- [Dinamik oluşturma desteği](#_core_to_add_dynamic_creation_support)

- [Serileştirme desteği](#_core_to_add_serialization_support)

Genel bir açıklamasını `CObject` işlevselliği makaleye göz atın [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md).

- [Çalışma zamanı sınıf bilgileri](#_core_to_add_run.2d.time_class_information)
#### <a name="_core_to_add_run.2d.time_class_information"></a> Çalışma zamanı sınıf bilgileri eklemek için

1. Öğesinden, bir sınıf türetin `CObject`anlatılan şekilde [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md) makalesi.

1. DECLARE_DYNAMIC makrosu, burada gösterildiği gibi sınıfı bildiriminde kullanın:

     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. Implement_dynamıc makrosu uygulama dosyasında kullanın (. CPP) sınıfınızın. Bu makro bağımsız değişken olarak sınıfı ve temel sınıfın adını aşağıdaki gibi alır:

     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
>  Her zaman uygulama dosyasında ımplement_dynamıc yerleştirin (. CPP) sınıfınız için. Implement_dynamıc makrosu derleme sırasında yalnızca bir kez değerlendirilir ve bu nedenle bir arabirim dosyasında kullanılmamalıdır (. H), büyük olasılıkla birden fazla dosyasına dahil.

#### <a name="_core_to_add_dynamic_creation_support"></a> Dinamik oluşturma desteği eklemek için

1. Öğesinden, bir sınıf türetin `CObject`.

1. DECLARE_DYNCREATE makrosu, sınıf bildirimi içinde kullanın.

1. Bir oluşturucu bağımsız değişken olmadan (varsayılan bir oluşturucu) tanımlayın.

1. IMPLEMENT_DYNCREATE makrosu sınıf uygulama dosyasında kullanın.

#### <a name="_core_to_add_serialization_support"></a> Serileştirme desteği eklemek için

1. Öğesinden, bir sınıf türetin `CObject`.

1. Geçersiz kılma `Serialize` üye işlevi.

    > [!NOTE]
    >  Eğer `Serialize` doğrudan diğer bir deyişle, istemediğiniz çok biçimli bir işaretçiyle nesneyi serileştirmek 3 ile 5 arasındaki adımları atlayın.

1. Declare_serıal makrosu, sınıf bildirimi içinde kullanın.

1. Bir oluşturucu bağımsız değişken olmadan (varsayılan bir oluşturucu) tanımlayın.

1. Implement_serıal makrosu sınıf uygulama dosyasında kullanın.

> [!NOTE]
>  Bir sınıfın bir nesnesi için bir "çok biçimli işaretçinin" işaret (çağrısından A) veya bir (örneğin, B) türetilmiş sınıfın bir nesnesi. Çerçevesi çok biçimli bir işaretçi ile seri hale getirmek için bazı temel sınıftan (A) herhangi bir sınıfın bir nesnesi olabileceğinden, (B) serileştiren bir nesnenin çalışma zamanı sınıfının belirlemeniz gerekir.

Öğesinden, bir sınıf türetin olduğunda serileştirme etkinleştirme hakkında daha fazla ayrıntı için `CObject`, makalelere göz atın [MFC'deki dosyalar](../mfc/files-in-mfc.md) ve [serileştirme](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CObject'ten Sınıf Türetme](../mfc/deriving-a-class-from-cobject.md)
