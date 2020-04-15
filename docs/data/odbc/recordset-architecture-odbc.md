---
title: 'Kayıt kümesi: Mimari (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, data members
- field data members, recordset architecture
- field data members
- m_nParams data member, recordsets
- recordsets, architecture
- parameter data members in recordsets
- m_nFields data member
- ODBC recordsets, architecture
- m_nParams data member
- m_nFields data member, recordsets
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
ms.openlocfilehash: 3ed6a862cda769769cd07d2dcd72007292068dc3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367091"
---
# <a name="recordset-architecture-odbc"></a>Kayıt kümesi: Mimari (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, kayıt kümesi nesnesinin mimarisini oluşturan veri üyelerini açıklar:

- [Alan veri üyeleri](#_core_field_data_members)

- [Parametre veri üyeleri](#_core_parameter_data_members)

- [m_nFields ve m_nParams veri üyelerini kullanma](#_core_using_m_nfields_and_m_nparams)

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı türetilen nesneler için geçerlidir. Toplu satır alma uygulanıyorsa, mimari benzer. Farklılıkları anlamak için bkz: [Recordset: Kayıtları Toplu Olarak Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="sample-class"></a><a name="_core_a_sample_class"></a>Örnek Sınıf

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Yine de bir tüketiciyi el ile oluşturabilirsiniz.

**Sınıf Ekle** sihirbazından [MFC ODBC Tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md) Sihirbazı'nı türetilen `CRecordset`bir kayıt kümesi sınıfını bildirmek için kullandığınızda, ortaya çıkan sınıf aşağıdaki basit sınıfta gösterilen genel yapıya sahiptir:

```cpp
class CCourse : public CRecordset
{
public:
   CCourse(CDatabase* pDatabase = NULL);
   ...
   CString m_strCourseID;
   CString m_strCourseTitle;
   CString m_strIDParam;
};
```

Sınıfın başında, sihirbaz [alan veri üyeleri](#_core_field_data_members)kümesi yazar. Sınıfı oluştururken, bir veya daha fazla alan veri üyesi belirtmeniz gerekir. Sınıf parametreliyse, örnek sınıf (veri üyesiyle `m_strIDParam`birlikte) [olarak, parametre veri üyelerini](#_core_parameter_data_members)el ile eklemeniz gerekir. Sihirbaz, sınıfa parametre eklemeyi desteklemez.

## <a name="field-data-members"></a><a name="_core_field_data_members"></a>Alan Veri Üyeleri

Kayıt kümesi sınıfınızın en önemli üyeleri alan veri üyeleridir. Veri kaynağından seçtiğiniz her sütun için, sınıf o sütun için uygun veri türünden bir veri üyesi içerir. Örneğin, bu konunun başında gösterilen [örnek sınıf](#_core_a_sample_class) iki alan veri `CString`üyesi `m_strCourseID` vardır, her ikisi de türü , denir ve `m_strCourseTitle`.

Kayıt kümesi bir kayıt kümesi seçtiğinde, çerçeve geçerli kaydın sütunlarını (çağrıdan `Open` sonra, ilk kayıt geçerlidir) nesnenin alan veri üyelerine otomatik olarak bağlar. Diğer bir deyişle, çerçeve, bir kayıt sütununun içeriğini depolamak için bir arabellek olarak uygun alan veri üyesi kullanır.

Kullanıcı yeni bir kayda kaydırılırken, çerçeve geçerli kaydı temsil etmek için alan veri üyelerini kullanır. Çerçeve, önceki kaydın değerlerini değiştirerek alan veri üyelerini yeniler. Alan verileri üyeleri, geçerli kaydı güncelleştirmek ve yeni kayıtlar eklemek için de kullanılır. Bir kaydı güncelleştirme işleminin bir parçası olarak, değerleri doğrudan uygun alan veri üyesine veya üyelerine atayarak güncelleştirme değerlerini belirtirsiniz.

## <a name="parameter-data-members"></a><a name="_core_parameter_data_members"></a>Parametre Veri Üyeleri

Sınıf parametreliise, bir veya daha fazla parametre veri üyesi vardır. Parametreli sınıf, kayıt kümesi sorgusunu çalışma zamanında elde edilen veya hesaplanan bilgilere dayandırmama nızı sağlar.

Genellikle, parametre aşağıdaki örnekte olduğu gibi seçimi daraltma yardımcı olur. Bu konunun başındaki [örnek sınıfa](#_core_a_sample_class) bağlı olarak, kayıt kümesi nesnesi aşağıdaki SQL deyimini yürütebilir:

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?
```

"?" çalışma zamanında sağladığınız bir parametre değeri için bir yer tutucudur. Kayıt kümesini oluşturup veri `m_strIDParam` üyesini MATH101 olarak ayarladığınızda, kayıt kümesiiçin etkili SQL deyimi şu olur:

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101
```

Parametre veri üyelerini tanımlayarak, çerçeveyi SQL dizesindeki parametreler hakkında anlatırsınız. Çerçeve, ODBC'nin yer tutucunun yerine hangi değerleri alacağını bilmesini sağlayan parametreyi bağlar. Örnekte, ortaya çıkan kayıt kümesi yalnızca Ders TABLOSUndan değeri MATH101 olan Bir Ders Kimliği sütununa sahip kaydı içerir. Bu kaydın belirtilen tüm sütunları seçilir. İhtiyaç duyduğunuz kadar parametre (ve yer tutucu) belirtebilirsiniz.

> [!NOTE]
> MFC parametreleri ile kendisi hiçbir şey yapmaz - özellikle, bir metin ikame gerçekleştirmez. Bunun yerine, MFC ODBC'ye parametreyi nereden alacağını söyler; ODBC verileri alır ve gerekli parametrelendirmeyi gerçekleştirir.

> [!NOTE]
> Parametrelerin sırası önemlidir. Bu ve parametreler hakkında daha fazla bilgi için Kayıt [Kümesi: Bir Kayıt Kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)'ye bakın.

## <a name="using-m_nfields-and-m_nparams"></a><a name="_core_using_m_nfields_and_m_nparams"></a>m_nFields ve m_nParams kullanma

Bir sihirbaz sınıfınız için bir oluşturucu yazarsa, sınıftaki alan veri üye sayısını belirten [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) veri [üyesini](#_core_field_data_members) de başlatAbıdır. Sınıfınıza herhangi bir [parametre](#_core_parameter_data_members) eklerseniz, [parametre](../../mfc/reference/crecordset-class.md#m_nparams) veri üye sayısını belirten m_nParams veri üyesi için de bir başlatma eklemeniz gerekir. Çerçeve, veri üyeleriyle çalışmak için bu değerleri kullanır.

Daha fazla bilgi ve örnekler için [Bkz. Alan Değişimi Kaydet: RFX kullanma.](../../data/odbc/record-field-exchange-using-rfx.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
