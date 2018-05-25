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
ms.openlocfilehash: fda9359da6ddc48248874227d58f0c184af45c54
ms.sourcegitcommit: 9b442b44ee912822d06cabec826aac4a8d82ec75
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Denetime Özellik Ekleme (ATL Eğitmeni, Bölüm 3)
`IPolyCtl` Denetimin özel yöntemleri ve özellikleri içeren arabirimi, ve bir özellik ekleyeceksiniz.  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bir özelliği eklemek için  
  
1.  Sınıf Görünümü'nde Çokgen dalını genişletin.  
  
2.  IPolyCtl sağ tıklayın.  
  
3.  Kısayol menüsünde **Ekle**ve ardından **Özellik Ekle**.  
  
     Özellik Ekleme Sihirbazı'nı görünür.  
  
4.  Özellik türleri aşağı açılan listesinde seçin `SHORT`.  
  
5.  Tür `Sides` olarak **özellik adı.**  
  
6.  Tıklatın **son** özellik ekleme işlemini sonlandırmak için.  
  
 Arabirimine özelliği eklediğinizde MIDL (.idl dosyalarını derler programı) tanımlayan bir `Get` değerini almak için yöntemi ve `Put` yeni bir değer ayarlamak için yöntemi. Eklenerek yöntemleri adlı `put_` ve `get_` özellik adı.  
  
 Özellik Ekleme Sihirbazı'nı gerekli satırları .idl dosyasına ekler. Ayrıca ekler `Get` ve `Put` işlev prototipleri PolyCtl.h sınıf tanımına ve PolyCtl.cpp için boş bir uygulama ekler. Bu PolyCtl.cpp açarak ve işlevleri için arayarak denetleyebilirsiniz `get_Sides` ve `put_Sides`.  
  
 Şimdi ayarlamak ve özellik almak için iskelet işlevleri sahip olsa da depolanması için bir yer gerekir. Özellik depolamak ve işlevleri uygun şekilde güncelleştirmek için bir değişken oluşturur.  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>Özellik depolamak ve put güncelleştirmek ve yöntemleri almak için bir değişken oluşturmak için  
  
1.  PolyCtl.h Çözüm Gezgini'nden açın ve sonra tanımını aşağıdaki satırı ekleyin `m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  Varsayılan değer olarak ayarlanmış `m_nSides`. Bir satır PolyCtl.h oluşturucuda ekleyerek bir üçgen şekil varsayılan yap:  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  Uygulama `Get` ve `Put` yöntemleri. `get_Sides` Ve `put_Sides` işlev bildirimleri PolyCtl.h için eklenmiştir. İçin PolyCtl.cpp kodla `get_Sides` ve `put_Sides` aşağıdaki kod ile:  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 `get_Sides` Yöntemi döndürür geçerli değeri `Sides` özelliği üzerinden `pVal` işaretçi. İçinde `put_Sides` yöntemi, kodu sağlar kullanıcı ayarı `Sides` özelliği için geçerli bir değer. En az 3 olmalıdır ve noktalar dizisi için her iki yanına kullanılacağından makul bir sınır için bir maksimum değer 100'dür.  
  
 Şimdi adlı bir özellik olan `Sides`. Sonraki adımda kullanmak için çizim kodunu değiştirir.  
  
 [2. adım dön](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [adıma 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici](../atl/active-template-library-atl-tutorial.md)

