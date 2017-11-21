---
title: "Kayıt kümesi: Mimari (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1846426caf759dfc2cce7e6b2e9177ddb4c6b12d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recordset-architecture-odbc"></a>Kayıt kümesi: Mimari (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda, bir kayıt kümesi nesnesi mimarisini oluşturan veri üyeleri açıklanmaktadır:  
  
-   [Alan veri üyeleri](#_core_field_data_members)  
  
-   [Parametre veri üyeleri](#_core_parameter_data_members)  
  
-   [M_nFields ve m_nParams veri üyelerini kullanma](#_core_using_m_nfields_and_m_nparams)  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme uygulanmışsa, benzer bir mimaridir. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_a_sample_class"></a>Örnek sınıfı  
 Kullandığınızda [MFC ODBC Tüketici Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) gelen **sınıfı Ekle** bir kayıt kümesi sınıfı bildirmek için Sihirbazı türetilen `CRecordset`, sonuçta elde edilen sınıf, aşağıda basit gösterildiği genel yapısının sınıfı:  
  
```  
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
  
 Sınıf başlangıcında, sihirbaz kümesi Yazar [alan veri üyeleri](#_core_field_data_members). Sınıfı oluşturduğunuzda, bir veya daha fazla alan veri üyeleri belirtmeniz gerekir. Sınıf parametreli, örnek olarak sınıftır (veri üyesi ile `m_strIDParam`), el ile eklemeniz gerekir [parametre veri üyeleri](#_core_parameter_data_members). Sihirbaz, bir sınıf parametreler eklemeyi desteklemez.  
  
##  <a name="_core_field_data_members"></a>Alan veri üyeleri  
 En önemli kayıt kümesi sınıfınız alan veri üyeleri üyeleridir. Veri kaynağından seçtiğiniz her sütun için uygun veri türünü bu sütun için veri üyesini sınıfı içerir. Örneğin, [örnek sınıf](#_core_a_sample_class) bu başında gösterilen konu sahip iki alan veri üyeleri, her iki tür `CString`adlı `m_strCourseID` ve `m_strCourseTitle`.  
  
 Kayıt kümesi bir kayıt kümesini seçtiğinde, çerçeve otomatik olarak geçerli kayıt sütunlarının bağlar (sonra **açık** çağrısı, ilk kaydı geçerli) nesne alan veri üyeleri için. Diğer bir deyişle, çerçeve kaydı sütunun içeriğine depolanacağı bir arabellek olarak uygun alan veri üyesi kullanır.  
  
 Kullanıcı yeni bir kayda kayarken çerçeve alan veri üyeleri geçerli kaydı temsil etmek için kullanır. Framework önceki kaydın değerleri değiştirerek alan veri üyeleri yeniler. Alan veri üyeleri geçerli kaydı güncelleştirmek ve yeni kayıtları eklemek için de kullanılır. Kayıt güncelleştirme işleminin bir parçası olarak, doğrudan uygun alan veri üyesi veya üyeleri değerler atayarak güncelleştirme değerlerini belirtin.  
  
##  <a name="_core_parameter_data_members"></a>Parametre veri üyeleri  
 Sınıf parametreli bir veya daha fazla parametre veri üyeleri yoktur. Parametreli bir sınıf, bir kayıt kümesi sorgusunu çalışma zamanında hesaplanan veya alınan bilgileri temel sağlar.  
  
 Genellikle, parametre aşağıdaki örnekteki gibi seçimi daraltmaya yardımcı olur. Temel [örnek sınıf](#_core_a_sample_class) bu konunun başındaki kayıt kümesi nesnesi aşağıdaki SQL deyimi yürütülemiyor:  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?  
```  
  
 "?" Çalışma zamanında sağladığınız bir parametre değeri için bir yer tutucudur. Kayıt kümesi oluşturmak zaman ve kendi `m_strIDParam` kayıt kümesi için etkili SQL deyimi veri üyesi MATH101 olur:  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101  
```  
  
 Parametre veri üyeleri tanımlayarak framework SQL dizesi parametrelerinde hakkında verin. Framework yerine değerler için yer tutucu nereden ODBC sağlayan parametreyi bağlar. Örnekte, sonuçta elde edilen kayıt kümesi yalnızca MATH101 değeri olan CourseID sütunu indirmelere tablosundan kaydı içerir. Bu kaydın belirtilen tüm sütunları seçilir. Sayıda parametre (ve yer tutucular) belirtebilirsiniz gerektiği.  
  
> [!NOTE]
>  MFC yapmaz kendisini parametrelerle — özellikle, bir metin değiştirme gerçekleştirmez. Bunun yerine, MFC ODBC parametresi alınacağı söyler; ODBC verileri alır ve gerekli parametrelemeyi gerçekleştirir.  
  
> [!NOTE]
>  Parametreler sırası önemlidir. Bu konu hakkında bilgi ve parametreleri hakkında daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
##  <a name="_core_using_m_nfields_and_m_nparams"></a>M_nFields ve m_nParams kullanma  

 Sihirbaz, sınıf için bir oluşturucu yazdığında, aynı zamanda başlatır [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) sayısını belirtir veri üyesi [alan veri üyeleri](#_core_field_data_members) sınıfında. Herhangi bir eklerseniz [parametreleri](#_core_parameter_data_members) sınıfı, bir başlatma için de eklemelisiniz [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) parametre veri üyeleri sayısını belirtir veri üyesi. Çerçeve veri üyeleri ile çalışmak için bu değerleri kullanır.  
  
 Daha fazla bilgi ve örnekler için bkz: [kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: bir sınıf bir tablo için bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)