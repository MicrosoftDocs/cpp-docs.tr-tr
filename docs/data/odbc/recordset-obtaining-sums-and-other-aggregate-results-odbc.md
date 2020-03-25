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
ms.openlocfilehash: 1a8abc8b73ee878ac2feefa210268e87c608e938
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212842"
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
>  SQL deyiminize bir SQL **Group By** yan tümcesi (ve muhtemelen bir **HAVING** yan tümcesi) eklemek için `m_strFilter`sonuna ekleyin. Örneğin:

```
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";
```

Sütunları filtreleyerek ve sıralayarak toplama sonuçları elde etmek için kullandığınız kayıt sayısını sınırlayabilirsiniz.

> [!CAUTION]
>  Bazı toplama işleçleri, topladıkları sütunlardan farklı bir veri türü döndürür.

- **Sum** ve **AVG** bir sonraki daha büyük veri türünü döndürebilir (örneğin, `int` ile çağırmak **uzun** veya **çift**döndürür).

- **Count** genellikle hedef sütun türünden bağımsız olarak **uzun** döndürür.

- **Max** ve **MIN** , hesaplandıkları sütunlarla aynı veri türünü döndürür.

     Örneğin, **sınıf ekleme** Sihirbazı bir satış sütununa uyum sağlamak için `long` `m_lSales` oluşturur, ancak bunu toplama sonucunu karşılamak için `double m_dblSumSales` bir veri üyesiyle değiştirmeniz gerekir. Aşağıdaki örneğe bakın.

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

1. Kayıt kümesini açın. Toplama işleminin sonucu `m_dblSumSales`bırakılır.

> [!NOTE]
>  Sihirbaz aslında veri üyesi adlarını Macarca ön ekler olmadan atar. Örneğin, sihirbaz, daha önce çizim için kullanılan `m_lSales` adı yerine bir satış sütunu için `m_Sales` üretecektir.

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
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
