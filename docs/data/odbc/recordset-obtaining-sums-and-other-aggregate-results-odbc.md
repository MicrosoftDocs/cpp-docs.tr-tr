---
title: "Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)"
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
ms.openlocfilehash: 9ebbe78191d0c4140baf3557637ba2103886577d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368650"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Yine de bir tüketiciyi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, aşağıdaki [SQL](../../data/odbc/sql.md) anahtar kelimeleri kullanarak toplu sonuçların nasıl elde edilebildiğini açıklar:

- **TOPLAM** Sayısal veri türüne sahip bir sütundaki değerlerin toplamını hesaplar.

- **MIN** Sayısal veri türüne sahip bir sütundaki en küçük değeri ayıklar.

- **MAX** Sayısal veri türüne sahip bir sütundaki en büyük değeri ayıklar.

- **AVG** Sayısal veri türüne sahip bir sütundaki tüm değerlerin ortalama değerini hesaplar.

- **SAY** Herhangi bir veri türündeki bir sütundaki kayıt sayısını sayar.

Bu SQL işlevlerini, veri kaynağından kayıtları ayıklamak yerine bir veri kaynağındaki kayıtlar hakkında istatistiksel bilgi elde etmek için kullanırsınız. Oluşturulan kayıt kümesi genellikle bir değer içeren tek bir kayıttan (tüm sütunlar agregaysa) oluşur. (GROUP **BY** yan tümcesi kullandıysanız birden fazla kayıt olabilir.) Bu değer, SQL işlevi tarafından gerçekleştirilen hesaplama veya çıkarma nın sonucudur.

> [!TIP]
> SQL ekstrenize bir SQL **GROUP BY** yan tümcesi (ve muhtemelen `m_strFilter` **HAVING** yan tümcesi) eklemek için, bunu sonuna ekleyin. Örneğin:

```
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";
```

Sütunları filtreleyerek ve sıralayarak toplu sonuçlar elde etmek için kullandığınız kayıt sayısını sınırlayabilirsiniz.

> [!CAUTION]
> Bazı toplama işleçleri, üzerinde topladıkları sütunlardan farklı bir veri türü döndürer.

- **SUM** ve **AVG** sonraki büyük veri türünü döndürebilir (örneğin, `int` **uzun** veya **çift**döndürücülerle arama).

- **COUNT** genellikle hedef sütun türüne bakılmaksızın **UZUN** döndürür.

- **MAX** ve **MIN,** hesapladıkları sütunlar ile aynı veri türünü döndürer.

     Örneğin, **Sınıf Ekle** sihirbazı `long` `m_lSales` bir Satış sütununa uyum sağlamak için `double m_dblSumSales` oluşturur, ancak toplu sonucu karşılamak için bunu bir veri üyesiyle değiştirmeniz gerekir. Aşağıdaki örneğe bakın.

#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>Bir kayıt kümesi için toplam sonuç elde etmek için

1. Toplu sonuçlar elde etmek istediğiniz sütunları içeren [bir MFC ODBC Tüketici eklemede](../../mfc/reference/adding-an-mfc-odbc-consumer.md) açıklandığı gibi bir kayıt kümesi oluşturun.

1. Kayıt kümesi için [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) işlevini değiştirin. Sütun adını [(RFX](../../data/odbc/record-field-exchange-using-rfx.md) işlev çağrılarının ikinci bağımsız değişkeni) temsil eden dizeyi sütundaki toplama işlevini temsil eden bir dizeyle değiştirin. Örneğin, değiştirin:

    ```
    RFX_Long(pFX, "Sales", m_lSales);
    ```

     Yeni değer:

    ```
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)
    ```

1. Kayıt kümesini açın. Toplama işleminin sonucu `m_dblSumSales`.

> [!NOTE]
> Sihirbaz aslında Macar önekleri olmadan veri üye adları atar. Örneğin, sihirbaz, illüstrasyon `m_Sales` için daha önce kullanılan `m_lSales` ad yerine bir Satış sütunu için üretim yapacak.

Verileri görüntülemek için bir [CRecordView](../../mfc/reference/crecordview-class.md) sınıfı kullanıyorsanız, yeni veri üye değerini görüntülemek için DDX işlev çağrısını değiştirmeniz gerekir; bu durumda, değiştirerek:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);
```

Hedef:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
