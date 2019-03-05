---
title: CGopherConnection sınıfı
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
ms.openlocfilehash: d960d566a63531af211592a7a8ae8f1cb35c5958
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300730"
---
# <a name="cgopherconnection-class"></a>CGopherConnection sınıfı

Gopher Internet sunucusuyla olan bağlantınızı yönetir.

> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri bırakılmıştır, Windows XP platformu üzerinde çalışmaz, ancak önceki platformları üzerinde çalışmaya devam eder.

## <a name="syntax"></a>Sözdizimi

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Oluşturur bir `CGopherConnection` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGopherConnection::CreateLocator](#createlocator)|Oluşturur bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) bir gopher sunucusunda dosyaları bulmak için nesne.|
|[CGopherConnection::GetAttribute](#getattribute)|Gopher nesnesine ilişkin öznitelik bilgileri alır.|
|[CGopherConnection::OpenFile](#openfile)|Bir gopher dosyasını açar.|

## <a name="remarks"></a>Açıklamalar

Gopher hizmet MFC WinINet sınıfları tarafından tanınan üç Internet Hizmetleri biridir.

Sınıf `CGopherConnection` bir oluşturucu ve gopher servisini yönetebileceğiniz üç ek üye işlevleri içerir: [Openfıle](#openfile), [CreateLocator](#createlocator), ve [GetAttribute](#getattribute).

Bir gopher Internet sunucusuyla iletişim kurmak için öncelikle bir örneğini oluşturmanız gerekir [Cınternetsession](../../mfc/reference/cinternetsession-class.md)ve sonra çağrı [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), oluşturan `CGopherConnection` Nesne ve bir işaretçi döndürür. Asla oluşturma bir `CGopherConnection` doğrudan nesne.

Hakkında daha fazla bilgi edinmek için `CGopherConnection` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md). Desteklenen Internet hizmetlerine diğer iki kullanma hakkında daha fazla bilgi için FTP ve HTTP sınıfları görmek [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection

Bu üye işlevi oluşturmak için çağrılan bir `CGopherConnection` nesne.

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

*pSession*<br/>
İlgili bir işaretçiye [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne.

*hConnected*<br/>
Geçerli Internet oturumu Windows tanıtıcısı.

*pstrServer*<br/>
FTP sunucusu adını içeren bir dize işaretçisi.

*dwContext*<br/>
İşlem bağlamı tanımlayıcısı. *dwContext* tarafından döndürülen işlem durumu bilgilerini tanımlayan [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; Ancak, belirli bir bağlam kimliği işlemi için açıkça atayabilirsiniz. Nesne ve mevcut herhangi bir iş, bir bağlam kimliği ile ilişkilendirilecek

*pstrUserName*<br/>
Oturum açmak için kullanıcı adını belirten bir null ile sonlandırılmış dize işaretçisi. NULL ise, anonim bir varsayılandır.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten bir boş sonlandırılmış dizeye bir işaretçi. Her iki *pstrPassword* ve *pstrUserName* NULL, varsayılan anonim kullanıcı e-posta adını paroladır. Varsa *pstrPassword* boş (veya boş bir dize) ancak *pstrUserName* NULL değil boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklar *pstrUserName* ve *pstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya ""|NULL veya ""|"anonim"|Kullanıcının e-posta adı|
|BOŞ olmayan bir dize|NULL veya ""|*pstrUserName*|" "|
|BOŞ bir NULL olmayan dize|HATA|HATA||
|BOŞ olmayan bir dize|BOŞ olmayan bir dize|*pstrUserName*|*pstrPassword*|

*nbağlantı noktası*<br/>
Sunucu üzerinde kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

### <a name="remarks"></a>Açıklamalar

Asla oluşturma bir `CGopherConnection` doğrudan. Bunun yerine çağrı [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), oluşturan bir `CGopherConnection` nesnesi ve bir işaretçi döndürür.

##  <a name="createlocator"></a>  CGopherConnection::CreateLocator

Bulmak veya bir gopher sunucusunda dosya tanımlamak için bir gopher Bulucusu oluşturmak için bu üye işlevini çağırın.

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
Gopher belge veya alınacak dizin adını içeren bir dize işaretçisi. Varsa *pstrDisplayString* gopher sunucusu için varsayılan dizin parametresi, NULL döndürülür.

*pstrSelectorString*<br/>
Bir öğe almak için gopher sunucuya gönderilecek Seçici dizeye bir işaretçi. *pstrSelectorString* NULL olabilir.

*dwGopherType*<br/>
Bu belirtir olup olmadığını *pstrSelectorString* bir dizin veya belge ifade eder ve isteği gopher veya gopher + olup. Yapı için öznitelikleri görmek [GOPHER_FIND_DATA](/windows/desktop/api/wininet/ns-wininet-gopher_find_dataa) Windows SDK.

*pstrLocator*<br/>
Açmak için dosyaya tanımlayan bir dize işaretçisi. Genellikle, bu dize çağrısından döndürülen [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).

*pstrServerName*<br/>
Gopher sunucu adını içeren bir dize işaretçisi.

*nbağlantı noktası*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan numara.

### <a name="return-value"></a>Dönüş Değeri

A [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlevini statik sürümünü, statik olmayan sürüm bağlantı nesnesi sunucu adını kullanırken, bir sunucu belirtmek gerektirir.

Bir gopher sunucusundan bilgi almak için bir uygulama ilk kez bir gopher Bulucu almanız gerekir. Uygulama ardından Bulucu donuk bir belirteç olarak ele almanız gerekir (diğer bir deyişle, uygulama Bulucu kullanın ancak değil doğrudan değiştirmek veya bu karşılaştırın). Normalde, çağrılar için Bulucu uygulamanın kullandığı [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) belirli bir bilgi almak için üye işlevi.

##  <a name="getattribute"></a>  CGopherConnection::GetAttribute

Gopher sunucusundan bir öğeyle ilgili belirli bir öznitelik bilgileri almak için bu üye işlevini çağırın.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>Parametreler

*refLocator*<br/>
Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.

*strRequestedAttributes*<br/>
İstenen öznitelikleri adlarını belirten boşlukla ayrılmış bir dize.

*strResult*<br/>
Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) , Bulucu türünü alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

##  <a name="openfile"></a>  CGopherConnection::OpenFile

Bir gopher sunucusunda bir dosyayı açmak için bu üye işlevini çağırın.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*refLocator*<br/>
Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.

*CertOpenStore*<br/>
Herhangi bir birleşimini INTERNET_FLAG_ * işaretler. Bkz: [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) INTERNET_FLAG_ ilgili daha fazla bilgi için\* bayrakları.

*pstrView*<br/>
Dosya görünümü dizeye bir işaretçi. Dosyanın çeşitli görünümlerini sunucuda mevcutsa, bu parametre hangi dosya görünümü açmak için belirtir. Varsa *pstrView* NULL ise varsayılan dosya görünümüne kullanılır.

*dwContext*<br/>
Açılan dosya bağlam kimliği. Bkz: **açıklamalar** hakkında daha fazla bilgi için *dwContext*.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [CGopherFile](../../mfc/reference/cgopherfile-class.md) açılması için nesne.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılma *dwContext* varsayılan bağlamı tanımlayıcısını bir değere ayarlamak için. Bu belirli işlemle ilişkili bağlam tanımlayıcıdır `CGopherConnection` tarafından oluşturulan nesne kendi [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile belirtilen işlem durumu sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpConnection Sınıfı](../../mfc/reference/cftpconnection-class.md)<br/>
[CHttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CGopherLocator Sınıfı](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CInternetSession Sınıfı](../../mfc/reference/cinternetsession-class.md)
