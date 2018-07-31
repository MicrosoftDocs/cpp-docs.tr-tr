---
title: (MFC veri erişimi) ikinci kayıt kümesinden liste kutusunu doldurma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, filling list boxes
- list boxes, filling from second recordset
- recordsets [C++], filling list boxes or combo boxes
- CComboBox class, filling object from second rowset
- ODBC recordsets [C++], filling list boxes or combo boxes
- combo boxes [C++], filling from second recordset
- CListCtrl class, filling from second recordset
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e980f42384052e0ab4fbd0f98889509c41accf0b
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339776"
---
# <a name="filling-a-list-box-from-a-second-recordset--mfc-data-access"></a>(MFC veri erişimi) ikinci kayıt kümesinden liste kutusunu doldurma
Varsayılan olarak, kayıt görünümü alanları kayıt görünümünün denetimlere eşlenmiş bir tek bir kayıt kümesi nesnesi ile ilişkilidir. Bazen, bir liste kutusu koymak isteyebilirsiniz veya birleşik giriş kutusu kayıt görünümünüzde denetlemek ve ikinci bir kayıt kümesi nesnesi değerlerle doldurun. Kullanıcı, kaydı görüntülemek için bilgileri yeni bir kategori seçmek için liste kutusunu kullanabilirsiniz. Bu konu nasıl ve ne zaman açıklar. Bunu yapmak için.  
  
> [!TIP]
>  Birleşik giriş kutusu veya bir veri kaynağı kümesinden liste kutusunu doldurma yavaş olabileceğini unutmayın. Çok sayıda kayıt kayıt kümesinden bir denetimi doldurmak çalışırken karşı önlem alın.  
  
 Bu konu için bir model, form denetimlerini ikincil bir kayıt kümesini bir liste kutusu veya açılan kutu doldururken dolduran birincil bir kayıt kümesi içerir. Liste kutusundan bir dize seçerek programınızı ne seçili olduğuna bağlı birincil bir kayıt sorgulayacak neden olur. Aşağıdaki yordam bir birleşik giriş kutusu kullanır, ancak liste kutusu için eşit oranda geçerlidir.  
  
#### <a name="to-fill-a-combo-box-or-list-box-from-a-second-recordset"></a>Birleşik giriş kutusu ya da ikinci kayıt kümesinden liste kutusunu doldurmak için  
  
1.  Kayıt kümesi nesnesi oluşturun ([CRecordset](../mfc/reference/crecordset-class.md).  
  
2.  Bir işaretçi alma [CComboBox](../mfc/reference/ccombobox-class.md) birleşik giriş kutusu denetimi için nesne.  
  
3.  Önceki tüm İçindekiler birleşik giriş kutusu boş.  
  
4.  Kayıt kümesindeki tüm kayıtlar arasında taşıma çağırma [CComboBox::AddString](../mfc/reference/ccombobox-class.md#addstring) geçerli kayıttan birleşik giriş kutusuna eklemek istediğiniz her bir dizenin için.  
  
5.  Seçimi birleşik giriş kutusundaki başlatın.  
  
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
  
 Bu işlev, ikinci kayıt kullanır `m_courseSet`, sunulan her ders için kayıt içeren ve bir `CComboBox` denetimi `m_ctlCourseList`, kayıt görünümü sınıfta depolanır.  
  
 İşlev alır `m_courseSet` belgeden ve onu açar. Bu ardından `m_ctlCourseList` ve aracılığıyla kaydırır `m_courseSet`. Her kayıt için açılan kutunun işlev çağrıları `AddString` kayıttan kurs kimliği değeri eklemek için üye işlevi. Son olarak, kod birleşik giriş kutusunun seçimi ayarlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)