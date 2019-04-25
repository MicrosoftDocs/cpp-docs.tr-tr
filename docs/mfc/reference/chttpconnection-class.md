---
title: CHttpConnection sınıfı
ms.date: 03/27/2019
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
ms.openlocfilehash: 1941af1e16a897235dd90db509d6ed29c2d9a875
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237577"
---
# <a name="chttpconnection-class"></a>CHttpConnection sınıfı

HTTP sunucusuyla olan bağlantınızı yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHttpConnection::CHttpConnection](#chttpconnection)|Oluşturur bir `CHttpConnection` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHttpConnection::OpenRequest](#openrequest)|Bir HTTP isteği açar.|

## <a name="remarks"></a>Açıklamalar

HTTP MFC WinINet sınıfları tarafından uygulanan üç Internet sunucusu protokolden biridir.

Sınıf `CHttpConnection` bir oluşturucu ve bir üye işlevi içeren [OpenRequest](#openrequest), bir HTTP protokolü ile sunucu bağlantıları yönetir.

Bir HTTP sunucusu ile iletişim kurmak için öncelikle bir örneğini oluşturmanız gerekir [Cınternetsession](../../mfc/reference/cinternetsession-class.md)ve ardından bir [CHttpConnection](#chttpconnection) nesne. Asla oluşturma bir `CHttpConnection` doğrudan nesne; bunun yerine, çağırarak [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), oluşturan `CHttpConnection` nesnesi ve bir işaretçi döndürür.

Hakkında daha fazla bilgi edinmek için `CHttpConnection` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md). Diğer iki kullanarak sunuculara bağlanma hakkında daha fazla bilgi desteklenen Internet protokolleri, gopher ve FTP için bkz: sınıfları [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="chttpconnection"></a>  CHttpConnection::CHttpConnection

Bu üye işlevi oluşturmak için çağrılan bir `CHttpConnection` nesne.

```
CHttpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pSession*<br/>
Bir işaretçi bir [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne.

*hConnected*<br/>
Internet bağlantısı için bir tanıtıcı.

*pstrServer*<br/>
Sunucu adını içeren bir dize işaretçisi.

*dwContext*<br/>
İçerik tanımlayıcısı `CInternetConnection` nesne. Hakkında daha fazla bilgi için *dwContext*, bkz: **açıklamalar** bölümü.

*nbağlantı noktası*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan numara.

*pstrUserName*<br/>
Oturum açmak için kullanıcı adını belirten bir null ile sonlandırılmış dize işaretçisi. NULL ise, anonim bir varsayılandır.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten bir null ile sonlandırılmış dizeye bir işaretçi. Her iki *pstrPassword* ve *pstrUserName* NULL, varsayılan anonim kullanıcı e-posta adını paroladır. Varsa *pstrPassword* NULL veya boş bir dize ancak *pstrUserName* NULL değil boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklar *pstrUserName* ve *pstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya ""|NULL veya ""|"anonim"|Kullanıcının e-posta adı|
|BOŞ olmayan bir dize|NULL veya ""|*pstrUserName*|" "|
|NULL |BOŞ olmayan bir dize|HATA|HATA|
|BOŞ olmayan bir dize|BOŞ olmayan bir dize|*pstrUserName*|*pstrPassword*|

*CertOpenStore*<br/>
Herhangi bir birleşimini `INTERNET_FLAG_*` bayrakları. Bölümündeki tabloya bakın **açıklamalar** bölümünü [CHttpConnection::OpenRequest](#openrequest) açıklamasını *CertOpenStore* değerleri.

### <a name="remarks"></a>Açıklamalar

Asla oluşturma bir `CHttpConnection` doğrudan. Bunun yerine, çağırarak bir nesne oluşturma [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).

##  <a name="openrequest"></a>  CHttpConnection::OpenRequest

Bir HTTP bağlantısı açmak için bu üye işlevini çağırın.

```
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

CHttpFile* OpenRequest(
    int nVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```

### <a name="parameters"></a>Parametreler

*pstrVerb*<br/>
İstekte kullanmak için fiili içeren bir dize işaretçisi. NULL ise, "Al" kullanılır.

*pstrObjectName*<br/>
Belirtilen fiili hedef nesneye içeren bir dize işaretçisi. Bu genellikle bir dosya adı, bir çalıştırılabilir modüle veya bir arama tanımlayıcısı dizedir.

*pstrReferer*<br/>
' % S'adresi (URL) belge belirten bir dize işaretçisi istek URL'SİNDE (*pstrObjectName*) alınamadı. NULL ise, hiçbir HTTP üst bilgisi belirtildi.

*dwContext*<br/>
İçerik tanımlayıcısı `OpenRequest` işlemi. Hakkında daha fazla bilgi için *dwContext*, Açıklamalar bölümüne bakın.

*ppstrAcceptTypes*<br/>
İstemci tarafından kabul edilen içerik türleri gösteren dizelerin LPCTSTR işaretçileri null ile sonlandırılmış bir dizi için bir işaretçi. Varsa *ppstrAcceptTypes* NULL ise istemci yalnızca tür belge kabul ettiğinden sunucuları yorumlama "metin / *" (diğer bir deyişle, yalnızca metin belgeleri ve resimleri veya diğer ikili dosyalar). İçerik türü, HTTP POST ve PUT gibi bilgileri ekli sorgular için verilerin türünü tanımlar CGI değişken CONTENT_TYPE eşdeğerdir.

*pstrVersion*<br/>
HTTP sürümünü tanımlayan bir dize işaretçisi. NULL ise, "HTTP/1.0" kullanılır.

*CertOpenStore*<br/>
Herhangi bir birleşimini INTERNET_ FLAG_ * bayrakları. Olası bir açıklaması için Açıklamalar bölümüne bakın *CertOpenStore* değerleri.

*nVerb*<br/>
HTTP isteği türüyle ilişkili bir sayı. Aşağıdakilerden biri olabilir:

|HTTP istek türü|*nVerb* değeri|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1.|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [CHttpFile](../../mfc/reference/chttpfile-class.md) istenen nesne.

### <a name="remarks"></a>Açıklamalar

*CertOpenStore* aşağıdakilerden biri olabilir:

|Internet bayrağı|Açıklama|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|İstenen dosya, nesne veya dizin listeleme, indirme, kaynak sunucu, önbellekten zorlar.|
|INTERNET_FLAG_DONT_CACHE|Döndürülen varlığı için önbelleği eklemez.|
|INTERNET_FLAG_MAKE_PERSISTENT|Döndürülen varlığı kalıcı bir varlık olarak önbelleğe ekler. Bu, standart önbellek temizleme, tutarlılık denetimi veya çöp toplama bu öğeyi önbellekten kaldırılamıyor anlamına gelir.|
|INTERNET_FLAG_SECURE|Güvenli işlem semantiği kullanır. SSL/PCT kullanmaya çevirir ve yalnızca HTTP isteklerini anlamlı|
|INTERNET_FLAG_NO_AUTO_REDIRECT|Yalnızca HTTP ile kullanılan, yeniden yönlendirmelerini otomatik olarak işleneceğini olmamalıdır belirtir [CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|

Geçersiz kılma `dwContext` varsayılan bağlamı tanımlayıcısını bir değere ayarlamak için. Bu belirli işlemle ilişkili bağlam tanımlayıcıdır `CHttpConnection` tarafından oluşturulan nesne kendi [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile belirtilen işlem durumu sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

Bu işlev ile özel durumlar.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
