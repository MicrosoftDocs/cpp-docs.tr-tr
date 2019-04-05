---
title: 'Kayıt kümesi: (ODBC) bir kayıt kümesini parametreleştirme'
ms.date: 11/04/2016
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
ms.openlocfilehash: df67256c54cae3e2adb054d653d3e58bb91dd631
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026168"
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>Kayıt kümesi: (ODBC) bir kayıt kümesini parametreleştirme

Bu konu MFC ODBC sınıflarına uygulanır.

Bazen, çalışma zamanında kayıtları seçmek hesaplanan veya son Kullanıcınızdan alınan bilgileri kullanarak isteyebilirsiniz. Kayıt kümesi parametreleri bu amacı gerçekleştirmenize olanak tanır.

Bu konu şunları açıklar:

- [Parametreli bir kayıt kümesinin amacı](#_core_parameterized_recordsets).

- [Ne zaman ve neden, bir kayıt kümesini parametreleştirme isteyebilirsiniz](#_core_when_to_use_parameters).

- [Kayıt kümesi sınıfı veri üyelerinde parametre bildirmeyi](#_core_parameterizing_your_recordset_class).

- [Kayıt kümesi nesnesi için çalışma zamanında parametre bilgileri nasıl](#_core_passing_parameter_values_at_run_time).

##  <a name="_core_parameterized_recordsets"></a> Parametreli kayıt kümeleri

Parametreli bir kayıt kümesi çalışma zamanında parametre bilgilerini geçirmenize olanak tanır. Bu iki değerli etkilere sahiptir:

- Daha iyi yürütme hızı neden olabilir.

- Tasarım zamanında kullanılabilir olmayan bilgileri gibi bilgileri Kullanıcınızdan alınan veya çalışma zamanında hesaplanan temel çalışma zamanında, bir sorgu oluşturmanıza olanak sağlar.

Çağırdığınızda `Open` sorguyu çalıştırmak için tamamlamak için parametre bilgileri kayıt kümesini kullanır, **SQL SELECT** deyimi. Bir kayıt kümesini parametreleştirme.

##  <a name="_core_when_to_use_parameters"></a> Ne zaman parametreleri kullanma

Parametreler için tipik kullanımları şunlardır:

- Önceden tanımlanmış sorgu için çalışma zamanı bağımsız değişkenleri geçirme.

   Bir saklı yordamın parametreleri geçirmek için tam bir özel ODBC belirtmelisiniz **çağrı** deyimi — parametresi tutucularla — çağırdığınızda `Open`, kümesinin varsayılan SQL deyimi geçersiz kılma. Daha fazla bilgi için [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) içinde *sınıf kitaplığı başvurusu* ve [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md) ve [kayıt kümesi: Bir sınıf bildirme (ODBC) önceden tanımlanmış sorgu için](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).

- Verimli bir şekilde farklı parametre bilgileri ile çok sayıda sorgular gerçekleştirme.

   Örneğin, her zaman son kullanıcı için Öğrenci kayıt defteri veritabanında belirli bir öğrenci bilgi arar, Öğrenci adı veya kimliği kullanıcıdan alınan bir parametre olarak belirtebilirsiniz. Ardından, kümenizin çağırdığınızda `Requery` üye işlevi, sorgu yalnızca bu öğrencinin kaydı seçer.

   Depolanan kümenizin filtre dizesi `m_strFilter`, şuna benzeyebilir:

    ```cpp
    "StudentID = ?"
    ```

   Öğrenci Kimliği değişkeninde elde varsayalım `strInputID`. Bir parametre ayarlandığında `strInputID` (örneğin, kimliği 100 Öğrenci) tarafından temsil edilen parametresi yer tutucu değişkenin değerini bağlıdır "?" filtre dizesi içinde.

   Parametre değerini şu şekilde atayın:

    ```cpp
    strInputID = "100";
    ...
    m_strParam = strInputID;
    ```

   Bu şekilde bir filtre dizesi ayarlama istemezsiniz:

    ```cpp
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted
                                       // for some drivers
    ```

   Teklif için filtre dizeleri doğru kullanma hakkında bir tartışma için bkz [kayıt kümesi: Kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

   Parametre değeri kayıt için yeni bir öğrenci kimliği requery her zaman farklıdır

   > [!TIP]
   > Bir parametre kullanarak, sadece bir filtre kullanmaktan daha verimlidir. Parametreli bir kayıt kümesi için bir SQL veritabanı işlemelisiniz **seçin** deyimi yalnızca bir kez. Parametresiz, filtrelenmiş bir kayıt kümesi için **seçin** deyimi işlenmelidir her zaman `Requery` ile yeni bir filtre değeri.

Filtreleri hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

##  <a name="_core_parameterizing_your_recordset_class"></a> Sınıfınıza kayıt kümesini parametreleştirme

> [!NOTE]
> Bu bölüm, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme, parametreleri uygulama kullanıyorsanız benzer bir işlemdir. Daha fazla bilgi için [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Kayıt kümesi sınıfı oluşturmadan önce gereksinim duyduğunuz parametreleri, veri türlerini nelerdir ve kayıt bunları nasıl kullandığını belirleyin.

#### <a name="to-parameterize-a-recordset-class"></a>Kayıt kümesi sınıfı parametre haline getirmek için

1. Çalıştırma [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) gelen **sınıfı Ekle** sınıfı oluşturmak için.

1. Alan veri üyeleri kayıt kümesinin sütunlar için belirtin.

1. Sınıf Sihirbazı, projenizdeki bir dosyaya yazar sonra .h dosyasına gidin ve bir veya daha fazla parametre veri üyeleri sınıf bildirimi için el ile ekleyin. Ayrıca, aşağıdaki örneğe benzer bir şey görünebilir, bir anlık görüntü sınıfın parçası için tasarlanmış sorgu yanıt "olan Öğrenciler son sınıfta?"

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

   Sonra alan Sihirbazı tarafından üretilen veri üyeleri, parametre veri üyeleri ekleyin. "Parametre" sözcüğü için her bir kullanıcı tarafından tanımlanan parametre adı eklemek için kullanılan kuraldır.

1. Değiştirme [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlev tanımında .cpp dosyası. RFX işlev çağrısı bir sınıfa eklediğiniz her parametre veri üyesi ekleyin. RFX işlevlerinizi yazma hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX'in çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md). RFX çağrıları parametreleri için tek bir çağrı ile koyun:

    ```cpp
    pFX->SetFieldType( CFieldExchange::param );
    // RFX calls for parameter data members
    ```

1. Kayıt kümesi sınıfı oluşturucusunun içinde parametre sayısını artırmak `m_nParams`.

   Bilgi için [kayıt alanı değişimi: Sihirbaz kodu ile çalışma](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md).

1. Bu sınıfın bir kayıt kümesi nesnesi oluşturan kodu yazdığınız zaman yerleştirileceği bir "?" bir parametre değiştirilecek olduğu her yerde SQL deyimi dizelerinizi (soru işareti) simgesi.

   Çalışma zamanında "?" yer tutucuları doldurulur, sırayla, geçirdiğiniz parametre değerleri ile. Sonra ilk parametresinin veri üye kümesi [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) çağrı değiştirir ilk "?"SQL dizesinde ikinci parametre veri üyesi ikinci değiştirir"?" ve benzeri.

> [!NOTE]
> Parametre sırası önemlidir: RFX sırasını çağıran parametreler için `DoFieldExchange` işlevi parametre içindeki yer tutucuları SQL dizenizi sırasını eşleşmesi gerekir.

> [!TIP]
> Çalışmak için en olası dize belirttiğiniz dizedir (varsa) için sınıfın [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesi, ancak bazı ODBC sürücüleri izin parametreleri diğer SQL yan tümcelerinde.

##  <a name="_core_passing_parameter_values_at_run_time"></a> Çalışma zamanında parametre değerlerini geçirme

Çağırmadan önce parametre değerlerini belirtin `Open` (için yeni bir kayıt kümesi nesnesi) veya `Requery` (için mevcut bir).

#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>Çalışma zamanında bir kayıt nesnesine parametre değerlerini geçirmek için

1. Kayıt kümesi nesnesi oluşturun.

1. Bir dize veya dizeler gibi hazırlama `m_strFilter` SQL deyiminin veya bazı bölümleri içeren bir dize. PUT "?" parametre bilgileri olduğu gitmek için yer tutucu.

1. Bir çalışma zamanı parametre değeri, her nesne parametresi veri üyesine atayın.

1. Çağrı `Open` üye işlevi (veya `Requery`, var olan bir kayıt kümesi için).

Örneğin, çalışma zamanında alınan bilgileri kullanarak kayıt için bir filtre dizesi belirtmek istediğinizi varsayalım. Bir kayıt kümesi sınıfının oluşturulmuş varsayar `CStudentSet` önceki — adlı `rsStudents` — ve artık belirli bir öğrenci bilgi türünü de requery istiyorsunuz.

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

Kayıt kümesi kayıtlarını çalışma zamanı parametrelerinden oluşturulmuş filtre tarafından belirtilen koşulları karşılayan bu Öğrenciler için kayıtları içerir. Bu durumda, kayıt kümesinin tüm üst düzey Öğrenciler için kayıtlar içerir.

> [!NOTE]
>  Gerekli olursa, parametre veri üyesinin değerini Null olarak ayarlayabilirsiniz kullanarak [SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull). Benzer şekilde bir parametre veri üyesi Null olup olmadığını denetleyebiliriz kullanarak [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Kayıt kümesi: Kayıtları seçme biçimi (ODBC) nasıl kaydeder](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)