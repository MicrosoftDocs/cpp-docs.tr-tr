---
title: Özellik ekleme (ATL Eğitmeni, Bölüm 3) denetimine | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cbfb0b22579aceb5cbee196e3c5eda3079c9304
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848723"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Denetime Özellik Ekleme (ATL Eğitmeni, Bölüm 3)
`IPolyCtl` Denetimin özel yöntemleri ve özellikleri içeren bir arabirimdir ve bir özellik ekleyeceksiniz.  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bir özelliği eklemek için  
  
1.  Sınıf Görünümü'nde Çokgen dalını genişletin.  
  
2.  IPolyCtl sağ tıklayın.  
  
3.  Kısayol menüsünde **Ekle**ve ardından **Özellik Ekle**.  
  
     Özellik Ekleme Sihirbazı'nı görünür.  
  
4.  Özellik türü açılan listesinde seçin `SHORT`.  
  
5.  Tür *yüz* olarak **özellik adı.**  
  
6.  Tıklayın **son** özelliği ekleme işlemini sonlandırmak için.  
  
 Arabirimi özelliği eklediğinizde, MIDL (.idl dosyalarını derleme program) tanımlayan bir `Get` değerini almak için yöntem ve bir `Put` yöntemi yeni bir değer ayarlamak için. Eklenerek yöntemleri adlı `put_` ve `get_` özellik adı.  
  
 Özellik Ekleme Sihirbazı'nı gerekli satırları .idl dosyasına ekler. Ayrıca ekler `Get` ve `Put` işlev prototipleri PolyCtl.h içindeki sınıf tanımına ve PolyCtl.cpp için boş bir uygulama ekler. Bu PolyCtl.cpp açarak ve arama işlevleri için denetleyebilirsiniz `get_Sides` ve `put_Sides`.  
  
 Özelliği almak ve ayarlamak için iskelet işlevleri artık sahip, ancak bir yerde depolanması gerekir. İşlevleri güncellemenize özelliği depolamak için bir değişken oluşturur.  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>Depolama özelliği, put ve get yöntemleri bir değişken oluşturmak için  
  
1.  PolyCtl.h Çözüm Gezgini'nden açın ve sonra tanımını aşağıdaki satırı ekleyin `m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  Varsayılan değerini `m_nSides`. PolyCtl.h içindeki Oluşturucusu bir satır ekleyerek bir üçgen şekli varsayılan olun:  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  Uygulama `Get` ve `Put` yöntemleri. `get_Sides` Ve `put_Sides` işlev bildirimleri için PolyCtl.h eklenmiştir. PolyCtl.cpp için kodu değiştirin `get_Sides` ve `put_Sides` aşağıdaki kod ile:  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 `get_Sides` Yöntemi geçerli değerini döndürür `Sides` özelliği aracılığıyla `pVal` işaretçi. İçinde `put_Sides` yöntem, kod sağlar kullanıcı ayarı `Sides` özelliğini kabul edilebilir bir değer. En az 3 olmalıdır ve bir dizi noktaları her bir kenar için kullanılacağından, maksimum değer için makul bir sınır 100'dür.  
  
 Artık adlı bir özelliğe sahip `Sides`. Sonraki adımda kullanmak için çizim kodunu değiştirir.  
  
 [2. adım dön](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [4. adım açın](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici](../atl/active-template-library-atl-tutorial.md)

