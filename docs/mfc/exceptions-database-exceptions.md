---
title: 'Özel durumlar: Veritabanı özel durumları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2168bc530accfdde6fad4d41cd68e94d3088f153
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-database-exceptions"></a>Özel durumlar: Veritabanı Özel Durumları
Bu makalede, veritabanı özel durumları işleme açıklanmaktadır. Bu makaledeki malzemesini çoğunu ile MFC sınıfları açık veritabanı bağlantısı (ODBC) veya MFC sınıfları için veri erişim nesneleri (DAO) çalıştığınız olup olmadığını geçerlidir. Malzeme birini veya diğer model belirli açık olarak işaretlenir. Konular şunlardır:  
  
-   [Özel durum işleme yaklaşımları](#_core_approaches_to_exception_handling)  
  
-   [Bir veritabanı özel durum işleme örneği](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a> Özel durum işleme yaklaşımları  
 DAO veya ODBC ile çalışıyorsanız olup olmadığını aynı yaklaşımdır.  
  
 Her zaman özel durumları işlemek için özel durum işleyicileri yazmanız gerekir.  
  
 Veritabanı özel durumları yakalama en kolay yaklaşım, özel durum senaryoları ile uygulamanızı test etmektir. Bir işlem, kodunuzda oluşabilir ve gerçekleşmesi için özel durum zorla büyük olasılıkla özel durumlar belirleyin. Ardından hangi özel durum görmek için izleme çıktıyı inceleyin ya da hata ayıklayıcısında döndürülen hata bilgilerini inceleyin. Bu, hangi dönüş kodları, kullanmakta olduğunuz özel durum senaryoları için görürsünüz bilmenizi sağlar.  
  
### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC özel durumları için kullanılan hata kodları  
 Çerçevesi tarafından tanımlanan dönüş kodları ek olarak, hangi sahip formun adını **AFX_SQL_ERROR_XXX**, bazı [CDBExceptions](../mfc/reference/cdbexception-class.md) dayalı [ODBC](../data/odbc/odbc-basics.md) dönüş kodları. Bu tür özel durumlar için dönüş kodları biçiminde adlara sahip **SQL_ERROR_XXX**.  
  
 Dönüş kodları — framework tanımlı hem ODBC tanımlı — veritabanı sınıfları belgelenmiştir altında döndürebilir [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) sınıfı veri üyesi `CDBException`. ODBC tarafından tanımlanan dönüş kodları hakkında ek bilgi ODBC SDK'ın kullanılabilir *Programcının Başvurusu* MSDN Kitaplığı'nda.  
  
### <a name="error-codes-used-for-dao-exceptions"></a>DAO özel durumlar için kullanılan hata kodları  
 Daha fazla bilgi için DAO özel durumları, tipik olarak kullanılabilir. Üç veri üyeleri bir yakalanan hata bilgilerini erişebilirsiniz [CDaoException](../mfc/reference/cdaoexception-class.md) nesnesi:  
  
-   [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) gösteren bir işaretçi içeren bir [Cdaoerrorınfo](../mfc/reference/cdaoerrorinfo-structure.md) veritabanıyla ilişkili hata nesnelerin DAO'ın koleksiyonundaki hata bilgileri yalıtan nesne.  
  
-   [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) MFC DAO sınıflarını bir genişletilmiş hata kodunu içeriyor. Biçiminde adlara sahip bu hata kodları **AFX_DAO_ERROR_XXX**, veri üyesi altında belgelenen `CDaoException`.  
  
-   [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) bir OLE içeren `SCODE` DAO, varsa. Ayrıca, ancak bu hata kodu ile çalışma nadiren gerekir. Genellikle daha fazla bilgi diğer iki veri üyeleri kullanılabilir. Veri üyesi daha fazla bilgi için bkz: `SCODE` değerleri.  
  
 DAO hatalar, DAO hata nesne türü ve DAO hatalar koleksiyonuna hakkında ek bilgi sınıfı altında kullanılabilir [CDaoException](../mfc/reference/cdaoexception-class.md).  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a> Bir veritabanı özel durum işleme örneği  
 Aşağıdaki örnek oluşturmak çalışır bir [CRecordset](../mfc/reference/crecordset-class.md)-yığınla nesnesinde türetilmiş **yeni** işleci ve kayıt kümesi (ODBC veri kaynağını) açın. DAO sınıfları için benzer bir örnek için "DAO özel durum" aşağıdaki örneğe bakın.  
  
### <a name="odbc-exception-example"></a>ODBC özel durumu örneği  
 [Açık](../mfc/reference/crecordset-class.md#open) üye işlevi bir özel durum özel durum (tür [CDBException](../mfc/reference/cdbexception-class.md) ODBC sınıfları için), bu nedenle bu kod köşeli **açık** çağıran bir **deneyin**  bloğu. Sonraki **catch** catch bloğu bir `CDBException`. Adlı özel durum nesnesi kendisini inceleyin `e`, ancak bu durumda bir kayıt kümesi oluşturma girişimi başarısız olduğunu bilmeniz yeterlidir. **Catch** bloğu bir ileti kutusu görüntüler ve kayıt kümesi nesnesi silerek temizler.  
  
 [!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]  
  
### <a name="dao-exception-example"></a>DAO özel durumu örneği  
 DAO örnek ODBC örneğin benzer, ancak genellikle daha fazla bilgi türlerini alır. Aşağıdaki kod bir kayıt kümesi açmak de çalışır. Bu girişim bir özel durum oluşturursa, veri üyesi hata bilgileri için özel durum nesnesi inceleyebilirsiniz. Büyük olasılıkla önceki ODBC örnekle olduğu gibi bir kayıt kümesi oluşturma girişimi başarısız olduğunu bilmek için yeterli.  
  
 [!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]  
  
 Bu kodu bir hata iletisi dizeden alır [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) özel durum nesnesi üyesi. MFC özel durum oluşturduğunda bu üye doldurur.  
  
 Tarafından döndürülen hata bilgilerinin bir tartışma için bir `CDaoException` nesne, sınıfları görmek [CDaoException](../mfc/reference/cdaoexception-class.md) ve [Cdaoerrorınfo](../mfc/reference/cdaoerrorinfo-structure.md).  
  
 ODBC ile çalışırken, Microsoft Jet (.mdb) veritabanlarıyla ve çoğu durumda çalışırken, yalnızca bir hata nesnesi olacaktır. Nadir durumlarda ODBC veri kaynağını kullanan ve birden çok hata olduğunda, tarafından döndürülen hataları sayısına dayalı DAO'ın hataları koleksiyonu aracılığıyla bir döngüye girer [CDaoException::GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount). Döngünün her tamamlanışında çağrısı [CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) yenileme için `m_pErrorInfo` veri üyesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

