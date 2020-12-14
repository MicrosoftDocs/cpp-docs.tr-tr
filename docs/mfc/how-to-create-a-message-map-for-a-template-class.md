---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bir şablon sınıfı için Ileti eşlemesi oluşturma'
title: 'Nasıl yapılır: Bir Şablon Sınıfı için İleti Eşlemesi Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
ms.openlocfilehash: 16d1d486bae77d0e580521ba71d29216701c4481
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253435"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>Nasıl yapılır: Bir Şablon Sınıfı için İleti Eşlemesi Oluşturma

MFC 'de ileti eşleme, Windows iletilerini uygun bir C++ nesne örneğine yönlendirmek için etkili bir yol sağlar. MFC ileti eşleme hedefleri örnekleri uygulama sınıfları, belge ve Görünüm sınıfları, denetim sınıfları vb. içerir.

Geleneksel MFC ileti haritaları, ileti eşlemesinin başlangıcını, her ileti işleyici sınıfı yöntemi için bir makro girişini ve son olarak ileti eşlemesinin sonunu bildirmek üzere [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) makrosunu bildirmek için [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) makrosu kullanılarak bildirilmiştir.

[BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) makrolarıyla bir sınırlama, şablon bağımsız değişkenleri içeren bir sınıfla birlikte kullanıldığında oluşur. Bir şablon sınıfıyla birlikte kullanıldığında, makro genişletmesi sırasında eksik şablon parametreleri nedeniyle bu makro, derleme zamanı hatasına neden olur. [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) makrosu, tek bir şablon bağımsız değişkeni içeren sınıfların kendi ileti eşlemelerini bildirmesine olanak tanımak üzere tasarlanmıştır.

## <a name="example"></a>Örnek

MFC [Clienstbox](reference/clistbox-class.md) sınıfının bir dış veri kaynağıyla eşitleme sağlamak için genişletilmişse bir örnek düşünün. Kurgusal `CSyncListBox` sınıf şu şekilde bildirilmiştir:

[!code-cpp[NVC_MFC_CListBox#42](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]

`CSyncListBox`Sınıfı, eşitleyeceği veri kaynağını açıklayan tek bir tür üzerinde şablonlanır. Ayrıca, sınıfının ileti eşlemesine katılacak üç yöntem bildirir: `OnPaint` , `OnDestroy` , ve `OnSynchronize` . `OnSynchronize`Yöntemi aşağıdaki gibi uygulanır:

[!code-cpp[NVC_MFC_CListBox#43](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]

Yukarıdaki uygulama, sınıfının, `CSyncListBox` ve gibi yöntemini uygulayan herhangi bir sınıf türü üzerinde özelleştirilmiş olmasını sağlar `GetCount` `CArray` `CList` `CMap` . `StringizeElement`İşlevi, prototipte aşağıdaki tarafından yazılan bir şablon işlevidir:

[!code-cpp[NVC_MFC_CListBox#44](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]

Normalde, bu sınıf için ileti eşlemesi şöyle tanımlanır:

```cpp
BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)
  ON_WM_PAINT()
  ON_WM_DESTROY()
  ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)
END_MESSAGE_MAP()
```

Burada **LBN_SYNCHRONIZE** , uygulama tarafından tanımlanan özel bir Kullanıcı iletisidir; örneğin:

[!code-cpp[NVC_MFC_CListBox#45](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]

Yukarıdaki makro Haritası, sınıf için şablon belirtiminin `CSyncListBox` makro genişletmesi sırasında eksik olacağı için derlenmeyecektir. **BEGIN_TEMPLATE_MESSAGE_MAP** makro, belirtilen şablon parametresini genişletilmiş makro haritasına ekleyerek bunu çözer. Bu sınıf için ileti eşlemesi şu şekilde olur:

[!code-cpp[NVC_MFC_CListBox#46](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]

Aşağıda, `CSyncListBox` sınıfının bir nesnesi kullanılarak örnek kullanımı gösterilmektedir `CStringList` :

[!code-cpp[NVC_MFC_CListBox#47](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]

Testi gerçekleştirmek için, `StringizeElement` işlevin sınıfla çalışması için özelleştirilmiş olması gerekir `CStringList` :

[!code-cpp[NVC_MFC_CListBox#48](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)<br/>
[İleti Işleme ve eşleme](message-handling-and-mapping.md)
