---
title: CHttpFile sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 0c8c401b43361a5e1472e3470f5ea452c91b957f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505956"
---
# <a name="chttpfile-class"></a>CHttpFile sınıfı

Bir HTTP sunucusunda dosya isteme ve okuma işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHttpFile::CHttpFile](#chttpfile)|Bir `CHttpFile` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHttpFile:: AddRequestHeaders](#addrequestheaders)|HTTP sunucusuna gönderilen istek için üst bilgiler ekler.|
|[CHttpFile:: EndRequest](#endrequest)|[SendRequestEx](#sendrequestex) üye işleviyle http sunucusuna gönderilen isteği sonlandırır.|
|[CHttpFile:: GetFileURL](#getfileurl)|Belirtilen dosyanın URL 'sini alır.|
|[CHttpFile:: GetObject](#getobject)|Bir HTTP sunucusuna yapılan istekte fiilin hedef nesnesini alır.|
|[CHttpFile:: GetVerb](#getverb)|HTTP sunucusuna yapılan bir istekte kullanılan fiili 'i alır.|
|[CHttpFile:: QueryInfo](#queryinfo)|HTTP sunucusundan gelen yanıt veya istek üst bilgilerini döndürür.|
|[CHttpFile:: Querınınfostatuscode](#queryinfostatuscode)|Bir HTTP isteğiyle ilişkili durum kodunu alır ve sağlanan `dwStatusCode` parametreye koyar.|
|[CHttpFile:: SendRequest](#sendrequest)|HTTP sunucusuna bir istek gönderir.|
|[CHttpFile:: SendRequestEx](#sendrequestex)|Bir HTTP sunucusuna, ' ın `CInternetFile` [Write](../../mfc/reference/cinternetfile-class.md#write) veya [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) yöntemlerini kullanarak bir istek gönderir.|

## <a name="remarks"></a>Açıklamalar

Internet oturumunuz bir HTTP sunucusundan verileri okuyorsa, bir örneği `CHttpFile`oluşturmanız gerekir.

Diğer MFC Internet sınıflarıyla nasıl `CHttpFile` çalıştığı hakkında daha fazla bilgi edinmek için bkz. [WinINet ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

##  <a name="addrequestheaders"></a>CHttpFile:: AddRequestHeaders

HTTP istek tanıtıcısına bir veya daha fazla HTTP istek üst bilgisi eklemek için bu üye işlevi çağırın.

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

*pstrHeaders*<br/>
İsteğe eklenecek üstbilgiyi veya üstbilgileri içeren bir dizeye yönelik işaretçi. Her üst bilgi bir CR/LF çifti tarafından sonlandırılmalıdır.

*dwFlags*<br/>
Yeni üstbilgilerin semantiğini değiştirir. Aşağıdakilerden biri olabilir:

- HTTP_ADDREQ_FLAG_COALESCE, Sonraki üstbilgiye bulunan ilk üstbilgiyi eklemek için bayrağını kullanarak aynı ada sahip üst bilgileri birleştirir. Örneğin, "kabul et: Text/\*" in ardından "Accept: Audio/\*", tek üstbilginin "Accept: Text/\*, Audio/\*" olarak sonuçlanır. Birleştirme veya ayrı üst bilgiler ile gönderilen isteklere göre alınan verilerle ilgili olarak, birbirine bağlı bir düzen sağlamak için çağıran uygulamaya çalışır.

- HTTP_ADDREQ_FLAG_REPLACE, geçerli üst bilgiyi değiştirecek bir Remove ve Add uygular. Üstbilgi adı geçerli üstbilgiyi kaldırmak için kullanılır ve yeni üst bilgiyi eklemek için tam değer kullanılır. Üst bilgi değeri boşsa ve üst bilgi bulunursa, kaldırılır. Boş değilse, üst bilgi değeri değiştirilmiştir.

- HTTP_ADDREQ_FLAG_ADD_IF_NEW yalnızca, zaten mevcut değilse üstbilgiyi ekler. Varsa, bir hata döndürülür.

- HTTP_ADDREQ_FLAG_ADD, REPLACE ile kullanılır. Mevcut değilse üst bilgiyi ekler.

*dwHeadersLen*<br/>
*PstrHeaders*için karakter cinsinden uzunluk. Bu-1L ise, *pstrHeaders* 'in sıfır ile sonlandırıldığını ve uzunluğunun hesaplandığını kabul edilir.

*üstbilgisine*<br/>
Eklenecek istek üst bilgisini veya üst bilgileri içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) WIN32 Win32 işlevi çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`AddRequestHeaders`HTTP istek tanıtıcısına ek, serbest biçimli üstbilgiler ekler. HTTP sunucusuna gönderilen tam istek üzerinde ayrıntılı denetim gerektiren Gelişmiş istemciler tarafından kullanılmak üzere tasarlanmıştır.

> [!NOTE]
>  Uygulama, HTTP_ADDREQ_FLAG_ADD veya HTTP_ADDREQ_FLAG_ADD_IF_NEW kullanarak bir `AddRequestHeaders` çağrı için *pstrHeaders* veya *Str* içinde birden fazla üst bilgi geçirebilir. Uygulama HTTP_ADDREQ_FLAG_REMOVE veya HTTP_ADDREQ_FLAG_REPLACE kullanarak bir üst bilgiyi kaldırmaya veya değiştirmeye çalışırsa, *lpszHeaders*içinde yalnızca bir üst bilgi sağlanabilir.

##  <a name="chttpfile"></a>CHttpFile::CHttpFile

Bu üye işlevi bir `CHttpFile` nesne oluşturmak için çağırılır.

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

*hFile*<br/>
Internet dosyası için bir tanıtıcı.

*hSession*<br/>
Bir Internet oturumu için tanıtıcı.

*pstrObject*<br/>
`CHttpFile` Nesneyi içeren bir dize işaretçisi.

*pstrServer*<br/>
Sunucu adını içeren bir dize işaretçisi.

*pstrVerb*<br/>
İstek gönderilirken kullanılacak yöntemi içeren bir dizeye yönelik işaretçi. GÖNDERI, baş veya GET olabilir.

*dwContext*<br/>
`CHttpFile` Nesnenin bağlam tanımlayıcısı. Bu parametre hakkında daha fazla bilgi için bkz. **açıklamalar** .

*pConnection*<br/>
[CHttpConnection](../../mfc/reference/chttpconnection-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Hiçbir şey doğrudan bir `CHttpFile` nesne oluşturun; bunun yerine [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) ' i çağırın.

Varsayılan değeri `dwContext` , MFC `CHttpFile` tarafından `CHttpFile` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesnesine gönderilir. Bir nesne oluşturduğunuzda `CHttpConnection` `CHttpFile` veya bir nesnesi oluşturmak için, bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. `CInternetSession::OpenURL` Bağlam tanımlayıcısı, tanımlanan nesne üzerinde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) öğesine döndürülür. Bkz. [Internet ilk adımlar: Bağlam](../../mfc/wininet-basics.md) tanımlayıcısı hakkında daha fazla bilgi için WinINet.

##  <a name="endrequest"></a>CHttpFile:: EndRequest

[SendRequestEx](#sendrequestex) üye IŞLEVIYLE bir http sunucusuna gönderilen isteği sonlandırmak için bu üye işlevini çağırın.

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
İşlemi açıklayan bayraklar. Uygun bayrakların bir listesi için, Windows SDK [HttpEndRequest](/windows/win32/api/wininet/nf-wininet-httpendrequestw) bölümüne bakın.

*lpBuffIn*<br/>
İşlem için kullanılan giriş arabelleğini açıklayan başlatılmış bir [INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw) işaretçisi.

*dwContext*<br/>
`CHttpFile` İşlemin bağlam tanımlayıcısı. Bu parametre hakkında daha fazla bilgi için bkz. açıklamalar.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, oluşturulan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini saptayın.

### <a name="remarks"></a>Açıklamalar

*DwContext* için varsayılan değer, MFC `CHttpFile` tarafından `CHttpFile` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesnesine gönderilir. Bir`CHttpFile` nesne oluşturmak için [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ' ı çağırdığınızda, bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı, tanımlanan nesne üzerinde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) öğesine döndürülür. Bkz. [Internet 'te ilk adımlar: Bağlam](../../mfc/wininet-basics.md) tanımlayıcısı hakkında daha fazla bilgi için WinINet.

##  <a name="getfileurl"></a>CHttpFile:: GetFileURL

HTTP dosyasının adını bir URL olarak almak için bu üye işlevi çağırın.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu dosyayla ilişkili kaynağa başvuran bir URL içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest](#sendrequest) 'e başarılı bir çağrıdan veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla `CHttpFile` oluşturulan bir nesnede kullanın.

##  <a name="getobject"></a>CHttpFile:: GetObject

Bununla ilişkili `CHttpFile`nesnenin adını almak için bu üye işlevi çağırın.

```
CString GetObject() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin adını içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest](#sendrequest) 'e başarılı bir çağrıdan veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla `CHttpFile` oluşturulan bir nesnede kullanın.

##  <a name="getverb"></a>CHttpFile:: GetVerb

Bu `CHttpFile`üye işlevini, bununla ilişkili http fiilini (veya yöntemini) almak için çağırın.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Dönüş Değeri

HTTP fiilinin adını (veya yöntemini) içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest](#sendrequest) 'e başarılı bir çağrıdan veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla `CHttpFile` oluşturulan bir nesnede kullanın.

##  <a name="queryinfo"></a>CHttpFile:: QueryInfo

HTTP isteğinden yanıt veya istek üst bilgilerini döndürmek için bu üye işlevi çağırın.

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

*dwInfoLevel*<br/>
Sorgulanacak özniteliğin bir birleşimi ve istenen bilgi türünü belirten aşağıdaki bayraklar:

- HTTP_QUERY_CUSTOM üst bilgi adını bulur ve çıktıda *lpvBuffer* içinde bu değeri döndürür. HTTP_QUERY_CUSTOM, üst bilgi bulunmazsa bir onaylama işlemi oluşturur.

- HTTP_QUERY_FLAG_REQUEST_HEADERS genellikle uygulama, yanıt üst bilgilerini sorgular, ancak bir uygulama bu bayrağı kullanarak istek üstbilgilerini de sorgulayabilir.

- HTTP_QUERY_FLAG_SYSTEMTIME değeri bir tarih/saat dizesi olan ("son değiştirilme zamanı" gibi), bu bayrak üst bilgi değerini uygulamanın verileri ayrıştırmasına gerek olmayan standart bir Win32 [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısı olarak döndürür. Bu bayrağı kullanırsanız, işlevini `SYSTEMTIME` geçersiz kılmayı kullanmak isteyebilirsiniz.

- Değer, durum kodu gibi bir sayı olan bu üstbilgiler Için HTTP_QUERY_FLAG_NUMBER, bu bayrak, verileri 32 bitlik bir sayı olarak döndürür.

Olası değerlerin listesi için **açıklamalar** bölümüne bakın.

*lpvBuffer*<br/>
Bilgileri alan arabelleğin işaretçisi.

*lpdwBufferLength*<br/>
Girişte, bu, karakter veya bayt sayısı cinsinden veri arabelleğinin uzunluğunu içeren bir değere işaret eder. Bu parametre hakkında daha ayrıntılı bilgi için **açıklamalar** bölümüne bakın.

*lpdwIndex*<br/>
Sıfır tabanlı üst bilgi dizinine yönelik bir işaretçi. NULL olabilir. Aynı ada sahip birden fazla üstbilgiyi numaralandırmak için bu bayrağı kullanın. Giriş sayfasında *lpdwIndex* , döndürülecek belirtilen üstbilginin dizinini gösterir. Çıkışta, *Lpdwını* , sonraki üstbilginin dizinini gösterir. Sonraki dizin bulunamazsa, ERROR_HTTP_HEADER_NOT_FOUND döndürülür.

*üstbilgisine*<br/>
Döndürülen bilgileri alan [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine bir başvuru.

*dwIndex*<br/>
Bir dizin değeri. Bkz. *lpdwIndex*.

*pSysTime*<br/>
Win32 [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) WIN32 Win32 işlevi çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest](#sendrequest) 'e başarılı bir çağrıdan veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla `CHttpFile` oluşturulan bir nesnede kullanın.

Aşağıdaki veri türlerini şuradan `QueryInfo`alabilirsiniz:

- dizeler (varsayılan)

- `SYSTEMTIME`("veri:" "süre sonu:" vb. başlıklar)

- DWORD (STATUS_CODE, CONTENT_LENGTH vb.)

Bir dize, arabelleğe yazıldığında ve üye işlevi başarılı olursa, Sonlandırıcı null karakteri için `lpdwBufferLength` , karakter cinsinden bir dizenin uzunluğunu eksi 1 olarak içerir.

Olası *dwInfoLevel* değerleri şunlardır:

- HTTP_QUERY_MIME_VERSION

- HTTP_QUERY_CONTENT_TYPE

- HTTP_QUERY_CONTENT_TRANSFER_ENCODING

- HTTP_QUERY_CONTENT_ID

- HTTP_QUERY_CONTENT_DESCRIPTION

- HTTP_QUERY_CONTENT_LENGTH

- HTTP_QUERY_ALLOWED_METHODS

- HTTP_QUERY_PUBLIC_METHODS

- HTTP_QUERY_DATE

- HTTP_QUERY_EXPIRES

- HTTP_QUERY_LAST_MODIFIED

- HTTP_QUERY_MESSAGE_ID

- HTTP_QUERY_URI

- HTTP_QUERY_DERIVED_FROM

- HTTP_QUERY_LANGUAGE

- HTTP_QUERY_COST

- HTTP_QUERY_WWW_LINK

- HTTP_QUERY_PRAGMA

- HTTP_QUERY_VERSION

- HTTP_QUERY_STATUS_CODE

- HTTP_QUERY_STATUS_TEXT

- HTTP_QUERY_RAW_HEADERS

- HTTP_QUERY_RAW_HEADERS_CRLF

##  <a name="queryinfostatuscode"></a>CHttpFile:: Querınınfostatuscode

Bir HTTP isteğiyle ilişkili durum kodunu almak ve sağlanan *dwStatusCode* parametresine yerleştirmek için bu üye işlevi çağırın.

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>Parametreler

*dwStatusCode*<br/>
Bir durum koduna başvuru. Durum kodları, istenen olayın başarısını veya başarısızlığını gösterir. Durum kodu açıklamaları seçimine ilişkin **açıklamalar** bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) WIN32 Win32 işlevi çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest](#sendrequest) 'e başarılı bir çağrıdan veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla `CHttpFile` oluşturulan bir nesnede kullanın.

HTTP durum kodları, isteğin başarısını veya başarısızlığını belirten gruplara girer. Aşağıdaki tablolarda durum kodu grupları ve en sık kullanılan HTTP durum kodları ana hatlarıyla verilmiştir.

|Grup|Açıklama|
|-----------|-------------|
|200-299|Başarılı|
|300-399|Bilgiler|
|400-499|İstek hatası|
|500-599|Sunucu hatası|

Ortak HTTP durum kodları:

|Durum kodu|Açıklama|
|-----------------|-------------|
|200|URL bulunuyor, iletim takip ediyor|
|400|Anlaşılır olmayan istek|
|404|İstenen URL bulunamadı|
|405|Sunucu istenen yöntemi desteklemiyor|
|500|Bilinmeyen sunucu hatası|
|503|Sunucu kapasitesine ulaşıldı|

##  <a name="sendrequest"></a>CHttpFile:: SendRequest

Bir HTTP sunucusuna istek göndermek için bu üye işlevi çağırın.

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

*pstrHeaders*<br/>
Gönderileceği üst bilgilerin adını içeren bir dize işaretçisi.

*dwHeadersLen*<br/>
*PstrHeaders*tarafından tanımlanan üst bilgilerin uzunluğu.

*Lpopıll*<br/>
İstek üstbilgilerinden hemen sonra göndermek için isteğe bağlı veriler. Bu genellikle POST ve PUT işlemlerinde kullanılır. Bu, göndermek için isteğe bağlı veri yoksa NULL olabilir.

*dwOptionalLen*<br/>
*Lpopsel*uzunluğu.

*strHeaders*<br/>
Gönderilmekte olan istek için üst bilgilerin adını içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, oluşturulan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini saptayın.

##  <a name="sendrequestex"></a>CHttpFile:: SendRequestEx

Bir HTTP sunucusuna istek göndermek için bu üye işlevi çağırın.

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

*dwTotalLen*<br/>
İstekte gönderilecek bayt sayısı.

*dwFlags*<br/>
İşlemi açıklayan bayraklar. Uygun bayrakların bir listesi için, Windows SDK bkz. [HttpSendRequestEx](/windows/win32/api/wininet/nf-wininet-httpsendrequestexw) .

*dwContext*<br/>
`CHttpFile` İşlemin bağlam tanımlayıcısı. Bu parametre hakkında daha fazla bilgi için bkz. açıklamalar.

*lpBuffIn*<br/>
İşlem için kullanılan giriş arabelleğini açıklayan başlatılmış bir [INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw) işaretçisi.

*lpBuffOut*<br/>
İşlem için kullanılan çıkış arabelleğini açıklayan başlatılmış bir INTERNET_BUFFERS işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı. Çağrı başarısız olursa, oluşturulan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini saptayın.

### <a name="remarks"></a>Açıklamalar

Bu işlev, uygulamanızın [Write](../../mfc/reference/cinternetfile-class.md#write) ve [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) yöntemlerini `CInternetFile`kullanarak veri göndermesini sağlar. Bu işlevin geçersiz kılınması çağrılmadan önce göndermek için verilerin uzunluğunu bilmeniz gerekir. İlk geçersiz kılma, göndermek istediğiniz verilerin uzunluğunu belirtmenize olanak tanır. İkinci geçersiz kılma, INTERNET_BUFFERS yapılarının işaretçilerini kabul eder ve bu da, arabelleği en iyi şekilde tanımlayan şekilde kullanılabilir.

İçerik dosyaya yazıldıktan sonra, işlemi sonlandırmak için [EndRequest](#endrequest) ' i çağırın.

*DwContext* için varsayılan değer, MFC `CHttpFile` tarafından `CHttpFile` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesnesine gönderilir. Bir`CHttpFile` nesne oluşturmak için [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ' ı çağırdığınızda, bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı, tanımlanan nesne üzerinde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) öğesine döndürülür. Bkz. [Internet ilk adımlar: Bağlam](../../mfc/wininet-basics.md) tanımlayıcısı hakkında daha fazla bilgi için WinINet.

### <a name="example"></a>Örnek

Bu kod parçası, bir dizenin içeriğini MFCıSAPı adlı bir DLL 'ye gönderir. DLL 'yi LOCALHOST sunucusunda yapın. Bu örnek için `WriteString`yalnızca bir çağrısı kullandığından, blok halinde veri göndermek için birden çok çağrı kullanılması kabul edilebilir.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)
