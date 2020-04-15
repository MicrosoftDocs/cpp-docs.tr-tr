---
title: Chttpfile Sınıfı
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
ms.openlocfilehash: cba3ba7d86577703de2bf5709d66bbd5e0298863
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368388"
---
# <a name="chttpfile-class"></a>Chttpfile Sınıfı

BIR HTTP sunucusunda dosya istemek ve okumak için işlevsellik sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHttpFile::CHttpFile](#chttpfile)|Bir `CHttpFile` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|BIR HTTP sunucusuna gönderilen isteğe üstbilgi ekler.|
|[CHttpFile::EndRequest](#endrequest)|[SendRequestEx](#sendrequestex) üye işleviile bir HTTP sunucusuna gönderilen bir isteği sona erdirer.|
|[CHttpFile::GetFileURL](#getfileurl)|Belirtilen dosyanın URL'sini alır.|
|[CHttpFile::GetObject](#getobject)|Bir istekteki fiilin hedef nesnesini bir HTTP sunucusuna alır.|
|[CHttpFile::GetVerb](#getverb)|Bir istekte kullanılan fiili bir HTTP sunucusuna alır.|
|[CHttpFile::QueryInfo](#queryinfo)|Yanıt veya istek üstbilgilerini HTTP sunucusundan döndürür.|
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|BIR HTTP isteğiyle ilişkili durum kodunu alır ve `dwStatusCode` sağlanan parametreye yerleştirir.|
|[CHttpFile::SendRequest](#sendrequest)|Bir HTTP sunucusuna istek gönderir.|
|[CHttpFile::SendRequestEx](#sendrequestex)|[Yazma](../../mfc/reference/cinternetfile-class.md#write) veya [Yazma String](../../mfc/reference/cinternetfile-class.md#writestring) yöntemlerini kullanarak bir `CInternetFile`HTTP sunucusuna istek gönderir.|

## <a name="remarks"></a>Açıklamalar

Internet oturumunuz bir HTTP sunucusundan gelen verileri okuyorsa, bir .. `CHttpFile`

Diğer MFC `CHttpFile` Internet sınıfları ile nasıl çalıştığı hakkında daha fazla bilgi edinmek için [WinInet ile internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

[Cstdiofile](../../mfc/reference/cstdiofile-class.md)

[Cınternetfile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="chttpfileaddrequestheaders"></a><a name="addrequestheaders"></a>CHttpFile::AddRequestHeaders

HTTP istek tanıtıcısına bir veya daha fazla HTTP istek üstbilgisini eklemek için bu üye işlevini arayın.

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
İsteğe eklemek için üstbilgi veya üstbilgi içeren bir dize için bir işaretçi. Her üstbilgi bir CR/LF çifti tarafından sonlandırılmalıdır.

*Dwflags*<br/>
Yeni üstbilginin anlambilimini değiştirir. Aşağıdakilerden biri olabilir:

- HTTP_ADDREQ_FLAG_COALESCE Sonraki üstbilgide bulunan ilk üstbilgieklemek için bayrağı kullanarak aynı adı taşıyan üstbilgibirleştirir. Örneğin, "Kabul et:\*metin/ " ardından\*"Accept: audio/ " tek başlık "Kabul\*et:\*metin/ , ses/ " oluşumuyla sonuçlanır. Birleştirilmiş veya ayrı üstbilgilerle gönderilen istekler tarafından alınan verilerle ilgili tutarlı bir şema sağlamak arama uygulamasına kalmıştır.

- HTTP_ADDREQ_FLAG_REPLACE Geçerli üstbilginin yerine kaldırma ve ekleme yapar. Üstbilgi adı geçerli üstbilgi kaldırmak için kullanılır ve tam değer yeni üstbilgi eklemek için kullanılır. Üstbilgi değeri boşsa ve üstbilgi bulunursa, kaldırılır. Boş değilse, üstbilgi değeri değiştirilir.

- HTTP_ADDREQ_FLAG_ADD_IF_NEW Yalnızca üstbilgi zaten yoksa ekler. Varsa, bir hata döndürülür.

- HTTP_ADDREQ_FLAG_ADD REPLACE ile kullanılır. Yoksa üstbilgi ekler.

*dwHeadersLen*<br/>
Uzunluk, karakterler, *pstrHeaders*. Bu -1L ise, *pstrHeaders* sıfır sonlandırılmış olarak kabul edilir ve uzunluğu hesaplanır.

*Str*<br/>
Eklenecek istek üstbilgisini veya üstbilgisini içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`AddRequestHeaders`http istek koluna ek, serbest biçimli üstbilgi ekler. Bu, HTTP sunucusuna gönderilen tam istek üzerinde ayrıntılı denetime ihtiyaç duyan gelişmiş istemciler tarafından kullanılmak üzere tasarlanmıştır.

> [!NOTE]
> Uygulama, HTTP_ADDREQ_FLAG_ADD veya HTTP_ADDREQ_FLAG_ADD_IF_NEW kullanarak bir `AddRequestHeaders` çağrı için *pstrHeaders* veya *str* birden fazla üstbilgi geçebilir. Uygulama, HTTP_ADDREQ_FLAG_REMOVE veya HTTP_ADDREQ_FLAG_REPLACE kullanarak bir üstbilgikaldırmaya veya değiştirmeye çalışırsa, *lpszHeaders'da*yalnızca bir üstbilgi sağlanabilir.

## <a name="chttpfilechttpfile"></a><a name="chttpfile"></a>CHttpFile::CHttpFile

Bu üye işlev bir `CHttpFile` nesne oluşturmak için çağrılır.

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
Bir Internet dosyasının tutamacı.

*hSession*<br/>
Internet oturumuiçin bir tanıtıcı.

*pstrObject*<br/>
Nesneyi içeren bir `CHttpFile` dize için bir işaretçi.

*pstrServer*<br/>
Sunucunun adını içeren bir dize için bir işaretçi.

*pstrVerb*<br/>
İstek gönderirken kullanılacak yöntemi içeren bir dize işaretçisi. POST, HEAD veya GET olabilir.

*dwBağlam*<br/>
Nesneiçin bağlam tanımlayıcısı. `CHttpFile` Bu parametre hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

*pBağlantı*<br/>
[CHttpConnection](../../mfc/reference/chttpconnection-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir `CHttpFile` nesneyi asla doğrudan oluşturmazsınız; bunun yerine [CInternetSession'ı arayın::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) yerine.

Varsayılan değer, `dwContext` MFC tarafından `CHttpFile` `CHttpFile` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesneye gönderilir. Bir `CHttpFile` nesneyi `CHttpConnection` aradiğinizde `CInternetSession::OpenURL` veya oluşturmak için, bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan nesne üzerinde durum sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

## <a name="chttpfileendrequest"></a><a name="endrequest"></a>CHttpFile::EndRequest

[SendRequestEx](#sendrequestex) üye işlevine sahip bir HTTP sunucusuna gönderilen isteği sona erdirmek için bu üye işlevini arayın.

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
İşlemi açıklayan bayraklar. Uygun bayrakların listesi için Windows SDK'daki [HttpEndRequest](/windows/win32/api/wininet/nf-wininet-httpendrequestw) bölümüne bakın.

*lpBuffIn*<br/>
İşlem için kullanılan giriş arabelleği açıklayan başharfli bir [INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw) işaretçi.

*dwBağlam*<br/>
İşlem için bağlam tanımlayıcısı. `CHttpFile` Bu parametre hakkında daha fazla bilgi için Açıklamalar'a bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, atılan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini belirleyin.

### <a name="remarks"></a>Açıklamalar

*dwContext* için varsayılan değer, MFC `CHttpFile` tarafından `CHttpFile` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesneye gönderilir. [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection'ı](../../mfc/reference/chttpconnection-class.md) bir `CHttpFile` nesne oluşturmak için aradiğinizde, bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan nesne üzerinde durum sağlamak için. Makale [internet ilk adımlar bakınız: Bağlam](../../mfc/wininet-basics.md) tanımlayıcısı hakkında daha fazla bilgi için WinInet.

## <a name="chttpfilegetfileurl"></a><a name="getfileurl"></a>CHttpFile::GetFileURL

HTTP dosyasının adını URL olarak almak için bu üye işlevini arayın.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu dosyayla ilişkili kaynağa başvuran bir URL içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest'e](#sendrequest) yapılan `CHttpFile` başarılı bir çağrıdan sonra veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla oluşturulan bir nesnede kullanın.

## <a name="chttpfilegetobject"></a><a name="getobject"></a>CHttpFile::GetObject

Bununla `CHttpFile`ilişkili nesnenin adını almak için bu üye işlevi arayın.

```
CString GetObject() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin adını içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest'e](#sendrequest) yapılan `CHttpFile` başarılı bir çağrıdan sonra veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla oluşturulan bir nesnede kullanın.

## <a name="chttpfilegetverb"></a><a name="getverb"></a>CHttpFile::GetVerb

Bu `CHttpFile`ile ilişkili HTTP fiili (veya yöntemi) almak için bu üye işlevi arayın.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Dönüş Değeri

HTTP fiilinin (veya yöntemin) adını içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest'e](#sendrequest) yapılan `CHttpFile` başarılı bir çağrıdan sonra veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla oluşturulan bir nesnede kullanın.

## <a name="chttpfilequeryinfo"></a><a name="queryinfo"></a>CHttpFile::QueryInfo

Yanıtı döndürmek veya bir HTTP isteğinden üstbilgi istemek için bu üye işlevini arayın.

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
Sorguya öznitelik ve istenen bilgi türünü belirten aşağıdaki bayrakların birleşimi:

- HTTP_QUERY_CUSTOM üstbilgi adını bulur ve bu değeri *çıktıda lpvBuffer'da* döndürür. HTTP_QUERY_CUSTOM üstbilgi bulunamazsa bir iddia atar.

- HTTP_QUERY_FLAG_REQUEST_HEADERS Genellikle, uygulama yanıt üstbilgisini sorgular, ancak bir uygulama bu bayrağı kullanarak istek üstbilgilerini de sorgulayabilir.

- HTTP_QUERY_FLAG_SYSTEMTIME Değeri "Son Değiştirilen Zaman" gibi bir tarih/saat dizesi olan üstbilgiler için bu bayrak, altbilgi değerini, uygulamayı verileri ayrıştırmak için gerektirmeyen standart bir Win32 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısı olarak döndürür. Bu bayrağı kullanırsanız, işlevin `SYSTEMTIME` geçersiz kılınmasını kullanmak isteyebilirsiniz.

- HTTP_QUERY_FLAG_NUMBER Değeri durum kodu gibi bir sayı olan üstbilgiler için bu bayrak verileri 32 bit lik bir sayı olarak döndürür.

Olası değerlerin listesi için **Açıklamalar** bölümüne bakın.

*lpvBuffer*<br/>
Bilgileri alan arabellek için bir işaretçi.

*lpdwTamponUzunluk*<br/>
Girişte, bu, karakter veya bayt sayısı, veri arabelleği uzunluğunu içeren bir değere işaret eder. Bu parametre hakkında daha ayrıntılı bilgi için **Açıklamalar** bölümüne bakın.

*lpdwIndex*<br/>
Sıfır tabanlı üstbilgi dizinine işaretçi. NULL olabilir. Aynı ada sahip birden çok üstbilgi sıralamak için bu bayrağı kullanın. Girişte, *lpdwIndex* döndürmek için belirtilen üstbilginin dizini gösterir. *Çıktıda, lpdwIndex* bir sonraki üstbilginin dizinini gösterir. Sonraki dizin bulunamazsa, ERROR_HTTP_HEADER_NOT_FOUND döndürülür.

*Str*<br/>
Döndürülen bilgileri alan [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine yapılan başvuru.

*dwIndex*<br/>
Dizin değeri. Bkz. *lpdwIndex*.

*pSysTime*<br/>
Win32 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest'e](#sendrequest) yapılan `CHttpFile` başarılı bir çağrıdan sonra veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla oluşturulan bir nesnede kullanın.

Aşağıdaki veri türlerini `QueryInfo`alabilirsiniz:

- dizeleri (varsayılan)

- `SYSTEMTIME`("Veri:" "Sona erer:" vb, üstbilgiler için)

- DWORD (STATUS_CODE, CONTENT_LENGTH, vb. için)

Arabelleğe bir dize yazıldığında ve üye işlev `lpdwBufferLength` başarılı olduğunda, sonlandırıcı NULL karakteri için eksi 1 karakterdeki dize uzunluğunu içerir.

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

## <a name="chttpfilequeryinfostatuscode"></a><a name="queryinfostatuscode"></a>CHttpFile::QueryInfoStatusCode

Http isteğiyle ilişkili durum kodunu almak ve verilen *dwStatusCode* parametresine yerleştirmek için bu üye işlevini arayın.

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>Parametreler

*dwStatusCode*<br/>
Durum koduna başvuru. Durum kodları, istenen olayın başarısını veya başarısızlığını gösterir. Durum kodu açıklamalarının seçimi için **Açıklamalar'a** bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yalnızca [SendRequest'e](#sendrequest) yapılan `CHttpFile` başarılı bir çağrıdan sonra veya [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)tarafından başarıyla oluşturulan bir nesnede kullanın.

HTTP durum kodları, isteğin başarısını veya başarısızlığını belirten gruplara ayrılır. Aşağıdaki tablolar durum kodu gruplarını ve en yaygın HTTP durum kodlarını ana hatlarını ve

|Grup|Anlamı|
|-----------|-------------|
|200-299|Başarılı|
|300-399|Bilgi|
|400-499|İstek hatası|
|500-599|Sunucu hatası|

Ortak HTTP Durum Kodları:

|Durum kodu|Anlamı|
|-----------------|-------------|
|200|URL bulunur, iletim aşağıdaki|
|400|Anlaşılmaz istek|
|404|İstenen URL bulunamadı|
|405|Sunucu istenen yöntemi desteklemiyor|
|500|Bilinmeyen sunucu hatası|
|503|Sunucu kapasitesine ulaşıldı|

## <a name="chttpfilesendrequest"></a><a name="sendrequest"></a>CHttpFile::SendRequest

Bir HTTP sunucusuna istek göndermek için bu üye işlevini arayın.

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
Gönderilen üstbilginin adını içeren bir dize işaretçisi.

*dwHeadersLen*<br/>
*PstrHeaders*tarafından tanımlanan başlıkların uzunluğu.

*lpİsteğe bağlı*<br/>
İstek üstbilgileri hemen sonra göndermek için herhangi bir isteğe bağlı veri. Bu genellikle POST ve PUT işlemleri için kullanılır. Gönderilecek isteğe bağlı veri yoksa bu NULL olabilir.

*dwOptionalLen*<br/>
*lpOptional*uzunluğu .

*strHeaders*<br/>
Gönderilen istek için üstbilginin adını içeren bir dize.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, atılan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini belirleyin.

## <a name="chttpfilesendrequestex"></a><a name="sendrequestex"></a>CHttpFile::SendRequestEx

Bir HTTP sunucusuna istek göndermek için bu üye işlevini arayın.

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

*Dwflags*<br/>
İşlemi açıklayan bayraklar. Uygun bayrakların listesi için Windows SDK'daki [HttpSendRequestEx](/windows/win32/api/wininet/nf-wininet-httpsendrequestexw) bölümüne bakın.

*dwBağlam*<br/>
İşlem için bağlam tanımlayıcısı. `CHttpFile` Bu parametre hakkında daha fazla bilgi için Açıklamalar'a bakın.

*lpBuffIn*<br/>
İşlem için kullanılan giriş arabelleği açıklayan başharfli bir [INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw) işaretçi.

*lpBuffOut*<br/>
İşlem için kullanılan çıktı arabelleği açıklayan başharfe INTERNET_BUFFERS işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır değil. Arama başarısız olursa, atılan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini belirleyin.

### <a name="remarks"></a>Açıklamalar

Bu işlev, uygulamanızın [Yazma](../../mfc/reference/cinternetfile-class.md#write) ve [Yazma String](../../mfc/reference/cinternetfile-class.md#writestring) `CInternetFile`yöntemlerini kullanarak veri göndermesini sağlar. Bu işlevin geçersiz kılınmasını aramadan önce gönderilecek verilerin uzunluğunu bilmeniz gerekir. İlk geçersiz kılma, göndermek istediğiniz verilerin uzunluğunu belirtmenize olanak tanır. İkinci geçersiz kılma, arabelleği ayrıntılı olarak açıklamak için kullanılabilecek INTERNET_BUFFERS yapıları işaretçileri kabul eder.

İçerik dosyaya yazıldıktan sonra, işlemi sona erdirmek için [EndRequest'i](#endrequest) arayın.

*dwContext* için varsayılan değer, MFC `CHttpFile` tarafından `CHttpFile` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesneye gönderilir. [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) veya [CHttpConnection'ı](../../mfc/reference/chttpconnection-class.md) bir `CHttpFile` nesne oluşturmak için aradiğinizde, bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan nesne üzerinde durum sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

### <a name="example"></a>Örnek

Bu kod parçası, bir dize içeriğini MFCISAPI adlı bir DLL'ye gönderir. LOCALHOST sunucusunda DLL. Bu örnek, blokhalinde `WriteString`veri göndermek için birden çok çağrı kullanarak yalnızca bir arama kullanırken kabul edilebilir.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[ChttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)
