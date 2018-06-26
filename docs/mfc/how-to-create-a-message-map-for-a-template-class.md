---
title: 'Nasıl yapılır: bir şablon sınıfı için ileti eşlemesi oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7867cc40ae837da5fad957b6a1d584fb7c2c4ce
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929906"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>Nasıl yapılır: Bir Şablon Sınıfı için İleti Eşlemesi Oluşturma
İleti eşleme MFC'de uygun C++ nesne örneği Windows iletilerini yönlendirmek için etkili bir yol sağlar. MFC ileti eşlemesi hedefleri örnekleri uygulama sınıfları, belge ve görünüm sınıfları, Denetim sınıfları vb. içerir.  
  
 Geleneksel MFC ileti eşlemeleri kullanarak bildirildiğinde [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) makrosu girişi her bir ileti işleyicisi sınıfı yöntemi için ileti eşlemesi başlangıcı bildirmek için makrosu ve son olarak [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)makrosu ileti eşlemesi sonuna bildirin.  
  
 Bir sınırlama ile [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) makrosu bağımsız şablon içeren bir sınıf ile birlikte kullanıldığında oluşur. Bir şablon sınıfı ile kullanıldığında, bu makrosu makrosu genişletme sırasında bir derleme zamanı hatası nedeniyle eksik şablon parametreleri neden olur. [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) makrosu kendi ileti bildirmek için tek şablon bağımsız değişken içeren sınıfları eşleştirir izin verecek şekilde tasarlanmıştır.  
  
## <a name="example"></a>Örnek  
 Bir örneği göz önünde bulundurun burada MFC [CListBox](../mfc/reference/clistbox-class.md) sınıfı, bir dış veri kaynağı ile eşitleme sağlamak için genişletilir. Kurgusal `CSyncListBox` sınıfı şu şekilde bildirilen:  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 `CSyncListBox` Sınıfı ile eşitleyecek veri kaynağını tanımlayan tek bir türündeki şablonlu. Sınıfının ileti eşlemesi katılacak olan üç yöntem de bildirir: `OnPaint`, `OnDestroy`, ve `OnSynchronize`. `OnSynchronize` Yöntemi şu şekilde gerçekleştirilir:  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 Yukarıdaki uygulama verir `CSyncListBox` uygulayan bir sınıf türü özelleştirilmesi sınıfı `GetCount` yöntemi gibi `CArray`, `CList`, ve `CMap`. `StringizeElement` İşlevidir şunlarla örneklenmiş bir şablon işlevi:  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 Normalde, bu sınıfı için ileti eşlemesi olarak tanımlanması:  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 Burada **LBN_SYNCHRONIZE** gibi uygulama tarafından tanımlanan özel kullanıcı iletisi:  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 Yukarıdaki makrosu harita derlenmez, due için nedeni, şablon belirtimi için `CSyncListBox` sınıfı olacaktır eksik makrosu genişletme sırasında. **BEGIN_TEMPLATE_MESSAGE_MAP** makrosu çözdü bu genişletilmiş makrosu eşlemeye belirtilen şablon parametresi ekleyerek. Bu sınıf için ileti eşlemesi olur:  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 Aşağıdaki örnek kullanımını gösteren `CSyncListBox` kullanarak sınıfı bir `CStringList` nesnesi:  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 Sınama işlemini tamamlamak için `StringizeElement` işlevi özelleştirilmiş, çalışmak için `CStringList` sınıfı:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)   
 [İleti İşleme ve Eşleme](../mfc/message-handling-and-mapping.md)

