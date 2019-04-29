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
ms.openlocfilehash: 3c701f933d622adc5f3d8b1eb2371406e5b45e6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345805"
---
# <a name="chttpfile-class"></a>CHttpFile sınıfı

İstemek ve bir HTTP sunucusunda dosyaları okumak için gereken işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHttpFile::CHttpFile](#chttpfile)|Oluşturur bir `CHttpFile` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Bir HTTP sunucusuna gönderilen istek üst bilgileri ekler.|
|[CHttpFile::EndRequest](#endrequest)|Bir HTTP sunucusu ile gönderilen bir istek [SendRequestEx](#sendrequestex) üye işlevi.|
|[CHttpFile::GetFileURL](#getfileurl)|Belirtilen dosya için URL'yi alır.|
|[CHttpFile::GetObject](#getobject)|Fiili hedef nesneye bir HTTP sunucusuna bir istek alır.|
|[CHttpFile::GetVerb](#getverb)|Bir HTTP sunucusu bir istekte kullanılan fiili alır.|
|[CHttpFile::QueryInfo](#queryinfo)|HTTP sunucusundan yanıt veya istek üst bilgileri döndürür.|
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|Bir HTTP isteği ile ilişkili durum kodunu alır ve sağlanan yerleştirir `dwStatusCode` parametresi.|
|[CHttpFile::SendRequest](#sendrequest)|Bir isteği HTTP sunucusuna gönderir.|
|[CHttpFile::SendRequestEx](#sendrequestex)|Bir isteği kullanılarak bir HTTP sunucusuna gönderir [yazma](../../mfc/reference/cinternetfile-class.md#write) veya [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) yöntemlerinin `CInternetFile`.|

## <a name="remarks"></a>Açıklamalar

Internet oturumunuz bir HTTP sunucusundan veri okuyorsa, örneğini oluşturmalısınız `CHttpFile`.

Hakkında daha fazla bilgi edinmek için `CHttpFile` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[Cınternetfile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="addrequestheaders"></a>  CHttpFile::AddRequestHeaders

Eklemek için bu üye işlevi çağrısı veya daha fazla HTTP isteği için HTTP istek üstbilgilerinin işlemek.

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
Üst bilgi veya isteği eklemek için üst bilgileri içeren bir dize işaretçisi. Her üst bilgisi tarafından bir CR/LF çiftleri bitmelidir.

*CertOpenStore*<br/>
Yeni üst bilgileri semantiği değiştirir. Aşağıdakilerden biri olabilir:

- Sonraki başlıkta bulunan ilk başlık eklemek için bu bayrağı kullanarak aynı ada sahip üstbilgileri HTTP_ADDREQ_FLAG_COALESCE birleştirir. Örneğin, "kabul et: metin /\*" ardından "kabul et: ses /\*" sonuçları tek üstbilginin oluşturulması "kabul et: metin /\*, ses /\*". Bu birleşik veya ayrı başlıkları gönderilen istekleri tarafından alınan veriler göre cohesive bir düzeni emin olmak için çağıran uygulama kadar olur.

- HTTP_ADDREQ_FLAG_REPLACE bir kaldırma gerçekleştirir ve geçerli üstbilgi değiştirilecek ekleyin. Tam değeri yeni üst bilgiyi eklemek için kullanılan ve üst bilgi adı geçerli üstbilgiyi kaldırmak için kullanılır. Üst bilgi değeri boş ise ve üst bilgi bulundu, kaldırılır. Aksi halde üst bilgi değeri boş değiştirilir.

- Zaten yoksa, yalnızca HTTP_ADDREQ_FLAG_ADD_IF_NEW üstbilgisi ekler. Varsa, hata döndürülür.

- HTTP_ADDREQ_FLAG_ADD kullanılan değiştirin. Mevcut olmaması halinde üstbilgisi ekler.

*dwHeadersLen*<br/>
Karakter cinsinden uzunluğu, *pstrHeaders*. Bu,-1 L ardından ise *pstrHeaders* Sıfırla sonlandırılmış olarak kabul edilir ve uzunluğu hesaplanır.

*str*<br/>
Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) eklenecek üst bilgileri ve istek üst bilgisi içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`AddRequestHeaders` ek olarak, serbest biçimli üstbilgileri için HTTP istek işleyicisi ekler. Bu HTTP sunucusuna gönderilen tam istek üzerinde ayrıntılı denetime ihtiyaç duyan Gelişmiş istemciler tarafından kullanılması amaçlanmıştır.

> [!NOTE]
>  Uygulama birden çok üst bilgilerinde geçirebilirsiniz *pstrHeaders* veya *str* için bir `AddRequestHeaders` HTTP_ADDREQ_FLAG_ADD veya HTTP_ADDREQ_FLAG_ADD_IF_NEW kullanarak çağırın. Uygulamayı kaldırın veya değiştirin HTTP_ADDREQ_FLAG_REMOVE veya HTTP_ADDREQ_FLAG_REPLACE kullanarak üstbilgi çalışırsa, yalnızca bir üst bilgi sağlanabilir *lpszHeaders*.

##  <a name="chttpfile"></a>  CHttpFile::CHttpFile

Bu üye işlevi oluşturmak için çağrılan bir `CHttpFile` nesne.

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

*Hfıle*<br/>
Bir Internet dosyaya tanıtıcı.

*hSession*<br/>
Bir Internet oturumu için bir tanıtıcı.

*pstrObject*<br/>
İçeren bir dize işaretçisi `CHttpFile` nesne.

*pstrServer*<br/>
Sunucu adını içeren bir dize işaretçisi.

*pstrVerb*<br/>
İstek gönderilirken kullanılacak yöntemi içeren bir dize işaretçisi. POST, HEAD, olması veya alma kullanabilirsiniz.

*dwContext*<br/>
İçerik tanımlayıcısı `CHttpFile` nesne. Bkz: **açıklamalar** Bu parametre hakkında daha fazla bilgi için.

*pConnection*<br/>
Bir işaretçi bir [CHttpConnection](../../mfc/reference/chttpconnection-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Hiçbir zaman oluşturmak bir `CHttpFile` doğrudan nesne; bunun yerine çağrı [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) yerine.

İçin varsayılan değer `dwContext` MFC'ye tarafından gönderilen `CHttpFile` nesnesinden [Cınternetsession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CHttpFile` nesne. Çağırdığınızda `CInternetSession::OpenURL` veya `CHttpConnection` oluşturmak için bir `CHttpFile` nesne bağlamı tanımlayıcısını bir değere ayarlamak için varsayılan kılabilir. İçerik tanımlayıcısı döndürülür [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) durumu ile belirtilen nesneye sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

##  <a name="endrequest"></a>  CHttpFile::EndRequest

Bir HTTP sunucusu ile gönderilen bir istek sonlandırmak için bu üye işlevi çağrısı [SendRequestEx](#sendrequestex) üye işlevi.

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
İşlemi tanımlayan bayraklar. Uygun bayrakların listesi için bkz. [HttpEndRequest](/windows/desktop/api/wininet/nf-wininet-httpendrequesta) Windows SDK.

*lpBuffIn*<br/>
Başlatılan bir işaretçiye [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-_internet_buffersa) işlemi için kullanılan giriş arabelleği açıklar.

*dwContext*<br/>
İçerik tanımlayıcısı `CHttpFile` işlemi. Açıklamalar Bu parametre hakkında daha fazla bilgi için bkz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Oluşturulan inceleyerek çağrı başarısız olursa hatanın nedenini belirlemek [Cınternetexception](../../mfc/reference/cinternetexception-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

İçin varsayılan değer *dwContext* MFC'ye tarafından gönderilen `CHttpFile` nesnesinden [Cınternetsession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CHttpFile` nesne. Çağırdığınızda [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection](../../mfc/reference/chttpconnection-class.md) oluşturmak için bir `CHttpFile` nesne bağlamı tanımlayıcısını bir değere ayarlamak için varsayılan kılabilir. İçerik tanımlayıcısı döndürülür [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) durumu ile belirtilen nesneye sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

##  <a name="getfileurl"></a>  CHttpFile::GetFileURL

URL olarak HTTP dosyasının adını almak için bu üye işlevini çağırın.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) bu dosyayla ilişkili kaynak başvuran bir URL içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanın [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="getobject"></a>  CHttpFile::GetObject

Bununla ilişkili nesnenin adını almak için bu üye işlevi çağrısı `CHttpFile`.

```
CString GetObject() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesinin adını içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanın [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="getverb"></a>  CHttpFile::GetVerb

HTTP fiili (veya yöntem) ile ilişkili almak için bu üye işlevi çağrısı `CHttpFile`.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) HTTP fiili (veya yöntem) adını içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanın [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="queryinfo"></a>  CHttpFile::QueryInfo

Yanıt döndürmesine veya bir HTTP isteğinden istek üst bilgileri, bu üye işlevini çağırın.

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
Öznitelik sorgu ve istenen bilgi türünü belirten aşağıdaki bayrakları birleşimi:

- HTTP_QUERY_CUSTOM üst bilgi adı bulur ve bu değeri döndürür *lpvBuffer* çıktıyı. Üst bilgi bulunamazsa HTTP_QUERY_CUSTOM bir onaylama işlemi oluşturur.

- Uygulama yanıt üstbilgilerini genellikle HTTP_QUERY_FLAG_REQUEST_HEADERS sorgular, ancak bir uygulama da istek üst bilgilerini bu bayrağı kullanarak sorgulayabilirsiniz.

- HTTP_QUERY_FLAG_SYSTEMTIME değeri olan "En son değiştiren-zamanı" gibi bir tarih/saat dizesinin bu üst bilgiler için bu bayrağı döndürür üst bilgi değeri olarak standart bir Win32 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) uygulamaya gerektirmeyen yapısı ayrıştırılması denenecek veriler. Bu bayrağı kullanmanız durumunda kullanmak isteyebilirsiniz `SYSTEMTIME` işlevi geçersiz kılar.

- HTTP_QUERY_FLAG_NUMBER durum kodu gibi bir sayı olan değerdir, bu üst bilgiler için bu bayrağı veri 32 bit bir sayı döndürür.

Bkz: **açıklamalar** bölümünde bir liste için olası değerler.

*lpvBuffer*<br/>
Bilgileri alan arabellek için işaretçi.

*lpdwBufferLength*<br/>
Girişte veri arabelleği karakter veya bayt cinsinden uzunluğunu içeren bir değeri bu işaret eder. Bkz: **açıklamalar** Bu parametre hakkında daha fazla ayrıntı için bölüm.

*lpdwIndex*<br/>
Sıfır tabanlı üstbilgi dizini için bir işaretçi. NULL olabilir. Aynı ada sahip birden çok üst bilgi numaralandırmak için bu bayrağı kullanın. Giriş üzerinde *lpdwIndex* döndürmek için belirtilen üstbilgi dizinini gösterir. Çıktıyı *lpdwIndex* sonraki üstbilgi dizinini gösterir. Sonraki dizin bulunamazsa ERROR_HTTP_HEADER_NOT_FOUND döndürülür.

*str*<br/>
Bir başvuru [CString](../../atl-mfc-shared/reference/cstringt-class.md) döndürülen bilgileri alan nesne.

*dwIndex*<br/>
Bir dizin değeri. Bkz: *lpdwIndex*.

*pSysTime*<br/>
Bir Win32 işaretçisi [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanın [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

Aşağıdaki türde verileri alabilirsiniz `QueryInfo`:

- dize (varsayılan)

- `SYSTEMTIME` (için "veri:" "Expires:" vb., üst bilgiler)

- DWORD (için STATUS_CODE CONTENT_LENGTH, vs.)

Bir dizeyi arabelleğe yazılır ve üye işlevi başarılı, `lpdwBufferLength` uzunluğu eksi sondaki boş karakter için 1 karakter dizesi içerir.

Olası *dwInfoLevel* değerler şunlardır:

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

##  <a name="queryinfostatuscode"></a>  CHttpFile::QueryInfoStatusCode

Bir HTTP isteği ile ilişkili durum kodunu almak için bu üye işlevini çağırın ve sağlanan yerleştirin *dwStatusCode* parametresi.

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>Parametreler

*dwStatusCode*<br/>
Bir durum kodu bir başvuru. Durum kodları, başarı veya başarısızlık istenen olay gösterir. Bkz: **açıklamalar** durum kodu tanımları seçimi için.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Yalnızca başarılı çağrısı yapıldıktan sonra bu üye işlevi kullanın [SendRequest](#sendrequest) veya bir `CHttpFile` başarıyla tarafından oluşturulan nesne [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

HTTP durum kodları başarılı veya başarısız istek belirten gruplara ayrılır. Aşağıdaki tabloda ana hatlarıyla durumu kod gruplarını ve en yaygın HTTP durum kodları.

|Grup|Açıklama|
|-----------|-------------|
|200-299|Başarılı|
|300-399|Bilgiler|
|400-499|İstek hatası|
|500-599|Sunucu hatası|

Ortak HTTP durum kodları:

|Durum kodu|Açıklama|
|-----------------|-------------|
|200|İletim bulunan URL izler|
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

*pstrHeaders*<br/>
Üst bilgileri gönderme adını içeren bir dize işaretçisi.

*dwHeadersLen*<br/>
Tarafından tanımlanan Üstbilgi uzunluğu *pstrHeaders*.

*lpOptional*<br/>
İstek üstbilgilerini hemen sonra göndermek için isteğe bağlı tüm veriler. Bu, genellikle POST ve PUT işlemleri için kullanılır. İsteğe bağlı veri göndermek için yoksa bu boş olabilir.

*dwOptionalLen*<br/>
Uzunluğunu *lpOptional*.

*strHeaders*<br/>
Gönderilen istek için üstbilgileri adını içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Oluşturulan inceleyerek çağrı başarısız olursa hatanın nedenini belirlemek [Cınternetexception](../../mfc/reference/cinternetexception-class.md) nesne.

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

*dwTotalLen*<br/>
İstekte gönderilecek bayt sayısı.

*CertOpenStore*<br/>
İşlemi tanımlayan bayraklar. Uygun bayrakları bir listesi için bkz. [HttpSendRequestEx](/windows/desktop/api/wininet/nf-wininet-httpsendrequestexa) Windows SDK.

*dwContext*<br/>
İçerik tanımlayıcısı `CHttpFile` işlemi. Açıklamalar Bu parametre hakkında daha fazla bilgi için bkz.

*lpBuffIn*<br/>
Başlatılan bir işaretçiye [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-_internet_buffersa) işlemi için kullanılan giriş arabelleği açıklar.

*lpBuffOut*<br/>
İşlem için kullanılan çıkış arabelleği açıklayan bir başlatılmış INTERNET_BUFFERS işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı. Oluşturulan inceleyerek çağrı başarısız olursa hatanın nedenini belirlemek [Cınternetexception](../../mfc/reference/cinternetexception-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı kullanarak veri göndermek bu işlevi sağlayan [yazma](../../mfc/reference/cinternetfile-class.md#write) ve [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) yöntemlerinin `CInternetFile`. Bu işlevin ya da geçersiz kılma çağırmadan önce gönderilecek veri uzunluğu bilmeniz gerekir. İlk geçersiz kılma göndermek istediğiniz verilerin belirtmenizi sağlar. İkinci geçersiz kılma arabellek çok ayrıntılı olarak tanımlamak için kullanılabilecek INTERNET_BUFFERS yapılarına işaretçileri kabul eder.

İçeriği dosyaya yazıldıktan sonra çağırma [EndRequest](#endrequest) işlemi sonlandırmak için.

İçin varsayılan değer *dwContext* MFC'ye tarafından gönderilen `CHttpFile` nesnesinden [Cınternetsession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CHttpFile` nesne. Çağırdığınızda [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection](../../mfc/reference/chttpconnection-class.md) oluşturmak için bir `CHttpFile` nesne bağlamı tanımlayıcısını bir değere ayarlamak için varsayılan kılabilir. İçerik tanımlayıcısı döndürülür [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) durumu ile belirtilen nesneye sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

### <a name="example"></a>Örnek

Bu kod parçasını MFCISAPI adlı bir DLL için bir dize içeriği gönderir. DLL LOCALHOST sunucusunda. Bu örnekte yalnızca bir çağrı sırasında `WriteString`, bloklarında veri göndermek için birden çok çağrı kullanarak kabul edilebilir.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)
