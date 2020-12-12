---
description: 'Hakkında daha fazla bilgi edinin: özel durumlar: veritabanı özel durumları'
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
ms.openlocfilehash: 3e45f887d51b4b81196cd08d11f426f4ee6d4481
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290654"
---
# <a name="exceptions-database-exceptions"></a>Özel durumlar: Veritabanı Özel Durumları

Bu makalede veritabanı özel durumlarının nasıl işleneceği açıklanır. Bu makaledeki malzemenin çoğu, açık veritabanı bağlantısı (ODBC) için MFC sınıflarıyla veya veri erişim nesneleri (DAO) için MFC sınıflarıyla çalışırken geçerlidir. Bir veya diğer modele özgü malzemeler açıkça işaretlenir. Konu başlıkları şunlardır:

- [Özel durum işleme yaklaşımları](#_core_approaches_to_exception_handling)

- [Veritabanı özel durum işleme örneği](#_core_a_database_exception.2d.handling_example)

## <a name="approaches-to-exception-handling"></a><a name="_core_approaches_to_exception_handling"></a> Özel durum Işleme yaklaşımları

Bu yaklaşım, DAO (eski) veya ODBC ile çalışırken de aynıdır.

Olağanüstü koşulları işlemek için her zaman özel durum işleyicileri yazmanız gerekir.

Veritabanı özel durumlarını yakalamak için en kolay yaklaşım, uygulamanızı özel durum senaryolarıyla test kullanmaktır. Kodunuzda bir işlem için oluşabilecek olası özel durumları saptayın ve özel durumu ortaya çıkmaya zorlayın. Ardından, özel durumun ne olduğunu görmek için izleme çıkışını inceleyin veya hata ayıklayıcıda döndürülen hata bilgilerini inceleyin. Bu, kullanmakta olduğunuz özel durum senaryoları için hangi dönüş kodlarının görütireceğiz olduğunu bilmenizi sağlar.

### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC özel durumları için kullanılan hata kodları

**Afx_sql_error_xxx**, çerçeve tarafından tanımlanan, form adlarını içeren dönüş kodlarına ek olarak, bazı [CDBExceptions](reference/cdbexception-class.md) [ODBC](../data/odbc/odbc-basics.md) dönüş kodlarını temel alır. Bu özel durumlar için dönüş kodları **sql_error_xxx** biçim adlarına sahiptir.

Veritabanı sınıflarının döndürebildiği, hem çerçeve tanımlı hem de ODBC tanımlı dönüş kodları, sınıfının [m_nRetCode](reference/cdbexception-class.md#m_nretcode) veri üyesi altında belgelenmiştir `CDBException` . ODBC tarafından tanımlanan dönüş kodlarıyla ilgili ek bilgiler [ODBC Programcı başvurusu](/sql/odbc/reference/odbc-programmer-s-reference)' nda bulunabilir.

### <a name="error-codes-used-for-dao-exceptions"></a>DAO özel durumları için kullanılan hata kodları

DAO özel durumları için, daha fazla bilgi genellikle kullanılabilir. Yakalanan bir [CDaoException](reference/cdaoexception-class.md) nesnesinin üç veri üyesi aracılığıyla hata bilgilerine erişebilirsiniz:

- [m_pErrorInfo](reference/cdaoexception-class.md#m_perrorinfo) , DAO 'nun veritabanıyla ilişkili hata nesneleri koleksiyonundaki hata bilgilerini kapsülleyen bir [CDaoErrorInfo](reference/cdaoerrorinfo-structure.md) nesnesine yönelik bir işaretçi içerir.

- [m_nAfxDaoError](reference/cdaoexception-class.md#m_nafxdaoerror) , MFC DAO sınıflarından genişletilmiş bir hata kodu içerir. **Afx_dao_error_xxx** form adları olan bu hata kodları, içindeki veri üyesi altında belgelenmiştir `CDaoException` .

- [m_scode](reference/cdaoexception-class.md#m_scode) , varsa DAO 'DAN bir OLE **SCODE** içerir. Ancak, bu hata koduyla nadiren çalışmanız gerekir. Genellikle diğer iki veri üyelerinde daha fazla bilgi mevcuttur. **SCODE** değerleri hakkında daha fazla bilgi için veri üyesine bakın.

DAO hataları, DAO hatası nesne türü ve DAO hataları koleksiyonu hakkında ek bilgiler, [Cdaoözel durum](reference/cdaoexception-class.md)sınıfından kullanılabilir.

## <a name="a-database-exception-handling-example"></a><a name="_core_a_database_exception.2d.handling_example"></a> Bir veritabanı Exception-Handling örneği

Aşağıdaki örnek, işleçle yığın üzerinde bir [CRecordset](reference/crecordset-class.md)ile türetilmiş nesne oluşturmaya çalışır **`new`** ve ardından kayıt kümesini (ODBC veri kaynağı için) açar. DAO sınıflarına benzer bir örnek için aşağıdaki "DAO özel durum örneği" ne bakın.

### <a name="odbc-exception-example"></a>ODBC özel durum örneği

[Open](reference/crecordset-class.md#open) member işlevi ODBC sınıfları için bir özel durum ( [CDBException](reference/cdbexception-class.md) türünde) oluşturabilir, bu nedenle bu kod, `Open` çağrıyı bir blok ile ayraç içine alın **`try`** . Sonraki **`catch`** blok bir yakalar `CDBException` . Bilinen özel durum nesnesinin kendisini inceleyebilirsiniz, `e` ancak bu durumda bir kayıt kümesi oluşturma girişiminin başarısız olduğunu bilmek için yeterlidir. **`catch`** Blok bir ileti kutusu görüntüler ve kayıt kümesi nesnesini silerek temizler.

[!code-cpp[NVC_MFCDatabase#36](codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>DAO özel durum örneği

DAO örneği, ODBC örneğine benzerdir, ancak genellikle daha fazla bilgi türü elde edebilirsiniz. Aşağıdaki kod ayrıca bir kayıt kümesini açmaya çalışır. Bu girişim bir özel durum oluşturursa, hata bilgileri için özel durum nesnesinin bir veri üyesini inceleyebilirsiniz. Önceki ODBC örneğinde olduğu gibi, bir kayıt kümesi oluşturma girişiminin başarısız olduğunu bilmek büyük olasılıkla çok fazla.

[!code-cpp[NVC_MFCDatabase#37](codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Bu kod, özel durum nesnesinin [m_pErrorInfo](reference/cdaoexception-class.md#m_perrorinfo) üyesinden bir hata iletisi dizesi alır. MFC özel durumu oluşturduğunda bu üyeyi doldurur.

Bir nesne tarafından döndürülen hata bilgilerinin bir tartışması için `CDaoException` bkz. Classes [CDaoException](reference/cdaoexception-class.md) ve [CDaoErrorInfo](reference/cdaoerrorinfo-structure.md).

Microsoft Jet (. mdb) veritabanları ile çalışırken ve çoğu durumda ODBC ile çalışırken yalnızca bir hata nesnesi olur. Bir ODBC veri kaynağı kullanırken ve birden çok hata olduğunda, nadir olarak bir ODBC veri kaynağı kullandığınızda, bu sayının, [CDaoException:: GetErrorCount](reference/cdaoexception-class.md#geterrorcount)tarafından döndürülen hata sayısına bağlı olarak dao hata toplama aracılığıyla döngü yapabilirsiniz. Döngünün her seferinde, veri üyesini yeniden doldurmak için [CDaoException:: GetErrorInfo](reference/cdaoexception-class.md#geterrorinfo) çağırın `m_pErrorInfo` .

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
