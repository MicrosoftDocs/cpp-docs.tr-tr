---
title: "Kayıt kümesi: Kayıtları filtreleme (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b6d6e8b41e67c9f33d643a2f64c7bdf2d2251eff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-filtering-records-odbc"></a>Kayıt Kümesi: Kayıtları Filtreleme (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda, bir kayıt kümesi filtre, böylece yalnızca belirli bir alt kullanılabilir kayıtların seçer açıklanmaktadır. Örneğin, yalnızca MATH101 gibi belirli bir indirmelere sınıf bölümlerini seçmek isteyebilirsiniz. Bir SQL içeriğine göre tanımlanan bir arama koşulu filtredir **burada** yan tümcesi. İsteğe bağlı olarak framework kayıt kümenizin SQL deyimini ekler zaman **burada** yan tümcesi seçimi kısıtlar.  
  
 Bir kayıt kümesi nesnesinin filtresini nesneyi oluşturduktan sonra ancak çağırmadan önce oluşturmanız gerekir, **açık** üye işlevi (veya çağırmadan önce **Requery** var olan bir kayıt kümesi üye işlevi nesnesindeki **açık** üye işlevi önceden çağrıldıktan).  
  
#### <a name="to-specify-a-filter-for-a-recordset-object"></a>Kayıt kümesi nesnesi için bir filtre belirtmek için  
  
1.  Yeni bir kayıt kümesi nesnesi oluşturun (veya çağrı hazırlanma **Requery** var olan bir nesne için).  
  
2.  Nesnenin değerini [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesi.  
  
     SQL içeriğini içeren null ile sonlandırılmış bir dize filtredir **nerede** yan tümcesi ancak anahtar sözcüğünü içermeyen **burada**. Örneğin, kullanın:  
  
    ```  
    m_pSet->m_strFilter = "CourseID = 'MATH101'";  
    ```  
  
     not  
  
    ```  
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";  
    ```  
  
    > [!NOTE]
    >  Değişmez değer dize "MATH101" tek tırnak işaretiyle yukarıdaki gösterilir. ODBC SQL belirtiminde tek tırnak karakteri dize sabit değeri belirtmek için kullanılır. Bu durumda teklif gereksinimleri için ODBC sürücü belgelerinize bakın. Bu sözdiziminin da ele alınan bu konuda daha fazla çağrısına.  
  
3.  Sıralama düzeni, kilitleme modu veya parametreler gibi ihtiyacınız olan diğer seçenekleri ayarlayın. Parametre belirtmekle özellikle yararlıdır. Filtre kümesini parametreleştirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
4.  Çağrı **açık** yeni nesne için (veya **Requery** daha önce açılmış nesne için).  
  
> [!TIP]
>  İçinde filtre parametrelerini kullanarak olası kayıtları almak için en verimli yöntemdir.  
  
> [!TIP]
>  Kayıt kümesi filtreleri için yararlı [birleştirme](../../data/odbc/recordset-performing-a-join-odbc.md) tablolar ve kullanmak için [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) elde veya çalışma zamanında hesaplanan bilgilere dayanarak.  
  
 Kayıt kümesi, belirtilen arama koşulu karşılayan kayıtları seçer. Yukarıda indirmelere filtresi belirtmek için örneğin, açıklanan (bir değişken varsayılarak `strCourseID` , örneğin, "MATH101" ayarlanmış), aşağıdakileri yapın:  
  
```  
// Using the recordset pointed to by m_pSet  
  
// Set the filter  
m_pSet->m_strFilter = "CourseID = " + strCourseID;   
  
// Run the query with the filter in place  
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )  
  
// Use the recordset  
```  
  
 Kayıt kümesi MATH101 için tüm sınıf bölümleri kayıtlarını içerir.  
  
 Filtre dizesi bir dize değişkeni kullanarak yukarıdaki örnekte nasıl ayarlandığına dikkat edin. Bu tipik bir kullanımdır. Ancak indirmelere kimliği için değişmez değer olarak 100 belirtmek istediğinizi düşünün. Aşağıdaki kod, filtre dize değişmez değer ile düzgün şekilde ayarlamak gösterilmektedir:  
  
```  
m_strFilter = "StudentID = '100'";   // correct  
```  
  
 Tek tırnak karakteri kullanımına dikkat edin; filtre dizesi doğrudan ayarlamak için filtre dizesini varsa, **değil**:  
  
```  
m_strFilter = "StudentID = 100";   // incorrect for some drivers  
```  
  
 Yukarıda gösterilen tırnak içine alma ODBC belirtimine uygun, ancak bazı DBMS diğer tırnak karakterleri gerektirebilir. Daha fazla bilgi için bkz: [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
> [!NOTE]
>  Kendi SQL dizesi geçirerek kayıt kümesinin varsayılan SQL dizesi geçersiz kılmayı seçerseniz **açık**, özel dizenizi varsa, bir filtre ayarlamalısınız olmayan bir **burada** yan tümcesi. Varsayılan SQL geçersiz kılma hakkında daha fazla bilgi için bkz: [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)   
 [Kayıt kümesi: Nasıl kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [Kayıt kümesi: Kayıt kümeleri Güncelleştirmesi (ODBC) nasıl kaydeder.](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)