---
title: Denetime Özellik Ekleme (ATL Eğitmeni, Bölüm 3)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: 288dc9f5af57c02639d15a9a971419a633cfc08d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127593"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Denetime Özellik Ekleme (ATL Eğitmeni, Bölüm 3)

`IPolyCtl`, denetimin özel yöntemlerini ve özelliklerini içeren arabirimdir ve buna bir özellik eklersiniz.

### <a name="to-add-the-property-definitions-to-your-project"></a>Projenize özellik tanımlarını eklemek için

1. **Sınıf görünümü**, `Polygon` dalını genişletin.

1. `IPolyCtl`öğesine sağ tıklayın.

1. Kısayol menüsünde, **Ekle**' ye ve ardından **Özellik Ekle**' ye tıklayın. **Özellik ekleme** Sihirbazı görünür.

1. **Özellik adı**olarak `Sides` yazın.

1. **Özellik türünün**aşağı açılan listesinde `short`' yi seçin.

1. Özelliği eklemeyi bitirmeden **Tamam** ' ı tıklatın.

1. **Çözüm Gezgini**, Çokgen. IDL açın ve `IPolyCtl : IDispatch` arabiriminin sonundaki aşağıdaki satırları değiştirin:

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    örneklerini şununla değiştirin:

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. **Çözüm Gezgini**, PolyCtl. h ' yi açın ve `m_clrFillColor`tanımından sonra aşağıdaki satırları ekleyin:

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

Artık özelliği ve özelliği depolayacak bir değişkeni ayarlamak ve almak için iskelet işlevleriniz olsa da, işlevleri uygun şekilde uygulamalısınız.

### <a name="to-update-the-get-and-put-methods"></a>Get ve put yöntemlerini güncelleştirmek için

1. `m_nSides`varsayılan değerini ayarlayın. PolyCtl. h içindeki oluşturucuya bir çizgi ekleyerek varsayılan şekli bir üçgen yapın:

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. `Get` ve `Put` yöntemlerini uygulayın. `get_Sides` ve `put_Sides` işlev bildirimleri PolyCtl. h 'ye eklenmiştir. Artık `get_Sides` ve `put_Sides` kodunu şu şekilde PolyCtl. cpp öğesine ekleyin:

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

`get_Sides` yöntemi `pVal` işaretçisi aracılığıyla `Sides` özelliğinin geçerli değerini döndürür. `put_Sides` yönteminde, kod kullanıcının `Sides` özelliğini kabul edilebilir bir değere ayarlamamasını sağlar. En az 3 olmalıdır ve her bir kenar için bir punto dizisi kullanılacak, 100 en büyük bir değer için makul bir sınır olur.

Artık `Sides`adlı bir özelliğe sahipsiniz. Sonraki adımda, kullanılacak çizim kodunu değiştirirsiniz.

Adım &#124; [4 ' te](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) [Adım 2 ' ye dönün](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
