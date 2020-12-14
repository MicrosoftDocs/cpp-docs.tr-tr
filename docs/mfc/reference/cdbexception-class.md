---
description: 'Daha fazla bilgi edinin: CDBException sınıfı'
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
ms.openlocfilehash: 8e337cc0f66a4a281de07ba3839895096e8021d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222131"
---
# <a name="cdbexception-class"></a>CDBException sınıfı

Veritabanı sınıflarından kaynaklanan bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Syntax

```
class CDBException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDBException:: m_nRetCode](#m_nretcode)|EKCODE türünde açık bir veritabanı bağlantısı (ODBC) dönüş kodu içerir.|
|[CDBException:: m_strError](#m_strerror)|Hatayı alfasayısal koşullarda açıklayan bir dize içerir.|
|[CDBException:: m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC tarafından döndürülen hata kodları açısından hatayı açıklayan bir dize içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıfı, özel durumun nedenini veya özel durumu açıklayan bir kısa mesaj görüntülemeyi sağlamak için kullanabileceğiniz iki genel veri üyesini içerir. `CDBException` nesneler, veritabanı sınıflarının üye işlevleri tarafından oluşturulur ve oluşturulur.

> [!NOTE]
> Bu sınıf, MFC 'nin açık veritabanı bağlantısı (ODBC) sınıflarından biridir. Bunun yerine, daha yeni veri erişim nesneleri (DAO) sınıfları kullanıyorsanız, bunun yerine [CDaoException](../../mfc/reference/cdaoexception-class.md) kullanın. Tüm DAO sınıf adlarında ön ek olarak "CDao" vardır. Daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

Özel durumlar, programın denetimi dışında, veri kaynağı veya ağ g/ç hataları gibi koşullara göre olağan dışı yürütmeyle ilgili çalışmalardır. Programınızı yürütmenin normal sırasında görmeyi bekleolabileceğiniz hatalar genellikle özel durumlar olarak kabul edilmez.

Bu nesnelere bir **catch** ifadesinin kapsamı içinde erişebilirsiniz. Ayrıca, `CDBException` genel işlevi ile kendi kodunuzla nesneler de oluşturabilirsiniz `AfxThrowDBException` .

Genel veya nesneler hakkında özel durum işleme hakkında daha fazla bilgi için `CDBException` bkz. Makaleler [özel durum Işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="cdbexceptionm_nretcode"></a><a name="m_nretcode"></a> CDBException:: m_nRetCode

Bir ODBC uygulama programlama arabirimi (API) işlevi tarafından döndürülen EKCODE türünde bir ODBC hata kodu içerir.

### <a name="remarks"></a>Açıklamalar

Bu tür, ODBC tarafından tanımlanan SQL-önekli kodları ve veritabanı sınıfları tarafından tanımlanan AFX_SQL-önekli kodları içerir. Bir için `CDBException` , bu üye aşağıdaki değerlerden birini içerir:

- Veya çağrısı için AFX_SQL_ERROR_API_CONFORMANCE, `CDatabase::OpenEx` `CDatabase::Open` gereklı ODBC API uygunluğu düzeyi 1 ' e (SQL_OAC_LEVEL1) uymuyor.

- AFX_SQL_ERROR_CONNECT_FAIL veri kaynağıyla bağlantı kurulamadı. `CDatabase`Kayıt kümesi YAPıCıSıNA boş bir işaretçi geçirtiniz ve sonraki bir bağlantı oluşturma girişimi `GetDefaultConnect` başarısız oldu.

- AFX_SQL_ERROR_DATA_TRUNCATED için depolama alanı sağlamaktan daha fazla veri istediniz. Veya veri türleri için sağlanmış veri depolamayı artırma hakkında daha fazla bilgi için `CString` `CByteArray` , `nMaxLength` "makrolar ve genel" altındaki [RFX_Text](record-field-exchange-functions.md#rfx_text) ve [RFX_Binary](record-field-exchange-functions.md#rfx_binary) bağımsız değişkenine bakın.

- DYNASET istek için bir çağrı AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED `CRecordset::Open` başarısız oldu. Dinamik kümeler sürücü tarafından desteklenmez.

- Bir tabloyu açmaya çalıştınız (ya da verdiğiniz bir yordam çağrısı veya **Select** bildirisi olarak tanımlanamıyor), ancak `DoFieldExchange` geçersiz kılmanızda kayıt alanı değişimi (RFX) işlev çağrılarında tanımlanmış sütun yok. AFX_SQL_ERROR_EMPTY_COLUMN_LIST

- Geçersiz kılmada bir RFX işlevinin türü AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH, `DoFieldExchange` kayıt kümesindeki sütun veri türüyle uyumlu değil.

- `CRecordset::Update`Daha önce veya çağırılmadan AFX_SQL_ERROR_ILLEGAL_MODE `CRecordset::AddNew` çağırılır `CRecordset::Edit` .

- ODBC sürücünüz kilitlemeyi desteklemediğinden, güncelleştirme için kayıt kilitleme isteğiniz AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED karşılanmadı.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED, `CRecordset::Update` `Delete` benzersiz anahtarı olmayan ve birden çok kaydı değiştiren bir tablo için veya olarak çağırılır.

- Daha önce silinmiş bir kaydı düzenlemeye veya silmeye çalıştınız AFX_SQL_ERROR_NO_CURRENT_RECORD. Silinmeden sonra yeni bir geçerli kayda kaydırmanız gerekir.

- ODBC sürücünüz konumlandırılmış güncelleştirmeleri desteklemediğinden, bir Dynaset için isteğiniz yerine getirilemedi AFX_SQL_ERROR_NO_POSITIONED_UPDATES.

- Ya da olarak adlandırdığınızdan AFX_SQL_ERROR_NO_ROWS_AFFECTED `CRecordset::Update` `Delete` , ancak işlem başladığında kayıt artık bulunamamıştır.

- ODBC.DLL yükleme girişimi başarısız AFX_SQL_ERROR_ODBC_LOAD_FAILED; Windows bu DLL 'i bulamadı veya yükleyemedi. Bu hata önemli.

- Düzey 2 uyumlu bir ODBC sürücüsü gerektiğinden, bir dinamik küme için isteğiniz yerine getirilemedi AFX_SQL_ERROR_ODBC_V2_REQUIRED.

- Veri kaynağı geriye doğru kaydırmayı desteklemediğinden, kaydırma girişimi başarılı olmadı AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY.

- Anlık görüntü istemek için bir çağrı AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED `CRecordset::Open` başarısız oldu. Anlık görüntüler sürücü tarafından desteklenmez. (Bu yalnızca ODBC imleç kitaplığı ODBCCURS.DLL mevcut olmadığında gerçekleşir.)

- Veya çağrısı için AFX_SQL_ERROR_SQL_CONFORMANCE, `CDatabase::OpenEx` `CDatabase::Open` gereklı ODBC SQL uyumluluk düzeyi olan "minimum" (SQL_OSC_MINIMUM) ile uyumlu değildir.

- ODBC sürücüsü AFX_SQL_ERROR_SQL_NO_TOTAL bir veri değerinin toplam boyutunu belirleyemedi `CLongBinary` . Genel bir bellek bloğu önceden ayrılamadığından işlem muhtemelen başarısız oldu.

- Salt okunurdur bir kayıt kümesini güncelleştirmeye AFX_SQL_ERROR_RECORDSET_READONLY veya veri kaynağı salt okunurdur. Kayıt kümesi veya ilişkilendirildiği nesne ile hiçbir güncelleştirme işlemi gerçekleştirilemez `CDatabase` .

- SQL_ERROR Işlevi başarısız oldu. ODBC işlevi tarafından döndürülen hata iletisi `SQLError` `m_strError` veri üyesinde saklanır.

- Geçersiz ortam tanıtıcısı, bağlantı tanıtıcısı veya ekstre tanıtıcısı nedeniyle SQL_INVALID_HANDLE Işlevi başarısız oldu. Bu bir programlama hatası gösterir. ODBC işlevinden ek bilgi yok `SQLError` .

SQL-önekli kodları ODBC tarafından tanımlanır. AFX önekli kodlar AFXDB 'de tanımlanmıştır. H, MFC\INCLUDEKONUMUNDA bulundu.

## <a name="cdbexceptionm_strerror"></a><a name="m_strerror"></a> CDBException:: m_strError

Özel duruma neden olan hatayı açıklayan bir dize içerir.

### <a name="remarks"></a>Açıklamalar

Dize, hatayı alfasayısal koşullarda açıklar. Daha ayrıntılı bilgi ve bir örnek için bkz `m_strStateNativeOrigin` ..

## <a name="cdbexceptionm_strstatenativeorigin"></a><a name="m_strstatenativeorigin"></a> CDBException:: m_strStateNativeOrigin

Özel duruma neden olan hatayı açıklayan bir dize içerir.

### <a name="remarks"></a>Açıklamalar

Dize, "durum:% s, Yerel:% ld, Origin:% s" biçimindedir, burada biçim kodları sırasıyla, aşağıdakileri tanımlayan değerlerle değiştirilmiştir:

- ODBC işlevinin *szSqlState* parametresinde döndürülen beş karakterlik bir hata kodu içeren, null sonlandırılmış bir dize `SQLError` . SQLSTATE değerleri, ek A, [ODBC hata kodlarında](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes), *ODBC Programcı başvurusu*'nda listelenir. Örnek: "S0022".

- Veri kaynağına özgü yerel hata kodu, işlevin *pfNativeError* parametresinde döndürülür `SQLError` . Örnek: 207.

- İşlevin *szErrorMsg* parametresinde döndürülen hata iletisi metni `SQLError` . Bu ileti, birkaç köşeli parantez içine alınmış adlardan oluşur. Bir hata, kaynağından kullanıcıya geçirildiğinde, her ODBC bileşeni (veri kaynağı, sürücü, Sürücü Yöneticisi) kendi adını ekler. Bu bilgiler, hatanın kaynağını belirlemenize yardımcı olur. Örnek: [Microsoft] [ODBC SQL Server sürücüsü] [SQL Server]

Framework, hata dizesini yorumlar ve bileşenlerini öğesine koyar; birden `m_strStateNativeOrigin` `m_strStateNativeOrigin` fazla hata için bilgi içeriyorsa, hatalar newlines ile ayrılır. Framework alfasayısal hata metnini içine koyar `m_strError` .

Bu dizeyi oluşturmak için kullanılan kodlar hakkında daha fazla bilgi için, *ODBC Programmer 's Reference* Içindeki [SqlError](/sql/odbc/reference/syntax/sqlerror-function) işlevine bakın.

### <a name="example"></a>Örnek

ODBC 'den: "durum: S0022, Yerel: 207, kaynak: \[ Microsoft] \[ ODBC SQL Server sürücüsü] \[ SQL Server] geçersiz sütun adı ' ColName '"

' De `m_strStateNativeOrigin` : "durum: S0022, Yerel: 207, kaynak: \[ Microsoft] \[ ODBC SQL Server sürücü] \[ SQL Server]"

' De `m_strError` : "geçersiz sütun adı ' ColName '"

## <a name="see-also"></a>Ayrıca bkz.

[CException sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset:: Update](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset::D Sil](../../mfc/reference/crecordset-class.md#delete)<br/>
[CException sınıfı](../../mfc/reference/cexception-class.md)
