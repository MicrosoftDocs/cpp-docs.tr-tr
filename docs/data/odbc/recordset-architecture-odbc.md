---
title: 'Kayıt kümesi: Mimari (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e868e51acf4c4e8f3975010509a0c97799b5e38c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082209"
---
# <a name="recordset-architecture-odbc"></a>Kayıt kümesi: Mimari (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konu, bir kayıt kümesi nesnesi mimarisi oluşturan veri üyelerini açıklar:

- [Alan veri üyeleri](#_core_field_data_members)

- [Parametre veri üyeleri](#_core_parameter_data_members)

- [M_nFields ve m_nParams veri üyelerini kullanma](#_core_using_m_nfields_and_m_nparams)

> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme uygulanmışsa, benzer bir mimaridir. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="_core_a_sample_class"></a> Örnek sınıfı

Kullandığınızda, [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) gelen **sınıfı Ekle** sınıfından türetilen bir kayıt kümesi sınıfı bildirmek için Sihirbazı `CRecordset`, sonuçta elde edilen sınıfında aşağıdaki basit gösterilen genel yapı sınıf:

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

Sınıfın başında, bir dizi sihirbaz Yazar [alan veri üyeleri](#_core_field_data_members). Sınıfı oluşturduğunuzda, bir veya daha fazla alan veri üyeleri belirtmeniz gerekir. Sınıf parametreli, örnek olarak sınıftır (veri üyesi ile `m_strIDParam`), el ile eklemelisiniz [parametre veri üyeleri](#_core_parameter_data_members). Sihirbaz bir sınıfa parametreler eklemeyi desteklemez.

##  <a name="_core_field_data_members"></a> Alan veri üyeleri

Kayıt kümesi sınıfının en önemli alan veri üyeleri üyesidir. Veri kaynağını seçin ve her sütun için söz konusu sütun için uygun veri türünün veri üyesi sınıfı içerir. Örneğin, [örnek sınıf](#_core_a_sample_class) bu başında gösterilen bölümüne sahip iki alan veri üyeleri, her iki tür `CString`adlı `m_strCourseID` ve `m_strCourseTitle`.

Kayıt kümesi bir kayıt kümesi seçtiğinde geçerli kayıtla sütunlar çerçeve otomatik olarak bağlar. (sonra `Open` çağrısının ilk kaydı şu anda) nesne alan veri üyeleri için. Diğer bir deyişle, çerçeve uygun alan veri üyesi kayıt sütunu içeriğini depolamak için bir arabellek olarak kullanır.

Kullanıcı için yeni bir kayıt kaydırma gibi framework alan veri üyeleri geçerli kayıt temsil etmek için kullanır. Framework önceki kaydın değerleri değiştirerek alan veri üyeleri yeniler. Alan veri üyeleri, yeni kayıtlar ekleme ve geçerli kaydı güncelleştirmek için de kullanılır. Bir kaydı güncelleştirme işleminin bir parçası, uygun alan veri üyesi veya üyeleri için değerlerin atayarak güncelleştirme değerlerini belirtin.

##  <a name="_core_parameter_data_members"></a> Parametre veri üyeleri

Sınıf parametreli bir veya daha fazla parametre veri üyeleri yoktur. Parametreli bir sınıf, bir kayıt kümesi sorgu zamanında hesaplanan veya alınan bilgileri temel sağlar.

Genellikle, parametre seçim, aşağıdaki örnekte olduğu gibi daraltmaya yardımcı olur. Temel [örnek sınıf](#_core_a_sample_class) bu konunun başında, kayıt kümesi nesnesi şu SQL ifadesini paralellikle çalışabilir:

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?
```

"?", Çalışma zamanında sağladığınız parametre değeri için bir yer tutucudur. Kayıt kümesi oluşturmak zaman ve kendi `m_strIDParam` kayıt kümesi için geçerli SQL deyimi veri üyesi MATH101 olur:

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101
```

Parametre veri üyeleri tanımlayarak SQL dizesi parametrelerinde framework anlatın. Framework ODBC için yer tutucu değerleri yerine nereden alacağını bilmesini sağlayan parametreyi bağlar. Örnekte, yalnızca kaydı kurs tablosundan MATH101 CourseID sütun değeri ile elde edilen kayıt kümesi içerir. Bu kaydın tüm belirtilen sütun seçilmedi. Kadar parametreleri (ve yer tutucular) belirtebilirsiniz gerektiği.

> [!NOTE]
>  MFC kendisini başka bir şey parametrelerle yapmaz; özellikle, bir metin değiştirme gerçekleştirmez. Bunun yerine, MFC ODBC parametrenin nereden bildirir; ODBC verileri alır ve gerekli parametrelemeyi gerçekleştirir.

> [!NOTE]
>  Parametreler sırası önemlidir. Bu konu hakkında bilgi ve parametreleri hakkında daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

##  <a name="_core_using_m_nfields_and_m_nparams"></a> M_nFields ve m_nParams kullanma

Bir sihirbaz sınıfınız için bir oluşturucu yazdığında, ayrıca başlatır [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) sayısını belirten veri üyesi [alan veri üyeleri](#_core_field_data_members) sınıfında. Tüm eklerseniz [parametreleri](#_core_parameter_data_members) sınıfınız için bir başlatma için de eklemelisiniz [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) veri üyesi, parametre veri üyeleri sayısını belirtir. Framework, veri üyeleri ile çalışmak için bu değerleri kullanır.

Daha fazla bilgi ve örnekler için bkz. [kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)