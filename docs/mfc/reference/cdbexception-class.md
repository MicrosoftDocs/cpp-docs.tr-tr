---
title: CDBException Sınıf
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
ms.openlocfilehash: 1ab7daeb3af55c92985c951c632b1d4050681474
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321902"
---
# <a name="cdbexception-class"></a>CDBException Sınıf

Veritabanı sınıflarından kaynaklanan bir özel durum koşulu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDBException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDBException::m_nRetCode](#m_nretcode)|RETCODE türünden bir Açık Veritabanı Bağlantısı (ODBC) return code içerir.|
|[CDBException::m_strError](#m_strerror)|Hatayı alfasayısal terimlerle açıklayan bir dize içerir.|
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC tarafından döndürülen hata kodları açısından hatayı açıklayan bir dize içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, özel durum nedenini belirlemek veya özel durumu açıklayan bir metin iletisi görüntülemek için kullanabileceğiniz iki ortak veri üyesi içerir. `CDBException`nesneler veritabanı sınıflarının üye işlevleri tarafından oluşturulur ve atılır.

> [!NOTE]
> Bu sınıf, MFC'nin Açık Veritabanı Bağlantısı (ODBC) sınıflarından biridir. Bunun yerine yeni Veri Erişim Nesneleri (DAO) sınıflarını kullanıyorsanız, bunun yerine [CDaoException'ı](../../mfc/reference/cdaoexception-class.md) kullanın. Tüm DAO sınıf adlarının öneki olarak "CDao" vardır. Daha fazla bilgi için genel bakış makalesine [bakın: Veritabanı Programlama.](../../data/data-access-programming-mfc-atl.md)

Özel durumlar, veri kaynağı veya ağ G/Ç hataları gibi programın denetimi dışındaki koşulları içeren anormal yürütme durumlarıdır. Programınızı yürütme normal seyrinde görmeyi beklediğiniz hatalar genellikle özel durum olarak kabul edilmez.

Catch **ifadesi** kapsamında bu nesnelere erişebilirsiniz. Ayrıca, genel `CDBException` işlevle nesneleri kendi `AfxThrowDBException` kodunuzdan atabilirsiniz.

Genel olarak özel durum işleme veya `CDBException` nesneler hakkında daha fazla bilgi için, [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [Özel Durumlar: Veritabanı Özel Durumlar](../../mfc/exceptions-database-exceptions.md)makalelerine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="cdbexceptionm_nretcode"></a><a name="m_nretcode"></a>CDBException::m_nRetCode

ODBC uygulama programlama arabirimi (API) işlevi tarafından döndürülen RETCODE türünden bir ODBC hata kodu içerir.

### <a name="remarks"></a>Açıklamalar

Bu tür, ODBC tarafından tanımlanan SQL-prefixed kodları ve veritabanı sınıfları tarafından tanımlanan AFX_SQL önceden belirlenmiş kodları içerir. Bir `CDBException`için, bu üye aşağıdaki değerlerden birini içerecektir:

- AFX_SQL_ERROR_API_CONFORMANCE Bir `CDatabase::OpenEx` veya `CDatabase::Open` arama nın sürücüsü gerekli ODBC API Uygunluk düzeyi 1'e (SQL_OAC_LEVEL1) uymaz.

- AFX_SQL_ERROR_CONNECT_FAIL Veri kaynağına bağlantı başarısız oldu. Bir NULL`CDatabase` işaretçisini kayıt kümesi oluşturucunuza ve sonraki `GetDefaultConnect` başarısızlığa dayalı bir bağlantı oluşturma denemesine geçtiniz.

- AFX_SQL_ERROR_DATA_TRUNCATED Depolama sağladığınızdan daha fazla veri istediniz. Sağlanan veri depolamasını `CString` veya `CByteArray` veri türlerini artırma `nMaxLength` hakkında bilgi için, "Makrolar ve Küreseller" altında [RFX_Text](record-field-exchange-functions.md#rfx_text) ve [RFX_Binary](record-field-exchange-functions.md#rfx_binary) bağımsız değişkenine bakın.

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED Bir `CRecordset::Open` dinamit istemek için bir çağrı başarısız oldu. Dinamitler sürücü tarafından desteklenmez.

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST Bir tablo açmayı denediniz (veya ne verdiniz yordam çağrısı veya **SELECT** deyimi olarak tanımlanamadı) ancak geçersiz kılmanızda `DoFieldExchange` kayıt alanı değişimi (RFX) işlev aramalarında tanımlanan sütun yok.

- AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH Geçersiz kılmanızdaki `DoFieldExchange` RFX işlevinin türü, kayıt kümesindeki sütun veri türüyle uyumlu değildir.

- AFX_SQL_ERROR_ILLEGAL_MODE Daha `CRecordset::Update` önce `CRecordset::AddNew` aramadan `CRecordset::Edit`veya .

- AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED ODBC sürücünüz kilitlemeyi desteklemediği için güncelleştirme kayıtlarını kilitleme isteğiniz yerine getirilemedi.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED Benzersiz `CRecordset::Update` `Delete` anahtarı olmayan ve birden çok kaydı değiştirilen bir tabloyu aradınız veya çağırdınız.

- AFX_SQL_ERROR_NO_CURRENT_RECORD Önceden silinmiş bir kaydı düzenlemeye veya silmeye çalıştınız. Silme işleminden sonra yeni bir geçerli kayda kaydırmanız gerekir.

- AFX_SQL_ERROR_NO_POSITIONED_UPDATES ODBC sürücünüz konumlandırılmış güncelleştirmeleri desteklemediği için dinamit isteğiniz yerine getirilemedi.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED `CRecordset::Update` Aradınız `Delete`veya , ancak işlem başladığında kayıt artık bulunamadı.

- AFX_SQL_ERROR_ODBC_LOAD_FAILED ODBC yükleme girişimi. DLL başarısız oldu; Windows bu DLL'yi bulamadı veya yükleyemedi. Bu hata ölümcüldür.

- AFX_SQL_ERROR_ODBC_V2_REQUIRED Düzey 2 uyumlu bir ODBC sürücüsü gerektiğinden dinamit isteğiniz yerine getirilemedi.

- AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY Veri kaynağı geriye kaydırmayı desteklemediği için kaydırma girişimi başarılı olmadı.

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED Anlık `CRecordset::Open` görüntü isteme çağrısı başarısız oldu. Anlık görüntüler sürücü tarafından desteklenmez. (Bu yalnızca ODBC imleç kitaplığı ODBCCURS'ta oluşmalıdır. DLL mevcut değildir.)

- AFX_SQL_ERROR_SQL_CONFORMANCE Bir `CDatabase::OpenEx` veya `CDatabase::Open` arama nın sürücüsü gerekli ODBC SQL Uygunluk düzeyi "Minimum" (SQL_OSC_MINIMUM) ile uyumlu değildir.

- AFX_SQL_ERROR_SQL_NO_TOTAL ODBC sürücüsü bir `CLongBinary` veri değerinin toplam boyutunu belirtemedi. Genel bellek bloğu önceden tahsis edilemediği için işlem büyük olasılıkla başarısız oldu.

- AFX_SQL_ERROR_RECORDSET_READONLY Salt okunur kayıt kümesini güncelleştirmeyi denediniz veya veri kaynağı salt okunur. Kayıt kümesi veya ilişkili `CDatabase` nesneyle hiçbir güncelleştirme işlemi gerçekleştirilemez.

- SQL_ERROR İşlev başarısız oldu. ODBC işlevi `SQLError` tarafından döndürülen hata iletisi veri üyesinde `m_strError` depolanır.

- SQL_INVALID_HANDLE İşlev geçersiz bir ortam tutamacı, bağlantı tutamacı veya deyim tutamacı nedeniyle başarısız oldu. Bu bir programlama hatası gösterir. ODBC işlevinden `SQLError`ek bilgi yok.

SQL-prefixed kodları ODBC tarafından tanımlanır. AFX önceden belirlenmiş kodlar AFXDB'de tanımlanır. H, MFC\INCLUDE bulunur.

## <a name="cdbexceptionm_strerror"></a><a name="m_strerror"></a>CDBException::m_strError

Özel durum neden hata açıklayan bir dize içerir.

### <a name="remarks"></a>Açıklamalar

Dize, hatayı alfasayısal terimlerle açıklar. Daha ayrıntılı bilgi ve bir `m_strStateNativeOrigin`örnek için bkz.

## <a name="cdbexceptionm_strstatenativeorigin"></a><a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin

Özel durum neden hata açıklayan bir dize içerir.

### <a name="remarks"></a>Açıklamalar

Dize, biçim kodlarının sırayla açıklanan değerlerle değiştirildiği "Durum:%s,%s,%ld,Origin:%s" şeklindedir:

- SqlSTATE, ODBC işlevinin `SQLError` *szSqlState* parametresinde döndürülen beş karakterli bir hata kodu içeren null-sonlandırılan dize. SQLSTATE değerleri Ek A, [ODBC Hata Kodları,](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes) *ODBC Programcı'nın Referans*listelenir. Örnek: "S0022".

- Veri kaynağına özgü yerel hata kodu, `SQLError` işlevin *pfNativeError* parametresinde döndürülür. Örnek: 207.

- Hata iletisi metni `SQLError` işlevin *szErrorMsg* parametresinde döndürülür. Bu ileti birkaç parantez adından oluşur. Bir hata kaynağından kullanıcıya geçerken, her ODBC bileşeni (veri kaynağı, sürücü, Sürücü Yöneticisi) kendi adını ekler. Bu bilgiler, hatanın kaynağını belirlemeye yardımcı olur. Örnek: [Microsoft][ODBC SQL Server Driver][SQL Server]

Çerçeve hata dizesini yorumlar ve `m_strStateNativeOrigin`bileşenlerini; birden `m_strStateNativeOrigin` fazla hata için bilgi içeriyorsa, hatalar yeni satırlarla ayrılır. Çerçeve alfasayısal hata metnini `m_strError`.

Bu dizeyi oluşturan kodlar hakkında ek bilgi için *ODBC Programcısının Başvurusu'ndaki* [SQLError](/sql/odbc/reference/syntax/sqlerror-function) işlevine bakın.

### <a name="example"></a>Örnek

ODBC Gönderen:\["Devlet:S0022,Yerel:207,Origin:\[Microsoft] ODBC\[SQL Server Driver] SQL Server] Geçersiz sütun adı 'ColName'"

In `m_strStateNativeOrigin`: "State:S0022,Native:207,Origin:\[Microsoft]\[ODBC SQL Server Driver]\[SQL Server]"

In `m_strError`: "Geçersiz sütun adı 'ColName'"

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CfieldExchange Sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::Güncelleme](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)
