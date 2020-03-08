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
ms.openlocfilehash: b88b745e3b70cf030f77f247ab03cd69d910109f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855644"
---
# <a name="message-map-macros-mfc"></a>İleti Eşleme Makroları (MFC)

İleti eşlemelerini desteklemek için MFC aşağıdaki makroları sağlar:

### <a name="message-map-declaration-and-demarcation-macros"></a>İleti eşleme bildirimi ve demarcation makroları

|||
|-|-|
|[DECLARE_MESSAGE_MAP](#declare_message_map)|İleti eşlemesinin, iletileri işlevlere eşlemek için bir sınıfta kullanılacağını bildirir (sınıf bildiriminde kullanılması gerekir).|
|[BEGIN_MESSAGE_MAP](#begin_message_map)|İleti eşlemesinin tanımını başlatır (sınıf uygulamasında kullanılması gerekir).|
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_message_map)|Tek bir şablon bağımsız değişkeni içeren bir sınıf türündeki bir ileti eşlemesinin tanımına başlar. |
|[END_MESSAGE_MAP](#end_message_map)|İleti eşlemesinin tanımını sonlandırır (sınıf uygulamasında kullanılması gerekir).|

### <a name="message-mapping-macros"></a>İleti eşleme makroları

|||
|-|-|
|[ON_COMMAND](#on_command)|Hangi işlevin belirtilen komut iletisini işleyeceğini gösterir.|
|[ON_COMMAND_EX](#on_command_ex)|Hangi işlevin belirtilen komut iletisini işleyeceğini gösterir.|
|[ON_CONTROL](#on_control)|Hangi işlevin belirtilen denetim bildirim iletisini işleyeceğini gösterir.|
|[ON_MESSAGE](#on_message)|Hangi işlevin Kullanıcı tanımlı bir iletiyi işleyeceğini gösterir.|
|[ON_OLECMD](#on_olecmd)|Bir DocObject veya kapsayıcısından bir menü komutunu hangi işlevin işleyeceğini gösterir.|
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Hangi işlevin kayıtlı Kullanıcı tanımlı bir iletiyi işleyeceğini gösterir.|
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Bir `CWinThread` sınıfınız olduğunda, kayıtlı Kullanıcı tanımlı iletiyi hangi işlevin işleyeceğini gösterir.|
|[ON_THREAD_MESSAGE](#on_thread_message)|Bir `CWinThread` sınıfınız olduğunda, Kullanıcı tanımlı bir iletiyi hangi işlevin işleyeceğini gösterir.|
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Hangi işlevin belirtilen kullanıcı arabirimi güncelleştirme komut iletisini işleyeceğini gösterir.|

### <a name="message-map-range-macros"></a>İleti eşleme aralığı makroları

|||
|-|-|
|[ON_COMMAND_RANGE](#on_command_range)|Hangi işlevin, makroya yönelik ilk iki parametrede belirtilen komut kimliği aralığını işleyeceğini gösterir.|
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Hangi güncelleştirme işleyicisinin, makroya yönelik ilk iki parametrede belirtilen komut kimliği aralığını işleyeceğini gösterir.|
|[ON_CONTROL_RANGE](#on_control_range)|Hangi işlevin, ikinci ve üçüncü parametrelerinde belirtilen denetim kimliği aralığından gelen bildirimleri makroya işleyeceğini gösterir. İlk parametre, BN_CLICKED gibi bir denetim bildirim iletisidir.|

İleti haritaları, ileti eşleme bildirimi ve düzenleme makroları ile ileti eşleme makroları hakkında daha fazla bilgi için bkz. [ileti haritaları](../../mfc/reference/message-maps-mfc.md) ve [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md). İleti eşleme aralıkları hakkında daha fazla bilgi için bkz. [Ileti eşleme aralıkları Için işleyiciler](../../mfc/handlers-for-message-map-ranges.md).

## <a name="begin_message_map"></a>BEGIN_MESSAGE_MAP

İleti haritaınızın tanımını başlatır.

### <a name="syntax"></a>Sözdizimi

```
BEGIN_MESSAGE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
İleti eşlemesi bu olan sınıfın adını belirtir.

*baseClass*<br/>
Sınıfın temel sınıfının adını *belirtir.*

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevlerini tanımlayan uygulama (. cpp) dosyasında, ileti haritasını BEGIN_MESSAGE_MAP makroyla başlatın, ardından ileti işleyici işlevlerinizin her biri için makro girişleri ekleyin ve ileti haritasını END_MESSAGE_MAP ile doldurun makroya.

İleti haritaları hakkında daha fazla bilgi için bkz. [Ileti haritaları](message-maps-mfc.md)

### <a name="example"></a>Örnek

```cpp
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP

Tek bir şablon bağımsız değişkeni içeren bir sınıf türündeki bir ileti eşlemesinin tanımına başlar.

### <a name="syntax"></a>Sözdizimi

```
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
İleti eşlemesi bu olan sınıfın adını belirtir.

*type_name*<br/>
Sınıf için belirtilen şablon parametresinin adı.

*baseClass*<br/>
Sınıfın temel sınıfının adını *belirtir.*

### <a name="remarks"></a>Açıklamalar

Bu makro [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) makroya benzerdir; Ancak, bu makro tek bir şablon bağımsız değişkeni içeren sınıflar için tasarlanmıştır.

Sınıfınızın Yöntem uygulama bölümünde, ileti haritasını BEGIN_TEMPLATE_MESSAGE_MAP makrosu ile başlatın; ardından, standart ileti haritasında yaptığınız gibi her ileti işleyici yöntemlerinizin makro girdilerini ekleyin. BEGIN_MESSAGE_MAP makrosunda olduğu gibi, şablon ileti haritasını [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) makroyla doldurun.

Şablon sınıfları için ileti haritaları uygulama hakkında daha fazla bilgi için bkz. [nasıl yapılır: bir şablon sınıfı Için Ileti eşlemesi oluşturma](../how-to-create-a-message-map-for-a-template-class.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="declare_message_map"></a>DECLARE_MESSAGE_MAP

Sınıfın bir ileti eşlemesini tanımladığını bildirir. Programınızdaki her bir `CCmdTarget`türetilmiş sınıfın iletileri işlemek için bir ileti eşlemesi sağlaması gerekir.

### <a name="syntax"></a>Sözdizimi

```
DECLARE_MESSAGE_MAP( )
```

### <a name="remarks"></a>Açıklamalar

Sınıf bildirimindeki sonundaki DECLARE_MESSAGE_MAP makrosunu kullanın. Ardından, sınıfının üye işlevlerini tanımlayan. cpp dosyasında, ileti işleyici işlevlerinizin her biri için BEGIN_MESSAGE_MAP makrosunu, makro girişlerini ve END_MESSAGE_MAP makrosunu kullanın.

> [!NOTE]
>  DECLARE_MESSAGE_MAP sonra herhangi bir üye bildirirseniz, bunlar için yeni bir erişim türü (**genel**, **özel**veya **korumalı**) belirtmeniz gerekir.

İleti haritaları ve DECLARE_MESSAGE_MAP makrosu hakkında daha fazla bilgi için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Örnek

```cpp
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="end_message_map"></a>END_MESSAGE_MAP

İleti haritaınızın tanımını sonlandırır.

### <a name="syntax"></a>Sözdizimi

```
END_MESSAGE_MAP( )
```

### <a name="remarks"></a>Açıklamalar

İleti haritaları ve END_MESSAGE_MAP makrosu hakkında daha fazla bilgi için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="on_command"></a>ON_COMMAND

Bu makro bir komut iletisini bir üye işlevine eşler.

### <a name="syntax"></a>Sözdizimi

```
ON_COMMAND( commandId, memberFxn )
```

### <a name="parameters"></a>Parametreler

*CommandID*<br/>
Komut KIMLIĞI.

*memberFxn*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu, bir menü öğesi veya araç çubuğu düğmesi gibi bir komut Kullanıcı arabirimi nesnesinden komut iletisini hangi işlevin işleyeceğini gösterir.

Bir komut hedefi nesnesi belirtilen KIMLIĞE sahip bir Windows WM_COMMAND iletisi aldığında, ON_COMMAND, iletiyi işlemek için `memberFxn` üye işlevini çağırır.

Tek bir komutu bir üye işlevine eşlemek için ON_COMMAND kullanın. Bir komut kimliği aralığını tek bir üye işlevine eşlemek için [ON_COMMAND_RANGE](#on_command_range) kullanın. Yalnızca bir ileti eşleme girişi, belirli bir komut KIMLIĞIYLE eşleşir. Diğer bir deyişle, bir komutu birden fazla işleyiciyle eşleyemezsiniz. Daha fazla bilgi ve örnek için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Örnek

```cpp
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxmsg_. h

## <a name="on_command_ex"></a>ON_COMMAND_EX

Genişletilmiş komut işleyici üye işlevi.

### <a name="syntax"></a>Sözdizimi

```
ON_COMMAND_EX(commandId, memberFxn);
```

### <a name="parameters"></a>Parametreler

*CommandID*<br/>
Komut KIMLIĞI.

*memberFxn*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Gelişmiş kullanımlar için komut iletisi işleyicilerinin genişletilmiş bir biçimi vardır. ON_COMMAND_EX makro bu tür ileti işleyicileri için kullanılır ve [ON_COMMAND](message-map-macros-mfc.md#on_command) işlevselliğinin bir üst kümesini sağlar. Genişletilmiş komut işleyici üye işlevleri tek bir parametre, komut KIMLIĞINI içeren bir UINT alır ve BOOL döndürür. Komutun işlendiğini göstermek için dönüş değeri TRUE olmalıdır; Aksi takdirde yönlendirme diğer komut hedef nesnelerine devam eder.

Daha fazla bilgi için bkz. Teknik notun [TN006: Ileti haritaları] tm006-Message-maps.md).

### <a name="requirements"></a>Gereksinimler

Üst bilgi dosyası: afxmsg_. h

## <a name="on_control"></a>ON_CONTROL

Hangi işlevin özel denetim bildirim iletisini işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```
ON_CONTROL( wNotifyCode, commandId, memberFxn )
```

### <a name="parameters"></a>Parametreler

*wNotifyCode*<br/>
Denetimin bildirim kodu.

*CommandID*<br/>
Komut KIMLIĞI.

*memberFxn*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Denetim bildirim iletileri, bir denetimden ana pencereye gönderilen olanlardır.

İleti eşleminizde bir ileti işleyicisi işlevine eşlenmesi gereken her denetim bildirim iletisi için tam olarak bir ON_CONTROL makro bildirimi olmalıdır.

Daha fazla bilgi ve örnek için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxmsg_. h

## <a name="on_message"></a>ON_MESSAGE

Hangi işlevin Kullanıcı tanımlı bir iletiyi işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```
ON_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Parametreler

*message*<br/>
İleti kimliği.

*memberFxn*<br/>
İletinin eşlendiği ileti işleyicisi işlevinin adı.

İşlevin türü `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`olmalıdır.

### <a name="remarks"></a>Açıklamalar

Kullanıcı tanımlı iletiler, standart Windows WM_MESSAGE iletileri olmayan iletilerdir. Bir ileti KIMLIĞI seçerken, WM_USER (0x0400) aralığındaki değerleri 0x7FFF veya WM_APP (0x8000) ile 0xBFFF arasında kullanmanız gerekir. İleti kimlikleri hakkında daha fazla bilgi için bkz. [WM_APP](/windows/win32/winmsg/wm-app).

İleti eşleminizde, bir ileti işleyicisi işlevine eşlenmesi gereken her kullanıcı tanımlı ileti için tam olarak bir ON_MESSAGE makro bildirisi olmalıdır.

> [!NOTE]
>  Kullanıcı tanımlı iletilere ek olarak ON_MESSAGE daha az yaygın Windows iletilerini işler. Daha fazla bilgi için bkz. [Ileti haritaları](../../mfc/tn006-message-maps.md).

Daha fazla bilgi ve örnek için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md) ve [Kullanıcı tanımlı işleyiciler](user-defined-handlers.md)

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

**Üst bilgi:** afxmsg_. h

## <a name="on_olecmd"></a>ON_OLECMD

Komutları komut gönderme arabirimi `IOleCommandTarget`aracılığıyla yönlendirir.

### <a name="syntax"></a>Sözdizimi

```
ON_OLECMD( pguid, olecmdid, commandId )
```

### <a name="parameters"></a>Parametreler

*PGUID*<br/>
Komutun ait olduğu komut grubunun tanımlayıcısı. Standart grup için NULL değerini kullanın.

*OLECMDID*<br/>
OLE komutunun tanımlayıcısı.

*CommandID*<br/>
Menü KIMLIĞI, araç çubuğu KIMLIĞI, düğme KIMLIĞI veya komutu veren kaynağın veya nesnenin diğer KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

`IOleCommandTarget`, bir kapsayıcının bir DocObject kullanıcı arabiriminden kaynaklanan komutları almasına izin verir ve kapsayıcının aynı komutları (örneğin, Dosya menüsünde Yeni, aç, SaveAs ve Yazdır) göndermesini ve düzenleme menüsünü bir DocObject 'e kopyalamasını, yapıştırmayı, geri almasını ve devam etmesine izin verir.

`IOleCommandTarget` OLE otomasyonunun `IDispatch`daha basittir. `IOleCommandTarget`, genellikle bağımsız değişkenlere sahip olan standart bir komut kümesine bağlıdır ve hiçbir tür bilgisi dahil değildir (tür güvenliği, komut bağımsız değişkenleri için de düşer). Komutların bağımsız değişkenlerle birlikte dağıtım yapması gerekiyorsa [Copaserverdoc:: Onexecoelcmd](coleserverdoc-class.md#onexecolecmd)kullanın.

`IOleCommandTarget` standart menü komutları aşağıdaki makrolarda MFC tarafından uygulandı:

**ON_OLECMD_CLEARSELECTION ()**

Düzenle Clear komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`

**ON_OLECMD_COPY ()**

Kopyalama Düzenle komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`

**ON_OLECMD_CUT ()**

Kes Düzenle komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`

**ON_OLECMD_NEW ()**

Dosya yeni komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`

**ON_OLECMD_OPEN ()**

Dosya Aç komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`

**ON_OLECMD_PAGESETUP ()**

Dosya sayfası kurulum komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`

**ON_OLECMD_PASTE ()**

Yapıştırmayı Düzenle komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`

**ON_OLECMD_PASTESPECIAL ()**

Düzenleme Özel Yapıştır komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`

**ON_OLECMD_PRINT ()**

Dosya Print komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`

**ON_OLECMD_PRINTPREVIEW ()**

Dosya Baskı Önizleme komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`

**ON_OLECMD_REDO ()**

Edit Yinele komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`

**ON_OLECMD_SAVE ()**

Dosya Kaydet komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`

**ON_OLECMD_SAVE_AS ()**

Dosya farklı Kaydet komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`

**ON_OLECMD_SAVE_COPY_AS ()**

Dosya kopyasını Kaydet komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`

**ON_OLECMD_SELECTALL ()**

Düzenle Tümünü Seç komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`

**ON_OLECMD_UNDO ()**

Düzenle geri al komutunu dağıtır. Uygulanan:

`ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdocob. h

## <a name="on_registered_message"></a>ON_REGISTERED_MESSAGE

Windows `RegisterWindowMessage` işlevi, sistem genelinde benzersiz olması garanti edilen yeni bir pencere iletisi tanımlamak için kullanılır.

### <a name="syntax"></a>Sözdizimi

```
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Parametreler

*nMessageVariable*<br/>
Kayıtlı pencere-ileti KIMLIĞI değişkeni.

*memberFxn*<br/>
İletinin eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, kayıtlı iletiyi hangi işlevin işleyeceğini gösterir.

Daha fazla bilgi ve örnek için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Örnek

```cpp
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));

BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxmsg_. h

## <a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE

Windows RegisterWindowMessage işlevi tarafından kaydedilen iletiyi hangi işlevin işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Parametreler

*nMessageVariable*<br/>
Kayıtlı pencere-ileti KIMLIĞI değişkeni.

*memberFxn*<br/>
İletinin eşlendiği CWinThread-Message-Handler işlevinin adı.

### <a name="remarks"></a>Açıklamalar

RegisterWindowMessage, sistem genelinde benzersiz olması garanti edilen yeni bir pencere iletisi tanımlamak için kullanılır. Bir CWinThread sınıfınız olduğunda ON_REGISTERED_THREAD_MESSAGE ON_REGISTERED_MESSAGE yerine kullanılmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxmsg_. h

## <a name="on_thread_message"></a>ON_THREAD_MESSAGE

Hangi işlevin Kullanıcı tanımlı bir iletiyi işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```
ON_THREAD_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Parametreler

*message*<br/>
İleti kimliği.

*memberFxn*<br/>
İletinin eşlendiği `CWinThread`-Message-Handler işlevinin adı.

### <a name="remarks"></a>Açıklamalar

`CWinThread` sınıfınız olduğunda ON_MESSAGE yerine ON_THREAD_MESSAGE kullanılmalıdır. Kullanıcı tanımlı iletiler, standart Windows WM_MESSAGE iletileri olmayan iletilerdir. İleti eşleminizde, bir ileti işleyicisi işlevine eşlenmesi gereken her kullanıcı tanımlı ileti için tam olarak bir ON_THREAD_MESSAGE makro bildirisi olmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="on_update_command_ui"></a>ON_UPDATE_COMMAND_UI

Bu makro, Kullanıcı arabirimi güncelleştirme komut iletisini hangi işlevin işleyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```
ON_UPDATE_COMMAND_UI( messageId, memberFxn )
```

### <a name="parameters"></a>Parametreler

*Ileti*<br/>
İleti kimliği.

*memberFxn*<br/>
İletinin eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

İleti eşleminizde bir ileti işleyicisi işlevine eşlenmesi gereken her kullanıcı arabirimi güncelleştirme komutu için tam olarak bir ON_UPDATE_COMMAND_UI makro bildirisi olmalıdır.

Daha fazla bilgi ve örnek için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="on_command_range"></a>ON_COMMAND_RANGE

Bitişik bir komut kimliği aralığını tek bir ileti işleyicisi işlevine eşlemek için bu makroyu kullanın.

### <a name="syntax"></a>Sözdizimi

```
ON_COMMAND_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Parametreler

*ID1*<br/>
Komut kimliklerinin bitişik aralığının başındaki komut KIMLIĞI.

*ID2*<br/>
Komut kimliklerinin bitişik aralığının sonundaki komut KIMLIĞI.

*memberFxn*<br/>
Komutların eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Kimlik aralığı *ID1* ile başlar ve *ID2*ile biter.

Bir komut kimliği aralığını tek bir üye işlevine eşlemek için ON_COMMAND_RANGE kullanın. Tek bir komutu bir üye işlevine eşlemek için [ON_COMMAND](#on_command) kullanın. Yalnızca bir ileti eşleme girişi, belirli bir komut KIMLIĞIYLE eşleşir. Diğer bir deyişle, bir komutu birden fazla işleyiciyle eşleyemezsiniz. İleti aralıklarını eşleme hakkında daha fazla bilgi için bkz. [Ileti eşleme aralıkları Için işleyiciler](../../mfc/handlers-for-message-map-ranges.md).

İleti eşleme aralıkları için otomatik destek yoktur, bu nedenle makroyu kendiniz yerleştirmeniz gerekir.

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

**Üst bilgi:** afxmsg_. h

## <a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE

Bitişik bir komut kimliği aralığını tek bir güncelleştirme ileti işleyicisi işlevine eşler.

### <a name="syntax"></a>Sözdizimi

```
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Parametreler

*ID1*<br/>
Komut kimliklerinin bitişik aralığının başındaki komut KIMLIĞI.

*ID2*<br/>
Komut kimliklerinin bitişik aralığının sonundaki komut KIMLIĞI.

*memberFxn*<br/>
Komutların eşlendiği güncelleştirme iletisi işleyici işlevinin adı.

### <a name="remarks"></a>Açıklamalar

İleti işleyicilerini güncelleştirme, komutla ilişkili menü öğelerinin ve araç çubuğu düğmelerinin durumunu güncelleştirir. Kimlik aralığı *ID1* ile başlar ve *ID2*ile biter.

İleti eşleme aralıkları için otomatik destek yoktur, bu nedenle makroyu kendiniz yerleştirmeniz gerekir.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxmsg_. h

## <a name="on_control_range"></a>ON_CONTROL_RANGE

BN_CLICKED gibi belirli bir Windows bildirim iletisi için bir dizi denetim kimliğini tek bir ileti işleyicisi işleviyle eşlemek için bu makroyu kullanın.

### <a name="syntax"></a>Sözdizimi

```
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )
```

### <a name="parameters"></a>Parametreler

*wNotifyCode*<br/>
İşleyicinizin yanıt verdiği bildirim kodu.

*ID1*<br/>
Bitişik denetim kimliği aralığının başındaki komut KIMLIĞI.

*ID2*<br/>
Bitişik denetim kimliği aralığının sonundaki komut KIMLIĞI.

*memberFxn*<br/>
Denetimlerin eşlendiği ileti işleyicisi işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Kimlik aralığı *ID1* ile başlar ve *ID2*ile biter. İşleyici, eşlenen denetimlerden herhangi birinden gelen belirtilen bildirim için çağırılır.

İleti eşleme aralıkları için otomatik destek yoktur, bu nedenle makroyu kendiniz yerleştirmeniz gerekir.

Bir dizi denetim kimliği için işleyici işlevlerini uygulama hakkında daha fazla bilgi için, [Ileti eşleme aralıkları Için işleyiciler](../../mfc/handlers-for-message-map-ranges.md)bölümüne bakın.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxmsg_. h

## <a name="see-also"></a>Ayrıca bkz.

[ON_COMMAND](message-map-macros-mfc.md#on_command)<br/>
[TN006: İleti Eşlemeleri](../tn006-message-maps.md)<br/>
[COleCmdUI Sınıfı](colecmdui-class.md)<br/>
[Copaserverdoc:: Onexecoelcmd](coleserverdoc-class.md#onexecolecmd)<br/>
[RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew)<br/>
[Kullanıcı Tanımlı İşleyiciler](user-defined-handlers.md)<br/>
[CCmdUI Sınıfı](ccmdui-class.md)
