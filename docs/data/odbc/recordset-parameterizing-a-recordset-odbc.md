---
description: 'Daha fazla bilgi: kayıt kümesi: bir kayıt kümesini Parametreleme (ODBC)'
title: 'Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)'
ms.date: 05/09/2019
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
ms.openlocfilehash: 0801e503992204ac24bff2e9378f4e1d24f9864d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204530"
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bazen, son kullanıcıdan hesapladığınız veya aldığınız bilgileri kullanarak çalışma zamanında kayıtları seçebilmek isteyebilirsiniz. Kayıt kümesi parametreleri bu hedefi gerçekleştirmenize olanak sağlar.

Bu konuda aşağıdakiler açıklanmaktadır:

- [Parametreli bir kayıt kümesinin amacı](#_core_parameterized_recordsets).

- [Ne zaman ve neden bir kayıt kümesini parametreleştirmek](#_core_when_to_use_parameters)isteyebilirsiniz.

- [Kayıt kümesi sınıfınıza parametre veri üyelerini bildirme](#_core_parameterizing_your_recordset_class).

- [Çalışma zamanında parametre bilgilerini bir kayıt kümesi nesnesine geçirme](#_core_passing_parameter_values_at_run_time).

## <a name="parameterized-recordsets"></a><a name="_core_parameterized_recordsets"></a> Parametreli kayıt kümeleri

Parametreli bir kayıt kümesi, çalışma zamanında parametre bilgilerini geçirmenize olanak sağlar. Bu iki değerli etkiye sahiptir:

- Daha iyi yürütme hızına neden olabilir.

- Çalışma zamanında, kullanıcıdan elde edilen veya çalışma zamanında hesaplanan bilgiler gibi tasarım zamanında size kullanılamayan bilgileri temel alarak bir sorgu oluşturmanızı sağlar.

`Open`Sorguyu çalıştırmak için öğesini çağırdığınızda kayıt kümesi, **SQL SELECT** ifadesini tamamlayacak parametre bilgilerini kullanır. Herhangi bir kayıt kümesini parametreleştirebilirsiniz.

## <a name="when-to-use-parameters"></a><a name="_core_when_to_use_parameters"></a> Parametrelerin ne zaman kullanılacağı

Parametrelerin tipik kullanımları şunlardır:

- Çalışma zamanı bağımsız değişkenlerini önceden tanımlanmış bir sorguya geçirme.

   Parametreleri saklı bir yordama geçirmek için,  `Open` kayıt kümesinin varsayılan SQL ifadesini geçersiz kılarak, parametre yer tutucuları ile, tüm özel bir ODBC çağrı ekstresi belirtmeniz gerekir. Daha fazla bilgi için bkz. [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) *sınıf kitaplığı başvurusu* ve [SQL: kayıt KÜMENIZIN SQL ifadesini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md) ve [kayıt kümesi: önceden TANıMLANMıŞ sorgu için bir sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).

- Farklı parametre bilgileriyle çok sayıda yeniden sorgulama işlemi verimli bir şekilde gerçekleştiriliyor.

   Örneğin, Son Kullanıcı öğrenci kayıt veritabanındaki belirli bir öğrenciye ilişkin bilgileri her ararken, öğrencinin adını veya KIMLIĞINI kullanıcıdan alınan bir parametre olarak belirtebilirsiniz. Sonra, kayıt kümenizin `Requery` üye işlevini çağırdığınızda sorgu yalnızca söz konusu öğrencinin kaydını seçer.

   Kayıt kümenizin ' de depolanan filtre dizesi şöyle `m_strFilter` görünebilir:

    ```cpp
    "StudentID = ?"
    ```

   Değişkende öğrenci KIMLIĞINI aldığınızı varsayın `strInputID` . İçin bir parametre ayarladığınızda `strInputID` (örneğin, öğrencı no 100) değişkenin değeri, filtre dizesinde "?" ile temsil edilen parametre yer tutucusuna bağlanır.

   Parametre değerini aşağıdaki gibi atayın:

    ```cpp
    strInputID = "100";
    ...
    m_strParam = strInputID;
    ```

   Bu şekilde bir filtre dizesi ayarlamak istemezsiniz:

    ```cpp
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted
                                       // for some drivers
    ```

   Filtre dizeleri için tekliflerin doğru şekilde nasıl kullanılacağına ilişkin bir tartışma için bkz. [kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

   Parametre değeri, yeni bir öğrenci KIMLIĞI için kayıt kümesini her yeniden sorguışınızda farklıdır.

   > [!TIP]
   > Bir parametre kullanmak yalnızca bir filtreden daha etkilidir. Parametreli bir kayıt kümesi için veritabanının bir SQL **Select** ifadesini yalnızca bir kez işlemesi gerekir. Parametresiz filtrelenmiş bir kayıt kümesi için, **Select** ifadesinin her `Requery` Yeni filtre değeri ile her seferinde işlenmesi gerekir.

Filtreler hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

## <a name="parameterizing-your-recordset-class"></a><a name="_core_parameterizing_your_recordset_class"></a> Kayıt kümesi sınıfınızı parametrize etme

> [!NOTE]
> Bu bölüm, `CRecordset` toplu satır yakalamanın uygulanmadığı, öğesinden türetilmiş nesneler için geçerlidir. Toplu satır getirme kullanıyorsanız, parametreleri uygulamak benzer bir işlemdir. Daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Kayıt kümesi sınıfınızı oluşturmadan önce, hangi parametrelere ihtiyacınız olduğunu, veri türlerinin ne olduğunu ve kayıt kümesinin bunları nasıl kullandığını saptayın.

#### <a name="to-parameterize-a-recordset-class"></a>Bir kayıt kümesi sınıfını parametreleştirmek için

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Bu işlevi yine de el ile oluşturabilirsiniz.

1. Sınıfı oluşturmak için **Sınıf Ekle** ' den [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) ' nı çalıştırın.

1. Kayıt kümesi sütunları için alan veri üyelerini belirtin.

1. Sihirbaz, sınıfı projenizdeki bir dosyaya yazdıktan sonra. h dosyasına gidin ve sınıf bildirimine bir veya daha fazla parametre veri üyesini el ile ekleyin. Ek olarak, aşağıdaki örneğe benzer şekilde tasarlanan bir anlık görüntü sınıfının bir parçası olan "öğrenciler kıdemli sınıfta bulunan bir sorguyu yanıtlamak üzere tasarlandı"

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

   Sihirbaz tarafından oluşturulan alan verileri üyelerinden sonra parametre veri üyelerinizi ekleyin. Bu kural, her kullanıcı tanımlı parametre adına "param" sözcüğünü eklemedir.

1. . Cpp dosyasındaki [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlev tanımını değiştirin. Sınıfa eklediğiniz her bir parametre veri üyesi için bir RFX işlev çağrısı ekleyin. RFX işlevlerinizi yazma hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md). Parametrelerin tek bir çağrısıyla RFX çağrılarının önüne:

    ```cpp
    pFX->SetFieldType( CFieldExchange::param );
    // RFX calls for parameter data members
    ```

1. Kayıt kümesi sınıfınızın oluşturucusunda, parametre sayısını artırın `m_nParams` .

   Bilgi için bkz. [kayıt alanı değişimi: sihirbaz kodu Ile çalışma](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md).

1. Bu sınıfın bir kayıt kümesi nesnesi oluşturan kodu yazdığınızda, bir "?" yerleştirin (soru işareti) SQL deyiminizdeki her yerde bir parametrenin değiştirildiği bir yerde simge.

   Çalışma zamanında, "?" yer tutucuları geçirdiğiniz parametre değerleri tarafından sırayla doldurulur. [SETbir](../../mfc/reference/cfieldexchange-class.md#setfieldtype) çağrısından sonra ilk parametre veri üyesi KÜMESI, SQL dizesinde ilk "?" yerini almıştır, ikinci parametre veri üyesi ikinci "?" ve bu şekilde değiştirilir.

> [!NOTE]
> Parametre sırası önemlidir: işlevinizdeki parametreler için RFX çağrılarının sırası, `DoFieldExchange` SQL dizinizdeki parametre yer tutucuların sırasıyla aynı olmalıdır.

> [!TIP]
> Birlikte çalışmak için en olası dize, sınıfın [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesi için (varsa) belirttiğiniz dizedir, ancak bazı ODBC SÜRÜCÜLERI diğer SQL yan tümcelerinde parametrelere izin verebilir.

## <a name="passing-parameter-values-at-run-time"></a><a name="_core_passing_parameter_values_at_run_time"></a> Çalışma zamanında parametre değerlerini geçirme

Çağrı yapmadan önce `Open` (yeni bir kayıt kümesi nesnesi için) veya `Requery` (var olan bir kayıt için) parametre değerlerini belirtmeniz gerekir.

#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>Çalışma zamanında parametre değerlerini bir kayıt kümesi nesnesine geçirmek için

1. Kayıt kümesi nesnesini oluşturun.

1. `m_strFilter`SQL ifadesini veya bunun parçalarını içeren dize gibi bir dize veya dizeler hazırlayın. Parametre bilgisinin Gidecebileceği "?" yer tutucuları koyun.

1. Nesnenin her bir parametre veri üyesine bir çalışma zamanı parametre değeri atayın.

1. `Open`Üye işlevini (veya `Requery` varolan bir kayıt kümesi için) çağırın.

Örneğin, çalışma zamanında elde edilen bilgileri kullanarak kayıt kümeniz için bir filtre dizesi belirtmek istediğinizi varsayalım. Daha önce bir sınıf kayıt kümesi oluşturduğunuzu varsayalım — `CStudentSet` adlı `rsStudents` ve şimdi belirli bir öğrenci bilgileri türü için yeniden sorgulamak istiyorsunuz.

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

Kayıt kümesi, kayıtları, çalışma zamanı parametrelerinden oluşturulan filtre tarafından belirtilen koşullara uyan öğrenciler için kayıtlar içerir. Bu durumda, kayıt kümesi tüm kıdemli öğrenciler için kayıtlar içerir.

> [!NOTE]
> Gerekirse, [SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull)kullanarak bir parametre veri üyesinin değerini null olarak ayarlayabilirsiniz. Benzer şekilde, [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull)kullanarak bir parametre veri üyesinin null olup olmadığını kontrol edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: kayıtları ekleme, güncelleştirme ve silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Kayıt kümesi: kayıt kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
