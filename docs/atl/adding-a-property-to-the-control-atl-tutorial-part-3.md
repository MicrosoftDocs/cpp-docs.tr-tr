---
title: Denetime Özellik Ekleme (ATL Eğitmeni, Bölüm 3)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: c5f71880f780e793cd77eb5a7571d31de4a8d01a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219007"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Denetime Özellik Ekleme (ATL Eğitmeni, Bölüm 3)

`IPolyCtl`, denetimin özel yöntemlerini ve özelliklerini içeren arabirimdir ve buna bir özellik eklersiniz.

### <a name="to-add-the-property-definitions-to-your-project"></a>Projenize özellik tanımlarını eklemek için

1. **Sınıf görünümü**dal ' ı genişletin `Polygon` .

1. Sağ tıklayın `IPolyCtl` .

1. Kısayol menüsünde, **Ekle**' ye ve ardından **Özellik Ekle**' ye tıklayın. **Özellik ekleme** Sihirbazı görünür.

1. `Sides` **Özellik adı**olarak yazın.

1. **Özellik türünün**açılan listesinde, öğesini seçin **`short`** .

1. Özelliği eklemeyi bitirmeden **Tamam** ' ı tıklatın.

1. **Çözüm Gezgini**, Çokgen. IDL açın ve arabirimin sonundaki aşağıdaki satırları değiştirin `IPolyCtl : IDispatch` :

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    örneklerini şununla değiştirin:

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. **Çözüm Gezgini**, PolyCtl. h ' yi açın ve tanımından sonra aşağıdaki satırları ekleyin `m_clrFillColor` :

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

Artık özelliği ve özelliği depolayacak bir değişkeni ayarlamak ve almak için iskelet işlevleriniz olsa da, işlevleri uygun şekilde uygulamalısınız.

### <a name="to-update-the-get-and-put-methods"></a>Get ve put yöntemlerini güncelleştirmek için

1. Varsayılan değerini ayarlayın `m_nSides` . PolyCtl. h içindeki oluşturucuya bir çizgi ekleyerek varsayılan şekli bir üçgen yapın:

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. `Get`Ve yöntemlerini uygulayın `Put` . `get_Sides`Ve `put_Sides` Işlev bildirimleri PolyCtl. h 'ye eklenmiştir. Şimdi, ve için kodu `get_Sides` `put_Sides` Şu şekilde PolyCtl. cpp öğesine ekleyin:

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

`get_Sides`Yöntemi, `Sides` işaretçi aracılığıyla özelliğin geçerli değerini döndürür `pVal` . `put_Sides`Yönteminde, kod kullanıcının `Sides` özelliği kabul edilebilir bir değere ayarlamamasını sağlar. En az 3 olmalıdır ve her bir kenar için bir punto dizisi kullanılacak, 100 en büyük bir değer için makul bir sınır olur.

Artık adlı bir özellik var `Sides` . Sonraki adımda, kullanılacak çizim kodunu değiştirirsiniz.

Adım 2 ' ye [geri döndüğünüzde](../atl/adding-a-control-atl-tutorial-part-2.md) [4. adım](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124;

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
