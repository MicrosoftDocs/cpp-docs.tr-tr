---
description: 'Daha fazla bilgi edinin: CHttpConnection Class'
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
ms.openlocfilehash: 19a99f0f4eb6844d60a6e42a079214e1c70628fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143656"
---
# <a name="chttpconnection-class"></a>CHttpConnection sınıfı

Bir HTTP sunucusuyla bağlantınızı yönetir.

## <a name="syntax"></a>Syntax

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHttpConnection::CHttpConnection](#chttpconnection)|Bir `CHttpConnection` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHttpConnection:: OpenRequest](#openrequest)|Bir HTTP isteği açar.|

## <a name="remarks"></a>Açıklamalar

HTTP, MFC WinInet sınıfları tarafından uygulanan üç Internet sunucu protokollerinden biridir.

Sınıfı bir `CHttpConnection` Oluşturucu ve bir üye işlevi olan [OpenRequest](#openrequest), bir http protokolüyle sunucu bağlantılarını yönetir.

Bir HTTP sunucusuyla iletişim kurmak için, önce bir [CInternetSession](../../mfc/reference/cinternetsession-class.md)örneği oluşturmanız ve ardından bir [CHttpConnection](#chttpconnection) nesnesi oluşturmanız gerekir. Hiçbir şekilde doğrudan bir nesne oluşturmamanız gerekir `CHttpConnection` . bunun yerine, nesneyi oluşturan ve kendisine bir işaretçi döndüren [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)öğesini çağırın `CHttpConnection` .

Diğer MFC Internet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi edinmek için `CHttpConnection` bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi. Diğer iki desteklenen Internet protokollerini, gopher ve FTP 'yi kullanarak sunuculara bağlanma hakkında daha fazla bilgi için bkz. [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md)sınıfları.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="chttpconnectionchttpconnection"></a><a name="chttpconnection"></a> CHttpConnection::CHttpConnection

Bu üye işlevi bir nesne oluşturmak için çağırılır `CHttpConnection` .

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
[CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesine yönelik bir işaretçi.

*hConnected*<br/>
Internet bağlantısı için bir tanıtıcı.

*pstrServer*<br/>
Sunucu adını içeren bir dize işaretçisi.

*dwContext*<br/>
Nesnenin bağlam tanımlayıcısı `CInternetConnection` . *DwContext* hakkında daha fazla bilgi Için, **açıklamalar** bölümüne bakın.

*nPort*<br/>
Bu bağlantı için Internet bağlantı noktasını tanımlayan sayı.

*pstrUserName*<br/>
Oturum açmak için kullanıcının adını belirten, null ile sonlandırılmış bir dize işaretçisi. NULL ise, varsayılan olarak anonim olur.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten, null ile sonlandırılmış bir dize işaretçisi. Hem *pstrPassword* hem de *PSTRUSERNAME* null ise, varsayılan Anonim parola kullanıcının e-posta adıdır. *PstrPassword* null ya da boş bir dize ise, ancak *pstrUserName* null değilse boş bir parola kullanılır. Aşağıdaki tabloda *pstrUserName* ve *pstrPassword* öğesinin dört olası ayarlarının davranışı açıklanmaktadır:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen Kullanıcı adı|FTP sunucusuna parola gönderildi|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya ""|NULL veya ""|deðeri|Kullanıcının e-posta adı|
|NULL olmayan dize|NULL veya ""|*pstrUserName*|" "|
|NULL |NULL olmayan dize|HATA|HATA|
|NULL olmayan dize|NULL olmayan dize|*pstrUserName*|*pstrPassword*|

*dwFlags*<br/>
Bayrakların herhangi bir birleşimi `INTERNET_FLAG_*` . *DwFlags* değerlerinin açıklaması için [CHttpConnection:: OpenRequest](#openrequest) konusunun **açıklamalar** bölümünde bulunan tabloya bakın.

### <a name="remarks"></a>Açıklamalar

Hiçbir şekilde doğrudan oluşturmayın `CHttpConnection` . Bunun yerine, [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)çağırarak bir nesne oluşturursunuz.

## <a name="chttpconnectionopenrequest"></a><a name="openrequest"></a> CHttpConnection:: OpenRequest

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
İstekte kullanılacak fiil içeren bir dize işaretçisi. NULL ise "GET" kullanılır.

*pstrObjectName*<br/>
Belirtilen fiilin hedef nesnesini içeren bir dizeye yönelik işaretçi. Bu dize genellikle bir dosya adı, yürütülebilir bir modül veya bir arama belirticisidir.

*pstrReferer*<br/>
İstekteki URL 'nin (*pstrObjectName*) alındığı belgenin ADRESINI (URL) belirten bir dize işaretçisi. NULL ise, HTTP üstbilgisi belirtilmez.

*dwContext*<br/>
İşlemin bağlam tanımlayıcısı `OpenRequest` . *DwContext* hakkında daha fazla bilgi Için, açıklamalar bölümüne bakın.

*ppstrAcceptTypes*<br/>
İstemci tarafından kabul edilen içerik türlerini gösteren dizelerin, null ile sonlandırılan bir LPCTSTR işaretçileri dizisine yönelik bir işaretçi. *PpstrAcceptTypes* null ise, sunucular istemcinin yalnızca "metin/*" türündeki belgeleri kabul ettiğini (yani yalnızca metin belgelerini veya diğer ikili dosyaları) kabul ettiğini yorumlar. İçerik türü, HTTP POST ve PUT gibi ekli bilgilere sahip sorguların veri türünü tanımlayan CONTENT_TYPE CGI değişkenine eşdeğerdir.

*pstrVersion*<br/>
HTTP sürümünü tanımlayan bir dize işaretçisi. NULL ise "HTTP/1.0" kullanılır.

*dwFlags*<br/>
INTERNET_ FLAG_ * bayraklarının herhangi bir birleşimi. Olası *dwFlags* değerlerinin açıklaması için açıklamalar bölümüne bakın.

*Nfiil*<br/>
HTTP istek türüyle ilişkili bir sayı. Aşağıdakilerden biri olabilir:

|HTTP istek türü|*Nfiil* değeri|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>Dönüş Değeri

İstenen [CHttpFile](../../mfc/reference/chttpfile-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*dwFlags* , aşağıdakilerden biri olabilir:

|Internet bayrağı|Açıklama|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|İstenen dosya, nesne veya dizin listesinin önbellekten değil, kaynak sunucudan indirilmesini zorlar.|
|INTERNET_FLAG_DONT_CACHE|Döndürülen varlığı önbelleğe eklemez.|
|INTERNET_FLAG_MAKE_PERSISTENT|Döndürülen varlığı önbelleğe kalıcı bir varlık olarak ekler. Standart önbellek temizleme, tutarlılık denetimi veya çöp toplamanın bu öğeyi önbellekten kaldıramayacağı anlamına gelir.|
|INTERNET_FLAG_SECURE|Güvenli işlem semantiğini kullanır. SSL/PCT 'yi kullanmaya çevirir ve yalnızca HTTP isteklerinde anlamlı|
|INTERNET_FLAG_NO_AUTO_REDIRECT|Yalnızca HTTP ile birlikte kullanıldığında, [CHttpFile:: SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest)içinde otomatik olarak yeniden yönlendirmeler işlenmemelidir.|

`dwContext`Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılın. Bağlam tanımlayıcısı, `CHttpConnection` [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından oluşturulan nesnenin bu özel işlemiyle ilişkilidir. Değer, tanımlandıkları işlemde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) değerine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

Bu işlevle özel durumlar oluşturulabilir.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpFile sınıfı](../../mfc/reference/chttpfile-class.md)
