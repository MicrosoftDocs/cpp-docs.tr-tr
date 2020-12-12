---
description: 'Daha fazla bilgi edinin: CGopherConnection sınıfı'
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
ms.openlocfilehash: c75cdea4df7a0f5ecbead3770f572d482432382d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184094"
---
# <a name="cgopherconnection-class"></a>CGopherConnection sınıfı

Bir gopher Internet sunucusuyla bağlantınızı yönetir.

> [!NOTE]
> Sınıflar `CGopherConnection` , `CGopherFile` , `CGopherFileFind` `CGopherLocator` ve üyeleri Windows XP platformunda çalışmadıklarından kullanım dışı bırakılmıştır, ancak önceki platformlarda çalışmaya devam ederler.

## <a name="syntax"></a>Syntax

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGopherConnection:: CGopherConnection](#cgopherconnection)|Bir `CGopherConnection` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGopherConnection:: CreateLocator](#createlocator)|Bir gopher sunucusunda dosyaları bulmak için bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi oluşturur.|
|[CGopherConnection:: GetAttribute](#getattribute)|Gopher nesnesiyle ilgili öznitelik bilgilerini alır.|
|[CGopherConnection:: OpenFile](#openfile)|Bir gopher dosyası açar.|

## <a name="remarks"></a>Açıklamalar

Gopher hizmeti, MFC WinInet sınıfları tarafından tanınan üç Internet hizmetlerinden biridir.

Sınıfı, `CGopherConnection` bir Oluşturucu ve gopher hizmetini yöneten üç ek üye işlev içerir: [OpenFile](#openfile), [CreateLocator](#createlocator)ve [GetAttribute](#getattribute).

Gopher Internet sunucusuyla iletişim kurmak için, önce bir [CInternetSession](../../mfc/reference/cinternetsession-class.md)örneği oluşturmanız ve ardından nesneyi oluşturan ve ona bir Işaretçi döndüren [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)öğesini çağırmanız gerekir `CGopherConnection` . Hiçbir şekilde doğrudan bir nesne oluşturmamanız gerekir `CGopherConnection` .

Diğer MFC Internet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi edinmek için `CGopherConnection` bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi. Desteklenen diğer iki Internet hizmetini kullanma hakkında daha fazla bilgi için FTP ve HTTP, [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md)sınıflarını inceleyin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cgopherconnectioncgopherconnection"></a><a name="cgopherconnection"></a> CGopherConnection:: CGopherConnection

Bu üye işlevi bir nesne oluşturmak için çağırılır `CGopherConnection` .

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
İlgili [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesine yönelik bir işaretçi.

*hConnected*<br/>
Geçerli Internet oturumunun Windows tanıtıcısı.

*pstrServer*<br/>
FTP sunucu adını içeren bir dize işaretçisi.

*dwContext*<br/>
İşlemin bağlam tanımlayıcısı. *dwContext* , [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)tarafından döndürülen işlemin durum bilgilerini tanımlar. Varsayılan değer 1 ' e ayarlanır; Ancak, işlem için özel bir bağlam KIMLIĞINI açıkça atayabilirsiniz. Nesne ve onun yaptığı herhangi bir iş, bu bağlam KIMLIĞIYLE ilişkilendirilecektir.

*pstrUserName*<br/>
Oturum açmak için kullanıcının adını belirten, null ile sonlandırılmış bir dize işaretçisi. NULL ise, varsayılan olarak anonim olur.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten, null ile sonlandırılmış bir dize işaretçisi. Hem *pstrPassword* hem de *PSTRUSERNAME* null ise, varsayılan Anonim parola kullanıcının e-posta adıdır. *PstrPassword* null (veya boş bir dize) ise, ancak *pstrUserName* null değilse boş bir parola kullanılır. Aşağıdaki tabloda *pstrUserName* ve *pstrPassword* öğesinin dört olası ayarlarının davranışı açıklanmaktadır:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen Kullanıcı adı|FTP sunucusuna parola gönderildi|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya ""|NULL veya ""|deðeri|Kullanıcının e-posta adı|
|NULL olmayan dize|NULL veya ""|*pstrUserName*|" "|
|Null olmayan boş dize|HATA|HATA||
|NULL olmayan dize|NULL olmayan dize|*pstrUserName*|*pstrPassword*|

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını belirleyen bir sayı.

### <a name="remarks"></a>Açıklamalar

Hiçbir şekilde doğrudan oluşturmayın `CGopherConnection` . Bunun yerine, bir nesnesi oluşturan ve ona bir işaretçi döndüren [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)öğesini çağırın `CGopherConnection` .

## <a name="cgopherconnectioncreatelocator"></a><a name="createlocator"></a> CGopherConnection:: CreateLocator

Gopher sunucusunda bir dosyayı bulmak veya tanımlamak üzere bir Gopher Bulucu oluşturmak için bu üye işlevi çağırın.

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
Alınacak Gopher belgesi veya dizininin adını içeren bir dize işaretçisi. *PstrDisplayString* parametresi null ise, Gopher Sunucusu için varsayılan dizin döndürülür.

*pstrSelectorString*<br/>
Bir öğeyi almak için Gopher sunucusuna gönderilecek seçici dizesine yönelik bir işaretçi. *pstrSelectorString* null olabilir.

*dwGopherType*<br/>
Bu, *pstrSelectorString* 'in bir dizin veya belgeye başvurduğunu ve isteğin Gopher veya Gopher + olup olmadığını belirtir. Windows SDK yapı [GOPHER_FIND_DATA](/windows/win32/api/wininet/ns-wininet-gopher_find_dataw) yönelik özniteliklere bakın.

*pstrLocator*<br/>
Açılacak dosyayı tanımlayan dizeye yönelik bir işaretçi. Genellikle bu dize, [CGopherFileFind:: GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator)çağrısından döndürülür.

*pstrServerName*<br/>
Gopher sunucu adını içeren bir dize işaretçisi.

*nPort*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan sayı.

### <a name="return-value"></a>Dönüş Değeri

Bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevin statik sürümü bir sunucu belirtmenizi gerektirir, ancak statik olmayan sürüm bağlantı nesnesinden sunucu adını kullanır.

Bir gopher sunucusundan bilgi almak için öncelikle bir uygulamanın Gopher Bulucu alması gerekir. Daha sonra uygulama, Konumlandırıcı 'yı donuk bir belirteç olarak kabul etmelidir (yani, uygulama konum belirleyiciyi kullanabilir ancak doğrudan işleyemez veya karşılaştıramaz). Genellikle uygulama, belirli bir bilgi parçasını almak için [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) üye işlevine yapılan çağrılar için bulucu kullanır.

## <a name="cgopherconnectiongetattribute"></a><a name="getattribute"></a> CGopherConnection:: GetAttribute

Gopher sunucusundan bir öğe hakkında belirli öznitelik bilgilerini almak için bu üye işlevi çağırın.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>Parametreler

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesine bir başvuru.

*strRequestedAttributes*<br/>
İstenen özniteliklerin adlarını belirten boşlukla ayrılmış bir dize.

*strResult*<br/>
Konumlandırıcı türünü alan bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

## <a name="cgopherconnectionopenfile"></a><a name="openfile"></a> CGopherConnection:: OpenFile

Bir gopher sunucusunda bir dosya açmak için bu üye işlevi çağırın.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesine bir başvuru.

*dwFlags*<br/>
INTERNET_FLAG_ * bayraklarının herhangi bir birleşimi. INTERNET_FLAG_ bayrakları hakkında daha fazla bilgi için bkz. [CInternetSession:: OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) \* .

*pstrView*<br/>
Dosya görüntüleme dizesine yönelik bir işaretçi. Sunucuda birden çok görüntü varsa, bu parametre açılacak dosya görünümünü belirtir. *PstrView* null ise, varsayılan dosya görünümü kullanılır.

*dwContext*<br/>
Açılan dosyanın bağlam KIMLIĞI. *DwContext* hakkında daha fazla bilgi için bkz. **açıklamalar** .

### <a name="return-value"></a>Dönüş Değeri

Açılacak [CGopherFile](../../mfc/reference/cgopherfile-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için *dwContext* varsayılanını geçersiz kılın. Bağlam tanımlayıcısı, `CGopherConnection` [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından oluşturulan nesnenin bu özel işlemiyle ilişkilidir. Değer, tanımlandıkları işlemde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) değerine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpConnection sınıfı](../../mfc/reference/cftpconnection-class.md)<br/>
[CHttpConnection sınıfı](../../mfc/reference/chttpconnection-class.md)<br/>
[CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CGopherLocator sınıfı](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CInternetSession sınıfı](../../mfc/reference/cinternetsession-class.md)
