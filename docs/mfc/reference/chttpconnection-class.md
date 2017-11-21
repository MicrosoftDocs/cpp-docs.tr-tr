---
title: "CHttpConnection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
dev_langs: C++
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea35172c527d1dad62f2f565bf7cf2e25001323b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="chttpconnection-class"></a>CHttpConnection sınıfı
Bir HTTP sunucusuna bağlantınız yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHttpConnection::CHttpConnection](#chttpconnection)|Oluşturur bir `CHttpConnection` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHttpConnection::OpenRequest](#openrequest)|Bir HTTP isteği açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 HTTP MFC WinINet sınıfları tarafından uygulanan üç Internet sunucu protokolleri biridir.  
  
 Sınıf `CHttpConnection` oluşturucu ve bir üye fonksiyonu içeriyor [OpenRequest](#openrequest), sunucuya bir HTTP protokolü ile bağlantıları yönetir.  
  
 Bir HTTP sunucusu ile iletişim kurmak için önce bir örneğini oluşturmanız gerekir [CInternetSession](../../mfc/reference/cinternetsession-class.md)ve ardından oluşturun bir [CHttpConnection](#_mfc_chttpconnection) nesnesi. Hiçbir zaman oluşturduğunuz bir `CHttpConnection` doğrudan nesne; bunun yerine, çağrı [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), oluşturan `CHttpConnection` nesne ve bir işaretçi döndürür.  
  
 Hakkında daha fazla bilgi için `CHttpConnection` diğer MFC Internet sınıfları ile works başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md). Desteklenen Internet protokolleri, gopher ve FTP diğer iki kullanarak sunucuya bağlanma hakkında daha fazla bilgi için bkz: sınıflarını [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="chttpconnection"></a>CHttpConnection::CHttpConnection  
 Bu üye işlevi oluşturmak için çağrılan bir `CHttpConnection` nesnesi.  
  
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
 `pSession`  
 Bir işaretçi bir [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi.  
  
 `hConnected`  
 Internet bağlantısı için bir tanıtıcı.  
  
 `pstrServer`  
 Sunucu adını içeren bir dize için bir işaretçi.  
  
 `dwContext`  
 İçerik tanımlayıcısını `CInternetConnection` nesnesi. Bkz: **açıklamalar** hakkında daha fazla bilgi için `dwContext`.  
  
 `nPort`  
 Bu bağlantı için Internet bağlantı noktasını tanımlar sayı.  
  
 `pstrUserName`  
 İşaretçi null ile sonlandırılmış dizeye oturum açmak için kullanıcı adını belirtir. Varsa **NULL**, anonim varsayılandır.  
  
 `pstrPassword`  
 Oturum açmak için kullanılacak parolayı belirten null ile sonlandırılmış bir dize için bir işaretçi. Her iki `pstrPassword` ve `pstrUserName` olan **NULL**, varsayılan anonim parola kullanıcının e-posta adıdır. Varsa `pstrPassword` olan **NULL** (veya boş bir dize) ancak `pstrUserName` değil **NULL**, boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklanmaktadır `pstrUserName` ve `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** veya ""|**NULL** veya ""|"anonim"|Kullanıcının e-posta adı|  
|Olmayan- **NULL** dize|**NULL** veya ""|`pstrUserName`|" "|  
|**NULL** olmayan **NULL** dize|**HATA**|**HATA**||  
|Olmayan- **NULL** dize|Olmayan- **NULL** dize|`pstrUserName`|`pstrPassword`|  
  
 `dwFlags`  
 Herhangi bir bileşimini **INTERNET_ FLAG_\***  bayrakları. Bölümündeki tabloya bakın **açıklamalar** bölümünü [CHttpConnection::OpenRequest](#openrequest) bir açıklaması için `dwFlags` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman oluşturduğunuz bir `CHttpConnection` doğrudan. Bunun yerine, çağırarak bir nesne oluşturma [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).  
  
##  <a name="openrequest"></a>CHttpConnection::OpenRequest  
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
 `pstrVerb`  
 İstekte kullanmak için fiili içeren bir dize için bir işaretçi. Varsa `NULL`, "GET" kullanılır.  
  
 `pstrObjectName`  
 Belirtilen fiil hedef nesnesi içeren bir dize için bir işaretçi. Bu genellikle bir dosya adı yürütülebilir bir modül veya arama belirleyici içindir.  
  
 `pstrReferer`  
 Belgeden adresi (URL) belirten bir dize için bir işaretçi istek URL'SİNDE ( `pstrObjectName`) alınamadı. Varsa `NULL`, bir HTTP üstbilgisi belirtilir.  
  
 `dwContext`  
 İçerik tanımlayıcısını `OpenRequest` işlemi. Daha fazla bilgi için Açıklamalar bölümüne bakın `dwContext`.  
  
 `ppstrAcceptTypes`  
 Sonlandırılmış bir dizi için bir işaretçi `LPCTSTR` içerik türlerini gösteren dizelerin işaretçiler istemci tarafından kabul edildi. Varsa `ppstrAcceptTypes` olan `NULL`, sunucuların istemci türüne belgelerinin yalnızca kabul eder yorumlama "metin / *" (diğer bir deyişle, yalnızca metin belgeleri ve resimleri veya diğer ikili dosyaları). İçerik türü, HTTP POST ve PUT gibi bilgileri bağlı sorguları için veri türünü tanımlayan CGI değişken CONTENT_TYPE eşdeğerdir.  
  
 `pstrVersion`  
 HTTP sürümü tanımlayan bir dize için bir işaretçi. Varsa `NULL`, "HTTP/1.0" kullanılır.  
  
 `dwFlags`  
 INTERNET_ FLAG_ * bayrakları herhangi bir bileşimini. Olası bir açıklaması için Açıklamalar bölümüne bakın `dwFlags` değerleri.  
  
 `nVerb`  
 HTTP isteği türüyle ilişkili bir sayı. Aşağıdakilerden biri olabilir:  
  
|HTTP istek türü|`nVerb`değer|  
|-----------------------|-------------------|  
|`HTTP_VERB_POST`|0|  
|`HTTP_VERB_GET`|1.|  
|`HTTP_VERB_HEAD`|2|  
|`HTTP_VERB_PUT`|3|  
|`HTTP_VERB_LINK`|4|  
|`HTTP_VERB_DELETE`|5|  
|`HTTP_VERB_UNLINK`|6|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CHttpFile](../../mfc/reference/chttpfile-class.md) istenen nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `dwFlags`aşağıdakilerden biri olabilir:  
  
|Internet bayrağı|Açıklama|  
|-------------------|-----------------|  
|`INTERNET_FLAG_RELOAD`|İstenen dosya, nesne veya dizin listeleme indirme kaynak sunucudan, önbelleğinden zorlar.|  
|`INTERNET_FLAG_DONT_CACHE`|Döndürülen varlığı için önbelleği eklemez.|  
|`INTERNET_FLAG_MAKE_PERSISTENT`|Döndürülen varlığı kalıcı bir varlık olarak önbelleğe ekler. Bu, standart önbelleği temizleme, tutarlılık denetimi veya çöp toplama bu öğeyi önbellekten kaldıramazsınız anlamına gelir.|  
|`INTERNET_FLAG_SECURE`|Güvenli işlem semantiğini kullanır. Bu SSL/PCT kullanmaya dönüşür ve yalnızca HTTP isteklerinde anlamlıdır|  
|`INTERNET_FLAG_NO_AUTO_REDIRECT`|Yalnızca HTTP ile kullanılan, yeniden yönlendirme otomatik olarak işleneceğini değil belirtir [CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|  
  
 Geçersiz kılma `dwContext` varsayılan bağlam tanımlayıcı bir değerine ayarlayın. Bağlam tanıtıcısı belirli bu işlemle ilişkili `CHttpConnection` tarafından oluşturulan nesne kendi [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen işlem durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
 Bu işlev ile durumlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile sınıfı](../../mfc/reference/chttpfile-class.md)
