---
title: CHttpConnection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
dev_langs:
- C++
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03e773e57b4cdaee09331dab651f41f1fa8db211
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336068"
---
# <a name="chttpconnection-class"></a>CHttpConnection sınıfı
HTTP sunucusuyla olan bağlantınızı yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHttpConnection::CHttpConnection](#chttpconnection)|Oluşturur bir `CHttpConnection` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHttpConnection::OpenRequest](#openrequest)|Bir HTTP isteği açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 HTTP MFC WinINet sınıfları tarafından uygulanan üç Internet sunucusu protokolden biridir.  
  
 Sınıf `CHttpConnection` bir oluşturucu ve bir üye işlevi içeren [OpenRequest](#openrequest), bir HTTP protokolü ile sunucu bağlantıları yönetir.  
  
 Bir HTTP sunucusu ile iletişim kurmak için öncelikle bir örneğini oluşturmanız gerekir [Cınternetsession](../../mfc/reference/cinternetsession-class.md)ve ardından bir [CHttpConnection](#_mfc_chttpconnection) nesne. Asla oluşturma bir `CHttpConnection` doğrudan nesne; bunun yerine, çağırarak [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), oluşturan `CHttpConnection` nesnesi ve bir işaretçi döndürür.  
  
 Hakkında daha fazla bilgi edinmek için `CHttpConnection` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md). Diğer iki kullanarak sunuculara bağlanma hakkında daha fazla bilgi desteklenen Internet protokolleri, gopher ve FTP için bkz: sınıfları [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="chttpconnection"></a>  CHttpConnection::CHttpConnection  
 Bu üye işlevi oluşturmak için çağrılan bir `CHttpConnection` nesne.  
  
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
 *pSession*  
 Bir işaretçi bir [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne.  
  
 *hConnected*  
 Internet bağlantısı için bir tanıtıcı.  
  
 *pstrServer*  
 Sunucu adını içeren bir dize işaretçisi.  
  
 *dwContext*  
 İçerik tanımlayıcısı `CInternetConnection` nesne. Bkz: **açıklamalar** hakkında daha fazla bilgi için *dwContext*.  
  
 *nbağlantı noktası*  
 Bu bağlantı için Internet bağlantı noktasını tanımlayan numara.  
  
 *pstrUserName*  
 Oturum açmak için kullanıcı adını belirten bir null ile sonlandırılmış dize işaretçisi. NULL ise, anonim bir varsayılandır.  
  
 *pstrPassword*  
 Oturum açmak için kullanılacak parolayı belirten bir boş sonlandırılmış dizeye bir işaretçi. Her iki *pstrPassword* ve *pstrUserName* NULL, varsayılan anonim kullanıcı e-posta adını paroladır. Varsa *pstrPassword* boş (veya boş bir dize) ancak *pstrUserName* NULL değil boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklar *pstrUserName* ve *pstrPassword*:  
  
|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|NULL veya ""|NULL veya ""|"anonim"|Kullanıcının e-posta adı|  
|BOŞ olmayan bir dize|NULL veya ""|*pstrUserName*|" "|  
|BOŞ bir NULL olmayan dize|HATA|HATA||  
|BOŞ olmayan bir dize|BOŞ olmayan bir dize|*pstrUserName*|*pstrPassword*|  
  
 *CertOpenStore*  
 Herhangi bir birleşimini **INTERNET_ FLAG_\***  bayrakları. Bölümündeki tabloya bakın **açıklamalar** bölümünü [CHttpConnection::OpenRequest](#openrequest) açıklamasını *CertOpenStore* değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Asla oluşturma bir `CHttpConnection` doğrudan. Bunun yerine, çağırarak bir nesne oluşturma [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).  
  
##  <a name="openrequest"></a>  CHttpConnection::OpenRequest  
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
 *pstrVerb*  
 İstekte kullanmak için fiili içeren bir dize işaretçisi. NULL ise, "Al" kullanılır.  
  
 *pstrObjectName*  
 Belirtilen fiili hedef nesneye içeren bir dize işaretçisi. Bu, genellikle bir dosya adı, bir çalıştırılabilir modüle veya bir arama tanımlayıcısı.  
  
 *pstrReferer*  
 ' % S'adresi (URL) belge belirten bir dize işaretçisi istek URL'SİNDE ( *pstrObjectName*) alınamadı. NULL ise, hiçbir HTTP üst bilgisi belirtildi.  
  
 *dwContext*  
 İçerik tanımlayıcısı `OpenRequest` işlemi. Hakkında daha fazla bilgi için Açıklamalar bölümüne bakın *dwContext*.  
  
 *ppstrAcceptTypes*  
 İstemci tarafından kabul edilen içerik türleri gösteren dizelerin LPCTSTR işaretçileri null ile sonlandırılmış bir dizi için bir işaretçi. Varsa *ppstrAcceptTypes* NULL ise istemci yalnızca tür belge kabul ettiğinden sunucuları yorumlama "metin / *" (diğer bir deyişle, yalnızca metin belgeleri ve resimleri veya diğer ikili dosyalar). İçerik türü, HTTP POST ve PUT gibi bilgileri ekli sorgular için verilerin türünü tanımlar CGI değişken CONTENT_TYPE eşdeğerdir.  
  
 *pstrVersion*  
 HTTP sürümünü tanımlayan bir dize işaretçisi. NULL ise, "HTTP/1.0" kullanılır.  
  
 *CertOpenStore*  
 Herhangi bir birleşimini INTERNET_ FLAG_ * bayrakları. Olası bir açıklaması için Açıklamalar bölümüne bakın *CertOpenStore* değerleri.  
  
 *nVerb*  
 HTTP isteği türüyle ilişkili bir sayı. Aşağıdakilerden biri olabilir:  
  
|HTTP istek türü|*nVerb* değeri|  
|-----------------------|-------------------|  
|HTTP_VERB_POST|0|  
|HTTP_VERB_GET|1.|  
|HTTP_VERB_HEAD|2|  
|HTTP_VERB_PUT|3|  
|HTTP_VERB_LINK|4|  
|HTTP_VERB_DELETE|5|  
|HTTP_VERB_UNLINK|6|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CHttpFile](../../mfc/reference/chttpfile-class.md) istenen nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 *CertOpenStore* aşağıdakilerden biri olabilir:  
  
|Internet bayrağı|Açıklama|  
|-------------------|-----------------|  
|INTERNET_FLAG_RELOAD|İstenen dosya, nesne veya dizin listeleme, indirme, kaynak sunucu, önbellekten zorlar.|  
|INTERNET_FLAG_DONT_CACHE|Döndürülen varlığı için önbelleği eklemez.|  
|INTERNET_FLAG_MAKE_PERSISTENT|Döndürülen varlığı kalıcı bir varlık olarak önbelleğe ekler. Başka bir deyişle, standart önbellek temizleme, tutarlılık denetimi veya çöp toplama bu öğeyi önbellekten kaldırılamıyor.|  
|INTERNET_FLAG_SECURE|Güvenli işlem semantiği kullanır. Bu SSL/PCT kullanmaya çevirir ve yalnızca HTTP isteklerini anlamlı|  
|INTERNET_FLAG_NO_AUTO_REDIRECT|Yalnızca HTTP ile kullanılan, yeniden yönlendirmelerini otomatik olarak içinde işlenmesi gereken değil, belirtir [CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|  
  
 Geçersiz kılma `dwContext` varsayılan bağlamı tanımlayıcısını bir değere ayarlamak için. Bu belirli işlemle ilişkili bağlam tanımlayıcıdır `CHttpConnection` tarafından oluşturulan nesne kendi [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile belirtilen işlem durumu sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.  
  
 Bu işlev ile özel durumlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cınternetconnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Cınternetconnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
