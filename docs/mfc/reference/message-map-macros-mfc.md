---
title: "İleti eşleme makroları (MFC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXWIN/DECLARE_MESSAGE_MAP
- AFXWIN/BEGIN_MESSAGE_MAP
- AFXWIN/BEGIN_TEMPLATE_MESSAGE_MAP
- AFXWIN/END_MESSAGE_MAP
- AFXWIN/ON_COMMAND
- AFXWIN/ON_COMMAND_EX
- AFXWIN/ON_CONTROL
- AFXWIN/ON_MESSAGE
- AFXWIN/ON_OLECMD
- AFXWIN/ON_REGISTERED_MESSAGE
- AFXWIN/ON_REGISTERED_THREAD_MESSAGE
- AFXWIN/ON_THREAD_MESSAGE
- AFXWIN/ON_UPDATE_COMMAND_UI
- AFXWIN/ON_COMMAND_RANGE
- AFXWIN/ON_UPDATE_COMMAND_UI_RANGE
- AFXWIN/ON_CONTROL_RANGE
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [MFC], declaration
- demarcating Windows messages
- message maps [MFC], macros
- message maps [MFC], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7bf56b243118ceb7fdd995fc6970f6c49e0a5499
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="message-map-macros-mfc"></a>İleti Eşleme Makroları (MFC)
İleti eşlemeleri desteklemek için aşağıdaki makroları MFC sağlar:  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>İleti eşleme bildirim ve düzenleme makroları  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|İleti eşlemesi bir sınıfta (sınıfı bildiriminde kullanılmalıdır) işlevleri için ileti eşlemesi için kullanılacak bildirir.|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|(Sınıfı uygulamasında kullanılmalıdır) ileti eşlemesi tanımını başlar.|  
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_interface_map)|İleti eşlemesi tek şablon bağımsız değişken içeren bir sınıf türünün tanımı başlar. |
|[END_MESSAGE_MAP](#end_message_map)|(Sınıfı uygulamasında kullanılmalıdır) ileti eşlemesi tanımını sona erer.|  
  
### <a name="message-mapping-macros"></a>İleti eşleme makroları  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|Hangi işlevi belirtilen komut iletisi işleyeceğini gösterir.|  
|[ON_COMMAND_EX](#on_command_ex)|Hangi işlevi belirtilen komut iletisi işleyeceğini gösterir.|  
|[ON_CONTROL](#on_control)|Hangi işlev belirtilen denetim bildirim iletisi işleyeceğini gösterir.|  
|[ON_MESSAGE](#on_message)|Hangi işlevi bir kullanıcı tarafından tanımlanan ileti işleyeceğini gösterir.|  
|[ON_OLECMD](#on_olecmd)|Hangi işlev DocObject veya kapsayıcısı bir menü komutu işleyeceğini gösterir.|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Hangi işlev kayıtlı bir kullanıcı tarafından tanımlanan ileti işleyeceğini gösterir.|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Varsa, hangi işlevi kayıtlı bir kullanıcı tarafından tanımlanan ileti işleyecek gösteren bir `CWinThread` sınıfı.|  
|[ON_THREAD_MESSAGE](#on_thread_message)|Varsa, hangi işlevi bir kullanıcı tarafından tanımlanan ileti işleyecek gösteren bir `CWinThread` sınıfı.|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Hangi işlev belirtilen kullanıcı arabirimi güncelleştirme komut iletisi işleyeceğini gösterir.|  
  
### <a name="message-map-range-macros"></a>İleti eşleme aralığı makroları  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](#on_command_range)|Hangi işlev makrosu için ilk iki parametrelerinde belirtilen komut kimlikleri aralığını işleyecek gösterir.|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Hangi güncelleştirme işleyicisi ilk iki pa belirtilen komut kimlikleri aralığını işleyeceğini belirtir] makrosu için parametreler.|  
|[ON_CONTROL_RANGE](#on_control_range)|Hangi işlev bildirimleri denetim makrosu için ikinci ve üçüncü parametrelerinde belirtilen kimliklerini aralıktan işleyeceğini gösterir. İlk parametre denetimi bildirim iletisi, olduğu gibi **BN_CLICKED**.|  
  
 İleti eşlemeleri, ileti eşleme bildirim ve düzenleme makroları ve ileti eşleme makroları hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../mfc/reference/message-maps-mfc.md) ve [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md). İleti eşleme aralıkları hakkında daha fazla bilgi için bkz: [ileti eşleme aralıkları için işleyiciler](../../mfc/handlers-for-message-map-ranges.md).  


## <a name="begin_message_map"></a>BEGIN_MESSAGE_MAP
İleti eşlemesi tanımını başlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu harita, ileti sınıfın adını belirtir.  
  
 `baseClass`  
 Temel sınıfını adını belirtir `theClass`.  
  
### <a name="remarks"></a>Açıklamalar  
 İleti eşlemesi ile sınıfınız için üye işlevleri tanımlar uygulaması (.cpp) dosyasına Başlat `BEGIN_MESSAGE_MAP` makrosu, ardından her ileti işleyicisi işlevlerinizi için makrosu girişleri ekleyin ve ileti eşlemesi ile tamamlamak `END_MESSAGE_MAP` makrosu.  
  
 İleti eşlemeleri hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](message-maps-mfc.md)  
  
### <a name="example"></a>Örnek  
```cpp  
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h 

##  <a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP
İleti eşlemesi tek şablon bağımsız değişken içeren bir sınıf türünün tanımı başlar.  
   
### <a name="syntax"></a>Sözdizimi  
  ```
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )  
```
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Bu harita, ileti sınıfın adını belirtir.    
 `type_name`  
 Sınıfı için belirtilen şablon parametresinin adı.    
 `baseClass`  
 Temel sınıfını adını belirtir `theClass`.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu benzer [begın_message_map](message-map-macros-mfc.md#begin_message_map) makrosu; ancak, bu makrosu tek şablon bağımsız değişken içeren sınıflar için tasarlanmıştır.  
  
 İleti eşlemesi ile sınıfınızın yöntemi uygulama bölümünde Başlat **BEGIN_TEMPLATE_MESSAGE_MAP** makrosu; standart ileti eşlemesi için olduğu gibi ardından makrosu girişleri her ileti işleyicisi yöntemlerinizi ekleyin. İle **begın_message_map** makrosu, şablon ileti eşlemesi ile tamamlamak [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) makrosu.  
  
 İleti eşlemeleri şablon sınıfları için uygulama ile ilgili daha fazla bilgi için başvurmak [nasıl yapılır: bir şablon sınıfı için ileti eşlemesi oluşturma](../how-to-create-a-message-map-for-a-template-class.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
 
## <a name="declare_message_map"></a>DECLARE_MESSAGE_MAP
 Sınıfı ileti eşlemesi tanımlar bildirir. Her `CCmdTarget`-programınızı türetilen sınıfta iletileri işlemek için ileti eşlemesi sağlamalıdır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `DECLARE_MESSAGE_MAP` makrosu sınıf bildiriminin sonundaki. Ardından, sınıf için üye işlevleri tanımlayan .cpp dosyasında kullanmak `BEGIN_MESSAGE_MAP` makrosu, her ileti işleyicisi işlevlerinizi makrosu girişleri ve `END_MESSAGE_MAP` makrosu.  
  
> [!NOTE]
>  Sonra herhangi bir üyenin bildirirseniz `DECLARE_MESSAGE_MAP`, yeni bir erişim türü belirtmeniz gerekir (**ortak**, `private`, veya `protected`) onlar için.  
  
 İleti hakkında daha fazla bilgi için eşler ve `DECLARE_MESSAGE_MAP` makrosu, bkz: [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Örnek  
```cpp  
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
``` 
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  


## <a name="end_message_map"></a>END_MESSAGE_MAP
İleti eşlemesi tanımını sona erer.  
  
### <a name="syntax"></a>Sözdizimi  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İleti hakkında daha fazla bilgi için eşler ve `END_MESSAGE_MAP` makrosu, bkz: [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  

## <a name="on_command"></a>ON_COMMAND
Bu makrosu üye işlevi için bir komut iletisi eşler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 Komut kimliği.  
  
 `memberFxn`  
 Komut eşlenmiş ileti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Hangi işlevi bir komut iletisi menü öğesi veya araç çubuğu düğmesi gibi komut bir kullanıcı arabirimi nesnesinden işleyeceğini belirtir.  
  
 Ne zaman bir komut hedefi nesnesi alır Windows **WM_COMMAND** belirtilen Kimliğe sahip ileti `ON_COMMAND` üye fonksiyonu çağıracak `memberFxn` iletiyi işlemek için.  
  
 Kullanım `ON_COMMAND` üye işlevi için tek bir komut eşlemek için. Kullanım [ON_COMMAND_RANGE](#on_command_range) bir üye işlevine bir dizi komut kimlikleri eşlemek için. Yalnızca bir ileti eşleme girişi verilen komut kimliği eşleştirebilirsiniz. Diğer bir deyişle, birden fazla işleyici için bir komut eşlenemiyor. Daha fazla bilgi ve örnekler için bkz: [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Örnek  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  

 ## <a name="on_command_ex"></a>ON_COMMAND_EX
Komut işleyici üye işlevi genişletilmiş.  
   
### <a name="syntax"></a>Sözdizimi  
  ```  
ON_COMMAND_EX(id, memberFxn);  
```
### <a name="parameters"></a>Parametreler  
 `id`  
 Komut kimliği.  
  
 `memberFxn`  
 Komut eşlenmiş ileti işleyicisi işlevin adı.  
   
### <a name="remarks"></a>Açıklamalar 
Bir genişletilmiş komutu ileti işleyicileri İleri düzey kullanıcılar için kullanılabilir biçimidir. `ON_COMMAND_EX` Makrosu gibi ileti işleyicileri için kullanılır ve bir alt kümesi [ON_COMMAND] (#on_command) işlevselliği sağlar.  Genişletilmiş komut işleyici üye işlevlerini tek bir parametre ele bir **UINT** dönün ve komut Kimliğini içeren bir **BOOL**. Dönüş değeri GİRİNTİLİ olmalıdır 

Bu makrosu bir genişletilmiş komut işleyici üye işlevi için bir komut iletisi eşler.  
   
### <a name="syntax"></a>Sözdizimi  
```  
ON_COMMAND_EX(id,  memberFxn);  
```
### <a name="parameters"></a>Parametreler  
 `id`  
 Komut kimliği.  
  
 `memberFxn`  
 Komut eşlenmiş ileti işleyicisi işlevin adı.  
   
### <a name="remarks"></a>Açıklamalar  
 Bir genişletilmiş komutu ileti işleyicileri İleri düzey kullanıcılar için kullanılabilir biçimidir. `ON_COMMAND_EX` Makrosu gibi ileti işleyicileri için kullanılır ve bir alt kümesi sağlar [ON_COMMAND](message-map-macros-mfc.md#on_command) işlevselliği. Genişletilmiş komut işleyici üye işlevlerini tek bir parametre ele bir **UINT** dönün ve komut Kimliğini içeren bir **BOOL**. Dönüş değeri komutu işlendiğini göstermek için TRUE olmalıdır; Aksi takdirde yönlendirme diğer komutu hedef nesnelere devam eder.  
Daha fazla bilgi için bkz. Teknik Not [TN006: ileti eşlemeleri] tm006 ileti maps.md).  
   
### <a name="requirements"></a>Gereksinimler  
 Üstbilgi dosyası: afxmsg_.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [ON_COMMAND](message-map-macros-mfc.md#on_command)   
 [TN006: ileti eşlemeleri] tm006 ileti maps.md)

  
## <a name="on_control"></a>ON_CONTROL
Hangi işlev bir özel denetim bildirim iletisi işleyeceğini gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_CONTROL( wNotifyCode, id, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `wNotifyCode`  
 Denetim bildirimi kodu.  
  
 `id`  
 Komut kimliği.  
  
 `memberFxn`  
 Komut eşlenmiş ileti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim bildirimi iletileri kendi üst penceresi denetimden gönderilen izinlerdir.  
  
 Olması gerektiğini tam olarak bir `ON_CONTROL` bir ileti işleyicisi işleve eşlenmelidir her denetim bildirim ileti, ileti eşlemesi makrosu deyiminde.  
  
 Daha fazla bilgi ve örnekler için bkz: [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  
  

## <a name="on_message"></a>ON_MESSAGE  
Hangi işlevi bir kullanıcı tarafından tanımlanan ileti işleyeceğini gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `message`  
 İleti kimliği.  
  
 `memberFxn`  
 İleti eşlenmiş ileti işleyicisi işlevin adı.  
  
 İşlev türü olmalıdır `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı tanımlı iletiler olan standart Windows olmayan herhangi bir iletisi `WM_MESSAGE` iletileri. Bir ileti kimliği seçerken, aralığında değerleri kullanmanız gerekir `WM_USER` (0x0400) 0x7FFF için veya `WM_APP` (0x8000) 0xBFFF için. İleti kimlikleri hakkında daha fazla bilgi için bkz: [WM_APP](http://msdn.microsoft.com/library/windows/desktop/ms644930).  
  
 Olması gerektiğini tam olarak bir `ON_MESSAGE` bir ileti işleyicisi işleve eşlenmelidir her kullanıcı tarafından tanımlanan ileti, ileti eşlemesi makrosu deyiminde.  
  
> [!NOTE]
>  Kullanıcı tanımlı iletiler, ek olarak `ON_MESSAGE` daha az yaygın Windows iletilerini işleme. Daha fazla bilgi için bkz. Bilgi Bankası makalesi [99848: bilgi: kullanım ON_MESSAGE() makrosu harita daha az yaygın iletileri](http://go.microsoft.com/fwlink/p/?linkid=192022).  
  
 Daha fazla bilgi ve örnekler için bkz: [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md) ve [kullanıcı tanımlı işleyiciler](user-defined-handlers.md)  
  
### <a name="example"></a>Örnek  
```cpp  
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
 afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here. 

   return 0;
}
```   
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  

## <a name="on_olecmd"></a>ON_OLECMD  
Komut gönderme arabirimi aracılığıyla komutları yönlendirir `IOleCommandTarget`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>Parametreler  
 `pguid`  
 Komut ait olduğu komutu grup tanımlayıcısı. Kullanım **NULL** standart grubun.  
  
 *olecmdid*  
 OLE komut tanımlayıcısı.  
  
 `id`  
 Menü kimliği, araç kimliği, düğme kodu veya diğer kimliği kaynak ya da komutu veren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `IOleCommandTarget`DocObject'ın kullanıcı arabiriminde kaynaklanan komutları almak için bir kapsayıcı sağlar ve aynı komutları göndermek kapsayıcı sağlar (yeni, Aç, Farklı Kaydet ve Dosya menüsünde; yazdırma gibi ve kopyalama, yapıştırma, vb. Düzen menüsünden geri) DocObject için.  
  
 `IOleCommandTarget`OLE Otomasyonu'nun basittir `IDispatch`. `IOleCommandTarget`tamamen komutları standart kümesinde kullanır, nadiren bağımsız değişkenlere sahiptir ve hiçbir tür bilgileri söz konusu (de komut bağımsız değişkenleri için tür güvenliği yayınladıklarını). Komutlar bağımsız değişkenlerle gönderilmesi gerekiyorsa, [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).  
  
 `IOleCommandTarget` Standart menü komutlarını uygulanmıştır MFC tarafından aşağıdaki makroları:  
  
 **ON_OLECMD_CLEARSELECTION)**  
  
 Düzen Temizle komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **ON_OLECMD_COPY)**  
  
 Copy Düzenle komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **ON_OLECMD_CUT)**  
  
 Düzen kesme komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **ON_OLECMD_NEW)**  
  
 Yeni dosya komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **ON_OLECMD_OPEN)**  
  
 Dosya Aç komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **ON_OLECMD_PAGESETUP)**  
  
 Sayfa Yapısı komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **ON_OLECMD_PASTE)**  
  
 Yapıştır Düzenle komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **ON_OLECMD_PASTESPECIAL)**  
  
 Özel Yapıştır Düzenle komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **ON_OLECMD_PRINT)**  
  
 Dosya Yazdır komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **ON_OLECMD_PRINTPREVIEW)**  
  
 Dosya Baskı Önizleme komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **ON_OLECMD_REDO)**  
  
 Düzen Yinele komut gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **ON_OLECMD_SAVE)**  
  
 Dosya Kaydet komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **ON_OLECMD_SAVE_AS)**  
  
 Dosya Kaydet komutunu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **ON_OLECMD_SAVE_COPY_AS)**  
  
 Dosya Kopyala Kaydet komutunu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **ON_OLECMD_SELECTALL)**  
  
 Tümünü Seç Düzenle komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`  
  
 **ON_OLECMD_UNDO)**  
  
 Düzen Geri Al komutu gönderir. Olarak uygulanan:  
  
 `ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdocob.h  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [COleCmdUI sınıfı](colecmdui-class.md)   
 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>ON_REGISTERED_MESSAGE
