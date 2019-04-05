---
title: 'Kayıt Alanı Değişimi: RFX işlevlerini kullanma'
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
ms.openlocfilehash: dc717336a5279e7eda1b7c39b19a7c76f9055cd3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035990"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Kayıt Alanı Değişimi: RFX işlevlerini kullanma

Bu konuda, gövdesini oluşturan RFX işlev çağrıları kullanmayı açıklar, `DoFieldExchange` geçersiz kılar.

> [!NOTE]
>  Bu konu, türetilen sınıflar için geçerlidir. [CRecordset](../../mfc/reference/crecordset-class.md) toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (Bulk RFX) uygulanır. Toplu RFX RFX için benzerdir. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX genel işlevleri, veri kaynağını ve alan veri üyeleri kümenizde sütunlarda arasında veri değişimi. RFX işlev çağrılarını kümenizin içinde yazdığınız [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevi. Bu konu, işlevleri kısaca açıklar ve RFX işlevleri kullanılabilir veri türlerini gösterir. [Teknik Not 43](../../mfc/tn043-rfx-routines.md) nasıl ek veri türleri için kendi RFX işlevleri yazılacağını açıklar.

##  <a name="_core_rfx_function_syntax"></a> RFX işlev sözdizimi

Her RFX işlevi üç parametre alır (ve bazı isteğe bağlı dördüncü veya beşinci parametrenin yapın):

- Bir işaretçi bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesne. Geçirirsiniz `pFX` işaretçi geçirildi `DoFieldExchange`.

- Veri kaynağında haliyle sütunun adı görüntülenir.

- Karşılık gelen alan veri üyesi veya parametre veri üyesi kayıt kümesi sınıfı adı.

- (İsteğe bağlı) Bazı işlevler, dize veya dizi aktarılan uzunluğunun üst sınırı. Bu 255 bayt için varsayılan olarak, ancak bunu değiştirmek isteyebilirsiniz. En büyük boyutu en büyük boyutuna bağlı bir `CString` nesne — **INT_MAX** (2.147.483.647) bayt — ancak büyük olasılıkla bu boyut önce sürücü sınırları karşılaşacaksınız.

- (İsteğe bağlı) İçinde `RFX_Text` işlevi, bazen beşinci parametrenin bir sütunun veri türünü belirtmek için kullanın.

Daha fazla bilgi için bkz. altında RFX işlevleri [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *sınıf kitaplığı başvurusu*. Parametreleri zaman özel yapabileceğiniz örneği için bkz [kayıt kümesi: SUM'ları ve diğer toplama sonuçlarını (ODBC) alma](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).

##  <a name="_core_rfx_data_types"></a> RFX veri türleri

Sınıf kitaplığı, birçok farklı veri türleri kümeleriniz ve veri kaynağı arasında aktarılması RFX işlevleri sağlar. Aşağıdaki listede, veri türüne göre RFX işlevleri özetlenmiştir. Burada kendi RFX işlev çağrıları yazmanız gereken durumlarda, bu işlevler, veri türüne göre seçin.

|İşlev|Veri türü|
|--------------|---------------|
|`RFX_Bool`|**BOOL**|
|`RFX_Byte`|**BYTE**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**çift**|
|`RFX_Single`|**float**|
|`RFX_Int`|**int**|
|`RFX_Long`|**long**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|


Daha fazla bilgi için bkz. altında RFX işlev belgelerine [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *sınıf kitaplığı başvurusu*. Tablonun ANSI SQL veri türleri eşlenen C++ veri türleri için C++ veri türleri SQL veri türleriyle nasıl eşleştiği hakkında daha fazla bilgi için bkz, [SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Kayıt Alanı Değişimi: RFX'in çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Kayıt kümesi: (ODBC) bir kayıt kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Kayıt kümesi: (ODBC) veri sütunlarını dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)