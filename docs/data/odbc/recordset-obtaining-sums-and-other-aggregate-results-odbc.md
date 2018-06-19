---
title: "Kayıt kümesi: SUM'ları ve diğer toplama sonuçlarını (ODBC) alma | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4aa6de58e7e2c530a7a353281ba5af747f48cd4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092079"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda aşağıdaki kullanarak toplama sonuçları elde etmek açıklanmaktadır [SQL](../../data/odbc/sql.md) anahtar sözcükler:  
  
-   **SUM** sayısal veri türüne sahip bir sütundaki değerlerin toplamını hesaplar.  
  
-   **MIN** sayısal veri türüne sahip bir sütundaki en küçük değeri ayıklar.  
  
-   **MAX** sayısal veri türüne sahip bir sütundaki en büyük değeri ayıklar.  
  
-   **Ortalama** sayısal veri türüne sahip bir sütundaki tüm değerlerin ortalama bir değer hesaplar.  
  
-   **COUNT** herhangi bir veri türü sütununun kayıtlarının sayısını sayar.  
  
 Bu SQL işlevlerini veri kaynağındaki kayıtlar hakkında istatistiksel bilgiler edinmek için yerine veri kaynağından kayıtları ayıklamak için kullanın. Bir tek genellikle oluşturulan kayıt kümesi oluşur (tüm sütunları toplamalar varsa) kaydı, bir değer içeriyor. (Kullandıysanız birden fazla kayıt olabilir bir **GROUP BY** yan tümcesi.) Bu değer hesaplama veya SQL işlevi tarafından gerçekleştirilen ayıklama sonucudur.  
  
> [!TIP]
>  Bir SQL eklemek için **GROUP BY** yan tümcesi (ve muhtemelen bir **HAVING** yan tümcesi) SQL deyimine, onu sonuna **m_strFilter**. Örneğin:  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
 Sütunları sıralama ve filtreleme ile toplama sonuçları elde etmek için kullandığınız kayıtların sayısını sınırlayabilirsiniz.  
  
> [!CAUTION]
>  Bazı toplama işleçleri, farklı bir veri türü üzerinde bunlar topluyorsanız sütunlarından döndür.  
  
-   **SUM** ve **AVG** sonraki daha büyük veri türüne döndürebilir (örneğin, ile arama `int` döndürür **uzun** veya **çift**).  
  
-   **COUNT** genellikle döndürür **uzun** hedef sütun türü ne olursa olsun.  
  
-   **MAX** ve **MIN** hesaplanacak sütunlar aynı veri türünde döndürür.  
  
     Örneğin, **sınıfı Ekle** sihirbaz `long` `m_lSales` bunu değiştirmek bir satış sütunu, ancak uyum sağlaması gerekmektedir bir `double m_dblSumSales` toplam sonucu barındırmak için veri üyesi. Aşağıdaki örnekte bakın.  
  
#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>Bir kayıt kümesi için birleşik bir sonuç almak için  
  
1.  Bölümünde açıklandığı gibi bir kayıt kümesi oluşturma [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md) toplama sonuçları elde etmek istediğiniz sütunları içeren.  
  
2.  Değiştirme [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) kayıt kümesi için işlevi. Sütun adını temsil eden dize değiştirin (ikinci bağımsız değişkeni [RFX](../../data/odbc/record-field-exchange-using-rfx.md) işlev çağrıları) ile sütun toplama işlevini temsil eden bir dize. Örneğin, değiştirin:  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     İle:  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
3.  Kayıt kümesi'ni açın. Toplama işleminin sonucu left içinde `m_dblSumSales`.  
  
> [!NOTE]
>  Sihirbaz, aslında veri üye adlarını Macarca önekleri olmadan atar. Örneğin, sihirbaz msgıd `m_Sales` bir satış sütunu için yerine `m_lSales` önceki çizim için kullanılan ad.  
  
 Kullanıyorsanız bir [CRecordView](../../mfc/reference/crecordview-class.md) verileri görüntülemek için sınıf, yeni veri üyesi değerini; görüntülemek için DDX işlev çağrısı değiştirmek zorunda bu durumda, ondan değiştirme:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
 Hedef:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)