Windows **RegisterWindowMessage** işlevi, sistem genelinde benzersiz olması garanti yeni bir pencere iletisi tanımlamak için kullanılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `nMessageVariable`  
 Kayıtlı pencere iletisi kimliği değişkeni.  
  
 `memberFxn`  
 İleti eşlenmiş ileti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu hangi işlevi kayıtlı ileti işleyecek gösterir.  
  
 Daha fazla bilgi ve örnekler için bkz: [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Örnek  
```cpp  
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));


BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947)   
 [Kullanıcı Tanımlı İşleyiciler](user-defined-handlers.md)

## <a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE    
Hangi işlev Windows RegisterWindowMessage işlevi tarafından kaydedilen iletinin işleyecek gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `nMessageVariable`  
 Kayıtlı pencere iletisi kimliği değişkeni.  
  
 `memberFxn`  
 İleti eşlenmiş CWinThread ileti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 RegisterWindowMessage sistem genelinde benzersiz olması garanti yeni bir pencere iletisi tanımlamak için kullanılır. CWinThread sınıfı olduğunda on_regıstered_thread_message on_regıstered_message yerine kullanılmalıdır. 
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  

## <a name="on_thread_message"></a>ON_THREAD_MESSAGE  
Hangi işlevi bir kullanıcı tarafından tanımlanan ileti işleyeceğini gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_THREAD_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `message`  
 İleti kimliği.  
  
 `memberFxn`  
 Adı `CWinThread`-iletisi-ileti eşlendiği işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 `ON_THREAD_MESSAGE`yerine kullanılmalıdır `ON_MESSAGE` olduğunda bir `CWinThread` sınıfı. Kullanıcı tanımlı iletiler olan standart Windows olmayan herhangi bir iletisi **WM_MESSAGE** iletileri. Olması gerektiğini tam olarak bir `ON_THREAD_MESSAGE` bir ileti işleyicisi işleve eşlenmelidir her kullanıcı tarafından tanımlanan ileti, ileti eşlemesi makrosu deyiminde.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  

## <a name="on_update_command_ui"></a>ON_UPDATE_COMMAND_UI    
Bu makrosu hangi işlevi bir kullanıcı arabirimi güncelleştirme komut iletisi işleyeceğini gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_UPDATE_COMMAND_UI( id, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 İleti kimliği.  
  
 `memberFxn`  
 İleti eşlenmiş ileti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Olması gerektiğini tam olarak bir `ON_UPDATE_COMMAND_UI` bir ileti işleyicisi işleve eşlenmelidir her kullanıcı arabirimi güncelleştirme komutu, ileti eşlemesi makrosu deyiminde.  
  
 Daha fazla bilgi ve örnekler için bkz: [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdUI Sınıfı](ccmdui-class.md)

## <a name="on_command_range"></a>ON_COMMAND_RANGE  
Komut kimlikleri bitişik bir dizi tek ileti işleyicisi işleve eşlemek için bu makrosu kullanın.  
  
### <a name="syntax"></a>Sözdizimi
  
```  
ON_COMMAND_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `id1`  
 Komut kimlikleri bitişik bir dizi başındaki komut kimliği.  
  
 `id2`  
 Komut kimlikleri bitişik bir dizi sonunda komut kimliği.  
  
 `memberFxn`  
 Komutları eşlenen ileti işleyicisi işlev adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Olan aralığı kimlikleri ile başlayan `id1` ve biten `id2`.  
  
 Kullanım `ON_COMMAND_RANGE` bir üye işlevine bir dizi komut kimlikleri eşlemek için. Kullanım [ON_COMMAND](#on_command) üye işlevi için tek bir komut eşlemek için. Verilen komut kimliği. yalnızca bir ileti eşleme girişi ile eşleşen Diğer bir deyişle, birden fazla işleyici için bir komut eşlenemiyor. İleti eşleme aralıkları hakkında daha fazla bilgi için bkz: [ileti eşleme aralıkları için işleyiciler](../../mfc/handlers-for-message-map-ranges.md).  
  
 Kendiniz makrosu yerleştirmeniz gerekir böylece ileti eşleme aralıkları için otomatik desteği yoktur.  
  
### <a name="example"></a>Örnek  
```cpp  
// The code fragment below shows how to use ON_COMMAND_RANGE macro 
// to map a contiguous range of command IDs to a single message  
// handler function (i.e. OnRangeCmds() in the sample below). In  
// addition, it also shows how to use CheckMenuRadioItem() to check a  
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, 
      nID, MF_BYCOMMAND);
}
```
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  

## <a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE    
Komut kimlikleri bitişik bir dizi bir tek güncelleştirme ileti işleyicisi işleve eşler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `id1`  
 Komut kimlikleri bitişik bir dizi başındaki komut kimliği.  
  
 `id2`  
 Komut kimlikleri bitişik bir dizi sonunda komut kimliği.  
  
 `memberFxn`  
 Komutları eşlenen güncelleştirme ileti işleyicisi işlev adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Güncelleştirme ileti işleyicileri menü öğeleri ve komutla ilişkili araç çubuğu düğmeleri durumunu güncelleştirin. Olan aralığı kimlikleri ile başlayan `id1` ve biten `id2`.  
  
 Kendiniz makrosu yerleştirmeniz gerekir böylece ileti eşleme aralıkları için otomatik desteği yoktur.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  

## <a name="on_control_range"></a>ON_CONTROL_RANGE     
Denetim kimliklerinin bitişik bir dizi belirtilen bir Windows bildirim iletisi için bir tek ileti işleyicisi işlevi gibi eşleştirmek için bu makrosu kullanma **BN_CLICKED**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 `wNotifyCode`  
 Bildirim kodu işleyicinizi yanıt vermiyor.  
  
 `id1`  
 Denetim kimliklerinin bitişik bir dizi başındaki komut kimliği.  
  
 `id2`  
 Denetim kimliklerinin bitişik bir dizi sonunda komut kimliği.  
  
 `memberFxn`  
 Denetimleri eşlenen ileti işleyicisi işlev adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Olan aralığı kimlikleri ile başlayan `id1` ve biten `id2`. İşleyici eşlenen denetimleri hiçbirini gelen belirtilen bildirim için çağrılır.  
  
 Kendiniz makrosu yerleştirmeniz gerekir böylece ileti eşleme aralıkları için otomatik desteği yoktur.  
  
 İşleyici işlevleri bir dizi denetim kimlikleri için uygulama ile ilgili daha fazla bilgi için başvurmak [ileti eşleme aralıkları için işleyiciler](../../mfc/handlers-for-message-map-ranges.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  
  


