---
description: "Hakkında daha fazla bilgi edinin: Internet URL 'SI genel ve yardımcıları ayrıştırma"
title: Internet URL 'SI, genel ve yardımcıları ayrıştırma
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: 4dca0946686759a3880c73aa425edcc724d8772d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219505"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>Internet URL 'SI, genel ve yardımcıları ayrıştırma

Bir istemci Internet sunucusuna bir sorgu gönderdiğinde, istemci hakkında bilgi ayıklamak için genel olarak ayrıştırma URL 'sinden birini kullanabilirsiniz. Yardımcı işlevler diğer internet işlevlerini sağlar.

## <a name="internet-url-parsing-globals"></a>Internet URL Ayrıştırma Genel Öğeleri

|Ad|Açıklama|
|-|-|
|[AfxParseURL 'Si](#afxparseurl)|Bir URL dizesini ayrıştırır ve hizmet türünü ve bileşenlerini döndürür.|
|[AfxParseURLEx](#afxparseurlex)|Bir URL dizesini ayrıştırır ve hizmet türünü ve bileşenlerini ve Kullanıcı adını ve parolasını sağlar.|

## <a name="other-internet-helpers"></a>Diğer Internet yardımcıları

|Ad|Açıklama|
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Internet bağlantısıyla ilgili bir özel durum oluşturur.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Internet tanıtıcısının türünü belirler.|

## <a name="afxparseurl"></a><a name="afxparseurl"></a> AfxParseURL 'Si

Bu genel, [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)içinde kullanılır.

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
Ayrıştırılacak URL 'YI içeren bir dize işaretçisi.

*dwServiceType*<br/>
Internet hizmetinin türünü gösterir. Olası değerler aşağıdaki gibidir:

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
URL 'nin hizmet türünü izleyen ilk segmenti.

*strObject*<br/>
URL 'nin başvurduğu bir nesne (boş olabilir).

*nPort*<br/>
Varsa, URL 'nin sunucu veya nesne bölümlerinden belirlenir.

### <a name="return-value"></a>Dönüş Değeri

URL başarıyla ayrıştırılırsa sıfır dışı; Aksi takdirde, boş ise veya bilinen bir Internet hizmeti türü içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Bir URL dizesini ayrıştırır ve hizmet türünü ve bileşenlerini döndürür.

Örneğin, `AfxParseURL` *Service://Server/dir/dir/Object.ext:Port* formunun URL 'lerini ayrıştırır ve bileşenlerini şu şekilde saklı olarak döndürür:

*strServer* = = "sunucu"

*strObject* = = "/dir/dir/Object/Object.exe"

*Nport* = = #port

*Dwservicetype* = = #service

> [!NOTE]
> Bu işlevi çağırmak için projenizin AFXıNET. H içermesi gerekir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** AFXINET. h

## <a name="afxparseurlex"></a><a name="afxparseurlex"></a> AfxParseURLEx

Bu genel işlev, [AfxParseURL](#afxparseurl) 'nin genişletilmiş sürümüdür ve [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)' de kullanılır.

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
Ayrıştırılacak URL 'YI içeren bir dize işaretçisi.

*dwServiceType*<br/>
Internet hizmetinin türünü gösterir. Olası değerler aşağıdaki gibidir:

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
URL 'nin hizmet türünü izleyen ilk segmenti.

*strObject*<br/>
URL 'nin başvurduğu bir nesne (boş olabilir).

*nPort*<br/>
Varsa, URL 'nin sunucu veya nesne bölümlerinden belirlenir.

*strUsername*<br/>
`CString`Kullanıcının adını içeren bir nesneye başvuru.

*strPassword*<br/>
`CString`Kullanıcının parolasını içeren bir nesneye başvuru.

*dwFlags*<br/>
URL 'YI ayrıştırmayı denetleyen bayraklar. Aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Anlamı|
|-----------|-------------|
|ICU_DECODE|% XX kaçış dizilerini karakterlere Dönüştür.|
|ICU_NO_ENCODE|Güvenli olmayan karakterleri kaçış dizisine dönüştürmeyin.|
|ICU_NO_META|Meta dizileri kaldırmayın (örneğin, "\.") ve "\..") URL 'den.|
|ICU_ENCODE_SPACES_ONLY|Yalnızca boşlukları kodlayın.|
|ICU_BROWSER_MODE|' # ' Veya ' ' karakterinden sonra karakterleri kodlamayın veya kodu çözmeyin ve ' ' öğesinden sonra sondaki boşluğu kaldırmayın. Bu değer belirtilmezse, tüm URL kodlanır ve sondaki boşluk kaldırılır.|

Hiçbir bayrak olmayan MFC varsayılanını kullanırsanız, işlev güvenli olmayan tüm karakterleri ve meta dizileri (örneğin \\ ,., \.., ve \\ ...) kaçış sıralarına dönüştürür.

### <a name="return-value"></a>Dönüş Değeri

URL başarıyla ayrıştırılırsa sıfır dışı; Aksi takdirde, boş ise veya bilinen bir Internet hizmeti türü içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

Bir URL dizesini ayrıştırır ve hizmet türünü ve bileşenlerini döndürür ve kullanıcının adını ve parolasını sağlar. Bayraklar, güvenli olmayan karakterlerin nasıl işleneceğini gösterir.

> [!NOTE]
> Bu işlevi çağırmak için projenizin AFXıNET. H içermesi gerekir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** AFXINET. h

## <a name="afxgetinternethandletype"></a><a name="afxgetinternethandletype"></a> AfxGetInternetHandleType

Internet tanıtıcısının türünü öğrenmek için bu genel işlevi kullanın.

### <a name="syntax"></a>Sözdizimi

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>Parametreler

*hQuery*<br/>
Internet sorgusuna yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

WININET. H tarafından tanımlanan Internet hizmet türlerinden herhangi biri. Bu Internet hizmetlerinin listesi için açıklamalar bölümüne bakın. Tanıtıcı NULL veya tanınmazsa, işlev AFX_INET_SERVICE_UNK döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki liste tarafından döndürülen olası Internet türlerini içerir `AfxGetInternetHandleType` .

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
> Bu işlevi çağırmak için projenizin AFXıNET. H içermesi gerekir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="afxthrowinternetexception"></a><a name="afxthrowinternetexception"></a> AfxThrowInternetException

Bir Internet özel durumu oluşturur.

### <a name="syntax"></a>Sözdizimi

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>Parametreler

*dwContext*<br/>
Hataya neden olan işlem için bağlam tanımlayıcısı. *DwContext* 'in varsayılan değeri, Ilk olarak [cınternetoturumunda](cinternetsession-class.md) belirtilir ve [CInternetConnection](cinternetconnection-class.md)-ve [CInternetFile](cinternetfile-class.md)ile türetilmiş sınıflara geçirilir. Bir bağlantı veya dosya üzerinde gerçekleştirilen belirli işlemler için genellikle varsayılan ayarı kendi bir *dwContext* ile geçersiz kılarsınız. Bu değer daha sonra, belirli işlemin durumunu tanımlamak için [CInternetSession:: OnStatusCallback](cinternetsession-class.md#onstatuscallback) öğesine döndürülür.

*dwError*<br/>
Özel duruma neden hata.

### <a name="remarks"></a>Açıklamalar

İşletim sistemi hata koduna göre nedeni belirlemekten siz sorumlusunuz.

> [!NOTE]
> Bu işlevi çağırmak için projenizin AFXıNET. H içermesi gerekir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[CInternetException Sınıfı](cinternetexception-class.md)<br/>
[AfxParseURL 'Si](internet-url-parsing-globals.md#afxparseurl)
