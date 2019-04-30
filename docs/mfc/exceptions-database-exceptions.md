---
title: 'Özel durumlar: Veritabanı Özel Durumları'
ms.date: 11/04/2016
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
ms.openlocfilehash: 2f7f3bff9f28968361ecfa7374a235a727443004
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405904"
---
# <a name="exceptions-database-exceptions"></a>Özel durumlar: Veritabanı Özel Durumları

Bu makalede, veritabanı özel durumları işlemek açıklanmaktadır. Bu makalede malzeme çoğunu, MFC sınıfları ile açık veritabanı bağlantısı (ODBC) veya MFC sınıfları için veri erişim nesneleri (DAO) çalışıp çalışmadığını geçerlidir. Bir veya başka bir model için belirli bir malzeme açıkça işaretlenmiştir. Konular şunlardır:

- [Özel durum işleme yaklaşımları](#_core_approaches_to_exception_handling)

- [Bir veritabanı özel durum işleme örneği](#_core_a_database_exception.2d.handling_example)

##  <a name="_core_approaches_to_exception_handling"></a> Özel durum işleme yaklaşımları

DAO veya ODBC ile çalışıyor olmanızdan yaklaşım aynıdır.

Her zaman özel durumları işlemek için özel durum işleyicileri yazmanız gerekir.

Veritabanı özel durumları yakalama en kolay yaklaşım, uygulamanızın özel durum senaryoları ile test etmektir. Kodunuzda bir işlem için oluşur ve özel durum ortaya zorla olası özel durumları belirleyin. Daha sonra hangi özel durum görmek için izleme çıktıyı inceleyin veya hata ayıklayıcı döndürülen hata bilgileri inceleyin. Bu, dönüş kodları için kullanmakta olduğunuz özel durum senaryoları görürsünüz bilmenizi sağlar.

### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC özel durumları için kullanılan hata kodları

Framework tarafından tanımlanan dönüş kodları yanı sıra olan form adlarını **AFX_SQL_ERROR_XXX**, bazı [CDBExceptions](../mfc/reference/cdbexception-class.md) dayalı [ODBC](../data/odbc/odbc-basics.md) dönüş kodları. Bu tür özel durumlar için dönüş kodları adlarında formun **SQL_ERROR_XXX**.

Dönüş kodları — çerçeve tarafından tanımlanmış hem ODBC tanımlı — veritabanı sınıfları altında belgelenir döndürebilir [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) sınıfı veri üyesi `CDBException`. ODBC SDK'da ODBC tarafından tanımlanan dönüş kodları hakkında ek bilgi kullanılabilir *Programcının Başvurusu* MSDN Kitaplığı'nda.

### <a name="error-codes-used-for-dao-exceptions"></a>DAO özel durumlar için kullanılan hata kodları

DAO özel durumlar için daha fazla bilgi genellikle kullanılabilir. Üç veri üyelerinin bir yakalanan hata bilgilerini erişebileceğiniz [CDaoException](../mfc/reference/cdaoexception-class.md) nesnesi:

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) bir işaretçi içeren bir [Cdaoerrorınfo](../mfc/reference/cdaoerrorinfo-structure.md) veritabanıyla ilişkili hata nesnelerin DAO'ın koleksiyondaki hata bilgileri yalıtan nesne.

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) MFC DAO sınıflarına bir genişletilmiş hata kodu içerir. Adlarında ilgili daha fazla bilgi formu, bu hata kodları **AFX_DAO_ERROR_XXX**, veri üyesi altında belgelenen `CDaoException`.

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) OLE içeren **SCODE** DAO varsa. Nadiren, ancak bu hata kodu ile çalışmak gerekir. Genellikle diğer iki veri üyeleri daha fazla bilgi mevcuttur. Hakkında daha fazla bilgi için veri üyesi bakın **SCODE** değerleri.

DAO hataları, DAO hata nesne türü ve DAO hatalar koleksiyonuna hakkında ek bilgi sınıfı altında kullanılabilir [CDaoException](../mfc/reference/cdaoexception-class.md).

##  <a name="_core_a_database_exception.2d.handling_example"></a> Bir veritabanı özel durum işleme örneği

Aşağıdaki örnek oluşturmak çalışır bir [CRecordset](../mfc/reference/crecordset-class.md)-ile yığında nesne türetilmiş **yeni** işleci ve kayıt kümesi (ODBC veri kaynağında) açın. DAO sınıfları için benzer bir örnek için "DAO özel durum" aşağıdaki örneğe bakın.

### <a name="odbc-exception-example"></a>ODBC özel durumu örneği

[Açık](../mfc/reference/crecordset-class.md#open) üye işlevi bir özel durum oluşturur (tür [CDBException](../mfc/reference/cdbexception-class.md) ODBC sınıfları için), bu nedenle bu kod ayraç `Open` çağıran bir **deneyin** blok. Sonraki **catch** catch bloğu bir `CDBException`. Çağrılan özel durum nesne kendisine inceleyin `e`, ancak bu durumda bir kayıt kümesi oluşturma girişimi başarısız olduğunu bilmeniz yeterlidir. **Catch** blok bir ileti kutusu görüntüler ve kayıt kümesi nesnesi silerek temizler.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>DAO özel durumu örneği

DAO örnek ODBC için örneğe benzer, ancak genellikle daha fazla tür bilgileri alabilirsiniz. Aşağıdaki kod da bir kayıt kümesi açmayı dener. Bu girişim bir özel durum oluşturursa, özel durum nesnesi hata bilgileri için veri üyesi inceleyebilirsiniz. Büyük olasılıkla önceki ODBC örnekte olduğu gibi bir kayıt kümesi oluşturma girişimi başarısız olduğunu bilmek yeterli.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Bu kod bir hata iletisi dizeden alır [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) özel durum nesnesi bir üyesi. MFC özel durum oluşturur, bu üye doldurur.

Tarafından döndürülen hata bilgileri hakkında ayrıntılı bilgi için bir `CDaoException` nesne, sınıflara bakın [CDaoException](../mfc/reference/cdaoexception-class.md) ve [Cdaoerrorınfo](../mfc/reference/cdaoerrorinfo-structure.md).

ODBC ile çalışırken, Microsoft Jet (.mdb) veritabanlarında ve çoğu durumda çalışırken, yalnızca bir hata nesnesi olur. Nadir durumlarda ODBC veri kaynağını kullanan ve birden çok hata yoksa, DAO'ın hatalar koleksiyonuna tarafından döndürülen hataları sayısına bağlı döngü [CDaoException::GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount). Döngü, her zaman çağrı [CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) puanı almak için `m_pErrorInfo` veri üyesi.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
