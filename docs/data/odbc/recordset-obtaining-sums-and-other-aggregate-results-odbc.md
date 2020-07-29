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
ms.openlocfilehash: b9e70716ad90a14bbed552d47f48d5a3317e5a62
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225715"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu başlığı altında, aşağıdaki [SQL](../../data/odbc/sql.md) anahtar kelimeleri kullanılarak nasıl toplam sonuçlar elde edileceği açıklanmaktadır:

- **Toplam** Bir sütundaki değerlerin toplamını sayısal veri türüne göre hesaplar.

- **En az** En küçük değeri sayısal veri türüne sahip bir sütunda ayıklar.

- **En fazla** En büyük değeri sayısal veri türüne sahip bir sütunda ayıklar.

- **Ort** . Sayısal veri türüne sahip bir sütundaki tüm değerlerin ortalama değerini hesaplar.

- **Sayı** Herhangi bir veri türünün bir sütunundaki kayıtların sayısını sayar.

Veri kaynağındaki kayıtları ayıklamak yerine bir veri kaynağındaki kayıtlar hakkında istatistiksel bilgiler almak için bu SQL işlevlerini kullanırsınız. Oluşturulan kayıt kümesi, genellikle bir değer içeren tek bir kayıttan (tüm sütunlar toplamalarda) oluşur. ( **Group By** yan tümcesi kullandıysanız birden fazla kayıt olabilir.) Bu değer, SQL işlevi tarafından gerçekleştirilen hesaplamanın veya ayıklamanın sonucudur.

> [!TIP]
> SQL deyiminize bir SQL **Group By** yan tümcesi (ve muhtemelen bir **HAVING** yan tümcesi) eklemek için, sonuna ekleyin `m_strFilter` . Örnek:

```
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";
```

Sütunları filtreleyerek ve sıralayarak toplama sonuçları elde etmek için kullandığınız kayıt sayısını sınırlayabilirsiniz.

> [!CAUTION]
> Bazı toplama işleçleri, topladıkları sütunlardan farklı bir veri türü döndürür.

- **Sum** ve **AVG** bir sonraki daha büyük veri türünü döndürebilir (örneğin, ile çağırma **`int`** **uzun** veya döndürür **`double`** ).

- **Count** genellikle hedef sütun türünden bağımsız olarak **uzun** döndürür.

- **Max** ve **MIN** , hesaplandıkları sütunlarla aynı veri türünü döndürür.

     Örneğin, **Sınıf Ekle** Sihirbazı **`long`** `m_lSales` Satış sütununu kapsayacak şekilde oluşturur, ancak bunu `double m_dblSumSales` toplam sonucu karşılamak için bir veri üyesiyle değiştirmeniz gerekir. Aşağıdaki örneğe bakın.

#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>Bir kayıt kümesi için toplam sonuç elde etmek için

1. Toplu sonuçları almak istediğiniz sütunları içeren bir [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md) bölümünde açıklandığı gibi bir kayıt kümesi oluşturun.

1. Kayıt kümesi için [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) işlevini değiştirin. Sütun adını temsil eden dizeyi ( [RFX](../../data/odbc/record-field-exchange-using-rfx.md) işlev çağrılarının ikinci bağımsız değişkeni) sütunundaki toplama işlevini temsil eden bir dize ile değiştirin. Örneğin, şunu değiştirin:

    ```
    RFX_Long(pFX, "Sales", m_lSales);
    ```

     Yeni değer:

    ```
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)
    ```

1. Kayıt kümesini açın. Toplama işleminin sonucu bırakılır `m_dblSumSales` .

> [!NOTE]
> Sihirbaz aslında veri üyesi adlarını Macarca ön ekler olmadan atar. Örneğin, sihirbaz `m_Sales` `m_lSales` daha önce illüstrasyon için kullanılan ad yerine bir Sales sütunu için üretecektir.

Verileri görüntülemek için bir [CRecordView](../../mfc/reference/crecordview-class.md) sınıfı kullanıyorsanız, yeni veri üye değerini görüntülemek için DDX işlev çağrısını değiştirmeniz gerekir; Bu durumda, şu şekilde değiştiriliyor:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);
```

Hedef:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: kayıt kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
