---
title: Kompozit Kontrol Küresel Fonksiyonlar
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
ms.openlocfilehash: 99ecd4cf04b3eb696f897d6ef5a5e3839d46ef17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331606"
---
# <a name="composite-control-global-functions"></a>Kompozit Kontrol Küresel Fonksiyonlar

Bu işlevler iletişim kutuları oluşturmak ve ActiveX denetimleri oluşturmak, barındırmak ve lisanslama için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan kalıcı bir iletişim kutusu oluşturur. Ortaya çıkan iletişim kutusu ActiveX denetimleri içerebilir.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan modsuz bir iletişim kutusu oluşturur. Ortaya çıkan iletişim kutusu ActiveX denetimleri içerebilir.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX denetimi oluşturur, başlatılmasını, belirtilen pencerede barındırır ve denetimden bir arabirim işaretçisi (veya işaretçisi) alır.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Lisanslı activex denetimi oluşturur, başlatılmasını, belirtilen pencerede barındırır ve denetimden bir arabirim işaretçisi (veya işaretçisi) alır.|
|[AtlAxAttachKontrol](#atlaxattachcontrol)|Önceden oluşturulmuş bir denetimi belirtilen pencereye ekler.|
|[AtlAxGetHost](#atlaxgethost)|Tutamacı verilen belirli bir pencere (varsa) için kapsayıcıya doğrudan arabirim işaretçisi almak için kullanılır.|
|[AtlAxGetControl](#atlaxgetcontrol)|Tutamacı verilen belirli bir pencerenin içinde bulunan denetime (varsa) doğrudan bir arabirim işaretçisi almak için kullanılır.|
|[AtlSetChildSite](#atlsetchildsite)|Alt sitenin `IUnknown` baş harflerini ilke landırır.|
|[AtlAxWinInit](#atlaxwininit)|AxWin nesneleri için barındırma kodunu başharfe adazır.|
|[AtlAxWinTerm](#atlaxwinterm)|AxWin nesnelerinin barındırma kodunu uninitializes.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Nesnenin varsayılan kaynak arabirimi hakkındaki bilgileri verir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlhost.h

## <a name="atlaxdialogbox"></a><a name="atlaxdialogbox"></a>AtlAxDialogBox

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

*Hınstance*<br/>
[içinde] Yürütülebilir dosya iletişim kutusu şablonu içeren modülün bir örneğini tanımlar.

*lpTemplateName*<br/>
[içinde] İletişim kutusu şablonu tanımlar. Bu parametre, iletişim kutusu şablonunun adını belirten null-sonlandırılan karakter dizesinin işaretçisi veya iletişim kutusu şablonunun kaynak tanımlayıcısını belirten bir tamsayı değeridir. Parametre bir kaynak tanımlayıcısı belirtirse, yüksek sıralı sözcüğü sıfır olmalı ve düşük sıralı sözcüğü tanımlayıcıyı içermelidir. Bu değeri oluşturmak için [MAKEINTRESOURCE](/windows/win32/api/winuser/nf-winuser-makeintresourcew) makrosu kullanabilirsiniz.

*hWndParent*<br/>
[içinde] İletişim kutusunun sahibi olan pencereyi tanımlar.

*lpDialogProc*<br/>
[içinde] İletişim kutusu yordamını işaret edin. İletişim kutusu yordamı hakkında daha fazla bilgi için [DialogProc'a](/windows/win32/api/winuser/nc-winuser-dlgproc)bakın.

*dwInitParam*<br/>
[içinde] WM_INITDIALOG iletisinin *lParam* parametresinde iletişim kutusuna geçecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

ActiveX `AtlAxDialogBox` denetimi içeren bir iletişim şablonuyla kullanmak için, iletişim kaynağının **DENETIM** bölümünün *metin* alanı olarak geçerli bir CLSID, APPID veya URL dizesi ve aynı bölümün altındaki *sınıf adı* alanı olarak "AtlAxWin80" belirtin. Aşağıda, geçerli bir **CONTROL** bölümünün nasıl görünebileceği gösterilmiş olur:

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

Kaynak komut dosyalarını düzenleme hakkında daha fazla bilgi için [bkz.](../../windows/how-to-open-a-resource-script-file-in-text-format.md) Kaynak tanımlı denetim deyimleri hakkında daha fazla bilgi için Windows SDK altında [Ortak Denetim Parametreleri:](/windows/win32/menurc/common-control-parameters) SDK Araçları'na bakın.

Genel olarak iletişim kutuları hakkında daha fazla bilgi için Windows SDK'daki [DialogBox](/windows/win32/api/winuser/nf-winuser-dialogboxw) ve [CreateDialogParam'a](/windows/win32/api/winuser/nf-winuser-createdialogparamw) bakın.

## <a name="atlaxcreatedialog"></a><a name="atlaxcreatedialog"></a>AtlAxCreateDialog

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

*Hınstance*<br/>
[içinde] Yürütülebilir dosya iletişim kutusu şablonu içeren modülün bir örneğini tanımlar.

*lpTemplateName*<br/>
[içinde] İletişim kutusu şablonu tanımlar. Bu parametre, iletişim kutusu şablonunun adını belirten null-sonlandırılan karakter dizesinin işaretçisi veya iletişim kutusu şablonunun kaynak tanımlayıcısını belirten bir tamsayı değeridir. Parametre bir kaynak tanımlayıcısı belirtirse, yüksek sıralı sözcüğü sıfır olmalı ve düşük sıralı sözcüğü tanımlayıcıyı içermelidir. Bu değeri oluşturmak için [MAKEINTRESOURCE](/windows/win32/api/winuser/nf-winuser-makeintresourcew) makrosu kullanabilirsiniz.

*hWndParent*<br/>
[içinde] İletişim kutusunun sahibi olan pencereyi tanımlar.

*lpDialogProc*<br/>
[içinde] İletişim kutusu yordamını işaret edin. İletişim kutusu yordamı hakkında daha fazla bilgi için [DialogProc'a](/windows/win32/api/winuser/nc-winuser-dlgproc)bakın.

*dwInitParam*<br/>
[içinde] WM_INITDIALOG iletisinin *lParam* parametresinde iletişim kutusuna geçecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan iletişim kutusu ActiveX denetimleri içerebilir.

Bkz. Windows SDK'da [CreateDialog](/windows/win32/api/winuser/nf-winuser-createdialogw) ve [CreateDialogParam.](/windows/win32/api/winuser/nf-winuser-createdialogparamw)

## <a name="atlaxcreatecontrol"></a><a name="atlaxcreatecontrol"></a>AtlAxCreateControl

Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Denetime geçirilecek bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmelidir:

- Bir ProgID gibi`"MSCAL.Calendar.7"`

- Bir CLSID gibi`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- Gibi bir URL`"<https://www.microsoft.com>"`

- Aktif bir belgeye yapılan başvuru, örneğin`"file://\\\Documents\MyDoc.doc"`

- HTML gibi bir parçası`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML akışı olarak belirtilmek için HTML parçasından önce olmalıdır.

*Hwnd*<br/>
[içinde] Denetimin bağlı olacağı pencereye işledin.

*pStream*<br/>
[içinde] Denetimin özelliklerini başlatmak için kullanılan bir akış için işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
[çıkış] Kapsayıcının `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bu global fonksiyon size [AtlAxCreateControlEx](#atlaxcreatecontrolex)*(lpszName*, *hWnd*, *pStream*, NULL, NULL, NULL, NULL, NULL) arama ile aynı sonucu verir.

Lisanslı activex denetimi oluşturmak için [Bkz. AtlAxCreateControlLic.](#atlaxcreatecontrollic)

## <a name="atlaxcreatecontrolex"></a><a name="atlaxcreatecontrolex"></a>AtlAxCreateControlEx

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

*Lpszname*<br/>
Denetime geçirilecek bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmelidir:

- Bir ProgID gibi`"MSCAL.Calendar.7"`

- Bir CLSID gibi`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- Gibi bir URL`"<https://www.microsoft.com>"`

- Aktif bir belgeye yapılan başvuru, örneğin`"file://\\\Documents\MyDoc.doc"`

- HTML gibi bir parçası`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML akışı olarak belirtilmek için HTML parçasından önce olmalıdır.

*Hwnd*<br/>
[içinde] Denetimin bağlı olacağı pencereye işledin.

*pStream*<br/>
[içinde] Denetimin özelliklerini başlatmak için kullanılan bir akış için işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
[çıkış] Kapsayıcının `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

*ppUnkKontrol*<br/>
[çıkış] Oluşturulan denetimin `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

*iidSink*<br/>
İçe çıkan nesne üzerinde giden bir arabirimin arabirim tanımlayıcısı.

*punkSink*<br/>
İçerdiği `IUnknown` nesne başarıyla oluşturulduktan sonra *iidSink* tarafından içerdiği nesne üzerinde belirtilen bağlantı noktasına bağlanacak lavabo nesnesinin arabirimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlAxCreateControlEx`[AtlAxCreateControl](#atlaxcreatecontrol) benzer ama aynı zamanda yeni oluşturulan denetim için bir arayüz işaretçisi almak ve denetim tarafından ateşlenen olayları almak için bir olay lavabo kurmak sağlar.

Lisanslı activex denetimi oluşturmak için Bkz. [AtlAxCreateControlLicEx.](#atlaxcreatecontrollicex)

## <a name="atlaxcreatecontrollic"></a><a name="atlaxcreatecontrollic"></a>AtlAxCreateControlLic

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

*Lpszname*<br/>
Denetime geçirilecek bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmelidir:

- Bir ProgID gibi`"MSCAL.Calendar.7"`

- Bir CLSID gibi`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- Gibi bir URL`"<https://www.microsoft.com>"`

- Aktif bir belgeye yapılan başvuru, örneğin`"file://\\\Documents\MyDoc.doc"`

- HTML gibi bir parçası`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML akışı olarak belirtilmek için HTML parçasından önce olmalıdır.

*Hwnd*<br/>
Denetimin bağlı olacağı pencereye işledin.

*pStream*<br/>
Denetimin özelliklerini başlatmak için kullanılan bir akış için işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
Kapsayıcının `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

*bstrLic*<br/>
Kontrol için lisans içeren BSTR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="example"></a>Örnek

Nasıl kullanılacağına `AtlAxCreateControlLic`bir örnek için [ATL AXHost kullanarak Hosting ActiveX Denetimleri](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="atlaxcreatecontrollicex"></a><a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx

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

*Lpszname*<br/>
Denetime geçirilecek bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmelidir:

- Bir ProgID gibi`"MSCAL.Calendar.7"`

- Bir CLSID gibi`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- Gibi bir URL`"<https://www.microsoft.com>"`

- Aktif bir belgeye yapılan başvuru, örneğin`"file://\\\Documents\MyDoc.doc"`

- HTML gibi bir parçası`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML akışı olarak belirtilmek için HTML parçasından önce olmalıdır.

*Hwnd*<br/>
Denetimin bağlı olacağı pencereye işledin.

*pStream*<br/>
Denetimin özelliklerini başlatmak için kullanılan bir akış için işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
Kapsayıcının `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

*ppUnkKontrol*<br/>
[çıkış] Oluşturulan denetimin `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

*iidSink*<br/>
İçe çıkan nesne üzerinde giden bir arabirimin arabirim tanımlayıcısı.

*punkSink*<br/>
İçerdiği `IUnknown` nesne başarıyla oluşturulduktan sonra *iidSink* tarafından içerdiği nesne üzerinde belirtilen bağlantı noktasına bağlanacak lavabo nesnesinin arabirimine işaretçi.

*bstrLic*<br/>
Kontrol için lisans içeren BSTR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlAxCreateControlLicEx`[AtlAxCreateControlLic](#atlaxcreatecontrollic) benzer ama aynı zamanda yeni oluşturulan denetim için bir arayüz işaretçisi almak ve denetim tarafından ateşlenen olayları almak için bir olay lavabo kurmak sağlar.

### <a name="example"></a>Örnek

Nasıl kullanılacağına `AtlAxCreateControlLicEx`bir örnek için [ATL AXHost kullanarak Hosting ActiveX Denetimleri](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="atlaxattachcontrol"></a><a name="atlaxattachcontrol"></a>AtlAxAttachKontrol

Önceden oluşturulmuş bir denetimi belirtilen pencereye ekler.

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parametreler

*pKontrol*<br/>
[içinde] Denetimin işaretçisi. `IUnknown`

*Hwnd*<br/>
[içinde] Denetimi barındıracak pencereyi ele alın.

*ppUnkContainer*<br/>
[çıkış] Kapsayıcı nesnenin `IUnknown` işaretçisi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Aynı anda bir denetim oluşturmak ve eklemek için [AtlAxCreateControlEx](#atlaxcreatecontrolex) ve [AtlAxCreateControl'u](#atlaxcreatecontrol) kullanın.

> [!NOTE]
> Eklenen denetim nesnesi aramadan `AtlAxAttachControl`önce doğru bir şekilde başharfe alınmalıdır.

## <a name="atlaxgethost"></a><a name="atlaxgethost"></a>AtlAxGetHost

Belirli bir pencere için (varsa), kapsayıcıya tanıtıcısını göz önünde bulundurarak doğrudan bir arabirim işaretçisi alır.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
[içinde] Denetimi barındıran pencerenin tutamacı.

*S*<br/>
[çıkış] Kontrol `IUnknown` konteynerinin.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="atlaxgetcontrol"></a><a name="atlaxgetcontrol"></a>AtlAxGetControl

Belirli bir pencere içinde yer alan denetim için, tanıcısını göz önünde bulundurarak doğrudan arabirim işaretçisi alır.

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
[içinde] Denetimi barındıran pencerenin tutamacı.

*S*<br/>
[çıkış] Denetimin `IUnknown` barındırılması.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="atlsetchildsite"></a><a name="atlsetchildsite"></a>AtlSetChildSite

Alt nesnenin sitesini ana nesnenin alanına `IUnknown` ayarlamak için bu işlevi çağırın.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>Parametreler

*punkÇocuk*<br/>
[içinde] Çocuğun arabirimi `IUnknown` için bir işaretçi.

*punkEbeveyn*<br/>
[içinde] Üst arabirimine `IUnknown` bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="atlaxwininit"></a><a name="atlaxwininit"></a>AtlAxWinInit

Bu **işlev, "AtlAxWin80" ve "AtlAxWinLic80"** pencere sınıflarını ve birkaç özel pencere iletisini kaydederek ATL'nin denetim barındırma kodunu ortaya çıkarır. **"AtlAxWinLic80"**

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim barındırma kodunun başlatılması başarılı olduysa sıfırsız; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ApI barındırma ATL denetim kullanmadan önce çağrılmalıdır. Bu işlev için yapılan bir çağrının ardından, Windows SDK'da açıklandığı gibi CreateWindow veya [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindoww) aramalarında **"AtlAxWin"** pencere sınıfı kullanılabilir. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)

## <a name="atlaxwinterm"></a><a name="atlaxwinterm"></a>AtlAxWinTerm

Bu işlev, **"AtlAxWin80" ve "AtlAxWinLic80"** **"AtlAxWinLic80"** pencere sınıflarının kaydını kalarak ATL'nin denetim barındırma kodunu niçin şifreyi çözer.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK'da açıklandığı gibi [Kayıt Dışı Sınıfı'nı](/windows/win32/api/winuser/nf-winuser-unregisterclassw) çağırır.

[AtlAxWinInit'i](#atlaxwininit) aradıysanız ve artık ana bilgisayar pencereleri oluşturmanız gerekmiyorsa, varolan tüm ana bilgisayar pencereleri yok edildikten sonra temizlemek için bu işlevi arayın. Bu işlevi aramazsanız, işlem sona erdiğinde pencere sınıfı otomatik olarak kaydolmaz.

## <a name="atlgetobjectsourceinterface"></a><a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface

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
[içinde] Bilgilerin döndürülmek üzere olduğu nesneye işaretçi.

*plibid*<br/>
[çıkış] Kaynak arabirimin tanımını içeren tür kitaplığı LIBID için bir işaretçi.

*piid*<br/>
[çıkış] Nesnenin varsayılan kaynak arabiriminin arabirim kimliğine işaretçi.

*pdwMajor*<br/>
[çıkış] Kaynak arabirimin tanımını içeren tür kitaplığı ana sürüm numarasıiçin bir işaretçi.

*pdwMinor*<br/>
[çıkış] Kaynak arabirimin tanımını içeren tür kitaplığı küçük sürüm numarası için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`AtlGetObjectSourceInterface`varsayılan kaynak arabiriminin arabirim kimliğini, LIBID ve bu arabirimi açıklayan tür kitaplığın büyük ve küçük sürüm numaraları ile birlikte sağlayabilir.

> [!NOTE]
> Bu işlevin istenen bilgileri başarıyla alabilmesi için *punkObj* tarafından `IDispatch` temsil edilen nesnenin uygulama (ve tür bilgilerini aracılığıyla `IDispatch::GetTypeInfo`döndürme) uygulaması ve ayrıca ya da `IProvideClassInfo2` `IPersist`. Kaynak arabiriminin tür bilgileri, `IDispatch`tür bilgileriyle aynı tür kitaplığında olmalıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `CEasySink`çıplak temellere geçebileceğiniz `IDispEventImpl` şablon bağımsız değişkenlerinin sayısını azaltan bir olay lavabo sınıfını nasıl tanımlayabileceğiniz gösterilmektedir. `EasyAdvise`ve `EasyUnadvise` `AtlGetObjectSourceInterface` [DispEventAdvise veya DispEventUnadvise'i](idispeventsimpleimpl-class.md#dispeventadvise) aramadan [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)önce [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) üyelerini başlatmayı kullanın.

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Bileşik Denetim Makroları](../../atl/reference/composite-control-macros.md)
