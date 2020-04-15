---
title: 'Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)'
ms.date: 05/09/2019
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
ms.openlocfilehash: 6d28471bdc44d5d75a9eeac2327f92a8e2e265c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360654"
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bazen son kullanıcınızdan hesapladığınız veya elde ettiğiniz bilgileri kullanarak kayıtları çalışma zamanında seçmek isteyebilirsiniz. Recordset parametreleri bu hedefe ulaşmanızı sağlar.

Bu konu açıklar:

- [Parametreli kayıt kümesinin amacı.](#_core_parameterized_recordsets)

- [Bir kayıt kümesini ne zaman ve neden parametrelendirmek isteyebilirsiniz.](#_core_when_to_use_parameters)

- [Parametre veri üyelerini kayıt seti sınıfınızda nasıl beyan eyleyin.](#_core_parameterizing_your_recordset_class)

- [Parametre bilgilerinin çalışma zamanında kayıt kümesi nesnesine nasıl geçirilir?](#_core_passing_parameter_values_at_run_time)

## <a name="parameterized-recordsets"></a><a name="_core_parameterized_recordsets"></a>Parametreli Kayıt Kümeleri

Parametreli kayıt kümesi, parametre bilgilerini çalışma zamanında geçirmenizi sağlar. Bunun iki değerli etkisi vardır:

- Daha iyi yürütme hızı ile sonuçlanabilir.

- Kullanıcınızdan elde edilen veya çalışma zamanında hesaplanan bilgiler gibi tasarım zamanında sizin için kullanılamayan bilgilere dayanarak, çalışma zamanında bir sorgu oluşturmanıza olanak tanır.

Sorguyu `Open` çalıştırmak için aradiğinizde, kayıt kümesi **SQL SELECT** deyimini tamamlamak için parametre bilgilerini kullanır. Herhangi bir kayıt kümesini parametrenize edebilirsiniz.

## <a name="when-to-use-parameters"></a><a name="_core_when_to_use_parameters"></a>Parametreler Ne Zaman Kullanılır

Parametreler için tipik kullanımlar şunlardır:

- Çalışma zamanı bağımsız değişkenlerini önceden tanımlanmış bir sorguya geçirme.

   Parametreleri depolanan yordama geçirmek için, kayıt kümesinin **CALL** varsayılan SQL deyimini geçersiz kılarak `Open`parametre yer tutucuları içeren tam bir özel ODBC CALL deyimi belirtmeniz gerekir. Daha fazla bilgi için [CRecordset::Class](../../mfc/reference/crecordset-class.md#open) *Library Reference* ve [SQL'de aç: Recordset'inSQL Bildirimini (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md) özelleştirme ve [Kayıt Kümesi: Önceden Tanımlanmış Bir Sorgu (ODBC) için Sınıf Bildirme](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).

- Farklı parametre bilgileriyle çok sayıda yeniden sorguyı verimli bir şekilde gerçekleştirme.

   Örneğin, son kullanıcınız öğrenci kayıt veritabanında belirli bir öğrencinin bilgilerini her aradığında, kullanıcıdan alınan bir parametre olarak öğrencinin adını veya kimliğini belirtebilirsiniz. Daha sonra, kayıt setinizin `Requery` üye işlevini aradiğinizde, sorgu yalnızca o öğrencinin kaydını seçer.

   Kayıt setinizin filtre dizesi, depolanan `m_strFilter`, bu gibi görünebilir:

    ```cpp
    "StudentID = ?"
    ```

   Değişkendeki `strInputID`öğrenci kimliğini elde ettiğinizi varsayalım. Bir parametreyi (örneğin, öğrenci kimliği 100' e) `strInputID` ayarladığınızda, değişkenin değeri filtre dizesindeki "?" ile temsil edilen parametre yer tutucuya bağlıdır.

   Parametre değerini aşağıdaki gibi atayın:

    ```cpp
    strInputID = "100";
    ...
    m_strParam = strInputID;
    ```

   Bu şekilde bir filtre dizesi kurmak istemezsinize:

    ```cpp
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted
                                       // for some drivers
    ```

   Filtre dizeleri için tırnak işaretlerinin nasıl kullanılacağı nı tartışmak için [Bkz. Recordset: Filtreleme Kayıtları (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

   Yeni bir öğrenci kimliği için kayıt kümesini her yeniden sorguladığınızda parametre değeri farklıdır.

   > [!TIP]
   > Parametre kullanmak, basit bir filtreden daha etkilidir. Parametreli kayıt kümesi için veritabanının bir SQL **SELECT** deyimini yalnızca bir kez işlemesi gerekir. Parametreleri olmayan filtreuygulanmış bir kayıt kümesi için **SELECT** `Requery` deyimi, her zaman yeni bir filtre değeriyle işlenmelidir.

Filtreler hakkında daha fazla bilgi için Bkz. [Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

## <a name="parameterizing-your-recordset-class"></a><a name="_core_parameterizing_your_recordset_class"></a>Kayıt Kümesi Sınıfınızı Parametreleme

> [!NOTE]
> Bu bölüm, toplu satır `CRecordset` alma nın uygulanmadığı nesneler için geçerlidir. Toplu satır alma kullanıyorsanız, parametreleri uygulama benzer bir işlemdir. Daha fazla bilgi için [bkz: Kayıt Kümesi: Toplu Olarak Kayıt Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Kayıt kümesi sınıfınızı oluşturmadan önce, hangi parametrelere ihtiyacınız olduğunu, veri türlerinin ne olduğunu ve kayıt kümesinin bunları nasıl kullandığını belirleyin.

#### <a name="to-parameterize-a-recordset-class"></a>Kayıt kümesi sınıfParametrelendirmek için

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Bu işlevselliği el ile oluşturmaya devam edebilirsiniz.

1. Sınıfı oluşturmak için **Sınıf Ekle'den** [MFC ODBC Tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md) Sihirbazı'nı çalıştırın.

1. Kayıt kümesinin sütunları için alan veri üyelerini belirtin.

1. Sihirbaz sınıfı projenizdeki bir dosyaya yazdıktan sonra ,.h dosyasına gidin ve sınıf bildirimine el ile bir veya daha fazla parametre veri üyesi ekleyin. Ek aşağıdaki örnek gibi bir şey görünebilir, bir anlık görüntü sınıfının bir parçası sorusuna cevap vermek için tasarlanmış "Hangi öğrenciler son sınıfta?"

    ```cpp
    class CStudentSet : public CRecordset
    {
    // Field/Param Data
        CString m_strFirstName;
        CString m_strLastName;
        CString m_strStudentID;
        CString m_strGradYear;

        CString m_strGradYrParam;
    };
    ```

   Sihirbaz tarafından oluşturulan alan veri üyelerinden sonra parametre veri üyelerinizi ekleyin. Sözleşme, kullanıcı tarafından tanımlanan her parametre adına "Param" sözcüğünün ekini vermektir.

1. .cpp dosyasındaki [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlev tanımını değiştirin. Sınıfa eklediğiniz her parametre veri üyesi için bir RFX işlev çağrısı ekleyin. RFX işlevlerinizi yazma hakkında daha fazla bilgi için Kayıt [Alanı Değişimi: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md) RFX'in parametreleri tek bir çağrıyla önleme:

    ```cpp
    pFX->SetFieldType( CFieldExchange::param );
    // RFX calls for parameter data members
    ```

1. Kayıt kümesi sınıfınızın oluşturucusunda, parametrelerin sayısını `m_nParams`artım, .

   Bilgi için, [Bkz. Kayıt Alanı Değişimi: Sihirbaz Kodu ile çalışma.](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)

1. Bu sınıfın kayıt kümesi nesnesini oluşturan kodu yazarken, bir "?" (soru işareti) sembolü, bir parametrenin değiştirilebileceği SQL deyimi dizelerinizdeki her yerde.

   Çalışma zamanında, "?" yer tutucuları, geçtiğiniz parametre değerlerine göre sırayla doldurulur. [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) çağrısından sonra ilk parametre veri üyesi kümesi SQL dizesindeki ilk "?" yerine, ikinci parametre veri üyesi ikinci "?", ve benzeri değiştirir.

> [!NOTE]
> Parametre sırası önemlidir: Işlevinizdeki `DoFieldExchange` parametreler için RFX çağrılarının sırası, SQL dizenizdeki parametre yer tutucularının sırasına uygun olmalıdır.

> [!TIP]
> Çalışmak için en olası dize sınıfın [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesi için belirttiğiniz dize (varsa) ancak bazı ODBC sürücüleri diğer SQL yan tümcelerinde parametrelere izin verebilir.

## <a name="passing-parameter-values-at-run-time"></a><a name="_core_passing_parameter_values_at_run_time"></a>Çalışma Zamanında Parametre Değerlerini Geçirme

Aramadan `Open` önce (yeni bir kayıt kümesi nesnesi `Requery` için) veya (varolan bir nesne için) parametre değerlerini belirtmeniz gerekir.

#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>Parametre değerlerini çalışma zamanında kayıt kümesi nesnesine geçirmek için

1. Kayıt kümesi nesnesini oluştur.

1. SQL deyimini veya parçalarını içeren `m_strFilter` dize gibi bir dize veya dize hazırlayın. Parametre bilgilerinin gideceği yere "?" yer tutucuları koyun.

1. Nesnenin her parametre veri üyesine bir çalışma süresi parametre değeri atayın.

1. `Open` Üye işlevi (veya `Requery`varolan bir kayıt kümesi için) arayın.

Örneğin, çalışma zamanında elde edilen bilgileri kullanarak kayıt setiniz için bir filtre dizesi belirtmek istediğinizi varsayalım. Daha önce bir sınıf `CStudentSet` kayıt kümesi `rsStudents` inşa ettiğinizi varsayalım - adlı — ve şimdi öğrenci bilgilerinin belirli bir tür için yeniden sorgulamak istiyorum.

```cpp
// Set up a filter string with
// parameter placeholders
rsStudents.m_strFilter = "GradYear <= ?";

// Obtain or calculate parameter values
// to pass--simply assigned here
CString strGradYear = GetCurrentAcademicYear( );

// Assign the values to parameter data members
rsStudents.m_strGradYrParam = strGradYear;

// Run the query
if( !rsStudents.Requery( ) )
    return FALSE;
```

Kayıt kümesi, kayıtları filtre tarafından belirtilen koşulları karşılayan ve çalışma zamanı parametrelerinden oluşturulmuş olan öğrencilerin kayıtlarını içerir. Bu durumda, kayıt kümesi tüm son sınıf öğrencilerinin kayıtlarını içerir.

> [!NOTE]
> Gerekirse, [SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull)kullanarak bir parametre veri üyesinin değerini Null olarak ayarlayabilirsiniz. Aynı şekilde [isfieldnull](../../mfc/reference/crecordset-class.md#isfieldnull)kullanarak, bir parametre veri üyesi Null olup olmadığını kontrol edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
