---
title: "COleDocObjectItem sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
dev_langs: C++
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 246c645dad5ed11fb5428e2f90ed9b9574696417
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coledocobjectitem-class"></a>COleDocObjectItem sınıfı
Etkin belge kapsaması uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Oluşturan bir `COleDocObject` öğesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Varsayılan yazıcı ayarlarını kullanarak kapsayıcı uygulamanın belgeyi yazdırır.|  
|[COleDocObjectItem::ExecCommand](#execcommand)|Kullanıcı tarafından belirtilen komut yürütür.|  
|[COleDocObjectItem::GetActiveView](#getactiveview)|Belgenin etkin görünüm alır.|  
|[COleDocObjectItem::GetPageCount](#getpagecount)|Kapsayıcı uygulamanın belgedeki sayfaların sayısını alır.|  
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Kapsayıcı uygulamanın belge yazdırma için hazırlar.|  
|[COleDocObjectItem::OnPrint](#onprint)|Kapsayıcı uygulamanın belgeyi yazdırır.|  
|[COleDocObjectItem::QueryCommand](#querycommand)|Kullanıcı arabirimi olaylar tarafından oluşturulan bir veya daha fazla komut durumunu sorgular.|  
|[COleDocObjectItem::Release](#release)|Öğesi bağlı bir OLE bağlantısı serbest bırakır ve açık olması durumunda kapatır. İstemci öğesi yok.|  
  
## <a name="remarks"></a>Açıklamalar  
 MFC içinde bir normal, yerinde düzenlenebilir, aşağıdaki farklarla katıştırmak için etkin bir belge bir benzer şekilde ele alınır:  
  
-   `COleDocument`-Türetilmiş sınıf hala şu anda katıştırılmış öğeleri listesini tutar; ancak, bu öğeler olabilir `COleDocObjectItem`-türetilen öğelerinin.  
  
-   Etkin belge etkin olduğunda, yerinde etkin olduğunda görünümün tüm istemci alanı kaplar.  
  
-   Etkin belge kapsayıcısı üzerinde tam denetime sahip **yardımcı** menüsü.  
  
-   **Yardımcı** menüsü etkin belge kapsayıcısı ve sunucu için menü öğelerini içerir.  
  
 Etkin belge kapsayıcı sahibi olduğundan **yardımcı** menüsünde kapsayıcıdır sunucu iletmek için sorumlu **yardımcı** sunucuya menü iletileri. Bu tümleştirme tarafından işlenen `COleDocObjectItem`.  
  
 Menü birleştirme ve etkin belgeyi etkinleştirme hakkında daha fazla bilgi için genel bakış [etkin belge kapsaması](../../mfc/active-document-containment.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="coledocobjectitem"></a>COleDocObjectItem::COleDocObjectItem  
 Başlatmak için bu üye işlevini çağırın `COleDocObjectItem` nesnesi.  
  
```  
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pContainerDoc`  
 Bir işaretçi `COleDocument` etkin belge kapsayıcı olarak hareket nesnesi. Bu parametre olmalıdır **NULL** etkinleştirmek için **IMPLEMENT_SERIALIZE**. Normalde OLE öğeleri olmayan bir ile oluşturulan **NULL** belge işaretçi.  
  
##  <a name="dodefaultprinting"></a>COleDocObjectItem::DoDefaultPrinting  
 Varsayılan ayarları kullanarak bir belgeyi çerçevesi tarafından çağrılır.  
  
```  
static HRESULT DoDefaultPrinting(
    CView* pCaller,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCaller`  
 Bir işaretçi bir [CView](../../mfc/reference/cview-class.md) yazdırma komut gönderilirken nesnesi.  
  
 `pInfo`  
 Bir işaretçi bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) yazdırılmasını işini tanımlayan nesne.  
  
##  <a name="execcommand"></a>COleDocObjectItem::ExecCommand  
 Kullanıcı tarafından belirtilen komut yürütmek için bu üye işlevini çağırın.  
  
```  
HRESULT ExecCommand(
    DWORD nCmdID,  
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,  
    const GUID* pguidCmdGroup = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCmdID`  
 Komutun yürütülmesi için tanımlayıcı. Tarafından tanımlanan grubunda olmalıdır `pguidCmdGroup`.  
  
 `nCmdExecOpt`  
 Komut yürütme seçeneklerini belirtir. Kullanıcıya sormadan komutu yürütmek için varsayılan olarak ayarlayın. Bkz: [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) değerleri listesi.  
  
 `pguidCmdGroup`  
 Komut grubunun benzersiz tanımlayıcısı. Varsayılan olarak, **NULL**, standart grubun belirtir. Komut geçirilen `nCmdID` grubuna ait olmalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarılıysa; Aksi takdirde, aşağıdaki hata kodlarını döndürür.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Beklenmeyen bir hata oluştu.|  
|**E_FAIL**|Bir hata oluştu.|  
|**E_NOTIMPL**|MFC gösterir kendisini çevirin ve komut gönderme denemelisiniz.|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`olmayan olan **NULL** ancak tanınan komut grubu belirtmiyor.|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`Grup pGroup geçerli bir komut olarak tanınmıyor.|  
|**OLECMDERR_DISABLED**|Tarafından tanımlanan komutu `nCmdID` devre dışı bırakılır ve yürütülemez.|  
|**OLECMDERR_NOHELP**|Çağıran tarafından tanımlanan komutu hakkında Yardım için sorulan `nCmdID` ancak Yardım yok.|  
|**OLECMDERR_CANCELLED**|Kullanıcı yürütme iptal edildi.|  
  
### <a name="remarks"></a>Açıklamalar  
 `pguidCmdGroup` Ve `nCmdID` parametreleri birlikte çağrılacak komutu benzersiz şekilde tanımlar. `nCmdExecOpt` Parametresi, tam gerçekleştirilecek eylemi belirtir.  
  
##  <a name="getactiveview"></a>COleDocObjectItem::GetActiveView  
 Bir işaretçi almak için bu üye işlevini çağırın `IOleDocumentView` şu anda etkin görünümün arabirimi.  
  
```  
LPOLEDOCUMENTVIEW GetActiveView() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [IOleDocumentView](http://msdn.microsoft.com/library/windows/desktop/ms678455) şu anda etkin görünümün arabirimi. Geçerli Görünüm varsa yok, döndürür **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen başvuru sayısına `IOleDocumentView` işaretçi bu işlev tarafından döndürülen önce değil artar.  
  
##  <a name="getpagecount"></a>COleDocObjectItem::GetPageCount  
 Belgedeki sayfa sayısı almak için bu üye işlevini çağırın.  
  
```  
BOOL GetPageCount(
    LPLONG pnFirstPage,  
    LPLONG pcPages);
```  
  
### <a name="parameters"></a>Parametreler  
 *pnFirstPage*  
 Belgenin ilk sayfa sayısını gösteren bir işaretçi. Olabilir **NULL**, çağıranın belirttiği bu numarayı gerek yoktur.  
  
 *pcPages*  
 Belgedeki sayfaları toplam sayısı için bir işaretçi. Olabilir **NULL**, çağıranın belirttiği bu numarayı gerek yoktur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="onprepareprinting"></a>COleDocObjectItem::OnPreparePrinting  
 Bu üye işlevi, bir belge yazdırma için hazırlamak üzere çerçevesi tarafından çağrılır.  
  
```  
static BOOL OnPreparePrinting(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCaller`  
 Bir işaretçi bir [CView](../../mfc/reference/cview-class.md) yazdırma komut gönderilirken nesnesi.  
  
 `pInfo`  
 Bir işaretçi bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) yazdırılmasını işini tanımlayan nesne.  
  
 `bPrintAll`  
 Tüm belgeyi yazdırılması olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="onprint"></a>COleDocObjectItem::OnPrint  
 Bu üye işlevi bir belgeyi yazdır çerçevesi tarafından çağrılır.  
  
```  
static void OnPrint(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCaller`  
 Yazdırma komut gönderilirken bir CView nesnesi için bir işaretçi.  
  
 `pInfo`  
 Bir işaretçi bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) yazdırılmasını işini tanımlayan nesne.  
  
 `bPrintAll`  
 Tüm belgeyi yazdırılması olup olmadığını belirtir.  
  
##  <a name="querycommand"></a>COleDocObjectItem::QueryCommand  
 Kullanıcı arabirimi olaylar tarafından oluşturulan bir veya daha fazla komut durumunu sorgular.  
  
```  
HRESULT QueryCommand(
    ULONG nCmdID,  
    DWORD* pdwStatus,  
    OLECMDTEXT* pCmdText =NULL,  
    const GUID* pguidCmdGroup =NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCmdID`  
 için sorgulanan komut tanımlayıcısı.  
  
 `pdwStatus`  
 Sorgu sonucu olarak döndürülen bayrakları gösteren bir işaretçi. Olası değerler listesi için bkz: [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237).  
  
 `pCmdText`  
 İşaretçi bir [OLECMDTEXT](http://msdn.microsoft.com/library/windows/desktop/ms693314) yapısı, tek bir komut adı ve durum bilgilerini dönün. Olabilir **NULL** arayan bu bilgilere ihtiyacınız olmayan belirtmek için.  
  
 `pguidCmdGroup`  
 Komut grubu benzersiz tanıtıcısı; olabilir **NULL** standart grubun belirtmek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değerleri tam listesi için bkz: [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) Windows SDK'ın açıklandığı gibi yöntemi.  
  
##  <a name="release"></a>COleDocObjectItem::Release  
 Öğesi bağlı bir OLE bağlantısı serbest bırakır ve açık olması durumunda kapatır. İstemci öğesi yok.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCloseOption`  
 Yüklenen durumuna geri döndüğünde hangi koşullar altında OLE öğesi kaydedildiğinde belirten bayrak. Olası değerler listesi için bkz: [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).  
  
### <a name="remarks"></a>Açıklamalar  
 İstemci öğesi yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MFCBIND](../../visual-cpp-samples.md)   
 [COleClientItem sınıfı](../../mfc/reference/coleclientitem-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleClientItem sınıfı](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem Sınıfı](../../mfc/reference/cdocobjectserveritem-class.md)
