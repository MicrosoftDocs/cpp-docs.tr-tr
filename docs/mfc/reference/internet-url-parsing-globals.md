---
title: "Internet URL Ayrıştırma genel öğeleri ve Yardımcıları | Microsoft Docs"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.isapi
dev_langs: C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b30ecd8a8a508842d0edf9af8c4b3736728ca735
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="internet-url-parsing-globals-and-helpers"></a>Internet URL Ayrıştırma genel öğeleri ve Yardımcıları
Bir istemci Internet sunucusuna bir sorgu gönderdiğinde, URL Ayrıştırma genel öğeleri birini istemcisi hakkında bilgi ayıklamak için kullanabilirsiniz. Yardımcı işlevleri diğer Internet işlevsellik sağlar.
  
## <a name="internet-url-parsing-globals"></a>Internet URL Ayrıştırma Genel Öğeleri  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|URL dizesi ayrıştırır ve hizmet ve bileşenlerinin türünü döndürür.|  
|[AfxParseURLEx](#afxparseurlex)|URL dizesi ayrıştırır ve hizmet ve bileşenlerinin, yanı sıra kullanıcı adını ve parolasını sağlayarak türünü döndürür.|  

## <a name="other-internet-helpers"></a>Diğer Internet Yardımcıları
|||
|-|-|
|[Afxthrowınternetexception](#afxthrowinternetexception)|İnternet bağlantısı ile ilgili bir özel durum oluşturur.|
|[Afxgetınternethandletype](#afxgetinternethandletype)|Bir Internet tanıtıcısı türünü belirler.|
  
##  <a name="afxparseurl"></a>AfxParseURL  
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
 *pstrURL*  
 Ayrıştırılacak URL'sini içeren bir dize için bir işaretçi.  
  
 `dwServiceType`  
 Internet hizmet türünü belirtir. Olası değerler aşağıdaki gibidir:  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Hizmet türü aşağıdaki URL ilk kesimi.  
  
 `strObject`  
 URL başvurduğu bir nesne (boş olabilir).  
  
 `nPort`  
 Ya da varsa sunucu veya nesne URL bölümlerinden belirledi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 URL başarıyla ayrıştırıldığında, sıfır olmayan; Aksi takdirde, 0 boşsa veya bilinen Internet hizmet türü içermiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 URL dizesi ayrıştırır ve hizmet ve bileşenlerinin türünü döndürür.  
  
 Örneğin, `AfxParseURL` formun URL'lerini ayrıştırır **service://server/dir/dir/object.ext:port** ve aşağıdaki gibi depolanan bileşenlerinden döndürür:  
  
 `strServer`"server" ==  
  
 `strObject`== "/ dir/dir/object/object.ext"  
  
 `nPort`#port ==  
  
 `dwServiceType`#service ==  
  
> [!NOTE]
>  Bu işlevi çağırmak için projenizi AFXINET eklemeniz gerekir. H.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxinet.h  
  
##  <a name="afxparseurlex"></a>AfxParseURLEx  
 Bu genel işlevi, genişletilmiş sürümüdür [AfxParseURL](#afxparseurl) ve kullanılan [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
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
 *pstrURL*  
 Ayrıştırılacak URL'sini içeren bir dize için bir işaretçi.  
  
 `dwServiceType`  
 Internet hizmet türünü belirtir. Olası değerler aşağıdaki gibidir:  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Hizmet türü aşağıdaki URL ilk kesimi.  
  
 `strObject`  
 URL başvurduğu bir nesne (boş olabilir).  
  
 `nPort`  
 Ya da varsa sunucu veya nesne URL bölümlerinden belirledi.  
  
 *strUsername*  
 Bir başvuru bir `CString` kullanıcı adını içeren bir nesne.  
  
 `strPassword`  
 Bir başvuru bir `CString` kullanıcının parolasını içeren bir nesne.  
  
 `dwFlags`  
 URL ayrıştırmayı denetleme bayraklar. Aşağıdaki değerlerden bir bileşimi olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|**ICU_DECODE**|% XX kaçış sıraları karakterlerine dönüştürmek.|  
|**ICU_NO_ENCODE**|Çıkış sırası için güvenli olmayan karakterler dönüştürmez.|  
|**ICU_NO_META**|Meta dizilerini (örneğin, "\" kaldırma ve "\..") URL.|  
|**ICU_ENCODE_SPACES_ONLY**|Yalnızca boşluk kodlayın.|  
|**ICU_BROWSER_MODE**|Etmeyin kodlamak veya karakter kod çözme '# 'karakterinden sonra veya '' ve sonunda boşluk sonra kaldırmayın ''. Bu değer belirtilmezse, tüm URL kodlanmış ve sonunda boşluk kaldırılır.|  
  
 Hiçbir bayrakları MFC varsayılan kullanırsanız, tüm güvenli olmayan karakter ve meta sıraları işlevi dönüştürür (gibi \\., \.., ve \\...) kaçınmak için serileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 URL başarıyla ayrıştırıldığında, sıfır olmayan; Aksi takdirde, 0 boşsa veya bilinen Internet hizmet türü içermiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 URL dizesi ayrıştırır ve hizmet ve bileşenlerinin yanı kullanıcının adı ve parola sağlama türünü döndürür. Bayrakları nasıl güvenli olmayan karakterleri belirtmek işlenir.  
  
> [!NOTE]
>  Bu işlevi çağırmak için projenizi AFXINET eklemeniz gerekir. H.  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxinet.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
 
## <a name="afxgetinternethandletype"></a>Afxgetınternethandletype
Bu genel işlevi, bir Internet tanıtıcısı türünü belirlemek için kullanın.  
   
### <a name="syntax"></a>Sözdizimi  
  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );  
```
### <a name="parameters"></a>Parametreler  
 `hQuery`  
 Bir Internet sorgu için bir tanıtıcı.  
   
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir WİNINET tarafından tanımlanan Internet hizmet türü. H. Internet hizmetlerin listesini için Açıklamalar bölümüne bakın. Tanıtıcı NULL ya da tanınmayan ise işlevi AFX_INET_SERVICE_UNK döndürür.  
   
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki liste, olası Internet türleri tarafından döndürülen içermektedir `AfxGetInternetHandleType`.  
  
-   INTERNET_HANDLE_TYPE_INTERNET  
  
-   INTERNET_HANDLE_TYPE_CONNECT_FTP  
  
-   INTERNET_HANDLE_TYPE_CONNECT_GOPHER  
  
-   INTERNET_HANDLE_TYPE_CONNECT_HTTP  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_HTTP_REQUEST  
  
> [!NOTE]
>  Bu işlevi çağırmak için projenize AFXINET eklemeniz gerekir. H.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
 
## <a name="afxthrowinternetexception"></a>Afxthrowınternetexception
Bir Internet özel durum oluşturur.  
   
### <a name="syntax"></a>Sözdizimi    
```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );  
```
### <a name="parameters"></a>Parametreler  
 `dwContext`  
 Hatanın nedeni işlemi bağlam tanımlayıcısı. Varsayılan değer olan `dwContext` başlangıçta belirtilen [CInternetSession](cinternetsession-class.md) ve geçirilir [CInternetConnection](cinternetconnection-class.md)- ve [CInternetFile](cinternetfile-class.md)-türetilmiş sınıfları. Bir bağlantı veya bir dosya üzerinde gerçekleştirilen belirli işlemler için genellikle varsayılan geçersiz kılma bir `dwContext` kendi. Bu değer daha sonra döndürülen [CInternetSession::OnStatusCallback](cinternetsession-class.md#onstatuscallback) belirli işlemin durumunu belirlemek için. 
  
 `dwError`  
 Özel duruma neden hata.  
   
### <a name="remarks"></a>Açıklamalar  
 İşletim sistemi hata koduna göre nedenini belirlemek için sorumlu.  
  
> [!NOTE]
>  Bu işlevi çağırmak için projenizi AFXINET eklemeniz gerekir. H.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [CInternetException sınıfı](cinternetexception-class.md)   
 [THROW](#throw)
 

