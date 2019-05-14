---
title: Internet URL Ayrıştırma genel öğeleri ve Yardımcıları
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: 310e4ffb3fc207d874e97ba1fac65f6f8cb41a31
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611021"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>Internet URL Ayrıştırma genel öğeleri ve Yardımcıları

Bir istemci Internet sunucusuna bir sorgu gönderdiğinde, bu URL Ayrıştırma genel öğeleri birini istemcisi hakkında bilgi ayıklamak için kullanabilirsiniz. Yardımcı işlevleri diğer internet işlevselliği sağlar.

## <a name="internet-url-parsing-globals"></a>Internet URL Ayrıştırma Genel Öğeleri

|||
|-|-|
|[AfxParseURL](#afxparseurl)|Bir URL dizeyi ayrıştırır ve hizmet ve bileşenlerinin türünü döndürür.|
|[AfxParseURLEx](#afxparseurlex)|Bir URL dizeyi ayrıştırır ve hizmet ve bileşenlerinin yanı kullanıcı adı ve parola sağlama türünü döndürür.|

## <a name="other-internet-helpers"></a>Diğer Internet Yardımcıları

|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|İnternet bağlantısı ilgili özel durum oluşturur.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Bir Internet tanıtıcısı türünü belirler.|

##  <a name="afxparseurl"></a>  AfxParseURL

Bu genel olarak kullanılan [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

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
Ayrıştırılacak URL'sini içeren bir dize işaretçisi.

*dwServiceType*<br/>
Internet hizmet türünü belirtir. Olası değerler aşağıdaki gibidir:

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
İlk hizmet türü aşağıdaki URL kesimi.

*strObject*<br/>
URL başvurduğu nesneyi (boş olabilir).

*nbağlantı noktası*<br/>
Ya da varsa URL'yi sunucu veya nesne bölümlerinden belirledi.

### <a name="return-value"></a>Dönüş Değeri

URL başarıyla ayrıştırıldı olursa sıfır dışı; Aksi halde ise 0 boş veya bilinen bir Internet hizmet türü içermiyor.

### <a name="remarks"></a>Açıklamalar

Bu, bir URL dizeyi ayrıştırır ve hizmet ve bileşenlerinin türünü döndürür.

Örneğin, `AfxParseURL` biçimindeki URL'ler ayrıştırır *service://server/dir/dir/object.ext:port* ve şu şekilde depolanan bileşenleri döndürür:

*strServer* == "server"

*strObject* == "/dir/dir/object/object.ext"

*nbağlantı noktası* #port ==

*dwServiceType* == #service

> [!NOTE]
>  Bu işlevi çağırmak için projenizi AFXINET içermelidir. H

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxinet.h

##  <a name="afxparseurlex"></a>  AfxParseURLEx

Bu genel işlev genişletilmiş sürümüdür [AfxParseURL](#afxparseurl) ve kullanılan [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

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
Ayrıştırılacak URL'sini içeren bir dize işaretçisi.

*dwServiceType*<br/>
Internet hizmet türünü belirtir. Olası değerler aşağıdaki gibidir:

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
İlk hizmet türü aşağıdaki URL kesimi.

*strObject*<br/>
URL başvurduğu nesneyi (boş olabilir).

*nbağlantı noktası*<br/>
Ya da varsa URL'yi sunucu veya nesne bölümlerinden belirledi.

*strUsername*<br/>
Bir başvuru bir `CString` kullanıcı adını içeren bir nesne.

*strPassword*<br/>
Bir başvuru bir `CString` kullanıcının parolasını içeren nesne.

*CertOpenStore*<br/>
URL ayrıştırmayı denetleme bayraklar. Aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Açıklama|
|-----------|-------------|
|ICU_DECODE|% XX kaçış dizileri karakterlere dönüştürür.|
|ICU_NO_ENCODE|Güvenli olmayan karakterleri kaçış sırası dönüştürmez.|
|ICU_NO_META|Meta dizilerini (örneğin, "\." kaldırma ve "\..") URL.|
|ICU_ENCODE_SPACES_ONLY|Yalnızca boşluk kodlayın.|
|ICU_BROWSER_MODE|Değil kodlayın veya karakterler, '# 'karakterinden sonra kod çözme veya '' ve sonra sondaki boşluk kaldırmayın ''. Bu değer belirtilmezse, URL'nin tamamını kodlanır ve boşluk kaldırılır.|

Bayrak MFC varsayılanını kullanırsanız, tüm güvenli olmayan karakterleri ve meta dizileri işlevi dönüştürür (gibi \\., \.., ve \\...) kaçış dizileri.

### <a name="return-value"></a>Dönüş Değeri

URL başarıyla ayrıştırıldı olursa sıfır dışı; Aksi halde ise 0 boş veya bilinen bir Internet hizmet türü içermiyor.

### <a name="remarks"></a>Açıklamalar

Bu, bir URL dizeyi ayrıştırır ve hizmet ve bileşenlerinin yanı kullanıcı adı ve parola sağlama türünü döndürür. Bayrakları nasıl güvenli olmayan karakterleri gösterir işlenir.

> [!NOTE]
>  Bu işlevi çağırmak için projenizi AFXINET içermelidir. H

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxinet.h

## <a name="afxgetinternethandletype"></a>  AfxGetInternetHandleType

Bu genel işlev, bir Internet tanıtıcı türü belirlemek için kullanın.

### <a name="syntax"></a>Sözdizimi

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>Parametreler

*hQuery*<br/>
Bir Internet sorgu için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir WİNINET tarafından tanımlanan Internet hizmet türü. H Bu Internet hizmetlerin listesi için Açıklamalar bölümüne bakın. Tanıtıcı boş veya tanınmıyor, işlev AFX_INET_SERVICE_UNK döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki liste, olası Internet türleri tarafından döndürülen içermektedir `AfxGetInternetHandleType`.

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
>  Bu işlevi çağırmak için projenizin AFXINET içermelidir. H

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

## <a name="afxthrowinternetexception"></a>  Afxthrowınternetexception

Bir Internet özel durum oluşturur.

### <a name="syntax"></a>Sözdizimi

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>Parametreler

*dwContext*<br/>
Hataya neden olan işlem bağlam tanımlayıcısı. Varsayılan değer olan *dwContext* başlangıçta belirtilen [Cınternetsession](cinternetsession-class.md) ve geçirilen [Cınternetconnection](cinternetconnection-class.md)- ve [Cınternetfile](cinternetfile-class.md)-türetilmiş sınıflar. Bir bağlantı veya bir dosya üzerinde gerçekleştirilen belirli işlemler için genellikle varsayılan geçersiz bir *dwContext* kendi. Bu değer daha sonra döndürülen [CInternetSession::OnStatusCallback](cinternetsession-class.md#onstatuscallback) belirli işlemin durumunu belirlemek için.

*dwError*<br/>
Özel duruma neden hata.

### <a name="remarks"></a>Açıklamalar

İşletim sistemi hata koduna göre nedenini belirlemek için sorumlu olursunuz.

> [!NOTE]
>  Bu işlevi çağırmak için projenizi AFXINET içermelidir. H

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[CInternetException Sınıfı](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
