---
title: İkinci Kayıt Kümesinden Liste Kutusu Doldurma (MFC Veri Erişimi)
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
ms.openlocfilehash: 8664e98c6668568918cc0e6504a38119d2e71428
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336920"
---
# <a name="filling-a-list-box-from-a-second-recordset--mfc-data-access"></a>İkinci Kayıt Kümesinden Liste Kutusu Doldurma (MFC Veri Erişimi)

Varsayılan olarak, bir kayıt görünümü, alanları kayıt görünümü denetimlerine eşlenen tek bir kayıt kümesi nesnesiyle ilişkilidir. Bazen kayıt görünümünüze bir liste kutusu veya açılan kutu denetimi koymak ve ikinci bir kayıt kümesi nesnesi değerleri ile doldurmak isteyebilirsiniz. Kullanıcı, kayıt görünümünde görüntülenecek yeni bir bilgi kategorisi seçmek için liste kutusunu kullanabilir. Bu konu, bunun nasıl ve ne zaman yapılacağını açıklar.

> [!TIP]
> Bir açılan kutuyu veya liste kutusunu bir veri kaynağından doldurmanın yavaş olabileceğini unutmayın. Çok sayıda kayıt kümesinden denetimi doldurmaya çalışmaktan karşı önlem alın.

Bu konunun modeli, formunuzun denetimlerini dolduran birincil bir kayıt kümesinden oluşurken, ikincil bir kayıt kümesi bir liste kutusunu veya açılan kutuyu doldurur. Liste kutusundan bir dize seçmek, programınızın seçili olana göre birincil kayıt kümesini yeniden sorgulamasına neden olur. Aşağıdaki yordam bir açılan kutu kullanır, ancak bir liste kutusuna eşit olarak uygulanır.

#### <a name="to-fill-a-combo-box-or-list-box-from-a-second-recordset"></a>İkinci bir kayıt kümesinden açılan kutuyu veya liste kutusunu doldurmak için

1. Kayıt kümesi nesnesini oluşturma ([CRecordset](../mfc/reference/crecordset-class.md).

1. Açılan kutu denetimi için [CComboBox](../mfc/reference/ccombobox-class.md) nesnesine bir işaretçi edinin.

1. Önceki içeriklerin açılan kutusunu boşaltın.

1. Kayıt kümesindeki tüm kayıtlarda [ccomboBox'u](../mfc/reference/ccombobox-class.md#addstring) arayarak taşıyın::Açılan kutuya eklemek istediğiniz geçerli kayıttan her dize için AddString.

1. Seçimi açılan kutuda başlatma.

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

Bu işlev, `m_courseSet`sunulan her kurs için bir kayıt ve kayıt `CComboBox` görünümü `m_ctlCourseList`sınıfında depolanan bir denetim içeren ikinci bir kayıt kümesi kullanır.

İşlev `m_courseSet` belgeden alır ve açar. Sonra boşlar `m_ctlCourseList` ve içinden `m_courseSet`geçer. Her kayıt için işlev, kayıttan ders `AddString` kimliği değerini eklemek için açılan kutunun üye işlevini çağırır. Son olarak, kod açılan kutunun seçimini ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Görünümleri (MFC Veri Erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)
