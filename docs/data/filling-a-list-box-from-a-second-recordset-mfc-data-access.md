---
title: "(MFC veri erişimi) ikinci kayıt kümesinden liste kutusunu doldurma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views, filling list boxes
- list boxes, filling from second recordset
- recordsets [C++], filling list boxes or combo boxes
- CComboBox class, filling object from second rowset
- ODBC recordsets [C++], filling list boxes or combo boxes
- combo boxes [C++], filling from second recordset
- CListCtrl class, filling from second recordset
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: de1282b80517a1c264121fbc0b749d3ca4ca2add
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="filling-a-list-box-from-a-second-recordset--mfc-data-access"></a>(MFC veri erişimi) ikinci kayıt kümesinden liste kutusunu doldurma
Varsayılan olarak, kayıt görünümü alanları kayıt görünümünün denetimleriyle eşleştirilen bir tek kayıt kümesi nesnesi ile ilişkilidir. Bazen bir liste kutusu koymak isteyebilirsiniz veya birleşik giriş kutusunu kayıt görünümünüzde denetlemek ve ikinci bir kayıt kümesi nesnesi değerlerle doldurun. Kullanıcı, kayıt görünümünde görüntülenecek bilgileri yeni bir kategori seçmek için liste kutusunu kullanabilirsiniz. Bu konuda nasıl ve ne zaman açıklanmaktadır Bunu yapmak için.  
  
> [!TIP]
>  Birleşik giriş kutusu veya bir veri kaynağı kümesinden liste kutusunu doldurma yavaş olabileceğini unutmayın. Çok sayıda kayıt kayıt kümesinden denetim doldurmaya çalışmaya karşı önlem.  
  
 Bu konu için model ikincil bir kayıt kümesi bir liste kutusu veya açılan kutu doldururken, formun denetimleri doldurur birincil bir kayıt kümesi içerir. Liste kutusundan bir dize belirlenmesi programınızın neyin seçili olduğuna bağlı olarak birincil kayıt kümesi requery neden olur. Aşağıdaki yordam bir birleşik giriş kutusu kullanır ancak bir liste kutusu için eşit oranda geçerlidir.  
  
#### <a name="to-fill-a-combo-box-or-list-box-from-a-second-recordset"></a>Birleşik giriş kutusu veya ikinci kayıt kümesinden liste kutusunu doldurmak için  
  
1.  Kayıt kümesi nesnesi oluşturma ([CRecordset](../mfc/reference/crecordset-class.md).  
  
2.  Bir işaretçi elde [CComboBox](../mfc/reference/ccombobox-class.md) birleşik giriş kutusu denetimi için nesnesi.  
  
3.  Önceki içerikleri birleşik giriş kutusu boş.  
  
4.  Kayıt kümesindeki tüm kayıtlar hareket çağırma [CComboBox::AddString](../mfc/reference/ccombobox-class.md#addstring) açılan kutu eklemek istediğiniz geçerli kayıttaki her dize.  
  
5.  Birleşik giriş kutusu seçim başlatır.  
  
```  
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
  
 Bu işlev kullanır ikinci bir kayıt `m_courseSet`, sunulan her ders için bir kayıt içerir ve bir `CComboBox` denetimi `m_ctlCourseList`, kayıt görünümü sınıfında depolanır.  
  
 İşlevi alır `m_courseSet` belgedeki ve açar. Bu sonra `m_ctlCourseList` ve ile birlikte kayar `m_courseSet`. Her kayıt için açılan kutunun işlevi çağırır `AddString` kaydından indirmelere kimliği değeri eklemek için üye işlevi. Son olarak, kod birleşik giriş kutusu seçimini ayarlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [ODBC sürücü listesi](../data/odbc/odbc-driver-list.md)