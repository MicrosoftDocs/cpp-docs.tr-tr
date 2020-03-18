---
title: Bileşik denetim genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
ms.openlocfilehash: 525fc01247053a1e2bc993398978cb332262a1a5
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417784"
---
# <a name="composite-control-global-functions"></a>Bileşik denetim genel Işlevleri

Bu işlevler, iletişim kutuları oluşturma ve ActiveX denetimleri oluşturma, barındırma ve lisanslama için destek sağlar.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan kalıcı bir iletişim kutusu oluşturur. Elde edilen iletişim kutusu, ActiveX denetimleri içerebilir.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan modsuz bir iletişim kutusu oluşturur. Elde edilen iletişim kutusu, ActiveX denetimleri içerebilir.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Bir ActiveX denetimi oluşturur, onu başlatır, belirtilen pencerede barındırır ve denetimden bir arabirim işaretçisi (veya işaretçiler) alır.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır, belirtilen pencerede barındırır ve denetimden bir arabirim işaretçisi (veya işaretçiler) alır.|
|[AtlAxAttachControl](#atlaxattachcontrol)|Önceden oluşturulmuş bir denetimi belirtilen pencereye ekler.|
|[AtlAxGetHost](#atlaxgethost)|Belirli bir pencere için (varsa), kapsayıcısına doğrudan bir arabirim işaretçisi elde etmek için kullanılır (varsa).|
|[AtlAxGetControl](#atlaxgetcontrol)|Belirtilen bir pencere içinde (varsa) yer alan denetime (varsa) doğrudan bir arabirim işaretçisi elde etmek için kullanılır.|
|[AtlSetChildSite](#atlsetchildsite)|Alt sitenin `IUnknown` başlatır.|
|[AtlAxWinInit](#atlaxwininit)|AxWin nesneleri için barındırma kodunu başlatır.|
|[AtlAxWinTerm](#atlaxwinterm)|AxWin nesneleri için barındırma kodunu başlatır.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Bir nesnenin varsayılan kaynak arabirimiyle ilgili bilgileri döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atlhost. h

##  <a name="atlaxdialogbox"></a>AtlAxDialogBox

Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan kalıcı bir iletişim kutusu oluşturur.

```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
'ndaki Çalıştırılabilir dosyası iletişim kutusu şablonunu içeren modülün bir örneğini tanımlar.

*lpTemplateName*<br/>
'ndaki İletişim kutusu şablonunu tanımlar. Bu parametre, iletişim kutusu şablonunun adını belirten null ile sonlandırılmış bir karakter dizesinin işaretçisi veya iletişim kutusu şablonunun kaynak tanımlayıcısını belirten bir tamsayı değeridir. Parametresi bir kaynak tanımlayıcısı belirtiyorsa, yüksek sıralı sözcük sıfır olmalıdır ve alt sıra sözcüğü tanımlayıcıyı içermelidir. Bu değeri oluşturmak için [Makeintresource](/windows/win32/api/winuser/nf-winuser-makeintresourcew) makrosunu kullanabilirsiniz.

*hWndParent*<br/>
'ndaki İletişim kutusunun sahibi olan pencereyi tanımlar.

*lpDialogProc*<br/>
'ndaki İletişim kutusu yordamına işaret eder. İletişim kutusu yordamı hakkında daha fazla bilgi için bkz. [DialogProc](/windows/win32/api/winuser/nc-winuser-dlgproc).

*dwInitParam*<br/>
'ndaki WM_INITDIALOG iletisinin *lParam* parametresindeki iletişim kutusuna geçirilecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bir ActiveX denetimi içeren bir iletişim kutusu şablonuyla `AtlAxDialogBox` kullanmak için, iletişim kaynağının **Denetim** bölümünün *metin* alanı olarak GEÇERLI bir CLSID, AppID veya URL dizesi belirtin ve aynı bölümde *sınıf adı* alanı olarak "AtlAxWin80" ile birlikte "" kullanın. Aşağıda geçerli bir **Denetim** bölümünün nasıl görünebileceğini gösterilmektedir:

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

Kaynak betikleri düzenlemeyle ilgili daha fazla bilgi için bkz. [nasıl yapılır: kaynak betik dosyasını metin biçiminde açma](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Denetim kaynak tanımı deyimleri hakkında daha fazla bilgi için, Windows SDK: SDK Tools altındaki [ortak denetim parametrelerine](/windows/win32/menurc/common-control-parameters) bakın.

Genel içindeki iletişim kutuları hakkında daha fazla bilgi için, Windows SDK ' de [DialogBox](/windows/win32/api/winuser/nf-winuser-dialogboxw) ve [CreateDialogParam](/windows/win32/api/winuser/nf-winuser-createdialogparamw) ' a bakın.

##  <a name="atlaxcreatedialog"></a>AtlAxCreateDialog

Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan modsuz bir iletişim kutusu oluşturur.

```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
'ndaki Çalıştırılabilir dosyası iletişim kutusu şablonunu içeren modülün bir örneğini tanımlar.

*lpTemplateName*<br/>
'ndaki İletişim kutusu şablonunu tanımlar. Bu parametre, iletişim kutusu şablonunun adını belirten null ile sonlandırılmış bir karakter dizesinin işaretçisi veya iletişim kutusu şablonunun kaynak tanımlayıcısını belirten bir tamsayı değeridir. Parametresi bir kaynak tanımlayıcısı belirtiyorsa, yüksek sıralı sözcük sıfır olmalıdır ve alt sıra sözcüğü tanımlayıcıyı içermelidir. Bu değeri oluşturmak için [Makeintresource](/windows/win32/api/winuser/nf-winuser-makeintresourcew) makrosunu kullanabilirsiniz.

*hWndParent*<br/>
'ndaki İletişim kutusunun sahibi olan pencereyi tanımlar.

*lpDialogProc*<br/>
'ndaki İletişim kutusu yordamına işaret eder. İletişim kutusu yordamı hakkında daha fazla bilgi için bkz. [DialogProc](/windows/win32/api/winuser/nc-winuser-dlgproc).

*dwInitParam*<br/>
'ndaki WM_INITDIALOG iletisinin *lParam* parametresindeki iletişim kutusuna geçirilecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Elde edilen iletişim kutusu, ActiveX denetimleri içerebilir.

Windows SDK [CreateDialog](/windows/win32/api/winuser/nf-winuser-createdialogw) ve [CreateDialogParam](/windows/win32/api/winuser/nf-winuser-createdialogparamw) ' a bakın.

##  <a name="atlaxcreatecontrol"></a>AtlAxCreateControl

Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Denetime geçirilecek dizeye yönelik bir işaretçi. Aşağıdaki yollarla biçimlendirilmelidir:

- `"MSCAL.Calendar.7"` gibi bir ProgID

- `"{8E27C92B-1264-101C-8A2F-040224009C02}"` gibi bir CLSID

- `"<https://www.microsoft.com>"` gibi bir URL

- `"file://\\\Documents\MyDoc.doc"` gibi etkin bir belgeye yönelik bir başvuru

- `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"` gibi bir HTML parçası

   > [!NOTE]
   > `"MSHTML:"`, bir MSHTML akışı olarak belirlenmiş olması için HTML parçasının önüne gelmelidir.

*lendiği*<br/>
'ndaki Denetimin iliştirilecektir pencerenin tutamacı.

*pStream*<br/>
'ndaki Denetimin özelliklerini başlatmak için kullanılan akışa yönelik bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
dışı Kapsayıcının `IUnknown` alacak bir işaretçinin adresi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bu genel işlev, [AtlAxCreateControlEx](#atlaxcreatecontrolex)(*lpszName*, *HWND*, *pStream*, null, null, null, null), çağırma ile aynı sonucu verir;.

Lisanslı bir ActiveX denetimi oluşturmak için bkz. [AtlAxCreateControlLic](#atlaxcreatecontrollic).

##  <a name="atlaxcreatecontrolex"></a>AtlAxCreateControlEx

Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır. Yeni denetim için bir arabirim işaretçisi ve olay havuzu da oluşturulabilir.

```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Denetime geçirilecek dizeye yönelik bir işaretçi. Aşağıdaki yollarla biçimlendirilmelidir:

- `"MSCAL.Calendar.7"` gibi bir ProgID

- `"{8E27C92B-1264-101C-8A2F-040224009C02}"` gibi bir CLSID

- `"<https://www.microsoft.com>"` gibi bir URL

- `"file://\\\Documents\MyDoc.doc"` gibi etkin bir belgeye yönelik bir başvuru

- `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"` gibi bir HTML parçası

   > [!NOTE]
   > `"MSHTML:"`, bir MSHTML akışı olarak belirlenmiş olması için HTML parçasının önüne gelmelidir.

*lendiği*<br/>
'ndaki Denetimin iliştirilecektir pencerenin tutamacı.

*pStream*<br/>
'ndaki Denetimin özelliklerini başlatmak için kullanılan akışa yönelik bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
dışı Kapsayıcının `IUnknown` alacak bir işaretçinin adresi. NULL olabilir.

*ppUnkControl*<br/>
dışı Oluşturulan denetimin `IUnknown` alacak olan işaretçinin adresi. NULL olabilir.

*ııdsink*<br/>
Kapsanan nesnedeki bir giden arabirimin arabirim tanımlayıcısı.

*punkSink*<br/>
Kapsanan nesne başarıyla oluşturulduktan sonra kapsanan nesnede *ııdsink* tarafından belirtilen bağlantı noktasına bağlanacak havuz nesnesinin `IUnknown` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlAxCreateControlEx`, [AtlAxCreateControl](#atlaxcreatecontrol) ile benzerdir, ancak yeni oluşturulan denetime bir arabirim işaretçisi almanıza ve denetim tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak sağlar.

Lisanslı bir ActiveX denetimi oluşturmak için bkz. [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).

##  <a name="atlaxcreatecontrollic"></a>AtlAxCreateControlLic

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Denetime geçirilecek dizeye yönelik bir işaretçi. Aşağıdaki yollarla biçimlendirilmelidir:

- `"MSCAL.Calendar.7"` gibi bir ProgID

- `"{8E27C92B-1264-101C-8A2F-040224009C02}"` gibi bir CLSID

- `"<https://www.microsoft.com>"` gibi bir URL

- `"file://\\\Documents\MyDoc.doc"` gibi etkin bir belgeye yönelik bir başvuru

- `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"` gibi bir HTML parçası

   > [!NOTE]
   > `"MSHTML:"`, bir MSHTML akışı olarak belirlenmiş olması için HTML parçasının önüne gelmelidir.

*lendiği*<br/>
Denetimin iliştirilecektir pencerenin tutamacı.

*pStream*<br/>
Denetimin özelliklerini başlatmak için kullanılan akışa yönelik bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
Kapsayıcının `IUnknown` alacak bir işaretçinin adresi. NULL olabilir.

*Bstrlik*<br/>
Denetimin lisansını içeren BSTR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="example"></a>Örnek

`AtlAxCreateControlLic`nasıl kullanacağınızı gösteren bir örnek için bkz. [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) .

##  <a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır. Yeni denetim için bir arabirim işaretçisi ve olay havuzu da oluşturulabilir.

```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Denetime geçirilecek dizeye yönelik bir işaretçi. Aşağıdaki yollarla biçimlendirilmelidir:

- `"MSCAL.Calendar.7"` gibi bir ProgID

- `"{8E27C92B-1264-101C-8A2F-040224009C02}"` gibi bir CLSID

- `"<https://www.microsoft.com>"` gibi bir URL

- `"file://\\\Documents\MyDoc.doc"` gibi etkin bir belgeye yönelik bir başvuru

- `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"` gibi bir HTML parçası

   > [!NOTE]
   > `"MSHTML:"`, bir MSHTML akışı olarak belirlenmiş olması için HTML parçasının önüne gelmelidir.

*lendiği*<br/>
Denetimin iliştirilecektir pencerenin tutamacı.

*pStream*<br/>
Denetimin özelliklerini başlatmak için kullanılan akışa yönelik bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
Kapsayıcının `IUnknown` alacak bir işaretçinin adresi. NULL olabilir.

*ppUnkControl*<br/>
dışı Oluşturulan denetimin `IUnknown` alacak olan işaretçinin adresi. NULL olabilir.

*ııdsink*<br/>
Kapsanan nesnedeki bir giden arabirimin arabirim tanımlayıcısı.

*punkSink*<br/>
Kapsanan nesne başarıyla oluşturulduktan sonra kapsanan nesnede *ııdsink* tarafından belirtilen bağlantı noktasına bağlanacak havuz nesnesinin `IUnknown` arabirimine yönelik bir işaretçi.

*Bstrlik*<br/>
Denetimin lisansını içeren BSTR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlAxCreateControlLicEx`, [AtlAxCreateControlLic](#atlaxcreatecontrollic) ile benzerdir, ancak yeni oluşturulan denetime bir arabirim işaretçisi almanıza ve denetim tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak sağlar.

### <a name="example"></a>Örnek

`AtlAxCreateControlLicEx`nasıl kullanacağınızı gösteren bir örnek için bkz. [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) .

##  <a name="atlaxattachcontrol"></a>AtlAxAttachControl

Önceden oluşturulmuş bir denetimi belirtilen pencereye ekler.

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
'ndaki Denetimin `IUnknown` bir işaretçisi.

*lendiği*<br/>
'ndaki Denetimi barındıracak pencereyi işleyin.

*ppUnkContainer*<br/>
dışı Kapsayıcı nesnesinin `IUnknown` işaretçiye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Aynı anda bir denetim oluşturmak ve eklemek için [AtlAxCreateControlEx](#atlaxcreatecontrolex) ve [AtlAxCreateControl](#atlaxcreatecontrol) kullanın.

> [!NOTE]
>  `AtlAxAttachControl`çağrılmadan önce iliştirilmekte olan denetim nesnesinin doğru şekilde başlatılmış olması gerekir.

##  <a name="atlaxgethost"></a>AtlAxGetHost

Belirli bir pencere için (varsa), kapsayıcıya tanıtıcısını göz önünde bulundurarak doğrudan bir arabirim işaretçisi alır.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Parametreler

*olsun*<br/>
'ndaki Denetimi barındıran pencereye yönelik bir tanıtıcı.

*Sy*<br/>
dışı Denetim kapsayıcısının `IUnknown`.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="atlaxgetcontrol"></a>AtlAxGetControl

Belirli bir pencere içinde yer alan denetim için, tanıcısını göz önünde bulundurarak doğrudan arabirim işaretçisi alır.

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Parametreler

*olsun*<br/>
'ndaki Denetimi barındıran pencereye yönelik bir tanıtıcı.

*Sy*<br/>
dışı Barındırılmakta olan denetimin `IUnknown`.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="atlsetchildsite"></a>AtlSetChildSite

Alt nesnenin sitesini üst nesnenin `IUnknown` ayarlamak için bu işlevi çağırın.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>Parametreler

*punkChild*<br/>
'ndaki Alt öğenin `IUnknown` arabirimine yönelik bir işaretçi.

*punkParent*<br/>
'ndaki Üst öğenin `IUnknown` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="atlaxwininit"></a>AtlAxWinInit

Bu işlev, **"AtlAxWin80"** ve **"AtlAxWinLic80"** pencere sınıflarını ve birkaç özel pencere iletisi kaydederek ATL 'nin denetim barındırma kodunu başlatır.

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim barındırma kodunun başlatılması başarılı olursa sıfır dışı; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ATL Denetim barındırma API 'SI kullanılmadan önce çağrılmalıdır. Bu işleve yapılan çağrıdan sonra, **"AtlAxWin"** pencere sınıfı, Windows SDK bölümünde açıklandığı gibi [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) veya [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)çağrılarında kullanılabilir.

##  <a name="atlaxwinterm"></a>AtlAxWinTerm

Bu işlev, **"AtlAxWin80"** ve **"AtlAxWinLic80"** pencere sınıflarının kaydını kaldırarak ATL 'nin denetim barındırma kodunu başlatır.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca Windows SDK açıklandığı şekilde [UnregisterClass](/windows/win32/api/winuser/nf-winuser-unregisterclassw) öğesini çağırır.

[AtlAxWinInit](#atlaxwininit) olarak adlandırdıysanız tüm mevcut konak pencereleri yok edildiğinde temizlemek için bu işlevi çağırın ve artık ana bilgisayar pencereleri oluşturmanız gerekmez. Bu işlevi çağırmazsanız, işlem sonlandırıldığında pencere sınıfının kaydı otomatik olarak kaldırılır.

##  <a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface

Bir nesnenin varsayılan kaynak arabirimi hakkında bilgi almak için bu işlevi çağırın.

```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```

### <a name="parameters"></a>Parametreler

*punkObj*<br/>
'ndaki Bilgilerin döndürüleceği nesneye yönelik bir işaretçi.

*plibıd*<br/>
dışı Kaynak arabirimin tanımını içeren tür kitaplığının LIBıD işaretçisi.

*piıd*<br/>
dışı Nesnenin varsayılan kaynak arabiriminin arabirim KIMLIĞINE yönelik bir işaretçi.

*Pdwana*<br/>
dışı Kaynak arabirimin tanımını içeren tür kitaplığının ana sürüm numarasına yönelik bir işaretçi.

*pdwMinor*<br/>
dışı Kaynak arabirimin tanımını içeren tür kitaplığının küçük sürüm numarasına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`AtlGetObjectSourceInterface`, varsayılan kaynak arabirimin arabirim KIMLIĞINI ve bu arabirimi açıklayan tür kitaplığının LIBıD ve büyük ve küçük sürüm numaralarıyla birlikte sağlayabilir.

> [!NOTE]
>  Bu işlevin istenen bilgileri başarılı bir şekilde alabilmesi için, *punkObj* tarafından temsil edilen nesne `IDispatch` (ve `IDispatch::GetTypeInfo`aracılığıyla dönüş türü bilgilerini) uygulamalıdır ve ayrıca `IProvideClassInfo2` ya da `IPersist`uygulamalıdır. Kaynak arabirimin tür bilgileri, `IDispatch`için tür bilgileriyle aynı tür kitaplığında olmalıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `IDispEventImpl`, çıplak temel noktalara geçirebilmeniz için kullanabileceğiniz şablon bağımsız değişkenlerinin sayısını azaltan bir olay havuzu sınıfını nasıl tanımlayacağınızı `CEasySink`gösterilmektedir. `EasyAdvise` ve `EasyUnadvise` [Dispeventadmeni](idispeventsimpleimpl-class.md#dispeventadvise) veya [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)çağrılmadan önce [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) üyelerini başlatmak için `AtlGetObjectSourceInterface` kullanın.

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Bileşik Denetim Makroları](../../atl/reference/composite-control-macros.md)
