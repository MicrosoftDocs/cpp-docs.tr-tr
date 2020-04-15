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
ms.openlocfilehash: f1afded360cfeff564f1f3d8bb9b294aa33cb733
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367125"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma

Bu konu, `DoFieldExchange` geçersiz kılmanın gövdesini oluşturan RFX işlev çağrılarının nasıl kullanılacağını açıklar.

> [!NOTE]
> Bu konu, toplu satır alma nın uygulanmadığı [CRecordset'ten](../../mfc/reference/crecordset-class.md) türetilen sınıflar için geçerlidir. Toplu satır alma kullanıyorsanız, toplu kayıt alanı değişimi (Toplu RFX) uygulanır. Toplu RFX RFX benzer. Farklılıkları anlamak için bkz: [Recordset: Kayıtları Toplu Olarak Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX global işlevleri, kayıt setinizdeki veri kaynağı ndaki sütunlar ve alan veri üyeleri arasında veri alışverişi sağlar. Kayıt setinizin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevine RFX işlevi çağrılarını yazarsınız. Bu konu işlevleri kısaca açıklar ve RFX işlevlerinin kullanılabilir olduğu veri türlerini gösterir. [Teknik Not 43,](../../mfc/tn043-rfx-routines.md) ek veri türleri için kendi RFX işlevlerinizi nasıl yazılacınız gerektiğini açıklar.

## <a name="rfx-function-syntax"></a><a name="_core_rfx_function_syntax"></a>RFX İşlev Sözdizimi

Her RFX işlevi üç parametre alır (ve bazıları isteğe bağlı dördüncü veya beşinci parametre alır):

- [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesine işaretçi. Sadece `pFX` işaretçi boyunca geçti `DoFieldExchange`.

- Veri kaynağında görünen sütunun adı.

- Recordset sınıfında ilgili alan veri üyesinin veya parametre veri üyesinin adı.

- (İsteğe bağlı) Bazı işlevlerde, aktarılan dize veya dizinin maksimum uzunluğu. Bu varsayılan olarak 255 bayt adede edir, ancak değiştirmek isteyebilirsiniz. Maksimum boyut, bir `CString` nesnenin **(INT_MAX** (2.147.483.647) baytların maksimum boyutuna dayanır, ancak bu boyuttan önce büyük olasılıkla sürücü sınırlarıyla karşılaşırsınız.

- (İsteğe bağlı) İşlevde, `RFX_Text` bazen bir sütunun veri türünü belirtmek için beşinci bir parametre kullanırsınız.

Daha fazla bilgi için *Sınıf Kitaplığı Başvurusu'nda* [Makrolar ve Globaller](../../mfc/reference/mfc-macros-and-globals.md) altında RFX işlevlerine bakın. Parametreleri ne zaman özel olarak kullanabileceğinize bir örnek olarak, [bkz.](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

## <a name="rfx-data-types"></a><a name="_core_rfx_data_types"></a>RFX Veri Türleri

Sınıf kitaplığı, veri kaynağı ve kayıt kümeleriniz arasında birçok farklı veri türü aktarmak için RFX işlevleri sağlar. Aşağıdaki liste, RFX işlevlerini veri türüne göre özetlemektedir. Kendi RFX fonksiyon çağrılarınızı yazmanız gereken durumlarda, bu işlevlerden veri türüne göre seçim inizi verin.

|İşlev|Veri türü|
|--------------|---------------|
|`RFX_Bool`|**Bool**|
|`RFX_Byte`|**BYTE**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**float**|
|`RFX_Int`|**int**|
|`RFX_Long`|**long**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|

Daha fazla bilgi için *Sınıf Kitaplığı Başvurusu'nda* [Makrolar ve Globaller](../../mfc/reference/mfc-macros-and-globals.md) altındaki RFX işlev belgelerine bakın. C++ veri türlerinin SQL veri türleri ile nasıl eşleştiği hakkında bilgi için, [SQL: SQL ve C++ Veri Türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)tablosuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Kayıt Alanı Değişimi: RFX'in Çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CfieldExchange Sınıfı](../../mfc/reference/cfieldexchange-class.md)
