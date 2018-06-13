---
title: CHttpFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHttpFile
- AFXINET/CHttpFile
- AFXINET/CHttpFile::CHttpFile
- AFXINET/CHttpFile::AddRequestHeaders
- AFXINET/CHttpFile::EndRequest
- AFXINET/CHttpFile::GetFileURL
- AFXINET/CHttpFile::GetObject
- AFXINET/CHttpFile::GetVerb
- AFXINET/CHttpFile::QueryInfo
- AFXINET/CHttpFile::QueryInfoStatusCode
- AFXINET/CHttpFile::SendRequest
- AFXINET/CHttpFile::SendRequestEx
dev_langs:
- C++
helpviewer_keywords:
- CHttpFile [MFC], CHttpFile
- CHttpFile [MFC], AddRequestHeaders
- CHttpFile [MFC], EndRequest
- CHttpFile [MFC], GetFileURL
- CHttpFile [MFC], GetObject
- CHttpFile [MFC], GetVerb
- CHttpFile [MFC], QueryInfo
- CHttpFile [MFC], QueryInfoStatusCode
- CHttpFile [MFC], SendRequest
- CHttpFile [MFC], SendRequestEx
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a7fbdb3baff7531aa4e391e5d7e936c39e38fc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372625"
---
# <a name="chttpfile-class"></a>CHttpFile sınıfı
İstek ve bir HTTP sunucusunda dosyaları okumak için işlevsellik sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHttpFile::CHttpFile](#chttpfile)|Oluşturur bir `CHttpFile` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Bir HTTP sunucusuna gönderilen istek üstbilgileri ekler.|  
|[CHttpFile::EndRequest](#endrequest)|Bir HTTP sunucusuna gönderilen bir isteği sona [SendRequestEx](#sendrequestex) üye işlevi.|  
|[CHttpFile::GetFileURL](#getfileurl)|Belirtilen dosya için URL'yi alır.|  
|[CHttpFile::GetObject](#getobject)|Fiili hedef nesnesinin bir HTTP sunucusuna bir istek alır.|  
|[CHttpFile::GetVerb](#getverb)|Bir HTTP sunucusunda bir istekte kullanılan fiili alır.|  
|[CHttpFile::QueryInfo](#queryinfo)|HTTP sunucusundan yanıt veya istek üstbilgileri döndürür.|  
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|Bir HTTP isteğiyle ilişkili durum kodunu alır ve sağlanan yerleştirir `dwStatusCode` parametresi.|  
|[CHttpFile::SendRequest](#sendrequest)|Bir isteğin bir HTTP sunucusuna gönderir.|  
|[CHttpFile::SendRequestEx](#sendrequestex)|Bir isteği kullanılarak bir HTTP sunucusuna gönderir [yazma](../../mfc/reference/cinternetfile-class.md#write) veya [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) yöntemlerini `CInternetFile`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Internet oturumunuzu bir HTTP sunucusundan veri okuyan bir örneğini oluşturmanız gerekir `CHttpFile`.  
  
 Hakkında daha fazla bilgi için `CHttpFile` diğer MFC Internet sınıfları ile works başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="addrequestheaders"></a>  CHttpFile::AddRequestHeaders  
 Bir eklemek için bu üye işlevini çağırın veya daha fazla HTTP istek üstbilgilerinin HTTP isteğini işleyecek.  
  
```  
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,  
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,  
    int dwHeadersLen = -1);

 
BOOL AddRequestHeaders(
    CString& str,  
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrHeaders`  
 Üstbilgi veya isteğine eklemek için üstbilgiler içeren bir dize için bir işaretçi. Her üstbilgisi CR/LF çifti ile bitmelidir.  
  
 `dwFlags`  
 Yeni üst bilgileri semantiğini değiştirir. Aşağıdakilerden biri olabilir:  
  
- `HTTP_ADDREQ_FLAG_COALESCE` Sonraki üstbilgiye bulunan ilk üstbilgisi eklemek için bayrağını kullanarak aynı ada sahip üstbilgileri birleştirir. Örneğin, "kabul et: metin / *" ve ardından "kabul et: ses /\*" sonuçları tek üstbilgi oluşturulması "kabul et: metin /\*, ses /\*". Bağlı bir düzeni birleştirmesine veya ayrı başlığı ile gönderilen istekleri tarafından alınan veri göre emin olmak için çağrı yapan uygulamanın kadar olur.  
  
- `HTTP_ADDREQ_FLAG_REPLACE` Bir kaldırma gerçekleştirir ve geçerli üstbilgi değiştirmek için ekleyin. Üstbilgi adı geçerli üstbilgiyi kaldırmak için kullanılan ve yeni üstbilgi eklemek için tam değer kullanılır. Üstbilgi değeri boş ise ve üst bilgi bulunamadı, kaldırılır. Değilse boş üstbilgi değeri değiştirilir.  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW` Zaten yoksa, yalnızca bir üst bilgi ekler. Varsa, bir hata döndürülür.  
  
- `HTTP_ADDREQ_FLAG_ADD` METİNLE kullanılır. Yoksa üstbilgisi ekler.  
  
 `dwHeadersLen`  
 Karakter cinsinden uzunluğu, `pstrHeaders`. Bu-1 M ise, `pstrHeaders` sıfır sonlandırılan olduğu varsayılır ve uzunluğu hesaplanır.  
  
 `str`  
 Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) istek üstbilgisi veya eklemek için üstbilgiler içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `AddRequestHeaders` HTTP istek işleyicisi için ek, serbest biçimli üstbilgileri ekler. HTTP sunucuya gönderilen tam istek üzerinde ayrıntılı denetim isteyen Gelişmiş istemcileri tarafından kullanılmak üzere tasarlanmıştır.  
  
> [!NOTE]
>  Uygulamanın birden çok üst bilgilerinde geçirebilirsiniz `pstrHeaders` veya `str` için bir `AddRequestHeaders` çağrıda `HTTP_ADDREQ_FLAG_ADD` veya `HTTP_ADDREQ_FLAG_ADD_IF_NEW`. Uygulama kullanarak bir başlık değiştirin veya kaldırmak çalışırsa **HTTP_ADDREQ_FLAG_REMOVE** veya `HTTP_ADDREQ_FLAG_REPLACE`, yalnızca bir üstbilgi sağlanan içinde `lpszHeaders`.  
  
##  <a name="chttpfile"></a>  CHttpFile::CHttpFile  
 Bu üye işlevi oluşturmak için çağrılan bir `CHttpFile` nesnesi.  
  
```  
CHttpFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrObject,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrVerb,  
    DWORD_PTR dwContext);

 
CHttpFile(
    HINTERNET hFile,  
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObject,  
    CHttpConnection* pConnection);
```  
  
### <a name="parameters"></a>Parametreler  
 `hFile`  
 Internet dosyası için bir tanıtıcı.  
  
 `hSession`  
 Bir Internet oturumu için bir tanıtıcı.  
  
 *pstrObject*  
 İçeren bir dize için bir işaretçi `CHttpFile` nesnesi.  
  
 `pstrServer`  
 Sunucu adını içeren bir dize için bir işaretçi.  
  
 `pstrVerb`  
 İstek gönderirken kullanılacak yöntemi içeren bir dize için bir işaretçi. Olabilir **POST**, **HEAD**, veya `GET`.  
  
 dwContext  
 İçerik tanımlayıcısını `CHttpFile` nesnesi. Bkz: **açıklamalar** Bu parametre hakkında daha fazla bilgi.  
  
 `pConnection`  
 Bir işaretçi bir [CHttpConnection](../../mfc/reference/chttpconnection-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman oluşturmak bir `CHttpFile` doğrudan nesne; bunun yerine çağrısı [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) yerine.  
  
 İçin varsayılan değer `dwContext` MFC'ye tarafından gönderilen `CHttpFile` nesnesinin [CInternetSession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CHttpFile` nesne. Çağırdığınızda `CInternetSession::OpenURL` veya `CHttpConnection` oluşturmak için bir `CHttpFile` nesne bağlamı tanımlayıcı bir değerine ayarlamak için varsayılan geçersiz kılabilirsiniz. Bağlam tanıtıcısı döndürülen [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen bir nesne üzerinde durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
##  <a name="endrequest"></a>  CHttpFile::EndRequest  
 Bir HTTP sunucusuna gönderilen bir istek sonlandırmak için bu üye işlevini çağırın [SendRequestEx](#sendrequestex) üye işlevi.  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 İşlemi tanımlayan işaretler. Uygun bayrakları listesi için bkz: [HttpEndRequest](http://msdn.microsoft.com/library/windows/desktop/aa384230) Windows SDK'sındaki.  
  
 `lpBuffIn`  
 Başlatılan bir işaretçi [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) işleminde giriş arabelleği açıklar.  
  
 `dwContext`  
 İçerik tanımlayıcısını `CHttpFile` işlemi. Açıklamalar, bu parametre hakkında daha fazla bilgi için bkz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, atılmış inceleyerek hatanın nedenini belirleyin [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin varsayılan değer `dwContext` MFC'ye tarafından gönderilen `CHttpFile` nesnesinin [CInternetSession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CHttpFile` nesne. Çağırdığınızda [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection](../../mfc/reference/chttpconnection-class.md) oluşturmak için bir `CHttpFile` nesne bağlamı tanımlayıcı bir değerine ayarlamak için varsayılan geçersiz kılabilirsiniz. Bağlam tanıtıcısı döndürülen [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen bir nesne üzerinde durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
##  <a name="getfileurl"></a>  CHttpFile::GetFileURL  
 URL olarak HTTP dosyasının adı almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) bu dosyayla ilişkili kaynağa başvuran bir URL içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanmak [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getobject"></a>  CHttpFile::GetObject  
 Bu ile ilişkili nesne adını almak için bu üye işlevini çağırın `CHttpFile`.  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesinin adını içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanmak [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getverb"></a>  CHttpFile::GetVerb  
 HTTP fiili (veya yöntem) bu ile ilişkili almak için bu üye işlevini çağırın `CHttpFile`.  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) HTTP fiili (veya yöntem) adını içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanmak [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="queryinfo"></a>  CHttpFile::QueryInfo  
 Yanıt döndürür veya HTTP isteğinden üstbilgileri istemek için bu üye işlevini çağırın.  
  
```  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    LPVOID lpvBuffer,  
    LPDWORD lpdwBufferLength,  
    LPDWORD lpdwIndex = NULL) const;  
  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    CString& str,  
    LPDWORD dwIndex = NULL) const;  
  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    SYSTEMTIME* pSysTime,  
    LPDWORD dwIndex = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `dwInfoLevel`  
 Sorgu ve istenen bilgi türünü belirten aşağıdaki bayrakları özniteliğine birleşimi:  
  
- **HTTP_QUERY_CUSTOM** üstbilgi adı bulur ve bu değeri döndürür `lpvBuffer` çıktıyı. **HTTP_QUERY_CUSTOM** üstbilgi bulunamazsa bir onaylama oluşturur.  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS** genellikle, uygulamanın yanıt üstbilgileri sorgular, ancak bir uygulama da istek üstbilgileri Bu bayrak kullanarak sorgulayabilirsiniz.  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME** Bu bayrak değeri olan "Son değiştiren-zamanı," gibi bir tarih dizesi bu üstbilgileri için standart Win32 olarak üstbilgi değeri döndürür [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) gerektirmez yapısı verileri ayrıştırmak için uygulama. Bu bayrağı kullanırsanız kullanmak isteyebilirsiniz `SYSTEMTIME` işlevi geçersiz kılar.  
  
- **HTTP_QUERY_FLAG_NUMBER** değeri olan bir sayı durum kodu gibi bu üst bilgileri için bu bayrak verileri 32 bitlik bir sayı olarak döndürür.  
  
 Bkz: **açıklamalar** olası değerler listesi bölümü.  
  
 `lpvBuffer`  
 Bilgi alır arabellek için bir işaretçi.  
  
 `lpdwBufferLength`  
 Girişte, bu karakter veya bayt cinsinden veri arabelleği uzunluğunu içeren bir değeri gösterir. Bkz: **açıklamalar** Bu parametre hakkında daha ayrıntılı bilgi için bölüm.  
  
 `lpdwIndex`  
 Sıfır tabanlı üstbilgi dizini için bir işaretçi. Olabilir **NULL**. Aynı ada sahip birden çok üstbilgi numaralandırmak için bu bayrağı kullanın. Giriş üzerinde `lpdwIndex` döndürmek için belirtilen üstbilgi dizinini gösterir. Çıktıyı `lpdwIndex` sonraki üstbilgi dizinini gösterir. Sonraki dizin bulunamazsa **ERROR_HTTP_HEADER_NOT_FOUND** döndürülür.  
  
 `str`  
 Bir başvuru [CString](../../atl-mfc-shared/reference/cstringt-class.md) döndürülen bilgileri alan nesne.  
  
 `dwIndex`  
 Bir dizin değeri. Bkz: `lpdwIndex`.  
  
 *pSysTime*  
 Bir işaretçi bir Win32 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanmak [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Aşağıdaki veri türlerini alabilir `QueryInfo`:  
  
-   dizeler (varsayılan)  
  
- `SYSTEMTIME` (için "verileri:" "Expires:" vb., üst bilgiler)  
  
- `DWORD` (için **STATUS_CODE**, **CONTENT_LENGTH is sıfırdan büyük**, vb..)  
  
 Bir dize arabelleğe yazılır ve üye fonksiyonu başarılı, `lpdwBufferLength` eksi sonlandırma için 1 karakter dize uzunluğunu içeren **NULL** karakter.  
  
 Olası `dwInfoLevel` değerleri şunlardır:  
  
- **HTTP_QUERY_MIME_VERSION**  
  
- **HTTP_QUERY_CONTENT_TYPE**  
  
- **HTTP_QUERY_CONTENT_TRANSFER_ENCODING**  
  
- **HTTP_QUERY_CONTENT_ID**  
  
- **HTTP_QUERY_CONTENT_DESCRIPTION**  
  
- **HTTP_QUERY_CONTENT_LENGTH**  
  
- **HTTP_QUERY_ALLOWED_METHODS**  
  
- **HTTP_QUERY_PUBLIC_METHODS**  
  
- **HTTP_QUERY_DATE**  
  
- **HTTP_QUERY_EXPIRES**  
  
- **HTTP_QUERY_LAST_MODIFIED**  
  
- **HTTP_QUERY_MESSAGE_ID**  
  
- **HTTP_QUERY_URI**  
  
- **HTTP_QUERY_DERIVED_FROM**  
  
- **HTTP_QUERY_LANGUAGE**  
  
- **HTTP_QUERY_COST**  
  
- **HTTP_QUERY_WWW_LINK**  
  
- **HTTP_QUERY_PRAGMA**  
  
- **HTTP_QUERY_VERSION**  
  
- **HTTP_QUERY_STATUS_CODE**  
  
- **HTTP_QUERY_STATUS_TEXT**  
  
- **HTTP_QUERY_RAW_HEADERS**  
  
- **HTTP_QUERY_RAW_HEADERS_CRLF**  
  
##  <a name="queryinfostatuscode"></a>  CHttpFile::QueryInfoStatusCode  
 Bir HTTP isteğiyle ilgili durum kodu almak için bu üye işlevini çağırın ve sağlanan yerleştirin `dwStatusCode` parametresi.  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStatusCode`  
 Bir durum kodu bir başvuru. Durum kodları, başarı veya başarısızlık istenen olay gösterir. Bkz: **açıklamalar** durum kodu açıklamalarını seçimi için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanmak [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 HTTP durum kodları, başarı veya başarısızlık isteğin belirten gruba ayrılır. Aşağıdaki tablolarda, durum kodu grupları ve en sık kullanılan HTTP durum kodları verilmiştir.  
  
|Grup|Açıklama|  
|-----------|-------------|  
|200-299|Başarılı|  
|300-399|Bilgiler|  
|400-499|İstek hatası|  
|500-599|Sunucu hatası|  
  
 Ortak HTTP durum kodları:  
  
|Durum kodu|Açıklama|  
|-----------------|-------------|  
|200|URL, bulunan iletim izler|  
|400|Anlamsız isteği|  
|404|İstenen URL bulunamadı|  
|405|Sunucu istenen yöntemi desteklemiyor|  
|500|Bilinmeyen sunucu hatası|  
|503|Sunucu kapasitesini ulaşıldı|  
  
##  <a name="sendrequest"></a>  CHttpFile::SendRequest  
 Bir HTTP sunucusuna bir istek göndermek için bu üye işlevini çağırın.  
  
```  
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,  
    DWORD dwHeadersLen = 0,  
    LPVOID lpOptional = NULL,  
    DWORD dwOptionalLen = 0);

 
BOOL SendRequest(
    CString& strHeaders,  
    LPVOID lpOptional = NULL,  
    DWORD dwOptionalLen = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrHeaders`  
 Göndermek için üstbilgi adını içeren bir dize için bir işaretçi.  
  
 `dwHeadersLen`  
 Tarafından tanımlanan Üstbilgi uzunluğu `pstrHeaders`.  
  
 `lpOptional`  
 Hemen sonra istek üstbilgileri göndermek için isteğe bağlı tüm veriler. Bu genellikle kullanılan **POST** ve **PUT** işlemleri. Bu, **NULL** göndermek için isteğe bağlı veri yoksa.  
  
 *dwOptionalLen*  
 Uzunluğu `lpOptional`.  
  
 `strHeaders`  
 Gönderilen istek için üstbilgileri adını içeren dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, atılmış inceleyerek hatanın nedenini belirleyin [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi.  
  
##  <a name="sendrequestex"></a>  CHttpFile::SendRequestEx  
 Bir HTTP sunucusuna bir istek göndermek için bu üye işlevini çağırın.  
  
```  
BOOL SendRequestEx(
    DWORD dwTotalLen,  
    DWORD dwFlags = HSR_INITIATE,  
    DWORD_PTR dwContext = 1);

 
BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,  
    LPINTERNET_BUFFERS lpBuffOut,  
    DWORD dwFlags = HSR_INITIATE,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwTotalLen*  
 İstekte gönderilecek bayt sayısı.  
  
 `dwFlags`  
 İşlemi tanımlayan işaretler. Uygun bayrakları listesi için bkz: [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318) Windows SDK'sındaki.  
  
 `dwContext`  
 İçerik tanımlayıcısını `CHttpFile` işlemi. Açıklamalar, bu parametre hakkında daha fazla bilgi için bkz.  
  
 `lpBuffIn`  
 Başlatılan bir işaretçi [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) işleminde giriş arabelleği açıklar.  
  
 *lpBuffOut*  
 Başlatılan bir işaretçi **INTERNET_BUFFERS** işlem için kullanılan çıkış arabelleği açıklar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır. Çağrı başarısız olursa, atılmış inceleyerek hatanın nedenini belirleyin [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi kullanarak veri göndermek uygulamanız izin [yazma](../../mfc/reference/cinternetfile-class.md#write) ve [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) yöntemlerini `CInternetFile`. Bu işlevi ya da geçersiz kılma çağırmadan önce gönderilecek veri uzunluğu bilmeniz gerekir. İlk geçersiz kılma verileri göndermek istediğinizi uzunluk belirtmenize olanak tanır. İkinci geçersiz kılma işaretçileri kabul **INTERNET_BUFFERS** arabellek çok ayrıntılı olarak tanımlamak için kullanılan yapılar.  
  
 İçeriği dosyaya yazıldıktan sonra çağrısı [EndRequest](#endrequest) işlemi sona erdirmek için.  
  
 İçin varsayılan değer `dwContext` MFC'ye tarafından gönderilen `CHttpFile` nesnesinin [CInternetSession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CHttpFile` nesne. Çağırdığınızda [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection](../../mfc/reference/chttpconnection-class.md) oluşturmak için bir `CHttpFile` nesne bağlamı tanımlayıcı bir değerine ayarlamak için varsayılan geçersiz kılabilirsiniz. Bağlam tanıtıcısı döndürülen [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen bir nesne üzerinde durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
### <a name="example"></a>Örnek  
 Bu kod parçası MFCISAPI adlı bir DLL için bir dize içerik gönderir. DLL LOCALHOST sunucusunda. Bu örnek yalnızca bir çağrı kullanırken `WriteString`, birden fazla çağrı kullanarak veri bloğu gönderme kabul edilebilir.  
  
 [!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)   
 [CHttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)
