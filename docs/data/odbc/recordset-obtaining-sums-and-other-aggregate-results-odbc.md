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
ms.openlocfilehash: 639c5fb2df443de7e2eee963f942c9154dc4de6e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50058056"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konu başlığında, aşağıdaki kullanarak toplama sonuçları elde etmek açıklanmaktadır [SQL](../../data/odbc/sql.md) anahtar sözcükler:

- **SUM** sayısal veri türüne sahip bir sütundaki değerlerin toplamını hesaplar.

- **MIN** sayısal veri türüne sahip bir sütundaki en küçük değeri ayıklar.

- **En fazla** sayısal veri türüne sahip bir sütundaki en büyük değeri ayıklar.

- **Ortalama** ortalama değeri bir sütundaki tüm değerlerin sayısal veri türüne sahip hesaplar.

- **SAYISI** herhangi bir veri türü sütununun kayıtlarını sayar.

Bu SQL işlevleri, bir veri kaynağındaki kayıtları hakkında istatistiksel bilgi edinmek için yerine veri kaynağından kayıtlar ayıklamak için kullanın. Genellikle oluşturulan kayıt tek bir oluşan bir değer içeren kayıt (tüm sütunları toplamalar varsa). (Kullandıysanız birden fazla kayıtla olabilir bir **GROUP BY** yan tümcesi.) Bir SQL işlev tarafından gerçekleştirilebilse ayıklama veya hesaplama sonucu değerdir.

> [!TIP]
>  Bir SQL eklemek için **GROUP BY** yan tümcesi (ve muhtemelen bir **HAVING** yan tümcesi) SQL deyimine, sonuna `m_strFilter`. Örneğin:

```
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";
```

Filtreleme ve sıralama sütunlarını toplama sonuçları elde etmek için kullandığınız kayıt sayısını sınırlayabilirsiniz.

> [!CAUTION]
>  Bazı toplama işleçleri, farklı bir veri türü üzerinde toplama sütunları döndürür.

- **SUM** ve **ortalama** sonraki daha büyük veri türü döndürebilir (örneğin, ile arama `int` döndürür **uzun** veya **çift**).

- **SAYISI** genellikle döndürür **uzun** hedef sütun türü ne olursa olsun.

- **En fazla** ve **MIN** hesaplanacak sütunları aynı veri türünde döndürür.

     Örneğin, **sınıfı Ekle** sihirbaz `long` `m_lSales` satış sütun, ancak uyum sağlamak için bunu değiştirmeniz gerekir bir `double m_dblSumSales` toplam sonucu barındırmak için veri üyesi. Aşağıdaki örnekte bakın.

#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>Bir kayıt kümesi için birleşik bir sonuç elde etmek için

1. Bölümünde anlatıldığı gibi bir kayıt kümesi oluşturma [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md) toplama sonuçları elde etmek istediğiniz sütunları içeren.

1. Değiştirme [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) kayıt kümesi için işlevi. Sütun adını temsil eden dize değiştirin (ikinci bağımsız değişkeni [RFX](../../data/odbc/record-field-exchange-using-rfx.md) işlev çağrılarında) ile sütunda toplama işlevini temsil eden bir dize. Örneğin, değiştirin:

    ```
    RFX_Long(pFX, "Sales", m_lSales);
    ```

     İle:

    ```
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)
    ```

1. Kayıt kümesini açın. Toplama işleminin sonucu left içinde `m_dblSumSales`.

> [!NOTE]
>  Sihirbaz, aslında Macarca önekleri olmadan veri üye adlarını atar. Örneğin, sihirbaz oluşturur `m_Sales` bir satış sütunu için yerine `m_lSales` önceki çizim için kullanılan ad.

Kullanıyorsanız bir [CRecordView](../../mfc/reference/crecordview-class.md) verileri görüntülemek için sınıf, yeni veri üyesinin değerini görüntülemek için DDX işlev çağrısı değiştirmek zorunda bu durumda, ondan değiştirme:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);
```

Hedef:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);
```

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)