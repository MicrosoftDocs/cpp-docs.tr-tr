---
description: 'Daha fazla bilgi edinin: Ikinci bir kayıt kümesinden liste kutusu doldurma (MFC veri erişimi)'
title: Ikinci bir kayıt kümesinden liste kutusu doldurma (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, filling list boxes
- list boxes, filling from second recordset
- recordsets [C++], filling list boxes or combo boxes
- CComboBox class, filling object from second rowset
- ODBC recordsets [C++], filling list boxes or combo boxes
- combo boxes [C++], filling from second recordset
- CListCtrl class, filling from second recordset
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
ms.openlocfilehash: b912511512b42e15e98a35836758ba37bf4cb989
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170912"
---
# <a name="filling-a-list-box-from-a-second-recordset--mfc-data-access"></a>Ikinci bir kayıt kümesinden liste kutusu doldurma (MFC veri erişimi)

Varsayılan olarak, bir kayıt görünümü, alanları kayıt görünümü denetimleriyle eşlenen tek bir kayıt kümesi nesnesi ile ilişkilendirilir. Bazen, kayıt görünümünüzde bir liste kutusu veya Birleşik giriş kutusu denetimi koymak ve ikinci bir kayıt kümesi nesnesinden değerler ile doldurmanız gerekebilir. Kullanıcı, kayıt görünümünde görüntülenecek yeni bir bilgi kategorisi seçmek için liste kutusunu kullanabilir. Bu konu, bunun nasıl ve ne zaman yapılacağını açıklamaktadır.

> [!TIP]
> Bir Birleşik giriş kutusu veya liste kutusunun bir veri kaynağından doldurulması yavaş olabilir. Çok sayıda kayıt içeren bir kayıt kümesinden denetimi doldurmaya çalışırken önlem alın.

Bu konunun modeli, formunuzun denetimlerini dolduran birincil bir kayıt kümesinden oluşur, ancak ikincil bir kayıt kümesi bir liste kutusu veya Birleşik giriş kutusunu doldurur. Liste kutusundan bir dize seçilmesi, programınızın seçili olan öğeleri temel alarak birincil kayıt kümesini yeniden sorgulamasına neden olur. Aşağıdaki yordam bir açılan kutu kullanır, ancak bir liste kutusuna eşit olarak uygulanır.

#### <a name="to-fill-a-combo-box-or-list-box-from-a-second-recordset"></a>İkinci bir kayıt kümesinden açılan bir kutuyu veya liste kutusunu dolduracak şekilde

1. Kayıt kümesi nesnesini oluşturun ([CRecordset](../mfc/reference/crecordset-class.md).

1. Birleşik giriş kutusu denetimi için [CComboBox](../mfc/reference/ccombobox-class.md) nesnesine bir işaretçi alın.

1. Önceki içeriklerin Birleşik giriş kutusunu boşaltın.

1. Birleşik giriş kutusuna eklemek istediğiniz geçerli kayıttaki her bir dize için [CComboBox:: AddString](../mfc/reference/ccombobox-class.md#addstring) ' i çağırarak, kayıt kümesindeki tüm kayıtlar arasında geçiş yapın.

1. Açılan kutuda seçimi başlatın.

```cpp
void CSectionForm::OnInitialUpdate()
{
    // ...

    // Fill the combo box with all of the courses
    CENROLLDoc* pDoc = GetDocument();
    if (!pDoc->m_courseSet.Open())
        return;

    // ...

    m_ctlCourseList.ResetContent();
    if (pDoc->m_courseSet.IsOpen())
    {
        while (!pDoc->m_courseSet.IsEOF() )
        {
            m_ctlCourseList.AddString(
                pDoc->m_courseSet.m_CourseID);
            pDoc->m_courseSet.MoveNext();
        }
    }
    m_ctlCourseList.SetCurSel(0);
}
```

Bu işlev, `m_courseSet` sunulan her kurs için bir kayıt içeren ikinci bir kayıt kümesi ve `CComboBox` `m_ctlCourseList` kayıt görünümü sınıfında depolanan bir denetim kullanır.

İşlev belgeden alınır `m_courseSet` ve açar. Sonra yeniden boşaltır `m_ctlCourseList` ve kaydırın `m_courseSet` . Her kayıt için işlev, `AddString` kayıttaki kurs kimliği değerini eklemek için Birleşik giriş kutusunun üye işlevini çağırır. Son olarak, kod Birleşik giriş kutusunun seçimini ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC sürücü listesi](../data/odbc/odbc-driver-list.md)
