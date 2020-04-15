---
title: CGopherConnection Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
ms.openlocfilehash: eade1a82b674d5ad2e91146559139445ef017180
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373706"
---
# <a name="cgopherconnection-class"></a>CGopherConnection Sınıfı

Bir gopher Internet sunucusuna olan bağlantınızı yönetir.

> [!NOTE]
> Sınıflar `CGopherConnection`, `CGopherFile` `CGopherFileFind`, `CGopherLocator` , , windows xp platformunda çalışmıyor çünkü onların üyeleri küçümsenmiş, ancak önceki platformlarda çalışmaya devam edecektir.

## <a name="syntax"></a>Sözdizimi

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Bir `CGopherConnection` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CGopherConnection::CreateLocator](#createlocator)|Bir gopher sunucusunda dosyaları bulmak için bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi oluşturur.|
|[CGopherConnection::GetAttribute](#getattribute)|Gopher nesnesi hakkındaki öznitelik bilgilerini alır.|
|[CGopherConnection::OpenFile](#openfile)|Bir gopher dosyası açar.|

## <a name="remarks"></a>Açıklamalar

Gopher hizmeti, MFC WinInet sınıfları tarafından tanınan üç Internet hizmetinden biridir.

Sınıf `CGopherConnection` bir oluşturucu ve gopher hizmeti yönetmek üç ek üye işlevleri içerir: [OpenFile](#openfile), [CreateLocator](#createlocator), ve [GetAttribute](#getattribute).

Bir gopher Internet sunucusu ile iletişim kurmak için, önce [CInternetSession](../../mfc/reference/cinternetsession-class.md)bir örnek oluşturmanız gerekir , ve `CGopherConnection` sonra [CInternetSession çağrı::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), nesne oluşturur ve ona bir işaretçi döndürür. Hiçbir `CGopherConnection` nesneyi doğrudan oluşturmazsınız.

Diğer MFC `CGopherConnection` Internet sınıfları ile nasıl çalıştığı hakkında daha fazla bilgi edinmek için [WinInet ile internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın. Desteklenen diğer iki Internet hizmetlerini kullanma hakkında daha fazla bilgi için FTP ve HTTP [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md)sınıflarını görün.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cınternetconnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cgopherconnectioncgopherconnection"></a><a name="cgopherconnection"></a>CGopherConnection::CGopherConnection

Bu üye işlev bir `CGopherConnection` nesne oluşturmak için çağrılır.

```
CGopherConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CGopherConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parametreler

*pOturum*<br/>
İlgili [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinin işaretçisi.

*hBağlı*<br/>
Geçerli Internet oturumunun Windows tutamacı.

*pstrServer*<br/>
FTP sunucu adını içeren bir dize için bir işaretçi.

*dwBağlam*<br/>
İşlem için bağlam tanımlayıcısı. *dwContext,* CInternetSession tarafından döndürülen operasyonun durum bilgilerini [tanımlar::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; ancak, işlem için açıkça belirli bir bağlam kimliği atayabilirsiniz. Nesne ve yaptığı herhangi bir çalışma bu bağlam kimliği ile ilişkilendirilecektir.

*pstrUserName*<br/>
Oturum açmak için kullanıcının adını belirten null-sonlandırılan dize işaretçi. NULL ise, varsayılan adsızdır.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten, geçersiz sonlandırılmış bir dize için işaretçi. Hem *pstrPassword* hem de *pstrUserName* NULL ise, varsayılan anonim parola kullanıcının e-posta adıdır. *pstrPassword* NULL (veya boş bir dize) ancak *pstrUserName* NULL değilse, boş bir parola kullanılır. Aşağıdaki *tabloda pstrUserName* ve *pstrPassword*dört olası ayarları için davranış açıklanır:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya " "|NULL veya " "|"anonim"|Kullanıcının e-posta adı|
|Null Olmayan Dize|NULL veya " "|*pstrUserName*|" "|
|NULL Non-NULL Dize|HATA|HATA||
|Null Olmayan Dize|Null Olmayan Dize|*pstrUserName*|*pstrPassword*|

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

### <a name="remarks"></a>Açıklamalar

Asla doğrudan `CGopherConnection` bir şey yaratmazsın. Bunun yerine, [CInternetSession'ı arayın::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), bir `CGopherConnection` nesne oluşturur ve bir işaretçiyi ona döndürür.

## <a name="cgopherconnectioncreatelocator"></a><a name="createlocator"></a>CGopherConnection::CreateLocator

Bir gopher sunucusunda bir dosyayı bulmak veya tanımlamak için bir gopher bulucu oluşturmak için bu üye işlevi arayın.

```
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType);

static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parametreler

*pstrDisplayString*<br/>
Alınacak gopher belgesinin veya dizinin adını içeren bir dize işaretçisi. *pstrDisplayString* parametresi NULL ise, gopher sunucusu için varsayılan dizin döndürülür.

*pstrSelectorString*<br/>
Bir öğeyi almak için gopher sunucusuna gönderilecek seçici dizesine işaretçi. *pstrSelectorString* NULL olabilir.

*dwGopherType*<br/>
Bu, *pstrSelectorString'in* bir dizin veya belgeyle ifade edip etmediğini ve isteğin gopher veya gopher+ olup olmadığını belirtir. Windows SDK'da [GOPHER_FIND_DATA](/windows/win32/api/wininet/ns-wininet-gopher_find_dataw) yapının özniteliklerine bakın.

*pstrLocator*<br/>
Açılacak dosyayı tanımlayan bir dize işaretçisi. Genellikle, bu dize [CGopherFileFind bir çağrı döndürülür::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).

*pstrServerName*<br/>
Gopher sunucu adını içeren bir dize için bir işaretçi.

*nPort*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan numara.

### <a name="return-value"></a>Dönüş Değeri

Bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevin statik sürümü bir sunucu belirtmenizi gerektirirken, statik olmayan sürüm bağlantı nesnesinden sunucu adını kullanır.

Bir gopher sunucusundan bilgi almak için, bir uygulama nın öncelikle bir gopher bulucu alması gerekir. Uygulama daha sonra opak bir belirteç olarak yer değiştiricisi tedavi etmelidir (diğer bir zamanda, uygulama yer belirleyiciyi kullanabilir, ancak doğrudan işlemeyi veya karşılaştırmayı yapamaz). Normalde, uygulama CGopherFileFind aramaları için yer belirleyici [kullanır::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) üye işlevi belirli bir bilgi parçası almak için.

## <a name="cgopherconnectiongetattribute"></a><a name="getattribute"></a>CGopherConnection::GetAttribute

Gopher sunucusundan bir öğe hakkında belirli öznitelik bilgilerini almak için bu üye işlevi arayın.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>Parametreler

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesine bir gönderme.

*strRequestedAttributes*<br/>
İstenen özniteliklerin adlarını belirten bir boşluk sınırlandırMa dizesi.

*strResult*<br/>
Yer bulucu türünü alan bir [CString'e](../../atl-mfc-shared/reference/cstringt-class.md) başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

## <a name="cgopherconnectionopenfile"></a><a name="openfile"></a>CGopherConnection::OpenFile

Bir gopher sunucusunda bir dosya açmak için bu üye işlevi arayın.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesine bir gönderme.

*Dwflags*<br/>
INTERNET_FLAG_* bayrakların herhangi bir kombinasyonu. Bkz. [CInternetSession::INTERNET_FLAG_](../../mfc/reference/cinternetsession-class.md#openurl) \* bayrakları hakkında daha fazla bilgi için Açılan Url.

*pstrView*<br/>
Dosya görünümü dizesine işaretçi. Sunucuda dosyanın çeşitli görünümleri varsa, bu parametre hangi dosya görünümünün açılacağını belirtir. *pstrView* NULL ise, varsayılan dosya görünümü kullanılır.

*dwBağlam*<br/>
Açılan dosyanın bağlam kimliği. *dwContext*hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="return-value"></a>Dönüş Değeri

Açılacak [CGopherFile](../../mfc/reference/cgopherfile-class.md) nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için *dwContext* varsayılanını geçersiz kılın. Bağlam tanımlayıcısı, [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından `CGopherConnection` oluşturulan nesnenin bu özel çalışmasıyla ilişkilidir. Değer [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan işlem durumu sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpConnection Sınıfı](../../mfc/reference/cftpconnection-class.md)<br/>
[ChttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CGopherLocator Sınıf](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CInternetSession Sınıfı](../../mfc/reference/cinternetsession-class.md)
