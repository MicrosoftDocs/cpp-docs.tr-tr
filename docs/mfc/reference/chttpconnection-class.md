---
title: ChttpConnection Sınıfı
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
ms.openlocfilehash: af402b532b3aba28bdfefea5afa67331765db4c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351822"
---
# <a name="chttpconnection-class"></a>ChttpConnection Sınıfı

Bir HTTP sunucusuyla bağlantınızı yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[ChttpConnection::chttpconnection](#chttpconnection)|Bir `CHttpConnection` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHttpConnection::OpenRequest](#openrequest)|Bir HTTP isteği açar.|

## <a name="remarks"></a>Açıklamalar

HTTP, MFC WinInet sınıfları tarafından uygulanan üç Internet sunucusu protokolünden biridir.

Sınıf, `CHttpConnection` http protokolü olan bir sunucuya bağlantıları yöneten bir oluşturucu ve [openrequest](#openrequest)bir üye işlev içerir.

Bir HTTP sunucusuyla iletişim kurmak için önce [CInternetSession'ın](../../mfc/reference/cinternetsession-class.md)bir örneğini oluşturmanız ve ardından bir [CAnında Bağlantı](#chttpconnection) nesnesi oluşturmanız gerekir. Hiçbir `CHttpConnection` nesneyi doğrudan oluşturmazsınız; bunun yerine, [CInternetSession'ı arayın::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), nesneyi `CHttpConnection` oluşturur ve bir işaretçi döndürür.

Diğer MFC `CHttpConnection` Internet sınıfları ile nasıl çalıştığı hakkında daha fazla bilgi edinmek için [WinInet ile internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın. Diğer iki desteklenen Internet protokolleri, gopher ve FTP kullanarak sunuculara bağlanma hakkında daha fazla bilgi için, sınıflar [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cınternetconnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="chttpconnectionchttpconnection"></a><a name="chttpconnection"></a>ChttpConnection::chttpconnection

Bu üye işlev bir `CHttpConnection` nesne oluşturmak için çağrılır.

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

*pOturum*<br/>
[CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesine işaretçi.

*hBağlı*<br/>
Internet bağlantısıiçin bir tanıtıcı.

*pstrServer*<br/>
Sunucu adını içeren bir dize için bir işaretçi.

*dwBağlam*<br/>
Nesneiçin bağlam tanımlayıcısı. `CInternetConnection` *dwContext*hakkında daha fazla bilgi için **Açıklamalar** bölümüne bakın.

*nPort*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan numara.

*pstrUserName*<br/>
Oturum açacak kullanıcının adını belirten, geçersiz sonlandırılmış bir dize işaretçi. NULL ise, varsayılan adsızdır.

*pstrPassword*<br/>
Oturum açmada kullanılacak parolayı belirten, geçersiz sonlandırılmış bir dize için işaretçi. Hem *pstrPassword* hem de *pstrUserName* NULL ise, varsayılan anonim parola kullanıcının e-posta adıdır. *pstrPassword* NULL veya boş bir dize ise, ancak *pstrUserName* NULL değilse, boş bir parola kullanılır. Aşağıdaki *tabloda pstrUserName* ve *pstrPassword*dört olası ayarları için davranış açıklanır:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya " "|NULL veya " "|"anonim"|Kullanıcının e-posta adı|
|NULL Olmayan Dize|NULL veya " "|*pstrUserName*|" "|
|NULL |NULL Olmayan Dize|HATA|HATA|
|NULL Olmayan Dize|NULL Olmayan Dize|*pstrUserName*|*pstrPassword*|

*Dwflags*<br/>
Bayrakların `INTERNET_FLAG_*` herhangi bir kombinasyonu. [CHttpConnection'ın](#openrequest) **Açıklamalar** bölümündeki tabloya *bakın:DwFlags* değerlerinin açıklaması için OpenRequest.

### <a name="remarks"></a>Açıklamalar

Asla doğrudan `CHttpConnection` bir şey yaratmazsın. Bunun yerine, CInternetSession çağırarak bir nesne [oluşturmak::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).

## <a name="chttpconnectionopenrequest"></a><a name="openrequest"></a>CHttpConnection::OpenRequest

Bir HTTP bağlantısı açmak için bu üye işlevini arayın.

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
İstekte kullanılacak fiili içeren bir dize işaretçisi. NULL ise, "GET" kullanılır.

*pstrObjectName*<br/>
Belirtilen fiilin hedef nesnesini içeren bir dize işaretçisi. Bu dize genellikle bir dosya adı, yürütülebilir bir modül veya bir arama belirtimidir.

*pstrReferer*<br/>
İstekteki URL'nin *(pstrObjectName)* alındığı belgenin adresini (URL) belirten bir dize işaretçisi. NULL ise, hiçbir HTTP üstbilgi belirtilir.

*dwBağlam*<br/>
İşlem için bağlam tanımlayıcısı. `OpenRequest` *dwContext*hakkında daha fazla bilgi için Açıklamalar bölümüne bakın.

*ppstrAcceptTypes*<br/>
İstemci tarafından kabul edilen içerik türlerini gösteren dizeleri için LPCTSTR işaretçileri bir null-sonlandırılan dizi için bir işaretçi. *ppstrAcceptTypes* NULL ise, sunucular istemcinin yalnızca "text/*" türündeki belgeleri kabul ettiğini (diğer bir deyişle, resimler veya diğer ikili dosyalar değil, yalnızca metin belgeleri) kabul ettiğini yorumlar. İçerik türü, HTTP POST ve PUT gibi bilgileri iliştiren sorguların veri türünü tanımlayan CGI değişken CONTENT_TYPE eşdeğerdir.

*pstrVersion*<br/>
HTTP sürümünü tanımlayan bir dize için bir işaretçi. NULL ise "HTTP/1.0" kullanılır.

*Dwflags*<br/>
INTERNET_ FLAG_* bayraklarının herhangi bir kombinasyonu. Olası *dwFlags* değerlerinin açıklaması için Açıklamalar bölümüne bakın.

*nVerb*<br/>
HTTP istek türüyle ilişkili bir sayı. Aşağıdakilerden biri olabilir:

|HTTP istek türü|*nFiil* değeri|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>Dönüş Değeri

[CHttpFile](../../mfc/reference/chttpfile-class.md) nesnesi için bir işaretçi istenir.

### <a name="remarks"></a>Açıklamalar

*dwFlags* aşağıdakilerden biri olabilir:

|Internet bayrağı|Açıklama|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|İstenen dosyanın, nesnenin veya dizin listesinin önbellekten değil, kaynak sunucusundan karşıdan yüklenmesi zorlanır.|
|INTERNET_FLAG_DONT_CACHE|Döndürülen varlığı önbelleğe eklemez.|
|INTERNET_FLAG_MAKE_PERSISTENT|Döndürülen varlığı kalıcı bir varlık olarak önbelleğe ekler. Standart önbellek temizleme, tutarlılık denetimi veya çöp toplama nın bu öğeyi önbellekten kaldıramayacağı anlamına gelir.|
|INTERNET_FLAG_SECURE|Güvenli işlem semantiklerini kullanır. Bu SSL / PCT kullanarak çevirir ve sadece HTTP istekleri anlamlı|
|INTERNET_FLAG_NO_AUTO_REDIRECT|Yalnızca HTTP ile kullanıldığında, yönlendirmelerin CHttpFile'da otomatik olarak ele alınmaması gerektiğini [belirtir::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|

Bağlam tanımlayıcısını `dwContext` seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılın. Bağlam tanımlayıcısı, [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından `CHttpConnection` oluşturulan nesnenin bu özel çalışmasıyla ilişkilidir. Değer [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan işlem durumu sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

Bu işlevle özel durumlar atılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Chttpfile Sınıfı](../../mfc/reference/chttpfile-class.md)
