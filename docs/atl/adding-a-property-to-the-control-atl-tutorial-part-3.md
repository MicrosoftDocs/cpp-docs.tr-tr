---
title: Denetime Özellik Ekleme (ATL Eğitmeni, Bölüm 3)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: b5f9f9c8fde44dd67a9a05aeae0f91fb7b5f2f4d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281024"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Denetime Özellik Ekleme (ATL Eğitmeni, Bölüm 3)

`IPolyCtl` Denetimin özel yöntemleri ve özellikleri içeren bir arabirimdir ve bir özellik ekleyeceksiniz.

### <a name="to-add-the-property-definitions-to-your-project"></a>Özellik tanımları projenize eklemek için

1. İçinde **sınıf görünümü**, genişletme `Polygon` dal.

1. Sağ `IPolyCtl`.

1. Kısayol menüsünde **Ekle**ve ardından **Özellik Ekle**. **Özellik Ekle** Sihirbazı görünür.

1. Tür `Sides` olarak **özellik adı**.

1. Aşağı açılan listesinde **özellik türü**seçin `short`.

1. Tıklayın **Tamam** özelliği ekleme işlemini sonlandırmak için.

1. Gelen **Çözüm Gezgini**Polygon.idl açma ve sonuna aşağıdaki satırları değiştirin `IPolyCtl : IDispatch` arabirimi:

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    örneklerini şununla değiştirin:

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. Gelen **Çözüm Gezgini**PolyCtl.h açın ve sonra tanımını aşağıdaki satırları ekleyin `m_clrFillColor`:

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

Özellik ve özelliği depolamak için bir değişken almak ve ayarlamak için iskelet işlevleri artık sahip olsa da işlevleri uygun şekilde uygulamalıdır.

### <a name="to-update-the-get-and-put-methods"></a>Güncelleştirme get ve put yöntemleri

1. Varsayılan değerini `m_nSides`. PolyCtl.h içindeki Oluşturucusu bir satır ekleyerek bir üçgen şekli varsayılan olun:

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. Uygulama `Get` ve `Put` yöntemleri. `get_Sides` Ve `put_Sides` işlev bildirimleri için PolyCtl.h eklenmiştir. Şimdi için kod ekleyin `get_Sides` ve `put_Sides` aşağıdaki PolyCtl.cpp için:

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

`get_Sides` Yöntemi geçerli değerini döndürür `Sides` özelliği aracılığıyla `pVal` işaretçi. İçinde `put_Sides` yöntem, kod sağlar kullanıcı ayarı `Sides` özelliğini kabul edilebilir bir değer. En az 3 olmalıdır ve bir dizi noktaları her bir kenar için kullanılacağından, maksimum değer için makul bir sınır 100'dür.

Artık adlı bir özelliğe sahip `Sides`. Sonraki adımda kullanmak için çizim kodunu değiştirir.

[2. adım dön](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [4. adım açın](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
