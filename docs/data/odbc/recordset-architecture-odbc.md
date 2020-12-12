---
description: 'Daha fazla bilgi: kayıt kümesi: mimari (ODBC)'
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
ms.openlocfilehash: 0a7be1104cf16f9cc11effac1cd4151749167436
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186135"
---
# <a name="recordset-architecture-odbc"></a>Kayıt kümesi: Mimari (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, bir kayıt kümesi nesnesinin mimarisini oluşturan veri üyelerini açıklar:

- [Alan veri üyeleri](#_core_field_data_members)

- [Parametre veri üyeleri](#_core_parameter_data_members)

- [M_nFields ve m_nParams veri üyelerini kullanma](#_core_using_m_nfields_and_m_nparams)

> [!NOTE]
> Bu konu, `CRecordset` toplu satır yakalamanın uygulanmadığı, öğesinden türetilmiş nesneler için geçerlidir. Toplu satır getirme uygulanmışsa, mimari benzerdir. Farkları anlamak için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="sample-class"></a><a name="_core_a_sample_class"></a> Örnek sınıf

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Sınıfından türetilmiş bir kayıt kümesi sınıfını bildirmek için **sınıf ekleme** Sihirbazı ' ndan [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 'nı kullandığınızda `CRecordset` , elde edilen sınıf aşağıdaki basit sınıfta gösterilen genel yapıya sahiptir:

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

Sınıfının başlangıcında, sihirbaz bir [alan veri üyeleri](#_core_field_data_members)kümesi yazar. Sınıfı oluşturduğunuzda bir veya daha fazla alan veri üyesi belirtmeniz gerekir. Sınıf parametreli ise, örnek sınıf olarak (veri üyesiyle birlikte `m_strIDParam` ), [parametre veri üyelerini](#_core_parameter_data_members)el ile eklemeniz gerekir. Sihirbaz bir sınıfa parametre eklemeyi desteklemez.

## <a name="field-data-members"></a><a name="_core_field_data_members"></a> Alan veri üyeleri

Kayıt kümesi sınıfınızın en önemli üyeleri alan veri üyeleridir. Veri kaynağından seçtiğiniz her sütun için, sınıfı ilgili sütun için uygun veri türünün bir veri üyesini içerir. Örneğin, bu konunun başlangıcında gösterilen [örnek sınıfta](#_core_a_sample_class) , ve adlı iki alan veri üyesi vardır `CString` `m_strCourseID` `m_strCourseTitle` .

Kayıt kümesi bir kayıt kümesi seçtiğinde, çerçeve otomatik olarak geçerli kaydın sütunlarını ( `Open` çağrıdan sonra ilk kayıt geçerli olur) nesnenin alan veri üyelerine bağlar. Diğer bir deyişle, çerçeve bir kayıt sütununun içeriğini depolamak için uygun alan veri üyesini bir arabellek olarak kullanır.

Kullanıcı yeni bir kayda kaydığında, çerçeve geçerli kaydı temsil etmek için alan veri üyelerini kullanır. Çerçeve, önceki kaydın değerlerini değiştirerek alan veri üyelerini yeniler. Alan veri üyeleri, geçerli kaydı güncelleştirmek ve yeni kayıtlar eklemek için de kullanılır. Bir kaydı güncelleştirme sürecinin bir parçası olarak, değerleri doğrudan uygun alan veri üyesine veya üyelerine atayarak güncelleştirme değerlerini belirtirsiniz.

## <a name="parameter-data-members"></a><a name="_core_parameter_data_members"></a> Parametre veri üyeleri

Sınıf parametreli ise, bir veya daha fazla parametre veri üyesine sahiptir. Parametreli bir sınıf, çalışma zamanında alınan veya hesaplanan bilgilere bir kayıt kümesi sorgusu temellendirmenizi sağlar.

Genellikle parametresi, aşağıdaki örnekte olduğu gibi seçimi daraltmaya yardımcı olur. Bu konunun başındaki [örnek sınıfa](#_core_a_sample_class) bağlı olarak, kayıt kümesi NESNESI şu SQL ifadesini yürütebilir:

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?
```

"?", Çalışma zamanında sağladığınız parametre değeri için bir yer tutucudur. Kayıt kümesini oluşturduğunuzda ve `m_strIDParam` veri ÜYESINI MATH101 olarak ayarlarsanız, kayıt kümesi için ETKIN SQL açıklaması şu şekilde olur:

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101
```

Parametre veri üyelerini tanımlayarak, çerçeveye SQL dizesindeki parametreler hakkında söylemiş olursunuz. Framework parametresini bağlar, bu da ODBC 'nin yer tutucu için değiştirilecek değerlerin nereden alınacağını bilmesini sağlar. Örnekte, elde edilen kayıt kümesi yalnızca Kurs tablosundan, değeri MATH101 olan bir CourseID sütunuyla kayıt içerir. Bu kaydın tüm belirtilen sütunları seçilidir. İhtiyaç duyduğunuz kadar fazla parametre (ve yer tutucu) belirtebilirsiniz.

> [!NOTE]
> MFC parametrelerle hiçbir şey yapmaz — özellikle de bir metin değişimi gerçekleştirmez. Bunun yerine, MFC ODBC 'yi parametrenin nereden alınacağını belirtir; ODBC, verileri alır ve gerekli parametrelemeyi gerçekleştirir.

> [!NOTE]
> Parametrelerin sırası önemlidir. Bu ve parametreler hakkında daha fazla bilgi için bkz. [kayıt kümesi: bir kayıt kümesini parametrize (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

## <a name="using-m_nfields-and-m_nparams"></a><a name="_core_using_m_nfields_and_m_nparams"></a> M_nFields ve m_nParams kullanma

Bir sihirbaz sınıfınız için bir Oluşturucu yazdığında, bu, sınıftaki [alan veri üyelerinin](#_core_field_data_members) sayısını belirten [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) veri üyesini de başlatır. Sınıfınıza herhangi bir [parametre](#_core_parameter_data_members) eklerseniz, parametre veri üyelerinin sayısını belirten [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) veri üyesine yönelik bir başlatma da eklemeniz gerekir. Framework, veri üyeleriyle çalışmak için bu değerleri kullanır.

Daha fazla bilgi ve örnek için bkz. [kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: tablo için sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
