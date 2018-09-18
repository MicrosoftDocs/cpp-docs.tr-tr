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
ms.openlocfilehash: 701e6f2912c3f9a8b5f138d8f188003f9db43021
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096150"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>Nasıl yapılır: Bir Şablon Sınıfı için İleti Eşlemesi Oluşturma
MFC ileti eşlemede uygun C++ nesne örneği Windows iletilerini yönlendirmek için etkili bir yol sağlar. MFC ileti Haritası hedefleri uygulama sınıfları, belge ve görünüm sınıfları, Denetim sınıfları ve benzeri örneklerindendir.  
  
 Geleneksel MFC ileti eşlemeleri kullanarak bildirilir [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) makrosu ileti eşlemesi, her bir ileti işleyicisi sınıfı yöntemi için bir makro girişi başlangıcı bildirmek için ve son olarak [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)makrosu ileti eşlemede sonuna bildirmek için.  
  
 Tek sınırlama ile [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) makrosu, şablon bağımsız değişkenleri içeren bir sınıf ile birlikte kullanıldığında oluşur. Bir şablon sınıfı ile kullanıldığında, bu makroyu Makro genişletme sırasında eksik şablon parametreleri nedeniyle bir derleme zamanı hatasına neden olur. [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) makrosu, kendi ileti bildirmek için tek bir şablon bağımsız değişken içeren sınıflar eşler izin vermek için tasarlanmıştır.  
  
## <a name="example"></a>Örnek  
 Bir örneği göz önünde bulundurun burada MFC [CListBox](../mfc/reference/clistbox-class.md) sınıfı, bir dış veri kaynağı ile eşitleme sağlamak için genişletilir. Kurgusal `CSyncListBox` sınıfı gibi bildirilir:  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 `CSyncListBox` İle eşitleneceğini veri kaynağını tanımlayan tek bir türe göre şablonlu sınıf. Ayrıca sınıfın ileti eşlemede katılacak olan üç yöntem bildirir: `OnPaint`, `OnDestroy`, ve `OnSynchronize`. `OnSynchronize` Yöntemi şu şekilde gerçekleştirilir:  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 Yukarıdaki uygulama sağlayan `CSyncListBox` uygulayan bir sınıf türü özel olarak sınıf `GetCount` yöntemi gibi `CArray`, `CList`, ve `CMap`. `StringizeElement` İşlev, aşağıdaki prototipli bir şablon işlevi:  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 Normalde, bu sınıf için mesaj haritasını olarak tanımlanması:  
  
```cpp
BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)
  ON_WM_PAINT()
  ON_WM_DESTROY()
  ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)
END_MESSAGE_MAP()
```
  
 Burada **LBN_SYNCHRONIZE** gibi uygulama tarafından tanımlanan bir özel kullanıcı iletisi:  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 Yukarıdaki makrosu harita derlemeyecektir, bunun nedeni, şablon belirtiminde `CSyncListBox` sınıfı eksik olacaktır makro genişletme sırasında. **BEGIN_TEMPLATE_MESSAGE_MAP** makrosu çözer bu genişletilmiş makrosu eşlemeye belirtilen şablon parametre ekleyerek. Bu sınıf için mesaj haritasını olur:  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 Aşağıdaki örnek kullanımını gösterir `CSyncListBox` kullanarak bir `CStringList` nesnesi:  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 Testin tamamlanması `StringizeElement` işlevi özelleştirilmiş, birlikte çalışmak için `CStringList` sınıfı:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)   
 [İleti İşleme ve Eşleme](../mfc/message-handling-and-mapping.md)

