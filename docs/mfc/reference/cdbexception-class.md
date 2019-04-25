---
title: CDBException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
ms.openlocfilehash: 755b89635eedd7808f900dc63cd3039845db1dd3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253419"
---
# <a name="cdbexception-class"></a>CDBException sınıfı

Veritabanı sınıflarından kaynaklanan bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDBException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDBException::m_nRetCode](#m_nretcode)|RETCODE türünün bir açık veritabanı bağlantısı (ODBC) dönüş kodunu içerir.|
|[CDBException::m_strError](#m_strerror)|Alfasayısal koşullarını hatayı açıklayan bir dize içerir.|
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC tarafından döndürülen hata kodlarını açısından hatayı açıklayan bir dize içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıfı özel durumun nedenini belirlemek için ya da özel durumu açıklayan bir mesaj görüntülemek için kullanabileceğiniz iki genel veri üyelerini içerir. `CDBException` nesneleri oluşturulur ve veritabanı sınıfları üye işlevleri tarafından oluşturulur.

> [!NOTE]
>  Bu sınıf, açık veritabanı bağlantısı (ODBC) sınıfları MFC'nin biridir. Bunun yerine daha yeni bir veri erişim nesneleri (DAO) sınıfları'ı kullanıyorsanız, [CDaoException](../../mfc/reference/cdaoexception-class.md) yerine. Tüm DAO sınıf adları "CDao" ön eki olarak vardır. Daha fazla bilgi için bkz [genel bakış: Veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

Özel durumlar durumlarda veri kaynağı gibi programın denetimin dışında kalan koşullar ile ilgili olağan dışı yürütme veya ağ g/ç hataları. Genellikle, program yürütmenin normal kursun görmeyi beklediğiniz hataları özel durumları dikkate alınmaz.

Bu nesneler kapsamında erişebileceğiniz bir **CATCH** ifade. Ayrıca oluşturabilecek `CDBException` kendi kodunuzla nesnelerden `AfxThrowDBException` genel işlev.

Özel durum genel veya hakkında işleme hakkında daha fazla bilgi için `CDBException` nesneleri makalelere bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: Veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

##  <a name="m_nretcode"></a>  CDBException::m_nRetCode

Bir ODBC hata kodu türünde bir ODBC uygulama programlama arabiriminin (API) işlevi tarafından döndürülen RETCODE içerir.

### <a name="remarks"></a>Açıklamalar

Bu tür ODBC tarafından tanımlanan SQL önekli kodları ve veritabanı sınıfları tarafından tanımlanan AFX_SQL önekli kodları içerir. İçin bir `CDBException`, bu üye aşağıdaki değerlerden birini içerir:

- AFX_SQL_ERROR_API_CONFORMANCE sürücü için bir `CDatabase::OpenEx` veya `CDatabase::Open` çağrısı gerekli ODBC API Uyumluluk Düzeyi 1 (SQL_OAC_LEVEL1) ile uyumlu değil.

- Veri kaynağı AFX_SQL_ERROR_CONNECT_FAIL bağlantısı başarısız oldu. Bir NULL geçirilen`CDatabase` işaretçisi, kayıt kümesi oluşturucu ve bir bağlantı oluşturmak için sonraki deneme temel alarak `GetDefaultConnect` başarısız oldu.

- AFX_SQL_ERROR_DATA_TRUNCATED, sağladığınız depolama için daha fazla veri istedi. Sağlanan veri depolama için artırma hakkında daha fazla bilgi için `CString` veya `CByteArray` veri türlerini görmek `nMaxLength` için bağımsız değişken [RFX_Text](record-field-exchange-functions.md#rfx_text) ve [RFX_Binary](record-field-exchange-functions.md#rfx_binary) altında "makroları ve Globals."

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED bir çağrı `CRecordset::Open` isteyen bir dinamik başarısız oldu. Dynaset'ler sürücü tarafından desteklenmez.

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST çalıştığınız bir tabloyu (veya size verdiği bir yordam çağrısı tanımlanamıyor veya **seçin** deyimi) vardır ancak kayıt alanı değişimi (RFX) işlev çağrılarında tanımlanan bir sütun yok `DoFieldExchange` geçersiz kılar.

- RFX türünü AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH işlevi içinde `DoFieldExchange` geçersiz kılma kayıt sütunu veri türü ile uyumlu değil.

- AFX_SQL_ERROR_ILLEGAL_MODE çağrılır, `CRecordset::Update` önceden çağırma olmadan `CRecordset::AddNew` veya `CRecordset::Edit`.

- ODBC sürücünüz kilitleme desteklemediğinden AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED güncelleştirme için kayıtları kilitleme isteğinizi yerine getirilemedi.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED çağrılır, `CRecordset::Update` veya `Delete` benzersiz anahtar içeren bir tablo için ve birden çok kayıt değiştirildi.

- AFX_SQL_ERROR_NO_CURRENT_RECORD, düzenlemek veya daha önce silinmiş bir kaydı silmek çalıştı. Yeni bir geçerli kaydı silindikten sonra kaydırma gerekir.

- ODBC sürücünüz desteklemediğinden bir dinamik isteğinizi yerine getirilemedi AFX_SQL_ERROR_NO_POSITIONED_UPDATES güncelleştirmeler konumlandırıldı.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED çağrılır, `CRecordset::Update` veya `Delete`, ancak işlemi başladığında, artık kayıt bulunamadı.

- ODBC yükleme denemesi AFX_SQL_ERROR_ODBC_LOAD_FAILED. DLL başarısız oldu; Windows, bulunamadı veya bu DLL yüklenemedi. Bu önemli bir hatadır.

- AFX_SQL_ERROR_ODBC_V2_REQUIRED Düzey 2 ile uyumlu bir ODBC sürücüsünü gerektiğinden bir dinamik isteğinizi yerine getirilemedi.

- Veri kaynağına geri kaydırma desteklemediğinden AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY kaydırma girişimi başarısız oldu.

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED bir çağrı `CRecordset::Open` isteyen bir anlık görüntü işlemi başarısız oldu. Anlık görüntüleri, sürücü tarafından desteklenmez. (Bu yalnızca gerçekleşmelidir olduğunda ODBCCURS ODBC imleç kitaplığı. DLL mevcut değil.)

- AFX_SQL_ERROR_SQL_CONFORMANCE sürücü için bir `CDatabase::OpenEx` veya `CDatabase::Open` çağrısı "Minimum" (SQL_OSC_MINIMUM) gerekli ODBC SQL uyumluluk düzeyi ile uyumlu değil.

- Toplam boyutunu belirtmek AFX_SQL_ERROR_SQL_NO_TOTAL ODBC sürücüsü alamadı bir `CLongBinary` veri değeri. Genel bellek bloğu değil önceden ayrılmış çünkü büyük olasılıkla işlemi başarısız oldu.

- AFX_SQL_ERROR_RECORDSET_READONLY, salt okunur bir kayıt kümesi güncelleştirmeyi denedi ya da salt okunur veri kaynağıdır. Kayıt kümesi ile hiçbir güncelleştirme işlemleri gerçekleştirilebilir veya `CDatabase` ilişkili olduğu nesne.

- SQL_ERROR hatası işlevi başarısız oldu. ODBC işlevi tarafından döndürülen hata iletisi `SQLError` depolanan `m_strError` veri üyesi.

- SQL_INVALID_HANDLE işlevi geçersiz ortam tanıtıcısı, bağlantı tanıtıcısı veya deyim tanıtıcısı nedeniyle başarısız oldu. Bu, bir programlama hatası gösterir. ODBC işlevden kullanılabilir ek bilgi `SQLError`.

SQL önekli kodları ODBC tarafından tanımlanır. AFX önekli kodları AFXDB içinde tanımlanır. H, MFC\INCLUDE içinde bulunamadı.

##  <a name="m_strerror"></a>  CDBException::m_strError

Özel duruma neden olan hatayı açıklayan bir dize içerir.

### <a name="remarks"></a>Açıklamalar

Dize, alfasayısal koşullarında hata açıklar. Daha ayrıntılı bilgi ve örnek için bkz. `m_strStateNativeOrigin`.

##  <a name="m_strstatenativeorigin"></a>  CDBException::m_strStateNativeOrigin

Özel duruma neden olan hatayı açıklayan bir dize içerir.

### <a name="remarks"></a>Açıklamalar

Dize biçimi kodları sırayla açıklayan değerler tarafından değiştirildiği desene form "durumu: % s, yerel: % ld kaynağı: % s'ın" şöyledir:

- Beş karakterli hata kodu içeren null ile sonlandırılmış bir dize döndürdü SQLSTATE *szSqlState* ODBC işlevinin parametresi `SQLError`. SQLSTATE değerleri Ek A'da listelenen [ODBC hata kodları](/previous-versions/windows/desktop/ms714687(v=vs.85)), *ODBC Programcının Başvurusu*. Örnek: "S0022".

- Veri kaynağı için özel yerel hata kodunu döndürdü *pfNativeError* parametresinin `SQLError` işlevi. Örnek: 207.

- Döndürülen hata iletisi metni *szErrorMsg* parametresinin `SQLError` işlevi. Bu ileti, birden fazla parantezli adlarını oluşur. Kullanıcıya bir hata kaynağından geçirilen gibi kendi adına her bir ODBC bileşeni (veri kaynağı, sürücüsü, Sürücü Yöneticisi) ekler. Bu bilgiler hata kökenini belirlemenize yardımcı olur. Örnek: [Microsoft] [ODBC SQL Server sürücüsünü] [SQL Server]

Framework hata dizesi yorumlar ve bileşenlerine koyar `m_strStateNativeOrigin`if `m_strStateNativeOrigin` bilgilerini içeren karakterleriyle ayrılan birden fazla hata için hataları. Framework alfasayısal hata metne koyar `m_strError`.

Bu dize yapmak için kullanılan kodları hakkında ek bilgi için bkz. [SQLError](/previous-versions/windows/desktop/ms716312(v=vs.85)) işlevi *ODBC Programcının Başvurusu*.

### <a name="example"></a>Örnek

  ODBC'den: "Durumu: S0022, yerel: 207'de, kaynak:\[Microsoft]\[ODBC SQL Server sürücüsünü]\[SQL Server] Geçersiz sütun adı 'ColName'"

İçinde `m_strStateNativeOrigin`: "Durumu: S0022, yerel: 207'de, kaynak:\[Microsoft]\[ODBC SQL Server sürücüsünü]\[SQL Server]"

İçinde `m_strError`: "Geçersiz sütun adı 'ColName'"

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange Sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::Update](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)
