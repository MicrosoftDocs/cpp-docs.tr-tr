---
title: 'Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
ms.openlocfilehash: a54dbc10e80e19f744bb58c23639a4376156d2e7
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077087"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma

Bu konuda, `DoFieldExchange` geçersiz kılmanın gövdesini oluşturan RFX işlev çağrılarının nasıl kullanılacağı açıklanmaktadır.

> [!NOTE]
>  Bu konu, toplu satır yakalamanın uygulanmadığı [CRecordset](../../mfc/reference/crecordset-class.md) ' ten türetilmiş sınıflar için geçerlidir. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (toplu RFX) uygulanır. Toplu RFX, RFX 'e benzerdir. Farkları anlamak için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX genel işlevleri, veri kaynağındaki sütunlar ve kayıt kümenizin veri üyeleri arasındaki verileri değiş tokuş ediyor. RFX işlev çağrılarını kayıt kümenizin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevine yazarsınız. Bu konu, işlevleri kısaca açıklar ve RFX işlevlerinin kullanılabildiği veri türlerini gösterir. [Teknik not43](../../mfc/tn043-rfx-routines.md) ek veri türleri IÇIN kendi RFX işlevlerinizi nasıl yazacağınız açıklanmaktadır.

##  <a name="rfx-function-syntax"></a><a name="_core_rfx_function_syntax"></a>RFX Işlevi sözdizimi

Her RFX işlevi üç parametre alır (bazıları isteğe bağlı dördüncü veya beşinci bir parametre alır):

- [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Yalnızca `DoFieldExchange`geçirilen `pFX` işaretçi üzerinde geçiş yaparsınız.

- Sütunun veri kaynağında göründüğü haliyle adı.

- Kayıt kümesi sınıfındaki karşılık gelen alan veri üyesinin veya parametre veri üyesinin adı.

- Seçim Bazı işlevlerde, aktarılmakta olan dize veya dizinin uzunluk üst sınırı. Bu varsayılan değer 255 bayttır, ancak bunu değiştirmek isteyebilirsiniz. En büyük boyut, `CString` nesnenin en büyük boyutunu temel alır — **INT_MAX** (2.147.483.647) bayt), ancak büyük olasılıkla bu boyuttan önce sürücü limitleriyle karşılaşacaksınız.

- Seçim `RFX_Text` işlevinde bazen bir sütunun veri türünü belirtmek için beşinci bir parametre kullanırsınız.

Daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [makrolar ve genel](../../mfc/reference/mfc-macros-and-globals.md) öğeler altındaki RFX işlevleri. Parametreleri özel olarak kullanarak ilgili bir örnek için bkz. [kayıt kümesi: toplamları ve diğer toplama sonuçlarını alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).

##  <a name="rfx-data-types"></a><a name="_core_rfx_data_types"></a>RFX veri türleri

Sınıf kitaplığı, veri kaynağı ve kayıt kümeleriniz arasında birçok farklı veri türünü aktarmaya yönelik RFX işlevlerini sağlar. Aşağıdaki liste, RFX işlevlerini veri türüne göre özetler. Kendi RFX işlevi çağrılarınızı yazmanız gereken durumlarda, veri türüne göre bu işlevlerden birini seçin.

|İşlev|Veri türü|
|--------------|---------------|
|`RFX_Bool`|**BOOL**|
|`RFX_Byte`|**BAYT**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**float**|
|`RFX_Int`|**int**|
|`RFX_Long`|**long**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|

Daha fazla bilgi için, *sınıf kitaplığı başvurusunda* [makrolar ve Globals](../../mfc/reference/mfc-macros-and-globals.md) altındaki RFX işlevi belgelerine bakın. Veri türlerinin SQL veri C++ türleri ile nasıl eşlendiğine ilişkin bilgiler Için, SQL 'de C++ VERI TÜRLERINE eşlenmiş tablo ANSI SQL veri türleri [: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Kayıt Alanı Değişimi: RFX'in Çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange Sınıfı](../../mfc/reference/cfieldexchange-class.md)