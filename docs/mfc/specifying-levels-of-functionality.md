---
title: "İşlevsellik düzeylerini belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13a2897d5e442794198870e7f6bed36196744888
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-levels-of-functionality"></a>İşlevsellik Düzeylerini Belirtme
Bu makalede aşağıdaki işlevsellik düzeylerini eklemeyi açıklar, [CObject](../mfc/reference/cobject-class.md)-türetilmiş sınıf:  
  
-   [Çalışma zamanı sınıf bilgileri](#_core_to_add_run.2d.time_class_information)  
  
-   [Dinamik oluşturma desteği](#_core_to_add_dynamic_creation_support)  
  
-   [Serileştirme desteği](#_core_to_add_serialization_support)  
  
 Genel bir açıklaması için `CObject` işlevselliği makalesine bakın [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md).  
  
-   [Çalışma zamanı sınıf bilgileri](#_core_to_add_run.2d.time_class_information)  
#### <a name="_core_to_add_run.2d.time_class_information"></a>Çalışma zamanı sınıf bilgileri eklemek için  
  
1.  Sınıfından türetilen `CObject`açıklandığı gibi [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md) makalesi.  
  
2.  Kullanım `DECLARE_DYNAMIC` aşağıda gösterildiği gibi sınıf bildirimindeki makrosu:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]  
  
3.  Kullanım `IMPLEMENT_DYNAMIC` uygulama dosyasında makrosu (. CPP) sınıfınızın. Bu makrosu bağımsız değişken olarak sınıfı ve temel sınıfın adını şu şekilde yapar:  
  
     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]  
  
> [!NOTE]
>  Her zaman put `IMPLEMENT_DYNAMIC` uygulama dosyasında (. CPP) sınıfınız için. `IMPLEMENT_DYNAMIC` Makrosu derleme sırasında yalnızca bir kez değerlendirilmesi ve bu nedenle bir arabirim dosyasında kullanılmamalıdır (. H), büyük olasılıkla birden fazla dosyasına dahil.  
  
#### <a name="_core_to_add_dynamic_creation_support"></a>Dinamik oluşturma desteği eklemek için  
  
1.  Sınıfından türetilen `CObject`.  
  
2.  Kullanım `DECLARE_DYNCREATE` makrosu sınıf bildirimindeki.  
  
3.  Bağımsız değişkenler (varsayılan bir oluşturucu) bir oluşturucu tanımlar.  
  
4.  Kullanım `IMPLEMENT_DYNCREATE` sınıfı uygulama dosyasındaki makro.  
  
#### <a name="_core_to_add_serialization_support"></a>Seri hale getirme desteği eklemek için  
  
1.  Sınıfından türetilen `CObject`.  
  
2.  Geçersiz kılma `Serialize` üye işlevi.  
  
    > [!NOTE]
    >  Çağırırsanız `Serialize` doğrudan, diğer bir deyişle, istemediğiniz biçimli işaretçi üzerinden nesneyi serileştirmek 3 ile 5 arasındaki adımları atlayın.  
  
3.  Kullanım `DECLARE_SERIAL` makrosu sınıf bildirimindeki.  
  
4.  Bağımsız değişkenler (varsayılan bir oluşturucu) bir oluşturucu tanımlar.  
  
5.  Kullanım `IMPLEMENT_SERIAL` sınıfı uygulama dosyasındaki makro.  
  
> [!NOTE]
>  Bir sınıfın bir nesnesi için "Çok biçimli işaretçinin" işaret (çağrısından A) veya bir (say, B) türetilmiş herhangi bir sınıfın bir nesnesi. Çok biçimli bir işaretçi serileştirmek için framework çalışma zamanı sınıf bazı temel sınıfından (A) türetilen sınıfın bir nesnesi olabileceğinden, (B) serileştiren nesnesinin belirlemeniz gerekir.  
  
 Seri hale getirme, sınıfından türetilen zaman etkinleştirme hakkında daha fazla ayrıntı için `CObject`, makalelerine bakın [MFC'deki dosyalar](../mfc/files-in-mfc.md) ve [seri hale getirme](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject'ten Sınıf Türetme](../mfc/deriving-a-class-from-cobject.md)
