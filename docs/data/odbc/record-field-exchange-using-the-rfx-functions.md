---
description: 'Daha fazla bilgi edinin: kayıt alanı değişimi: RFX Işlevlerini kullanma'
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
ms.openlocfilehash: 8b597a6ca8ae43922b6bba57b63ea2fc93fb82d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298766"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma

Bu konuda, geçersiz kılmanın gövdesini oluşturan RFX işlev çağrılarının nasıl kullanılacağı açıklanmaktadır `DoFieldExchange` .

> [!NOTE]
> Bu konu, toplu satır yakalamanın uygulanmadığı [CRecordset](../../mfc/reference/crecordset-class.md) ' ten türetilmiş sınıflar için geçerlidir. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (toplu RFX) uygulanır. Toplu RFX, RFX 'e benzerdir. Farkları anlamak için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX genel işlevleri, veri kaynağındaki sütunlar ve kayıt kümenizin veri üyeleri arasındaki verileri değiş tokuş ediyor. RFX işlev çağrılarını kayıt kümenizin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevine yazarsınız. Bu konu, işlevleri kısaca açıklar ve RFX işlevlerinin kullanılabildiği veri türlerini gösterir. [Teknik not43](../../mfc/tn043-rfx-routines.md) ek veri türleri IÇIN kendi RFX işlevlerinizi nasıl yazacağınız açıklanmaktadır.

## <a name="rfx-function-syntax"></a><a name="_core_rfx_function_syntax"></a> RFX Işlevi sözdizimi

Her RFX işlevi üç parametre alır (bazıları isteğe bağlı dördüncü veya beşinci bir parametre alır):

- [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Yalnızca geçirilen işaretçi üzerinde geçiş yaparsınız `pFX` `DoFieldExchange` .

- Sütunun veri kaynağında göründüğü haliyle adı.

- Kayıt kümesi sınıfındaki karşılık gelen alan veri üyesinin veya parametre veri üyesinin adı.

- Seçim Bazı işlevlerde, aktarılmakta olan dize veya dizinin uzunluk üst sınırı. Bu varsayılan değer 255 bayttır, ancak bunu değiştirmek isteyebilirsiniz. En büyük boyut, en büyük bir `CString` nesne boyutunu ( **INT_MAX** (2.147.483.647) bayt) temel alır, ancak büyük olasılıkla bu boyuttan önce sürücü limitleriyle karşılaşacaksınız.

- Seçim `RFX_Text` İşlevinde bazen bir sütunun veri türünü belirtmek için beşinci bir parametre kullanırsınız.

Daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [makrolar ve genel](../../mfc/reference/mfc-macros-and-globals.md) öğeler altındaki RFX işlevleri. Parametreleri özel olarak kullanarak ilgili bir örnek için bkz. [kayıt kümesi: toplamları ve diğer toplama sonuçlarını alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).

## <a name="rfx-data-types"></a><a name="_core_rfx_data_types"></a> RFX veri türleri

Sınıf kitaplığı, veri kaynağı ve kayıt kümeleriniz arasında birçok farklı veri türünü aktarmaya yönelik RFX işlevlerini sağlar. Aşağıdaki liste, RFX işlevlerini veri türüne göre özetler. Kendi RFX işlevi çağrılarınızı yazmanız gereken durumlarda, veri türüne göre bu işlevlerden birini seçin.

|İşlev|Veri türü|
|--------------|---------------|
|`RFX_Bool`|**BOOL**|
|`RFX_Byte`|**BYTE**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**`double`**|
|`RFX_Single`|**`float`**|
|`RFX_Int`|**`int`**|
|`RFX_Long`|**`long`**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|

Daha fazla bilgi için, *sınıf kitaplığı başvurusunda* [makrolar ve Globals](../../mfc/reference/mfc-macros-and-globals.md) altındaki RFX işlevi belgelerine bakın. C++ veri türleri 'nin SQL veri türleriyle nasıl eşlendiğine ilişkin bilgiler için [SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)Içindeki c++ veri türlerine EŞLENMIŞ tablo ANSI SQL veri türleri başlığına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Kayıt alanı değişimi: RFX 'in çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Kayıt kümesi: bir kayıt kümesini Parametreleştirirken (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Kayıt kümesi: veri sütunlarını dinamik olarak bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)
