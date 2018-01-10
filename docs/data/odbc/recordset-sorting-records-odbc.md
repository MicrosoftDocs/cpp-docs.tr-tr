---
title: "Kayıt kümesi: Kayıtları sıralama (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 846b3cfd4d5abe6d0eb76cfb12840f094564c926
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-sorting-records-odbc"></a>Kayıt Kümesi: Kayıtları Sıralama (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda, kümenizin sıralama açıklanmaktadır. Bir veya daha fazla sütun sıralama temel alacağı belirtebilirsiniz ve artan veya azalan belirtebilirsiniz (`ASC` veya **DESC**; `ASC` varsayılandır) belirtilen her sütun için. Örneğin, iki sütun belirtirseniz, kayıtları ilk adlı ilk sütun ve ardından adlı ikinci sütun sıralanır. Bir SQL **ORDER BY** yan tümcesinin sıralama tanımlar. Ne zaman framework ekler **ORDER BY** kayıt kümenizin SQL yan tümcesini sorgu, seçimini sıralama yan tümcesi denetimleri.  
  
 Bir kayıt kümesinin sıralama düzenini nesneyi oluşturduktan sonra ancak çağırmadan önce oluşturmanız gerekir, **açık** üye işlevi (veya çağırmadan önce **Requery** varolan bir kayıt kümesi nesnesi için üye işlevi **açık** üye işlevi önceden çağrıldıktan).  
  
#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Kayıt kümesi nesnesi için bir sıralama düzeni belirtmek için  
  
1.  Yeni bir kayıt kümesi nesnesi oluşturun (veya çağrı hazırlanma **Requery** mevcut bir için).  
  
2.  Nesnenin değerini [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesi.  
  
     Sıralama null ile sonlandırılmış bir dizedir. İçeriğini içeren **ORDER BY** yan tümcesi ancak anahtar sözcüğünü içermeyen **ORDER BY**. Örneğin, kullanın:  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  Bir filtre, kilitleme modu veya parametreler gibi ihtiyacınız olan diğer seçenekleri ayarlayın.  
  
4.  Çağrı **açık** yeni nesne için (veya **Requery** var olan bir nesne için).  
  
 Seçili kayıtları sıralı belirtildiği gibi. Örneğin, bir soyadı sonra ad göre azalan sırada Öğrenci kayıt kümesi sıralamak için aşağıdakileri yapın:  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 Kayıt kümesi (Z'den A'ya) azalan sırada son adıyla sonra ilk adına göre sıralanır Öğrenci kayıtların tümünü içerir.  
  
> [!NOTE]
>  Kendi SQL dizesi geçirerek kayıt kümesinin varsayılan SQL dizesi geçersiz kılmayı seçerseniz **açık**, özel dizenizi varsa bir sıralama ayarlı değil bir **ORDER BY** yan tümcesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)