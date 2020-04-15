---
title: İleti Eşleme Makroları (MFC)
ms.date: 03/27/2019
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
ms.openlocfilehash: 6e9291f0f39057403bc27c7fe4ff5ca5a82dfe3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356592"
---
# <a name="message-map-macros-mfc"></a>İleti Eşleme Makroları (MFC)

İleti eşlemlerini desteklemek için MFC aşağıdaki makroları sağlar:

### <a name="message-map-declaration-and-demarcation-macros"></a>İleti-Harita Bildirimi ve Çizim Makroları

|||
|-|-|
|[DECLARE_MESSAGE_MAP](#declare_message_map)|İletileri işlevlerle eşlemek için bir sınıfta ileti eşlemi kullanılacağını bildirir (sınıf bildiriminde kullanılması gerekir).|
|[BEGIN_MESSAGE_MAP](#begin_message_map)|İleti eşlemi tanımını başla (sınıf uygulamasında kullanılmalıdır).|
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_message_map)|Tek bir şablon bağımsız değişkeni içeren bir sınıf türünde ileti eşlemi tanımını başlatın. |
|[END_MESSAGE_MAP](#end_message_map)|İleti eşlemi tanımını sona erdirin (sınıf uygulamasında kullanılmalıdır).|

### <a name="message-mapping-macros"></a>İleti Eşleme Makroları

|||
|-|-|
|[On_command](#on_command)|Hangi işlevin belirli bir komut iletisini işleyeceğini gösterir.|
|[ON_COMMAND_EX](#on_command_ex)|Hangi işlevin belirli bir komut iletisini işleyeceğini gösterir.|
|[ON_CONTROL](#on_control)|Hangi işlevin belirli bir denetim bildirim iletisini işleyeceğini gösterir.|
|[ON_MESSAGE](#on_message)|Hangi işlevin kullanıcı tanımlı bir iletiyi işleyeceğini gösterir.|
|[ON_OLECMD](#on_olecmd)|Bir DocObject veya kapsayıcısından menü komutunu hangi işlevin işleyeceğini gösterir.|
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Kayıtlı kullanıcı tanımlı bir iletiyi hangi işlevin işleyeceğini gösterir.|
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|`CWinThread` Sınıf olduğunda kayıtlı kullanıcı tanımlı bir iletiyi hangi işlevin işleyeceğini gösterir.|
|[ON_THREAD_MESSAGE](#on_thread_message)|`CWinThread` Bir sınıf olduğunda kullanıcı tanımlı bir iletiyi hangi işlevin işleyeceğini gösterir.|
|[On_update_command_uı](#on_update_command_ui)|Belirtilen kullanıcı arabirimi güncelleştirme komut iletisini hangi işlevin işleyeceğini gösterir.|

### <a name="message-map-range-macros"></a>İleti-Harita Aralığı Makroları

|||
|-|-|
|[ON_COMMAND_RANGE](#on_command_range)|Makroya ilk iki parametrede belirtilen komut iD'lerinin aralığını hangi işlevin işleyeceğini gösterir.|
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Makroya ilk iki parametrede belirtilen komut iD'lerinin aralığını hangi güncelleştirme işleyicisinin işleyeceğini gösterir.|
|[ON_CONTROL_RANGE](#on_control_range)|İkinci ve üçüncü parametrelerde belirtilen denetim iD'lerinin aralığından makroya hangi işlevin bildirimleri işleyeceğini gösterir. İlk parametre, BN_CLICKED gibi bir denetim bildirim iletisidir.|

İleti haritaları, ileti eşlemi bildirimi ve sınır oluşturma makroları ve ileti eşleme makroları hakkında daha fazla bilgi için [İleti Haritaları](../../mfc/reference/message-maps-mfc.md) ve [İleti İşleme ve Haritalama Konuları](../../mfc/message-handling-and-mapping.md)bölümüne bakın. İleti-eşlemi aralıkları hakkında daha fazla bilgi için [İleti-Harita Aralıkları için İşleyiciler'e](../../mfc/handlers-for-message-map-ranges.md)bakın.

## <a name="begin_message_map"></a><a name="begin_message_map"></a>BEGIN_MESSAGE_MAP

İleti haritanızın tanımını başlayır.

### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_MESSAGE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
İleti haritası bu olan sınıfın adını belirtir.

*Baseclass*<br/>
*Sınıfın*taban sınıfının adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıfınızın üye işlevlerini tanımlayan uygulama (.cpp) dosyasında, ileti eşlesini BEGIN_MESSAGE_MAP makrosuyla başlatın, ardından ileti işleyicisi işlevlerinizin her biri için makro girişleri ekleyin ve END_MESSAGE_MAP makrosuyla ileti eşlemi tamamlayın.

İleti haritaları hakkında daha fazla bilgi için [İleti Haritaları'na](message-maps-mfc.md) bakın

### <a name="example"></a>Örnek

```cpp
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="begin_template_message_map"></a><a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP

Tek bir şablon bağımsız değişkeni içeren bir sınıf türünde ileti eşlemi tanımını başlatın.

### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
İleti haritası bu olan sınıfın adını belirtir.

*Type_name*<br/>
Sınıf için belirtilen şablon parametresinin adı.

*Baseclass*<br/>
*Sınıfın*taban sınıfının adını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makro [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) makrobenzer; ancak, bu makro tek bir şablon bağımsız değişkeni içeren sınıflar için tasarlanmıştır.

Sınıfınızın yöntem uygulama bölümünde, BEGIN_TEMPLATE_MESSAGE_MAP makrosuyla ileti eşlesini başlatın; ardından, standart bir ileti eşlemi için olduğu gibi, ileti işleyici yöntemlerinizin her biri için makro girişleri ekleyin. BEGIN_MESSAGE_MAP makroda olduğu gibi, şablon ileti eşlesini [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) makrosuyla tamamlayın.

Şablon sınıfları için ileti eşlemleri uygulama hakkında daha fazla bilgi için [bkz.](../how-to-create-a-message-map-for-a-template-class.md)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="declare_message_map"></a><a name="declare_message_map"></a>DECLARE_MESSAGE_MAP

Sınıfın bir ileti eşlemi tanımladığını bildirir. Programınızdaki türetilmiş her `CCmdTarget`sınıf, iletileri işlemek için bir ileti eşlemesi sağlamalıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
DECLARE_MESSAGE_MAP( )
```

### <a name="remarks"></a>Açıklamalar

Sınıf bildirgenizin sonundaki DECLARE_MESSAGE_MAP makroyu kullanın. Ardından, sınıfın üye işlevlerini tanımlayan .cpp dosyasında, BEGIN_MESSAGE_MAP makroyu, ileti işleyici işlevlerinizin her biri için makro girişlerini ve END_MESSAGE_MAP makroyu kullanın.

> [!NOTE]
> herhangi bir üyeyi DECLARE_MESSAGE_MAP sonra beyan ederseniz, onlar için yeni bir erişim türü **(genel,** **özel**veya **korumalı)** belirtmeniz gerekir.

İleti haritaları ve DECLARE_MESSAGE_MAP makrosu hakkında daha fazla bilgi için [İleti İşleme ve Haritalama Konuları'na](../../mfc/message-handling-and-mapping.md)bakın.

### <a name="example"></a>Örnek

```cpp
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="end_message_map"></a><a name="end_message_map"></a>END_MESSAGE_MAP

İleti haritanızın tanımını sona erdirer.

### <a name="syntax"></a>Sözdizimi

```cpp
END_MESSAGE_MAP( )
```

### <a name="remarks"></a>Açıklamalar

İleti haritaları ve END_MESSAGE_MAP makro su yla ilgili daha fazla bilgi için [İleti İşleme ve Haritalama Konuları'na](../../mfc/message-handling-and-mapping.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="on_command"></a><a name="on_command"></a>On_command

Bu makro, bir komut iletisini bir üye işlevle eşler.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_COMMAND( commandId, memberFxn )
```

### <a name="parameters"></a>Parametreler

*Commandıd*<br/>
Komut kimliği.

*üyeFxn*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Menü öğesi veya araç çubuğu düğmesi gibi komut kullanıcı arabirimi nesnesinden gelen komut iletisini hangi işlevin işleyeceğini gösterir.

Komut hedef nesnesi belirtilen kimliği içeren bir Windows WM_COMMAND iletisi aldığında, ON_COMMAND iletiyi işlemek için üye işlevi `memberFxn` çağırır.

Tek bir komutu bir üye işlevle eşlemek için ON_COMMAND kullanın. Bir dizi komut iÞlesini tek bir üye işlevle eşlemek için [ON_COMMAND_RANGE](#on_command_range) kullanın. Yalnızca bir ileti eşlemi girişi belirli bir komut kimliğiyle eşleşebilir. Diğer bir süre, bir komutu birden fazla işleyiciyle eşleyebilirsiniz. Daha fazla bilgi ve örnekler için [İleti İşleme ve Haritalama Konuları'na](../../mfc/message-handling-and-mapping.md)bakın.

### <a name="example"></a>Örnek

```cpp
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmsg_.h

## <a name="on_command_ex"></a><a name="on_command_ex"></a>ON_COMMAND_EX

Genişletilmiş komut işleyiciüye işlevi.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_COMMAND_EX(commandId, memberFxn);
```

### <a name="parameters"></a>Parametreler

*Commandıd*<br/>
Komut kimliği.

*üyeFxn*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Gelişmiş kullanımlar için genişletilmiş bir komut ileti işleyicileri biçimi kullanılabilir. ON_COMMAND_EX makrosu bu tür ileti işleyicileri için kullanılır ve [ON_COMMAND](message-map-macros-mfc.md#on_command) işlevselliğinin bir üst kümesini sağlar. Genişletilmiş komut işleyici üye işlevleri tek bir parametre, komut kimliği içeren bir UINT alır ve bir BOOL döndürür. İade değeri komutun işlendiğini belirtmek için TRUE olmalıdır; aksi takdirde yönlendirme diğer komut hedef nesnelere devam edecektir.

Daha fazla bilgi için teknik not [TN006: İleti Haritaları]tm006-mesaj-maps.md) bakın.

### <a name="requirements"></a>Gereksinimler

Üstbilgi dosyası: afxmsg_.h

## <a name="on_control"></a><a name="on_control"></a>ON_CONTROL

Özel denetim bildirim iletisini hangi işlevin işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_CONTROL( wNotifyCode, commandId, memberFxn )
```

### <a name="parameters"></a>Parametreler

*wNotifyCode*<br/>
Denetimin bildirim kodu.

*Commandıd*<br/>
Komut kimliği.

*üyeFxn*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Denetim bildirim iletileri, denetimden üst penceresine gönderilen iletilerdir.

İleti işleyici işlevine eşlenen her denetim bildirimi iletisi için ileti haritanızda tam olarak bir ON_CONTROL makro bildirimi olmalıdır.

Daha fazla bilgi ve örnekler için [İleti İşleme ve Haritalama Konuları'na](../../mfc/message-handling-and-mapping.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmsg_.h

## <a name="on_message"></a><a name="on_message"></a>ON_MESSAGE

Hangi işlevin kullanıcı tanımlı bir iletiyi işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Parametreler

*İleti*<br/>
İleti kimliği.

*üyeFxn*<br/>
İletinin eşlendiği ileti işleyiciişlevinin adı.

İşlevin türü `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.

### <a name="remarks"></a>Açıklamalar

Kullanıcı tanımlı iletiler, standart Windows WM_MESSAGE iletileri olmayan iletilerdir. İleti kimliği seçerken, WM_USER (0x0400) ile 0x7FFF veya WM_APP (0x8000) ile 0xBFFF aralığındaki değerleri kullanmanız gerekir. İleti tümleri ile ilgili daha fazla bilgi için [WM_APP.](/windows/win32/winmsg/wm-app)

İleti haritanızda, ileti işleyicisi işlevine eşlenmesi gereken her kullanıcı tanımlı ileti için tam olarak bir ON_MESSAGE makro bildirimi olmalıdır.

> [!NOTE]
> Kullanıcı tanımlı iletilere ek olarak, ON_MESSAGE daha az yaygın Windows iletilerini işler. Daha fazla bilgi için [İleti Haritaları'na](../../mfc/tn006-message-maps.md)bakın.

Daha fazla bilgi ve örnekler için [İleti İşleme ve Haritalama Konuları ve](../../mfc/message-handling-and-mapping.md) Kullanıcı [Tanımlı İşleyiciler'e](user-defined-handlers.md) bakın

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

**Üstbilgi:** afxmsg_.h

## <a name="on_olecmd"></a><a name="on_olecmd"></a>ON_OLECMD

Komutları komut gönderme arabirimi `IOleCommandTarget`üzerinden yönlendirir.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_OLECMD( pguid, olecmdid, commandId )
```

### <a name="parameters"></a>Parametreler

*pguid*<br/>
Komutun ait olduğu komut grubunun tanımlayıcısı. Standart grup için NULL'u kullanın.

*olecmdid*<br/>
OLE komutunun tanımlayıcısı.

*Commandıd*<br/>
Menü kimliği, araç çubuğu kimliği, düğme kimliği veya komutu veren kaynağın veya nesnenin diğer kimliği.

### <a name="remarks"></a>Açıklamalar

`IOleCommandTarget`Bir kapsayıcının Bir DocObject'in kullanıcı arabiriminden kaynaklanan komutları almasına izin verir ve kapsayıcının aynı komutları (Dosya menüsünde Yeni, Aç, Kaydet ve Yazdır; ve Kopyala, Yapıştır, Geri Al ve benzeri) bir DocObject'e göndermesine olanak tanır.

`IOleCommandTarget`OLE Automation'ınkinden `IDispatch`daha basittir. `IOleCommandTarget`tamamen nadiren bağımsız değişkenleri olan standart bir komut kümesine dayanır ve hiçbir tür bilgisi söz konusu değildir (komut bağımsız değişkenleri için de tür güvenliği azalır). Bağımsız değişkenlerle komut göndermeniz gerekiyorsa, [COleServerDoc kullanın::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).

Standart `IOleCommandTarget` menü komutları MFC tarafından aşağıdaki makrolarda uygulanmıştır:

**ON_OLECMD_CLEARSELECTION ( )**

Temizle komutunu edit. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`

**ON_OLECMD_COPY ( )**

Kopyala komutunu edit komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`

**ON_OLECMD_CUT ( )**

Kesik Et komutunu edit komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`

**ON_OLECMD_NEW ( )**

Yeni Dosya komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`

**ON_OLECMD_OPEN ( )**

Dosya Aç komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`

**ON_OLECMD_PAGESETUP ( )**

Dosya Sayfası Kurulumu komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`

**ON_OLECMD_PASTE ( )**

Yapıştır komutunu edit komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`

**ON_OLECMD_PASTESPECIAL ( )**

Yapıştır Özel Yapıştır komutunu edin. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`

**ON_OLECMD_PRINT ( )**

Dosya Yazdırma komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`

**ON_OLECMD_PRINTPREVIEW ( )**

Dosya Yazdırma Önizleme komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`

**ON_OLECMD_REDO ( )**

Yeniden Yap komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`

**ON_OLECMD_SAVE ( )**

Dosya Kaydet komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`

**ON_OLECMD_SAVE_AS ( )**

DosyaYı Farklı Kaydet komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`

**ON_OLECMD_SAVE_COPY_AS ( )**

DosyaYı Kaydet Kopyasını Kopyala komutu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`

**ON_OLECMD_SELECTALL ( )**

Tümünü Seç komutunu Edit'i gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`

**ON_OLECMD_UNDO ( )**

Geri Gönder komutunu edit komutunu gönderir. Şu şekilde uygulanır:

`ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdocob.h

## <a name="on_registered_message"></a><a name="on_registered_message"></a>ON_REGISTERED_MESSAGE

Windows `RegisterWindowMessage` işlevi, sistem genelinde benzersiz olması garanti edilen yeni bir pencere iletisi tanımlamak için kullanılır.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Parametreler

*nMessageVariable*<br/>
Kayıtlı pencere iletisi kimliği değişkeni.

*üyeFxn*<br/>
İletinin eşlendiği ileti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, kayıtlı iletiyi hangi işlevin işleyeceğini gösterir.

Daha fazla bilgi ve örnekler için [İleti İşleme ve Haritalama Konuları'na](../../mfc/message-handling-and-mapping.md)bakın.

### <a name="example"></a>Örnek

```cpp
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));

BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmsg_.h

## <a name="on_registered_thread_message"></a><a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE

Windows RegisterWindowMessage işlevi tarafından kayıtlı iletiyi hangi işlevin işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Parametreler

*nMessageVariable*<br/>
Kayıtlı pencere iletisi kimliği değişkeni.

*üyeFxn*<br/>
İletinin eşlendiği CWinThread ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

RegisterWindowMessage, sistem genelinde benzersiz olması garanti edilen yeni bir pencere iletisini tanımlamak için kullanılır. ON_REGISTERED_THREAD_MESSAGE cwinthread sınıfına sahip olduğunuzda ON_REGISTERED_MESSAGE yerine kullanılmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmsg_.h

## <a name="on_thread_message"></a><a name="on_thread_message"></a>ON_THREAD_MESSAGE

Hangi işlevin kullanıcı tanımlı bir iletiyi işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_THREAD_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Parametreler

*İleti*<br/>
İleti kimliği.

*üyeFxn*<br/>
İletinin `CWinThread`eşlendiği -ileti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

ON_THREAD_MESSAGE `CWinThread` bir sınıf varsa ON_MESSAGE yerine kullanılmalıdır. Kullanıcı tanımlı iletiler, standart Windows WM_MESSAGE iletileri olmayan iletilerdir. İleti haritanızda, ileti işleyicisi işlevine eşlenmesi gereken her kullanıcı tanımlı ileti için tam olarak bir ON_THREAD_MESSAGE makro bildirimi olmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="on_update_command_ui"></a><a name="on_update_command_ui"></a>On_update_command_uı

Bu makro, kullanıcı arabirimi güncelleştirme komut iletisini hangi işlevin işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_UPDATE_COMMAND_UI( messageId, memberFxn )
```

### <a name="parameters"></a>Parametreler

*Messageıd*<br/>
İleti kimliği.

*üyeFxn*<br/>
İletinin eşlendiği ileti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

İleti işleyici işlevine eşlenen her kullanıcı arabirimi güncelleştirme komutu için ileti haritanızda tam olarak bir ON_UPDATE_COMMAND_UI makro bildirimi olmalıdır.

Daha fazla bilgi ve örnekler için [İleti İşleme ve Haritalama Konuları'na](../../mfc/message-handling-and-mapping.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="on_command_range"></a><a name="on_command_range"></a>ON_COMMAND_RANGE

Bitişik bir komut iI dizisini tek bir ileti işleyicisi işleviyle eşlemek için bu makroyu kullanın.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_COMMAND_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Parametreler

*id1*<br/>
Bitişik bir komut kimlikleri aralığının başındaki komut kimliği.

*id2*<br/>
Bitişik bir komut kimlikleri aralığının sonundaki komut kimliği.

*üyeFxn*<br/>
Komutların eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Kimliklerin aralığı *id1* ile başlar ve *id2*ile biter.

Bir dizi komut iÞlesini tek bir üye işlevle eşlemek için ON_COMMAND_RANGE kullanin. Tek bir komutu bir üye işlevle eşlemek için [ON_COMMAND](#on_command) kullanın. Yalnızca bir ileti eşlemi girişi belirli bir komut kimliğiyle eşleşebilir. Diğer bir süre, bir komutu birden fazla işleyiciyle eşleyebilirsiniz. İleti aralıklarını eşleme hakkında daha fazla bilgi için [İleti-Eş Aralığı İşleyicileri'ne](../../mfc/handlers-for-message-map-ranges.md)bakın.

İleti eşlemi aralıkları için otomatik destek yoktur, bu nedenle makroyu kendiniz yerleştirmeniz gerekir.

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

**Üstbilgi:** afxmsg_.h

## <a name="on_update_command_ui_range"></a><a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE

Bitişik bir komut dizisini tek bir güncelleştirme ileti işleyicisi işleviyle eşler.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Parametreler

*id1*<br/>
Bitişik bir komut kimlikleri aralığının başındaki komut kimliği.

*id2*<br/>
Bitişik bir komut kimlikleri aralığının sonundaki komut kimliği.

*üyeFxn*<br/>
Komutların eşlendiği güncelleştirme ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

İleti işleyicilerini güncelleştir komutuyla ilişkili menü öğelerinin ve araç çubuğu düğmelerinin durumunu güncelleştirin. Kimliklerin aralığı *id1* ile başlar ve *id2*ile biter.

İleti eşlemi aralıkları için otomatik destek yoktur, bu nedenle makroyu kendiniz yerleştirmeniz gerekir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmsg_.h

## <a name="on_control_range"></a><a name="on_control_range"></a>ON_CONTROL_RANGE

BN_CLICKED gibi belirli bir Windows bildirim iletisi için bitişik bir denetim ii'leri aralığını tek bir ileti işleyicisi işleviyle eşlemek için bu makroyu kullanın.

### <a name="syntax"></a>Sözdizimi

```cpp
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )
```

### <a name="parameters"></a>Parametreler

*wNotifyCode*<br/>
İşleyicinizin yanıt ladığı bildirim kodu.

*id1*<br/>
Bitişik bir denetim kimliklerinin başındaki komut kimliği.

*id2*<br/>
Bitişik bir denetim kimlikleri aralığının sonundaki komut kimliği.

*üyeFxn*<br/>
Denetimlerin eşlendiği ileti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

Kimliklerin aralığı *id1* ile başlar ve *id2*ile biter. İşleyici, eşlenen denetimlerden herhangi birinden gelen belirtilen bildirim için çağrılır.

İleti eşlemi aralıkları için otomatik destek yoktur, bu nedenle makroyu kendiniz yerleştirmeniz gerekir.

Bir dizi denetim işletmesi için işleyici fonksiyonlarının uygulanması hakkında daha fazla bilgi için [Ileti- Harita Araştırları işleyicilerine](../../mfc/handlers-for-message-map-ranges.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmsg_.h

## <a name="see-also"></a>Ayrıca bkz.

[On_command](message-map-macros-mfc.md#on_command)<br/>
[TN006: İleti Eşlemeleri](../tn006-message-maps.md)<br/>
[COleCmdUI Sınıfı](colecmdui-class.md)<br/>
[COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)<br/>
[RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew)<br/>
[Kullanıcı Tanımlı İşleyiciler](user-defined-handlers.md)<br/>
[CCmdUI Sınıfı](ccmdui-class.md)
