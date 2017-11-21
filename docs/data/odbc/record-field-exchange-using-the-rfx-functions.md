---
title: "Kayıt Alanı Değişimi: RFX işlevlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6c330ee2f9d3952068e2a400cd8f6e23103dc20e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma
Bu konu gövdesini oluşturan RFX işlevi çağrılarının nasıl kullanılacağını açıklar, `DoFieldExchange` geçersiz kılar.  
  
> [!NOTE]
>  Bu konu, türetilen sınıflar için geçerlidir [CRecordset](../../mfc/reference/crecordset-class.md) toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (Toplu RFX) uygulanır. Toplu RFX RFX için benzer. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 RFX genel işlevleri veri kaynağını ve alan veri üyeleri kümenizin sütunlarda arasında veri değişimi. RFX işlev çağrılarını kümenizin içinde yazma [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevi. Bu konu işlevleri kısaca açıklar ve RFX işlevleri kullanılabilir veri türleri gösterir. [Teknik Not 43](../../mfc/tn043-rfx-routines.md) ek veri türleri için kendi RFX işlevleri yazılacağını açıklar.  
  
##  <a name="_core_rfx_function_syntax"></a>RFX işlev sözdizimi  
 Her RFX işlevi üç parametre alır (ve bazı isteğe bağlı bir dördüncü veya beşinci parametre alan):  
  
-   Bir işaretçi bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesi. Geçirirsiniz `pFX` işaretçi geçirilen `DoFieldExchange`.  
  
-   Veri kaynağı üzerinde şekliyle sütunun adı görüntülenir.  
  
-   Karşılık gelen alan veri üyesi veya parametre veri üyesi kayıt kümesi sınıfı adı.  
  
-   (İsteğe bağlı) Bazı işlevler, dize veya dizinin aktarılan en büyük uzunluğu. Bu 255 bayt varsayılan olarak, ancak bunu değiştirmek isteyebilirsiniz. En büyük boyutu en büyük boyutuna göre bir `CString` nesne — **INT_MAX** (2.147.483.647) bayt — ancak büyük olasılıkla bu boyuttan önce sürücü sınırlarıyla karşılaşacaksınız.  
  
-   (İsteğe bağlı) İçinde `RFX_Text` işlevi, bazen beşinci bir parametre bir sütunun veri türünü belirtmek için kullanın.  
  
 RFX işlevleri altında daha fazla bilgi için bkz: [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *sınıf kitaplığı başvurusu*. Ne zaman özel yapabileceğiniz bir örnek için parametrelerini kullanmak için bkz: [kayıt kümesi: SUM'ları alma ve diğer toplama sonuçlarını (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).  
  
##  <a name="_core_rfx_data_types"></a>RFX veri türleri  
 Sınıf kitaplığı veri kaynağını ve kümeleriniz arasında birçok farklı veri türleri aktarımı için RFX işlevleri sunar. Aşağıdaki liste, veri türüne göre RFX işlevlerini özetler. Burada, kendi RFX işlev çağrılarını yazmanız gereken durumlarda, bu işlevler veri türüne göre seçin.  
  
|İşlev|Veri türü|  
|--------------|---------------|  
|`RFX_Bool`|**BOOL**|  
|`RFX_Byte`|**BAYT**|  
|`RFX_Binary`|`CByteArray`|  
|`RFX_Double`|**çift**|  
|`RFX_Single`|**kayan nokta**|  
|`RFX_Int`|`int`|  
|`RFX_Long`|**uzun**|  
|`RFX_LongBinary`|`CLongBinary`|  
|`RFX_Text`|`CString`|  
|`RFX_Date`|`CTime`|  
  

 Daha fazla bilgi için altında RFX işlevi belgelerine bakın [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *sınıf kitaplığı başvurusu*. Tablonun ANSI SQL veri türleri eşlenen C++ veri türleri için C++ veri türleri SQL veri türleri ile nasıl eşleme hakkında daha fazla bilgi için bkz, [SQL: SQL ve C++ veri türleri (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [Kayıt Alanı Değişimi: RFX nasıl çalışır?](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Kayıt kümesi: kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Kayıt kümesi: Veri sütunlarını (ODBC) dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset sınıfı](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)