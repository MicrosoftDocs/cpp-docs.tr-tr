---
title: İleti eşleme makroları (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61599d9080bf5cdce56f30ed38e6b20064032512
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216709"
---
# <a name="message-map-macros-mfc"></a>İleti Eşleme Makroları (MFC)
İleti eşlemeleri desteklemek için aşağıdaki makroları MFC sağlar:  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>İleti eşleme bildirim ve düzenleme makroları  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|İleti eşlemesi bir sınıfta (sınıf bildirimi içinde kullanılmalıdır) işlevleri için ileti eşlemesi için kullanılacak bildirir.|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|(Sınıfı uygulamasında kullanılmalıdır) ileti eşlemesi tanımını başlar.|  
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_interface_map)|Tek bir şablon bağımsız değişken içeren sınıf türünde bir ileti eşlemesi tanımını başlar. |
|[END_MESSAGE_MAP](#end_message_map)|(Sınıfı uygulamasında kullanılmalıdır) ileti eşlemesi tanımını sonlandırır.|  
  
### <a name="message-mapping-macros"></a>İleti eşleme makroları  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|Hangi işlev belirtilen komut iletisini işleyecek gösterir.|  
|[ON_COMMAND_EX](#on_command_ex)|Hangi işlev belirtilen komut iletisini işleyecek gösterir.|  
|[ON_CONTROL](#on_control)|Hangi işlev belirtilen denetimi bildirim iletisini işleyecek gösterir.|  
|[ON_MESSAGE](#on_message)|Hangi işlevi kullanıcı tanımlı bir ileti işleyecek gösterir.|  
|[ON_OLECMD](#on_olecmd)|Bir menü komutu DocObject veya kapsayıcısı hangi işlevi işleyecek gösterir.|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Hangi işlevi kullanıcı tanımlı bir kayıtlı ileti işleyecek gösterir.|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Varsa, hangi işlevi kullanıcı tanımlı kayıtlı bir ileti işleyecek gösteren bir `CWinThread` sınıfı.|  
|[ON_THREAD_MESSAGE](#on_thread_message)|Varsa, hangi işlevi kullanıcı tanımlı bir ileti işleyecek gösteren bir `CWinThread` sınıfı.|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Hangi işlevi, belirtilen kullanıcı arabirimi güncelleştirme komut iletisini işleyecek gösterir.|  
  
### <a name="message-map-range-macros"></a>Aralık ileti eşleme makroları  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](#on_command_range)|Hangi işlevin ilk iki parametresi için makro belirtilen komut kimlikleri aralığını işleyecek gösterir.|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Hangi güncelleştirme işleyicisi ilk iki pa belirtilen komut kimlikleri aralığını işleyecek gösterir] makro için parametreler.|  
|[ON_CONTROL_RANGE](#on_control_range)|Hangi işlev bildirimleri denetim makro için ikinci ve üçüncü parametre olarak belirtilen bir aralıktan işleyecek gösterir. İlk parametre BN_CLICKED gibi bir denetim bildirimi iletisidir.|  
  
 İleti eşlemeleri, ileti eşleme bildirim ve düzenleme makroları ve ileti eşleme makroları hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../mfc/reference/message-maps-mfc.md) ve [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md). İleti eşleme aralıkları hakkında daha fazla bilgi için bkz. [ileti eşleme aralıkları için işleyiciler](../../mfc/handlers-for-message-map-ranges.md).  


## <a name="begin_message_map"></a> BEGIN_MESSAGE_MAP
İleti haritanızı tanımını başlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>Parametreler  
 *Sınıfın*  
 Bu eşleme olan ileti sınıfı adını belirtir.  
  
 *baseClass*  
 Taban sınıfının adını belirtir *sınıfın*.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıfınız için üye işlevleri tanımlayan uygulama dosyasında (.cpp), ileti eşlemesi begın_message_map makrosu ile Başlat sonra her biri, ileti işleyici işlevleri için makro girişler ekleyin ve ileti eşlemesi END_MESSAGE_MAP ile tamamlayın Makro.  
  
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
Tek bir şablon bağımsız değişken içeren sınıf türünde bir ileti eşlemesi tanımını başlar.  
   
### <a name="syntax"></a>Sözdizimi  
  ```
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )  
```
### <a name="parameters"></a>Parametreler  
 *Sınıfın*  
 Bu eşleme olan ileti sınıfı adını belirtir.    
 *TYPE_NAME*  
 Sınıfı için belirtilen şablon parametresi adı.    
 *baseClass*  
 Taban sınıfının adını belirtir *sınıfın*.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu makro benzer [begın_message_map](message-map-macros-mfc.md#begin_message_map) makrosu; ancak, bu makroyu tek şablon bağımsız değişken içeren sınıflar için tasarlanmıştır.  
  
 Sınıfınızın yöntemi uygulama bölümünde ile BEGIN_TEMPLATE_MESSAGE_MAP makrosu ileti eşlemede Başlat; standart ileti eşlemesi için yaptığınız gibi makrosu girişleri her ileti işleyicisi yöntemlerinizi ekleyin. Begın_message_map makrosu ile şablon ileti eşlemesi ile tamamlarken [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) makrosu.  
  
 İleti eşlemeleri için şablon sınıfları uygulama ile ilgili daha fazla bilgi için [nasıl yapılır: bir şablon sınıfı için ileti eşlemesi oluşturma](../how-to-create-a-message-map-for-a-template-class.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
 
## <a name="declare_message_map"></a>  DECLARE_MESSAGE_MAP
 Sınıfı ileti eşlemesi tanımlar bildirir. Her `CCmdTarget`-türetilmiş sınıf programınızda, iletileri işlemek için ileti eşlemesi sağlamalıdır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Açıklamalar  
 DECLARE_MESSAGE_MAP makrosu, sınıf bildiriminin sonuna kullanın. Ardından, sınıfın üye işlevleri tanımlar .cpp dosyası begın_message_map makrosu, makro girişleri her biri, ileti işleyici işlevlerini ve END_MESSAGE_MAP makrosu için kullanın.  
  
> [!NOTE]
>  DECLARE_MESSAGE_MAP sonra herhangi bir üyenin bildirirseniz, yeni bir erişim türü belirtmeniz gerekir (**genel**, **özel**, veya **korumalı**) için bunları.  
  
 İleti eşlemeleri ve DECLARE_MESSAGE_MAP makrosu hakkında daha fazla bilgi için bkz. [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Örnek  
```cpp  
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
``` 
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  


## <a name="end_message_map"></a>  END_MESSAGE_MAP
İleti haritanızı tanımını sonlandırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İleti eşlemeleri ve END_MESSAGE_MAP makrosu hakkında daha fazla bilgi için bkz. [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  

## <a name="on_command"></a>  ON_COMMAND
Bu makro, bir üye işlevine bir komut iletisi eşler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 Komut kimliği.  
  
 *memberFxn*  
 Komut için eşlenmiş ileti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, hangi işlevi bir menü öğesi veya araç çubuğu düğmesi gibi bir komut kullanıcı arabirimi nesnesinden bir komut iletisi işleyecek gösterir.  
  
 ON_COMMAND komut-hedef nesne belirtilen Kimliğe sahip bir Windows WM_COMMAND ileti aldığında, üye işlevi çağıracaktır `memberFxn` iletisini işlemek için.  
  
 Tek bir komutu bir üye işleve eşlemenizi ON_COMMAND kullanın. Kullanım [ON_COMMAND_RANGE](#on_command_range) bir üye işlevine bir dizi komut kimlikleri eşleştirmek için. Belirtilen komut kimliği yalnızca bir ileti eşleme girişi eşleşebilir. Diğer bir deyişle, bir komut için birden fazla işleyici eşlenemiyor. Daha fazla bilgi ve örnekler için bkz. [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Örnek  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  

 ## <a name="on_command_ex"></a>  ON_COMMAND_EX
Komut işleyici üye işlevi genişletilmiş.  
   
### <a name="syntax"></a>Sözdizimi  
  ```  
ON_COMMAND_EX(id, memberFxn);  
```
### <a name="parameters"></a>Parametreler  
 *id*  
 Komut kimliği.  
  
 *memberFxn*  
 Komut için eşlenmiş ileti işleyici işlevinin adı.  
   
### <a name="remarks"></a>Açıklamalar 
Genişletilmiş bir form komut ileti işleyicileri, İleri düzey kullanıcılar için kullanılabilir. ON_COMMAND_EX makrosu gibi ileti işleyicileri için kullanılır ve bir işlevselliğin [ON_COMMAND] (#on_command) sağlar.  Genişletilmiş komut işleyici üye işlevleri, tek bir parametre, komut Kimliğini içeren bir UINT ve BOOL döndürür. Dönüş değeri true olmalıdır 

Bu makro, bir genişletilmiş komut işleyici üye işlevi için bir komut iletisi eşler.  
   
### <a name="syntax"></a>Sözdizimi  
```  
ON_COMMAND_EX(id,  memberFxn);  
```
### <a name="parameters"></a>Parametreler  
 *id*  
 Komut kimliği.  
  
 *memberFxn*  
 Komut için eşlenmiş ileti işleyici işlevinin adı.  
   
### <a name="remarks"></a>Açıklamalar  
 Genişletilmiş bir form komut ileti işleyicileri, İleri düzey kullanıcılar için kullanılabilir. ON_COMMAND_EX makrosu gibi ileti işleyicileri için kullanılır ve bir alt kümesi sağlayan [ON_COMMAND](message-map-macros-mfc.md#on_command) işlevselliği. Genişletilmiş komut işleyici üye işlevleri, tek bir parametre, komut Kimliğini içeren bir UINT ve BOOL döndürür. Dönüş değeri komut işlendiğini göstermek için TRUE olmalıdır; Aksi takdirde yönlendirme diğer komut hedef nesnelere devam eder.  
Daha fazla bilgi için bkz. Teknik Not [TN006: ileti eşlemeleri] tm006 ileti maps.md).  
   
### <a name="requirements"></a>Gereksinimler  
 Üst bilgi dosyası: afxmsg_.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [ON_COMMAND](message-map-macros-mfc.md#on_command)   
 [TN006: ileti eşlemeleri] tm006 ileti maps.md)

  
## <a name="on_control"></a>  ON_CONTROL
Hangi işlev bir özel denetim bildirim iletisini işleyecek gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_CONTROL( wNotifyCode, id, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *wNotifyCode*  
 Denetim bildirimi kodu.  
  
 *id*  
 Komut kimliği.  
  
 *memberFxn*  
 Komut için eşlenmiş ileti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir denetimi üst pencereye gönderilir denetimi bildirim iletileri olanlardır.  
  
 İleti haritanıza bir ileti işleyicisi işlevini eşlenmelidir her denetimi bildirim iletileri için tam olarak bir ON_CONTROL makrosu deyiminde olması gerekir.  
  
 Daha fazla bilgi ve örnekler için bkz. [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  
  

## <a name="on_message"></a>  ON_MESSAGE  
Hangi işlevi kullanıcı tanımlı bir ileti işleyecek gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *message*  
 İleti kimliği.  
  
 *memberFxn*  
 İleti için eşlenmiş ileti işleyici işlevinin adı.  
  
 İşlev türü olmalıdır `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı tanımlı iletiler standart Windows WM_MESSAGE iletiler iletiler ' dir. İleti kimliği seçerken, aralığı WM_USER (0x0400) içindeki değerleri 0x7FFF veya WM_APP (0x8000) 0xBFFF için kullanmanız gerekir. İleti kimliği ile ilgili daha fazla bilgi için bkz. [WM_APP](/windows/desktop/winmsg/wm-app).  
  
 Kullanıcı tanımlı bir ileti işleyicisi işlevini eşlenmesi gereken her ileti, ileti eşlemesi tam olarak bir ON_MESSAGE makrosu deyiminde olması gerekir.  
  
> [!NOTE]
>  Kullanıcı tanımlı iletileri yanı sıra ON_MESSAGE daha az yaygın Windows iletilerini işler. Daha fazla bilgi için bkz. Bilgi Bankası makalesi [99848: bilgi: kullanım ON_MESSAGE() makrosu harita daha az yaygın iletileri](http://go.microsoft.com/fwlink/p/?linkid=192022).  
  
 Daha fazla bilgi ve örnekler için bkz. [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md) ve [kullanıcı tanımlı işleyiciler](user-defined-handlers.md)  
  
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

## <a name="on_olecmd"></a>  ON_OLECMD  
Komutlar komut gönderme arabirimi aracılığıyla yönlendiren `IOleCommandTarget`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>Parametreler  
 *pguid*  
 Ait olduğu komutun komut grubu tanımlayıcısı. NULL standart bir grup için kullanın.  
  
 *olecmdid*  
 OLE komut tanımlayıcısı.  
  
 *id*  
 Menü kimliği, araç kimliği, düğme kodu veya diğer kaynak veya komutu veren nesne kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 `IOleCommandTarget` DocObject'ın kullanıcı arabiriminde kaynaklanan komutları almak bir kapsayıcı sağlar ve aynı komutları göndermek kapsayıcı sağlar (yeni, açık, Farklı Kaydet ve Dosya menüsündeki; yazdırma gibi ve kopyalama, yapıştırma, vb. Düzen menüsündeki Geri) DocObject için.  
  
 `IOleCommandTarget` OLE Otomasyon basittir `IDispatch`. `IOleCommandTarget` tamamen komutları standart bir dizi üzerinde kullanır, nadiren bağımsız değişkenlere sahip ve hiçbir tür bilgileri söz konusu (komut satırı bağımsız değişkenlerini için de tür güvenliği yayınladıklarını). Komutları bağımsız değişkenleri ile gönderilmesi gerekiyorsa kullanın [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).  
  
 `IOleCommandTarget` Standart menü komutları uygulanmıştır MFC tarafından aşağıdaki makrolarındaki:  
  
 **ON_OLECMD_CLEARSELECTION)**  
  
 Düzen temizleme komutu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **ON_OLECMD_COPY)**  
  
 Kopya Düzenle komutu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **ON_OLECMD_CUT)**  
  
 Düzen Kes komutu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **ON_OLECMD_NEW)**  
  
 Dosya yeni komutunun gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **ON_OLECMD_OPEN)**  
  
 Dosya Aç komutunu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **ON_OLECMD_PAGESETUP)**  
  
 Sayfa Yapısı komut gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **ON_OLECMD_PASTE)**  
  
 Düzen Paste komutu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **ON_OLECMD_PASTESPECIAL)**  
  
 Özel Yapıştır Düzenle komutu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **ON_OLECMD_PRINT)**  
  
 Dosya Yazdır komutunu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **ON_OLECMD_PRINTPREVIEW)**  
  
 Dosya Yazdırma Önizleme komutunu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **ON_OLECMD_REDO)**  
  
 Düzen Yinele komut gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **ON_OLECMD_SAVE)**  
  
 Dosya Kaydet komutunu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **ON_OLECMD_SAVE_AS)**  
  
 Dosyayı Farklı Kaydet komutu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **ON_OLECMD_SAVE_COPY_AS)**  
  
 Dosya kopyalama Kaydet komutunu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **ON_OLECMD_SELECTALL)**  
  
 Tümünü Seç Düzenle komutu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`  
  
 **ON_OLECMD_UNDO)**  
  
 Düzen geri alma komutu gönderir. Halinde uygulanır:  
  
 `ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdocob.h  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [Colecmduı sınıfı](colecmdui-class.md)   
 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>  ON_REGISTERED_MESSAGE
Windows `RegisterWindowMessage` işlevi, sistem genelinde benzersiz olması garanti yeni bir pencere iletisi tanımlamak için kullanılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *nMessageVariable*  
 Kayıtlı pencere iletisi kimliği değişkeni.  
  
 *memberFxn*  
 İleti için eşlenmiş ileti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro, hangi işlevi kayıtlı iletisini işleyecek gösterir.  
  
 Daha fazla bilgi ve örnekler için bkz. [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
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
 [RegisterWindowMessage](https://msdn.microsoft.com/library/windows/desktop/ms644947)   
 [Kullanıcı Tanımlı İşleyiciler](user-defined-handlers.md)

## <a name="on_registered_thread_message"></a>  ON_REGISTERED_THREAD_MESSAGE    
Hangi işlevi Windows RegisterWindowMessage işlevi tarafından kaydedilen iletinin işleyecek gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *nMessageVariable*  
 Kayıtlı pencere iletisi kimliği değişkeni.  
  
 *memberFxn*  
 İleti için eşlenmiş CWinThread ileti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 RegisterWindowMessage, sistem genelinde benzersiz olması garanti yeni bir pencere iletisi tanımlamak için kullanılır. CWinThread sınıfı olduğunda on_regıstered_thread_message on_regıstered_message yerine kullanılmalıdır. 
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  

## <a name="on_thread_message"></a>  ON_THREAD_MESSAGE  
Hangi işlevi kullanıcı tanımlı bir ileti işleyecek gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_THREAD_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *message*  
 İleti kimliği.  
  
 *memberFxn*  
 Adını `CWinThread`-iletisi-ileti eşleşen işleyici işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 ON_THREAD_MESSAGE varsa ON_MESSAGE yerine kullanılmalıdır bir `CWinThread` sınıfı. Kullanıcı tanımlı iletiler standart Windows WM_MESSAGE iletiler iletiler ' dir. Kullanıcı tanımlı bir ileti işleyicisi işlevini eşlenmesi gereken her ileti, ileti eşlemesi tam olarak bir ON_THREAD_MESSAGE makrosu deyiminde olması gerekir.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  

## <a name="on_update_command_ui"></a>  ON_UPDATE_COMMAND_UI    
Bu makro, hangi işlevi bir kullanıcı arabirimi güncelleştirme komut iletisini işleyecek gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_UPDATE_COMMAND_UI( id, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 İleti kimliği.  
  
 *memberFxn*  
 İleti için eşlenmiş ileti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 On_update_command_uı makrosu deyimi, bir ileti işleyicisi işlevini eşlenmelidir her kullanıcı arabirimini güncelleştirme komut için ileti eşlemesi tam olarak bir olmalıdır.  
  
 Daha fazla bilgi ve örnekler için bkz. [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
### <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdUI Sınıfı](ccmdui-class.md)

## <a name="on_command_range"></a>  ON_COMMAND_RANGE  
Komut kimlikleri bir aralıkta bir tek ileti işleyici işlevine eşlemek için bu makroyu kullanın.  
  
### <a name="syntax"></a>Sözdizimi
  
```  
ON_COMMAND_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *ıd1*  
 Komut kimlikleri bir aralıkta başlangıcında komut kimliği.  
  
 *ıd2*  
 Komut kimlikleri bir aralıkta sonunda komut kimliği.  
  
 *memberFxn*  
 Komutlar eşlenmiş ileti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Olan Aralık kimlikleri ile başlayan *ıd1* ve ile sona eren *ıd2*.  
  
 ON_COMMAND_RANGE bir üye işlevine bir dizi komut kimlikleri eşleştirmek için kullanın. Kullanım [ON_COMMAND](#on_command) tek bir komutu bir üye işlevine eşlemek için. Belirtilen komut kimliği. yalnızca bir ileti eşleme girişi eşleşebilir Diğer bir deyişle, bir komut için birden fazla işleyici eşlenemiyor. Eşleme ileti aralıkları hakkında daha fazla bilgi için bkz. [ileti eşleme aralıkları için işleyiciler](../../mfc/handlers-for-message-map-ranges.md).  
  
 Kendiniz makro yerleştirmeniz gerekir böylece ileti eşleme aralıkları için otomatik desteği yoktur.  
  
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

## <a name="on_update_command_ui_range"></a>  ON_UPDATE_COMMAND_UI_RANGE    
Komut kimlikleri bir aralıkta bir tek güncelleştirme ileti işleyici işlevine eşler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *ıd1*  
 Komut kimlikleri bir aralıkta başlangıcında komut kimliği.  
  
 *ıd2*  
 Komut kimlikleri bir aralıkta sonunda komut kimliği.  
  
 *memberFxn*  
 Komutlar eşlenmiş güncelleştirme ileti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü öğeleri ve komutla ilişkilendirilmiş araç çubuğu düğmeleri durumunu güncelleştirme ileti işleyicilerini güncelleştirin. Olan Aralık kimlikleri ile başlayan *ıd1* ve ile sona eren *ıd2*.  
  
 Kendiniz makro yerleştirmeniz gerekir böylece ileti eşleme aralıkları için otomatik desteği yoktur.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  

## <a name="on_control_range"></a>  ON_CONTROL_RANGE     
Bir tek ileti işleyici işlevi BN_CLICKED gibi belirtilen bir Windows bildirim iletisi için bir aralıkta denetimi kimlikleri eşlemek için bu makroyu kullanın.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parametreler  
 *wNotifyCode*  
 Bildirim kodu işleyicinizi yanıt veriyor.  
  
 *ıd1*  
 Denetim kimliklerinin bir aralıkta başlangıcında komut kimliği.  
  
 *ıd2*  
 Denetim kimliklerinin bir aralıkta sonunda komut kimliği.  
  
 *memberFxn*  
 Denetimleri eşlenmiş ileti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Olan Aralık kimlikleri ile başlayan *ıd1* ve ile sona eren *ıd2*. Eşlenen denetimleri hiçbirini yakında belirtilen bildirim işleyicisinde çağrılır.  
  
 Kendiniz makro yerleştirmeniz gerekir böylece ileti eşleme aralıkları için otomatik desteği yoktur.  
  
 Bir dizi Denetim kimliklerinin işleyici işlevlerini uygulama ile ilgili daha fazla bilgi için [ileti eşleme aralıkları için işleyiciler](../../mfc/handlers-for-message-map-ranges.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmsg_.h  
  