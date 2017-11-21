---
title: "Kayıt kümesi: kayıt kümesi (ODBC) kümesini parametreleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e282bf795435d21264ff4ab62575b9315781a0e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bazen, çalışma zamanında, kayıt seçebilmesini hesaplanan veya son kullanıcıdan alınan bilgileri kullanarak isteyebilirsiniz. Kayıt kümesi parametreleri, bu amacı gerçekleştirmenize olanak tanır.  
  
 Bu konuda açıklanmaktadır:  
  
-   [Parametreli kayıt kümesinin amacı](#_core_parameterized_recordsets).  
  
-   [Ne zaman ve neden bir kayıt kümesini parametreleştirme isteyebilirsiniz](#_core_when_to_use_parameters).  
  
-   [Parametre veri üyeleri kayıt kümesi sınıfınızda bildirmek nasıl](#_core_parameterizing_your_recordset_class).  
  
-   [Parametre bilgileri çalışma zamanında bir kayıt kümesi nesnesine geçirmek nasıl](#_core_passing_parameter_values_at_run_time).  
  
##  <a name="_core_parameterized_recordsets"></a>Parametreli kayıt kümeleri  
 Parametreli kayıt kümesi çalışma zamanında parametre bilgilerini geçirmenize olanak sağlar. Bu iki değerli etkilere sahiptir:  
  
-   Daha iyi yürütme hızıyla sonuçlanabilir.  
  
-   Tasarım zamanında kullanılabilir olmayan bilgileri gibi bilgiler, kullanıcıdan alınan veya çalışma zamanında hesaplanan temel çalışma zamanında bir sorgu oluşturmak olanak sağlar.  
  
 Çağırdığınızda **açık** sorguyu çalıştırmak için tamamlamak için parametre bilgilerini kayıt kümesi kullanan kendi **SQL SELECT** deyimi. Herhangi bir kayıt kümesini parametreleştirme.  
  
##  <a name="_core_when_to_use_parameters"></a>Zaman parametrelerini kullanmak için  
 Parametrelerin tipik kullanımları şunları içerir:  
  
-   Çalışma zamanı bağımsız değişkenleri geçirme önceden tanımlanmış sorgu için.  
  
     Bir saklı yordam parametreleri geçirmek için tam bir özel ODBC belirtin **ÇAĞRISI** deyimi — parametre yer tutucuları ile — çağırdığınızda **açık**, kayıt kümesinin varsayılan SQL deyimini geçersiz kılın. Daha fazla bilgi için bkz: [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) içinde *sınıf kitaplığı başvurusu* ve [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md) ve [ Kayıt kümesi: önceden tanımlanmış bir sorgu (ODBC) için bir sınıf bildirme](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).  

  
-   Verimli bir şekilde farklı parametre bilgileriyle çok sayıda sorgular gerçekleştirme.  
  
     Örneğin, bilgi Öğrenci kayıt veritabanında belirli bir öğrenci için son kullanıcı arayan her zaman, öğrencinin adı veya kimliği kullanıcıdan alınan bir parametre olarak belirtebilirsiniz. Ardından, kümenizin çağırdığınızda **Requery** üye işlevi, sorgu sadece bu öğrencinin kaydını seçer.  
  
     İçinde depolanan kümenizin filtre dizesini **m_strFilter**, şuna benzeyebilir:  
  
    ```  
    "StudentID = ?"  
    ```  
  
     Değişkeni Öğrenci Kimliğini elde varsayalım `strInputID`. Bir parametre ayarlandığında `strInputID` (örneğin, Öğrenci Kimliği 100) tarafından temsil edilen parametre yer tutucu değişkenin değerini bağlandığı "?" filtre dizesi içinde.  
  
     Parametre değeri gibi atayın:  
  
    ```  
    strInputID = "100";  
    ...  
    m_strParam = strInputID;  
    ```  
  
     Bu şekilde bir filtre dizesi ayarlama istemezsiniz:  
  
    ```  
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted  
                                       // for some drivers  
    ```  
  
     Tırnak işaretleri filtre dizeleri için doğru bir şekilde kullanmak nasıl bir tartışma için bkz [kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
     Parametre değeri kayıt için yeni bir öğrenci kimliği requery her zaman farklıdır  
  
    > [!TIP]
    >  Bir parametre kullanarak, sadece bir filtre kullanmaktan daha etkilidir. Parametreli bir kayıt kümesi için bir SQL veritabanı işlemelidir **seçin** deyimi yalnızca bir kez. Parametresiz, filtre uygulanmış bir kayıt kümesi için **seçin** deyimi işlenmelidir her zaman **Requery** yeni bir filtre değerine sahip.  
  
 Filtreler hakkında daha fazla bilgi için bkz: [kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
##  <a name="_core_parameterizing_your_recordset_class"></a>Kayıt kümesi sınıfınız kümesini parametreleştirme  
  
> [!NOTE]
>  Bu bölümde türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme, parametreleri uygulamak kullanıyorsanız benzer bir işlemdir. Daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Kayıt kümesi sınıfınızı oluşturmadan önce hangi parametrelere ihtiyacınız, kendi veri türleri nelerdir ve kayıt bunları nasıl kullandığını belirleyin.  
  
#### <a name="to-parameterize-a-recordset-class"></a>Kayıt kümesi sınıfı Parametreleştirme için  
  
1.  Çalıştırma [MFC ODBC Tüketici Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) gelen **sınıfı Ekle** sınıfı oluşturmak için.  
  
2.  Alan veri üyeleri için kayıt kümesinin sütunları belirtin.  
  
3.  Sihirbaz sınıfı projenizdeki bir dosyaya yazar. sonra .h dosyasına gidin ve el ile bir veya daha fazla parametre veri üyeleri için sınıf bildirimi ekleyin. Ayrıca aşağıdaki örneğe benzer bir şey görünebilir, bir anlık görüntü sınıfın parçası için tasarlanmış sorgu yanıt "hangi Öğrenciler son sınıfta?"  
  
    ```  
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
  
     Parametre veri üyeleri sonra sihirbaz tarafından oluşturulan alan veri üyeleri ekleyin. Her kullanıcı tarafından tanımlanan parametre adı "Param" sözcüğü eklemek için kullanılan kuraldır.  
  
4.  Değiştirme [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) .cpp dosyasındaki üye işlev tanımı. Sınıfa eklediğiniz her parametre veri üyesi için bir RFX işlev çağrısı ekleyin. RFX işlevleri yazma hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md). Tek bir çağrı parametreler için RFX çağrılarla koyun:  
  
    ```  
    pFX->SetFieldType( CFieldExchange::param );  
    // RFX calls for parameter data members  
    ```  
  
5.  Kayıt kümesi sınıfınız oluşturucuda parametre sayısını artırmak `m_nParams`.  
  
     Bilgi için bkz: [kayıt alanı değişimi: sihirbaz kodu ile çalışma](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md).  
  
6.  Bir kayıt kümesi oluşturur, bu sınıfın kodu yazarken yerleştirin bir "?" bir parametre değiştirilmesi olduğu her yerinde SQL deyimi dizeleri (soru işareti) simgesi.  
  
     Çalışma zamanında "?" yer tutucuları doldurulur, sırayla, geçirdiğiniz parametre değerleri ile. Sonra ilk parametre veri üye kümesi [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) çağrısı değiştirir ilk "?"içindeki SQL dizesi, ikinci parametre veri üyesi ikinci değiştirir"?" ve benzeri.  
  
> [!NOTE]
>  Parametre sırası önemlidir: RFX sırasını çağırır parametreler için de, `DoFieldExchange` işlevi SQL dizesi parametre yer tutucularını sırasını eşleşmesi gerekir.  
  
> [!TIP]

>  Çalışmak için büyük olasılıkla dizesi belirttiğiniz dizesidir (varsa) sınıfının için [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesi, ancak bazı ODBC sürücüleri izin parametreleri diğer SQL yan tümcelerinde.  
  
##  <a name="_core_passing_parameter_values_at_run_time"></a>Çalışma zamanında parametre değerlerini geçirme  
 Çağırmadan önce parametre değerlerini belirtmelisiniz **açık** (için yeni bir kayıt kümesi nesnesi) veya **Requery** (için mevcut bir).  
  
#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>Parametre değerleri için bir kayıt kümesi nesnesi çalışma zamanında geçirmek için  
  
1.  Kayıt kümesi nesnesi oluşturun.  
  
2.  Bir dize veya dize gibi hazırlama **m_strFilter** SQL deyimi veya bazı bölümleri içeren dize. PUT "?" yer tutucuları olduğu parametre bilgilerini gidin.  
  
3.  Bir çalışma zamanı parametre değeri, her nesne parametre veri üyesi atayın.  
  
4.  Çağrı **açık** üye işlevi (veya **Requery**, var olan bir kayıt kümesi için).  
  
 Örneğin, çalışma zamanında alınan bilgileri kullanarak kümeniz için filtre dizesini belirtmek istediğinizi varsayalım. Sınıfının bir kayıt oluşturulan varsayın `CStudentSet` önceki — adlı `rsStudents` — ve artık Öğrenci bilgileri belirli bir tür için requery istiyorsunuz.  
  
```  
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
  
 Kayıt kümesi kayıtlarını çalışma zamanı parametrelerinden oluşturulan Filtresi tarafından belirtilen koşullara uyan bu Öğrenciler için kayıtları içerir. Bu durumda, kayıt için tüm üst düzey Öğrenciler kayıtları içerir.  
  
> [!NOTE]
>  Gerekirse, parametre veri üyesinin değerini Null olarak ayarlayabilir kullanarak [SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull). Benzer şekilde bir parametre veri üyesi, Null olup olmadığını denetleyebilirsiniz kullanarak [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Kayıt kümesi: Nasıl kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)