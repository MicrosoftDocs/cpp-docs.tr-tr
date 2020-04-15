---
title: 'Özel durumlar: Veritabanı Özel Durumları'
ms.date: 09/17/2019
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
ms.openlocfilehash: 894960338a7e8c293054ade00e0cdf3295648bb7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366621"
---
# <a name="exceptions-database-exceptions"></a>Özel durumlar: Veritabanı Özel Durumları

Bu makalede, veritabanı özel durumları nasıl işleyeceğini açıklar. Bu makaledeki materyallerin çoğu, Açık Veritabanı Bağlantısı (ODBC) veya Veri Erişim Nesneleri (DAO) için MFC sınıfları ile çalışıp çalışmadığınızı uygular. Bir veya diğer modele özgü malzeme açıkça işaretlenir. Konu başlıkları şunlardır:

- [Özel durum işleme yaklaşımları](#_core_approaches_to_exception_handling)

- [Veritabanı özel durum işleme örneği](#_core_a_database_exception.2d.handling_example)

## <a name="approaches-to-exception-handling"></a><a name="_core_approaches_to_exception_handling"></a>İstisna İşleme Yaklaşımları

Dao (eski) veya ODBC ile çalışıyor sanız yaklaşım aynıdır.

İstisnai koşulları işlemek için her zaman özel durum işleyicileri yazmalısınız.

Veritabanı özel durumlarını yakalamak için en pragmatik yaklaşım, uygulamanızı özel durum senaryoları ile sınamaktır. Kodunuzdaki bir işlem için oluşabilecek olası özel durumları belirleyin ve özel durumu oluşmaya zorlayın. Ardından, hangi özel durum atıldığını görmek için izleme çıktısını inceleyin veya hata ayıklayıcıda döndürülen hata bilgilerini inceleyin. Bu, kullanmakta olduğunuz özel durum senaryoları için hangi iade kodlarını göreceğinizi bilmenizi sağlar.

### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC Özel Durumları için Kullanılan Hata Kodları

**Form**un adlarını AFX_SQL_ERROR_XXX olan çerçeve tarafından tanımlanan iade kodlarına ek olarak, bazı [CDBException'lar](../mfc/reference/cdbexception-class.md) [ODBC](../data/odbc/odbc-basics.md) iade kodlarını temel almaktadır. Bu tür özel durumlar için iade kodları **SQL_ERROR_XXX**form adları var.

Veritabanı sınıflarının dönebileceği, hem çerçeve tanımlı hem de ODBC tanımlı [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) iade kodları `CDBException`sınıfın m_nRetCode veri üyesi altında belgelenmiştir. ODBC tarafından tanımlanan iade kodları hakkında ek bilgiler, MSDN Kitaplığı'ndaki ODBC SDK *Programcısı* Referansı'nda mevcuttur.

### <a name="error-codes-used-for-dao-exceptions"></a>DAO Özel Durumları için Kullanılan Hata Kodları

DAO özel durumları için genellikle daha fazla bilgi kullanılabilir. Yakalanan bir [CDaoException](../mfc/reference/cdaoexception-class.md) nesnesinin üç veri üyesi aracılığıyla hata bilgilerine erişebilirsiniz:

- [m_pErrorInfo,](../mfc/reference/cdaoexception-class.md#m_perrorinfo) DAO'nun veritabanıyla ilişkili hata nesneleri koleksiyonundaki hata bilgilerini kapsülleyen bir [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) nesnesine işaretçi içerir.

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) MFC DAO sınıflarından genişletilmiş bir hata kodu içerir. **form AFX_DAO_ERROR_XXX**adları olan bu hata kodları, `CDaoException`veri üyesi altında belgelenmiştir.

- [m_scode,](../mfc/reference/cdaoexception-class.md#m_scode) varsa DAO'dan bir OLE **SCODE** içerir. Ancak, bu hata koduyla nadiren çalışmanız gerekir. Genellikle diğer iki veri üyesinde daha fazla bilgi mevcuttur. **SCODE** değerleri hakkında daha fazla bilgi için veri üyesine bakın.

DAO hataları, DAO Hata nesne türü ve DAO Hataları koleksiyonu hakkında ek bilgiler [sınıf CDaoException](../mfc/reference/cdaoexception-class.md)altında kullanılabilir.

## <a name="a-database-exception-handling-example"></a><a name="_core_a_database_exception.2d.handling_example"></a>Veritabanı Özel Durum İşleme Örneği

Aşağıdaki örnekte, **yeni** işleçle yığınüzerinde [CRecordset](../mfc/reference/crecordset-class.md)türetilmiş bir nesne oluşturmaya ve ardından kayıt kümesini (ODBC veri kaynağı için) açmaya çalışır. DAO sınıfları için benzer bir örnek için aşağıdaki "DAO Özel Durum Örneği"ne bakın.

### <a name="odbc-exception-example"></a>ODBC Özel Durum Örneği

[Açık](../mfc/reference/crecordset-class.md#open) üye işlevi bir özel durum (ODBC sınıfları için [CDBException](../mfc/reference/cdbexception-class.md) türü) atabilir, bu nedenle bu kod çağrıyı `Open` **deneme** bloğuyla paranteze akaratır. Sonraki **catch** bloğu bir `CDBException`. Özel durum nesnesinin kendisini `e`inceleyebilirsiniz, ancak bu durumda bir kayıt kümesi oluşturma girişiminin başarısız olduğunu bilmek yeterlidir. **Catch** bloğu bir ileti kutusu görüntüler ve kayıt kümesi nesnesini silerek temizler.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>DAO Özel Durum Örneği

DAO örneği ODBC örneğine benzer, ancak genellikle daha fazla bilgi türü alabilirsiniz. Aşağıdaki kod da bir kayıt kümesini açmaya çalışır. Bu girişim bir özel durum atarsa, hata bilgileri için özel durum nesnesinin bir veri üyesini inceleyebilirsiniz. Önceki ODBC örneğinde olduğu gibi, bir kayıt kümesi oluşturma girişiminin başarısız olduğunu bilmek büyük olasılıkla yeterlidir.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Bu kod, özel durum nesnesinin [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) üyesinden bir hata iletisi dizesi alır. MFC, özel durum attığında bu üyeyi doldurur.

Bir `CDaoException` nesne tarafından döndürülen hata bilgilerinin tartışılması için [CDaoException](../mfc/reference/cdaoexception-class.md) ve [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)sınıflarını görün.

Microsoft Jet (.mdb) veritabanlarıyla çalışırken ve çoğu durumda ODBC ile çalışırken yalnızca bir hata nesnesi olacaktır. Bir ODBC veri kaynağı kullanıyorsanız ve birden çok hata olduğunda, CDaoException tarafından döndürülen hata sayısına bağlı olarak DAO'nun Hatalar koleksiyonunda döngü [yapabilirsiniz:GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount). Döngü boyunca her zaman, [CDaoException arayın::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) `m_pErrorInfo` veri üyesi doldurmak için.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
