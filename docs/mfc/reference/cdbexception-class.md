---
title: CDBException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
dev_langs:
- C++
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7766b56e75edefda4f40194a5ce18572c8d6d78d
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952254"
---
# <a name="cdbexception-class"></a>CDBException sınıfı
Veritabanı sınıflardan doğan bir özel durumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|Türünün bir açık veritabanı bağlantısı (ODBC) dönüş kodunu içerir **RETCODE**.|  
|[CDBException::m_strError](#m_strerror)|Alfasayısal koşullarını hatayı açıklayan bir dize içeriyor.|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC tarafından döndürülen hata kodlarını bakımından hatayı açıklayan bir dize içeriyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfı özel durumu açıklayan bir metin iletisi görüntülenecek veya özel durum nedenini belirlemek için kullanabileceğiniz iki genel veri üyelerini içerir. `CDBException` nesneleri oluşturulan ve veritabanı sınıfları üye işlevleri tarafından oluşturulur.  
  
> [!NOTE]
>  Bu sınıf MFC'ın açık veritabanı bağlantısı (ODBC) sınıfları biridir. Bunun yerine daha yeni veri erişim nesneleri (DAO) sınıfları'ı kullanıyorsanız, [CDaoException](../../mfc/reference/cdaoexception-class.md) yerine. Tüm DAO sınıf adları "CDao" önek olarak vardır. Daha fazla bilgi için bkz: [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).  
  
 Özel durumlar programın denetimi veri kaynağı gibi dışındaki koşullar ile ilgili olağan dışı yürütme örneklerini ya da ağ g/ç hatası. Programınızı yürütmenin normal seyrinde görmeyi bekleyebilirsiniz hatalar genellikle özel durumları kabul edilmez.  
  
 Bu nesneler kapsamında erişim bir **CATCH** ifade. Ayrıca throw `CDBException` kendi koduyla nesnelerden `AfxThrowDBException` genel işlevi.  
  
 Özel durum genel veya hakkında işleme hakkında daha fazla bilgi için `CDBException` nesneleri, makalelere bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
##  <a name="m_nretcode"></a>  CDBException::m_nRetCode  
 Türünün bir ODBC hata kodunu içerir **RETCODE** bir ODBC uygulama programlama arabirimi (API) işlevi tarafından döndürülen.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tür ODBC tarafından tanımlanan SQL önekli kodları ve veritabanı sınıfları tarafından tanımlanan AFX_SQL önekli kodları içerir. İçin bir `CDBException`, bu üye aşağıdaki değerlerden birini içerir:  
  
- **AFX_SQL_ERROR_API_CONFORMANCE** sürücü için bir `CDatabase::OpenEx` veya `CDatabase::Open` çağrısı gerekli ODBC API Uyumluluk Düzeyi 1 uymuyor ( **SQL_OAC_LEVEL1**).  
  
- **AFX_SQL_ERROR_CONNECT_FAIL** veri kaynağı bağlantısı başarısız oldu. Geçirilen bir **NULL** `CDatabase` kayıt kümesi oluşturucusu ve bir bağlantı oluşturmak için sonraki deneme işaretçi temel alarak `GetDefaultConnect` başarısız oldu.  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED** depolama için sağlanan daha fazla veri istedi. Sağlanan veri depolama için artırma hakkında daha fazla bilgi için `CString` veya `CByteArray` veri türlerini görmek `nMaxLength` bağımsız değişkeni için [RFX_Text](record-field-exchange-functions.md#rfx_text) ve [RFX_Binary](record-field-exchange-functions.md#rfx_binary) altında "makroları ve Globals."  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED** yapılan bir çağrı `CRecordset::Open` bir dynaset isteyen başarısız oldu. Dinamik kümeler sürücüsü tarafından desteklenmez.  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST** tablo açılmaya çalışıldı (veya ne verdiğiniz bir yordam çağrısı tanımlanamadı veya **seçin** deyimi) vardır ancak kayıt alanı değişimi (RFX) tanımlanan bir sütun yok işlev çağrıları, `DoFieldExchange` geçersiz kılar.  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH** bir RFX işlevi türü, `DoFieldExchange` geçersiz kılma kümesinde sütunun veri türüyle uyumlu değil.  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE** , adlı `CRecordset::Update` önceden çağırma olmadan `CRecordset::AddNew` veya `CRecordset::Edit`.  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** ODBC sürücüsü kilitleme desteklemediğinden güncelleştirmesi kayıtları kilitleme isteğinizi yerine getirilemedi.  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** , adlı `CRecordset::Update` veya `Delete` benzersiz bir anahtar içeren bir tablo için ve birden çok kayıt değiştirildi.  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD** düzenlemek veya önceden silinmiş kayıt silme girişiminde bulunuldu. Yeni bir geçerli kayda silindikten sonra kaydırma gerekir.  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES** ODBC sürücüsü desteklemediğinden bir dynaset doldurulmayacak için isteğiniz güncelleştirmeler konumlandırıldı.  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED** , adlı `CRecordset::Update` veya `Delete`, ancak işlemi başladığında, artık kaydı bulunamadı.  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** ODBC yükleme girişimi. DLL başarısız oldu; Windows bulunamadı veya bu DLL yüklenemedi. Bu önemli bir hatadır.  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED** Düzey 2 uyumlu bir ODBC sürücü gerekli olmadığından, dinamik küme isteğinizi yerine getirilemedi.  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY** veri kaynağına geri kaydırma desteklemediğinden kaydırma denemesi başarılı olmadı.  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED** yapılan bir çağrı `CRecordset::Open` bir anlık görüntü isteyen başarısız oldu. Anlık görüntü sürücüsü tarafından desteklenmez. (Bu yalnızca gerçekleşeceğini zaman ODBC imleç kitaplığı ODBCCURS. DLL mevcut değil.)  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE** sürücü için bir `CDatabase::OpenEx` veya `CDatabase::Open` çağrısı "Minimum" gerekli ODBC SQL Uyumluluk düzeyini uymuyor ( **SQL_OSC_MINIMUM**).  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** toplam boyutunu belirtmek ODBC sürücü açamadı bir `CLongBinary` veri değeri. Bir genel bellek bloğu değil önceden ayrılmış işlemi büyük olasılıkla başarısız oldu.  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY** salt okunur kayıt güncelleştirmeyi denedi ya da veri kaynağı salt okunur durumdadır. Kayıt kümesi ile hiçbir güncelleştirme işlemleri gerçekleştirilebilir veya `CDatabase` ilişkili olduğu nesne.  
  
- **SQL_ERROR hatası** işlevi başarısız oldu. ODBC işlevi tarafından döndürülen hata iletisi `SQLError` depolanan **m_strError** veri üyesi.  
  
- **SQL_INVALID_HANDLE** işlevi geçersiz ortam işleyici, bağlantı tanıtıcısı veya deyim tanıtıcısı nedeniyle başarısız oldu. Bu bir programlama hatası gösterir. Ek bilgi yok ODBC işlevinden kullanılabilir **SQLError**.  
  
 SQL önekli kodları ODBC tarafından tanımlanır. AFX önekli kodları AFXDB içinde tanımlanmıştır. H, MFC\INCLUDE içinde bulunamadı.  
  
##  <a name="m_strerror"></a>  CDBException::m_strError  
 Özel duruma neden olan hatayı açıklayan bir dize içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Dize alfasayısal koşullarında hata açıklanır. Daha ayrıntılı bilgi ve örnek için bkz: **m_strStateNativeOrigin**.  
  
##  <a name="m_strstatenativeorigin"></a>  CDBException::m_strStateNativeOrigin  
 Özel duruma neden olan hatayı açıklayan bir dize içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Dize biçimi kodları, sırasıyla açıklayan değerleri nerede değiştirilir form "durumu: % s, yerel: % ld kaynağı: % s", şöyledir:  
  
-   **SQLSTATE**, döndürülen beş karakterli hata kodu içeren bir null ile sonlandırılmış dize *szSqlState* ODBC işlevinin parametresi `SQLError`. **SQLSTATE** değerleri ek A, listelenen [ODBC hata kodları](https://msdn.microsoft.com/library/ms714687.aspx), *ODBC Programcının Başvurusu*. Örnek: "S0022".  
  
-   Veri kaynağına belirli yerel hata kodunu döndürdü *pfNativeError* parametresinin `SQLError` işlevi. Örnek: 207.  
  
-   Döndürülen hata iletisi metni *szErrorMsg* parametresinin `SQLError` işlevi. Bu ileti birkaç köşeli parantez içindeki adlarını oluşur. Bir hata kullanıcıya kaynağından geçirilen gibi her ODBC bileşeni (veri kaynağı, sürücüsü, Sürücü Yöneticisi) kendi adını ekler. Bu bilgiler hata kökenini belirlemenize yardımcı olur. Örnek: [Microsoft] [ODBC SQL Server sürücüsü] [SQL Server]  
  
 Framework hata dizesi yorumlar ve bileşenlerinin içine yerleştirir **m_strStateNativeOrigin**if **m_strStateNativeOrigin** bilgileri içeren birden fazla hata için hataları ile ayrılmıştır satır başı. Alfasayısal hata metne framework koyar **m_strError**.  
  
 Bu dize yapmak için kullanılan kodları hakkında ek bilgi için bkz: [SQLError](https://msdn.microsoft.com/library/ms716312.aspx) işlevi *ODBC Programcının Başvurusu*.  
  
### <a name="example"></a>Örnek  
  ODBC'den: "Durum: S0022, yerel: 207, kaynak: [Microsoft] [ODBC SQL Server sürücüsü] [SQL Server] Geçersiz sütun adı 'ColName'"  
  
 İçinde **m_strStateNativeOrigin**: "Durum: S0022, yerel: 207, kaynak: [Microsoft] [ODBC SQL Server sürücüsü] [SQL Server]"  
  
 İçinde **m_strError**: "geçersiz sütun adı 'ColName'"  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)   
 [CRecordset sınıfı](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException Sınıfı](../../mfc/reference/cexception-class.md)
