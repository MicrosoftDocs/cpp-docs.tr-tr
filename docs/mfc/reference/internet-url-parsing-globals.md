---
title: Internet URL Ayrıştma Globals ve Yardımcıları
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: 742b381ecb55c433d0f384174b7612fcc21e9716
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356613"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>Internet URL Ayrıştma Globals ve Yardımcıları

İstemci Internet sunucusuna bir sorgu gönderdiğinde, istemci hakkında bilgi ayıklamak için genel bilgileri ayrıştan URL'lerden birini kullanabilirsiniz. Yardımcı işlevleri diğer internet işlevselliği sağlar.

## <a name="internet-url-parsing-globals"></a>Internet URL Ayrıştırma Genel Öğeleri

|||
|-|-|
|[AfxParseURL](#afxparseurl)|Bir URL dizesini parses ve hizmet türünü ve bileşenlerini döndürür.|
|[AfxParseURLEx](#afxparseurlex)|Bir URL dizesini parses ve hizmet türünü ve bileşenlerini döndürür, yanı sıra kullanıcı adı ve parola sağlar.|

## <a name="other-internet-helpers"></a>Diğer İnternet Yardımcıları

|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Internet bağlantısı ile ilgili bir istisna atar.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Internet tanıtıcısının türünü belirler.|

## <a name="afxparseurl"></a><a name="afxparseurl"></a>AfxParseURL

Bu global [CInternetSession kullanılır::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

```
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort);
```

### <a name="parameters"></a>Parametreler

*pstrURL*<br/>
Ayrışdırılacak URL'yi içeren bir dize için işaretçi.

*dwServiceType*<br/>
Internet hizmeti türünü gösterir. Olası değerler aşağıdaki gibidir:

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*strServer*<br/>
Hizmet türünü izleyen URL'nin ilk bölümü.

*strObject*<br/>
URL'nin başvurulmuştettiği (boş olabilir) bir nesne.

*nPort*<br/>
Varsa, URL'nin Sunucu veya Nesne bölümlerinden belirlenir.

### <a name="return-value"></a>Dönüş Değeri

URL başarıyla ayrıştıysa sıfır olmayan; aksi takdirde, boşsa veya bilinen bir Internet hizmet türü içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Bir URL dizesini ayrışdırır ve hizmet türünü ve bileşenlerini döndürür.

Örneğin, `AfxParseURL` formun URL'lerini *service://server/dir/dir/object.ext:port* parses ve depolanan bileşenlerini aşağıdaki gibi döndürür:

*strServer* == "sunucu"

*strObject* == "/dir/dir/object/object.ext"

*nPort* == #port

*dwServiceType* == #service

> [!NOTE]
> Bu işlevi aramak için projenizin AFXINET içermesi gerekir. H.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxinet.h

## <a name="afxparseurlex"></a><a name="afxparseurlex"></a>AfxParseURLEx

Bu global işlev [AfxParseURL](#afxparseurl) genişletilmiş sürümüdür ve [CInternetSession kullanılır::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

```
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort,
    CString& strUsername,
    CString& strPassword,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parametreler

*pstrURL*<br/>
Ayrışdırılacak URL'yi içeren bir dize için işaretçi.

*dwServiceType*<br/>
Internet hizmeti türünü gösterir. Olası değerler aşağıdaki gibidir:

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*strServer*<br/>
Hizmet türünü izleyen URL'nin ilk bölümü.

*strObject*<br/>
URL'nin başvurulmuştettiği (boş olabilir) bir nesne.

*nPort*<br/>
Varsa, URL'nin Sunucu veya Nesne bölümlerinden belirlenir.

*strUsername*<br/>
Kullanıcının adını `CString` içeren bir nesneye başvuru.

*strPassword*<br/>
Kullanıcının parolasını içeren bir `CString` nesneye başvuru.

*Dwflags*<br/>
URL'yi ayrışdırmayı kontrol eden bayraklar. Aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Anlamı|
|-----------|-------------|
|ICU_DECODE|%XX kaçış dizilerini karakterlere dönüştürün.|
|ICU_NO_ENCODE|Güvenli olmayan karakterleri kaçış sırasına dönüştürmeyin.|
|ICU_NO_META|Meta dizilerini ("\ " gibi) kaldırmayın. ve "\ ..") URL'den.|
|ICU_ENCODE_SPACES_ONLY|Yalnızca boşlukları kodlayın.|
|ICU_BROWSER_MODE|'#' veya ''''den sonra karakterleri kodlamayın veya şifreyi çözmayın ve ''''''''''''den sonra giden beyaz boşluğu kaldırmayın. Bu değer belirtilmemişse, URL'nin tamamı kodlanır ve sondaki beyaz alan kaldırılır.|

Bayrak olmayan MFC varsayılanını kullanırsanız, işlev dizilerden kaçmak için tüm güvenli olmayan \\karakterleri ve meta dizilerini (.,\ .., ve \\...) dönüştürür.

### <a name="return-value"></a>Dönüş Değeri

URL başarıyla ayrıştıysa sıfır olmayan; aksi takdirde, boşsa veya bilinen bir Internet hizmet türü içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Bir URL dizesini ayrışdırır ve hizmet türünü ve bileşenlerini döndürür, ayrıca kullanıcının adını ve parolasını sağlar. Bayraklar, güvenli olmayan karakterlerin nasıl işleneceğini gösterir.

> [!NOTE]
> Bu işlevi aramak için projenizin AFXINET içermesi gerekir. H.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxinet.h

## <a name="afxgetinternethandletype"></a><a name="afxgetinternethandletype"></a>AfxGetInternetHandleType

Internet tanıtıcısının türünü belirlemek için bu genel işlevi kullanın.

### <a name="syntax"></a>Sözdizimi

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>Parametreler

*hQuery*<br/>
Internet sorgusunun tutamacı.

### <a name="return-value"></a>Dönüş Değeri

WININET tarafından tanımlanan Internet servis türlerinden herhangi biri. H. Bu Internet hizmetlerinin listesi için Açıklamalar bölümüne bakın. Tanıtıcı NULL ise veya tanınmıyorsa, işlev AFX_INET_SERVICE_UNK döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki liste, '. tarafından `AfxGetInternetHandleType`döndürülen olası Internet türlerini içerir.

- INTERNET_HANDLE_TYPE_INTERNET

- INTERNET_HANDLE_TYPE_CONNECT_FTP

- INTERNET_HANDLE_TYPE_CONNECT_GOPHER

- INTERNET_HANDLE_TYPE_CONNECT_HTTP

- INTERNET_HANDLE_TYPE_FTP_FIND

- INTERNET_HANDLE_TYPE_FTP_FIND_HTML

- INTERNET_HANDLE_TYPE_FTP_FILE

- INTERNET_HANDLE_TYPE_FTP_FILE_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FIND

- INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FILE

- INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML

- INTERNET_HANDLE_TYPE_HTTP_REQUEST

> [!NOTE]
> Bu işlevi aramak için projenizin AFXINET içermesi gerekir. H.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="afxthrowinternetexception"></a><a name="afxthrowinternetexception"></a>AfxThrowInternetException

Bir Internet özel durum atar.

### <a name="syntax"></a>Sözdizimi

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>Parametreler

*dwBağlam*<br/>
Hataya neden olan işlemin bağlam tanımlayıcısı. *dwContext'ın* varsayılan değeri [cinternetsession'da](cinternetsession-class.md) orijinal olarak belirtilir ve [CInternetConnection](cinternetconnection-class.md)'a ve [CInternetFile](cinternetfile-class.md)türetilmiş sınıflara geçirilir. Bir bağlantı veya dosya üzerinde gerçekleştirilen belirli işlemler için, genellikle varsayılanı kendi *dwContext'ınızla* geçersiz kılarsınız. Bu değer daha sonra [CInternetSession döndürülür::OnStatusCallback](cinternetsession-class.md#onstatuscallback) belirli bir işlemin durumunu tanımlamak için.

*dwHata*<br/>
Özel duruma neden hata.

### <a name="remarks"></a>Açıklamalar

İşletim sistemi hata kodunu temel alan nedeni belirlemekten siz sorumlusunuz.

> [!NOTE]
> Bu işlevi aramak için projenizin AFXINET içermesi gerekir. H.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[CInternetException Sınıf](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
