---
title: Bileşik Denetim genel işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54e4ab00a0d0df90601d06d9e2ffa100d82d4c03
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037365"
---
# <a name="composite-control-global-functions"></a>Bileşik Denetim genel işlevleri

Bu işlevler, iletişim kutuları oluşturma ve oluşturma, barındırma ve ActiveX denetimlerini lisanslama için destek sağlar.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan kalıcı bir iletişim kutusu oluşturur. Ortaya çıkan iletişim kutusunda ActiveX denetimleri içerebilir.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan modsuz bir iletişim kutusu oluşturur. Ortaya çıkan iletişim kutusunda ActiveX denetimleri içerebilir.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Bir ActiveX denetimi oluşturur, onu başlatır, belirtilen pencerede barındırır ve denetiminden bir arabirim işaretçisi (veya işaretçiler) alır.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır, belirtilen pencerede barındırır ve denetiminden bir arabirim işaretçisi (veya işaretçiler) alır.|
|[AtlAxAttachControl](#atlaxattachcontrol)|Önceden oluşturulmuş bir denetimi belirtilen pencereye ekler.|
|[AtlAxGetHost](#atlaxgethost)|Belirli bir pencere için (varsa), kapsayıcıya doğrudan arabirim işaretçisi elde etmek için kullanılan belirli.|
|[AtlAxGetControl](#atlaxgetcontrol)|Doğrudan bir arabirim işaretçisi için bir pencere içinde (varsa), yer alan denetim elde etmek için kullanılan belirli.|
|[AtlSetChildSite](#atlsetchildsite)|Başlatır `IUnknown` alt sitenin.|
|[AtlAxWinInit](#atlaxwininit)|AxWin nesneleri barındırma kodunu başlatır.|
|[AtlAxWinTerm](#atlaxwinterm)|Barındırma kodunu AxWin nesneleri başlamasını iptal eder.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Bir nesnenin varsayılan kaynak arabirimi hakkında bilgi döndürür.|  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlhost.h  

##  <a name="atlaxdialogbox"></a>  AtlAxDialogBox

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
[in] İletişim kutusu şablonu, yürütülebilir dosya içeren modül bir örneğini tanımlar.

*lpTemplateName*<br/>
[in] İletişim kutusu şablonu tanımlar. Bu parametre, iletişim kutusu şablonunun adını belirten bir null ile sonlandırılmış dize işaretçisi veya iletişim kutusu şablonu kaynak tanımlayıcısını belirten bir tamsayı değeri olur. Parametre bir kaynak tanımlayıcısı belirtiyorsa, kendi dwpoint sıfır olmalıdır ve onun alt sıra sözcük tanımlayıcı içermelidir. Kullanabileceğiniz [MAKEINTRESOURCE](https://msdn.microsoft.com/library/windows/desktop/ms648029) makrosu bu değeri oluşturun.

*hWndParent*<br/>
[in] İletişim kutusunun sahibi penceresini tanımlar.

*lpDialogProc*<br/>
[in] İletişim kutusu yordamını işaret eder. İletişim kutusu yordamını hakkında daha fazla bilgi için bkz: [DialogProc](https://msdn.microsoft.com/library/windows/desktop/ms645469).

*dwInitParam*<br/>
[in] İletişim kutusundaki geçirmek için bir değer belirtir *lParam* WM_INITDIALOG iletisinin parametresi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Kullanılacak `AtlAxDialogBox` ActiveX denetimini içeren bir iletişim şablonunu ile geçerli bir CLSID, APPID veya URL dize olarak belirtin *metin* alanını **denetimi** bölümünü iletişim kutusu kaynağı ile birlikte " AtlAxWin80 "olarak *sınıf adı* aynı bölüme altında. Aşağıdaki ne bir geçerli gösterir **denetimi** bölümü gibi görünebilir:

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,  
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

Kaynak komut dosyaları düzenleme hakkında daha fazla bilgi için bkz. [nasıl yapılır: kaynak betik dosyasını metin biçiminde açma](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Denetim kaynak tanımı ifadeleri hakkında daha fazla bilgi için bkz. [ortak denetim parametreleri](/windows/desktop/menurc/common-control-parameters) Windows SDK'sı altında *: SDK Tools*.

Genel iletişim kutularında hakkında daha fazla bilgi için başvurmak [iletişim](/windows/desktop/api/winuser/nf-winuser-dialogboxa) ve [CreateDialogParam](/windows/desktop/api/winuser/nf-winuser-createdialogparama) Windows SDK.

##  <a name="atlaxcreatedialog"></a>  AtlAxCreateDialog

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
[in] İletişim kutusu şablonu, yürütülebilir dosya içeren modül bir örneğini tanımlar.

*lpTemplateName*<br/>
[in] İletişim kutusu şablonu tanımlar. Bu parametre, iletişim kutusu şablonunun adını belirten bir null ile sonlandırılmış dize işaretçisi veya iletişim kutusu şablonu kaynak tanımlayıcısını belirten bir tamsayı değeri olur. Parametre bir kaynak tanımlayıcısı belirtiyorsa, kendi dwpoint sıfır olmalıdır ve onun alt sıra sözcük tanımlayıcı içermelidir. Kullanabileceğiniz [MAKEINTRESOURCE](https://msdn.microsoft.com/library/windows/desktop/ms648029) makrosu bu değeri oluşturun.

*hWndParent*<br/>
[in] İletişim kutusunun sahibi penceresini tanımlar.

*lpDialogProc*<br/>
[in] İletişim kutusu yordamını işaret eder. İletişim kutusu yordamını hakkında daha fazla bilgi için bkz: [DialogProc](https://msdn.microsoft.com/library/windows/desktop/ms645469).

*dwInitParam*<br/>
[in] İletişim kutusundaki geçirmek için bir değer belirtir *lParam* WM_INITDIALOG iletisinin parametresi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan iletişim kutusunda ActiveX denetimleri içerebilir.

Bkz: [CreateDialog](/windows/desktop/api/winuser/nf-winuser-createdialoga) ve [CreateDialogParam](/windows/desktop/api/winuser/nf-winuser-createdialogparama) Windows SDK içinde.

##  <a name="atlaxcreatecontrol"></a>  AtlAxCreateControl

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
Denetime geçirilecek bir dizeye bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:

- Bir ProgID gibi "MSCAL. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID

- Gibi bir URL "http://www.microsoft.com"

- Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"

- HTML gibi bir parçasını "MSHTML:\<HTML >\<GÖVDESİ > metin satırı budur\</BODY >\</HTML >"

   > [!NOTE]
   > "MSHTML:" MSHTML stream olacak şekilde atanır böylece HTML parçasını gelmelidir.

*hWnd*<br/>
[in] Denetim iliştirilmiş penceresine işleyin.

*pStream*<br/>
[in] Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
[out] Adresi alacak bir işaretçi `IUnknown` kapsayıcının. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bu genel bir işlev çağrıldığında aynı sonucu verir [AtlAxCreateControlEx](#atlaxcreatecontrolex)(*lpszName*, *hWnd*, *pStream*, NULL, NULL NULL, NULL);.

Lisanslı bir ActiveX denetimi oluşturmak için bkz [AtlAxCreateControlLic](#atlaxcreatecontrollic).

##  <a name="atlaxcreatecontrolex"></a>  AtlAxCreateControlEx

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
Denetime geçirilecek bir dizeye bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:

- Bir ProgID gibi "MSCAL. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID

- Gibi bir URL "http://www.microsoft.com"

- Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"

- HTML gibi bir parçasını "MSHTML:\<HTML >\<GÖVDESİ > metin satırı budur\</BODY >\</HTML >"

   > [!NOTE]
   > "MSHTML:" MSHTML stream olacak şekilde atanır böylece HTML parçasını gelmelidir.

*hWnd*<br/>
[in] Denetim iliştirilmiş penceresine işleyin.

*pStream*<br/>
[in] Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
[out] Adresi alacak bir işaretçi `IUnknown` kapsayıcının. NULL olabilir.

*ppUnkControl*<br/>
[out] Adresi alacak bir işaretçi `IUnknown` oluşturulan denetimi. NULL olabilir.

*iidSink*<br/>
Kapsanan nesne üzerinde giden bir arabirim arabirimi tanımlayıcısı.

*punkSink*<br/>
Bir işaretçi `IUnknown` arabirimi tarafından belirtilen bağlantı noktasına bağlı havuz nesnenin *iidSink* kapsanan nesne başarıyla oluşturulduktan sonra kapsanan nesne üzerinde.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlAxCreateControlEx` benzer [AtlAxCreateControl](#atlaxcreatecontrol) ancak aynı zamanda yeni oluşturulan denetime bir arabirim işaretçisi alır ve denetimi tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak verir.

Lisanslı bir ActiveX denetimi oluşturmak için bkz [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).

##  <a name="atlaxcreatecontrollic"></a>  AtlAxCreateControlLic

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
Denetime geçirilecek bir dizeye bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:

- Bir ProgID gibi "MSCAL. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID

- Gibi bir URL "http://www.microsoft.com"

- Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"

- HTML gibi bir parçasını "MSHTML:\<HTML >\<GÖVDESİ > metin satırı budur\</BODY >\</HTML >"

   > [!NOTE]
   > "MSHTML:" MSHTML stream olacak şekilde atanır böylece HTML parçasını gelmelidir.

*hWnd*<br/>
Denetim iliştirilmiş penceresine işleyin.

*pStream*<br/>
Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
Adresi alacak bir işaretçi `IUnknown` kapsayıcının. NULL olabilir.

*bstrLic*<br/>
Denetim için lisans içeren BSTR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) nasıl kullanılacağını gösteren bir örnek `AtlAxCreateControlLic`.

##  <a name="atlaxcreatecontrollicex"></a>  AtlAxCreateControlLicEx

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
Denetime geçirilecek bir dizeye bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:

- Bir ProgID gibi "MSCAL. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID

- Gibi bir URL "http://www.microsoft.com"

- Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"

- HTML gibi bir parçasını "MSHTML:\<HTML >\<GÖVDESİ > metin satırı budur\</BODY >\</HTML >"

   > [!NOTE]
   > "MSHTML:" MSHTML stream olacak şekilde atanır böylece HTML parçasını gelmelidir.

*hWnd*<br/>
Denetim iliştirilmiş penceresine işleyin.

*pStream*<br/>
Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
Adresi alacak bir işaretçi `IUnknown` kapsayıcının. NULL olabilir.

*ppUnkControl*<br/>
[out] Adresi alacak bir işaretçi `IUnknown` oluşturulan denetimi. NULL olabilir.

*iidSink*<br/>
Kapsanan nesne üzerinde giden bir arabirim arabirimi tanımlayıcısı.

*punkSink*<br/>
Bir işaretçi `IUnknown` arabirimi tarafından belirtilen bağlantı noktasına bağlı havuz nesnenin *iidSink* kapsanan nesne başarıyla oluşturulduktan sonra kapsanan nesne üzerinde.

*bstrLic*<br/>
Denetim için lisans içeren BSTR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlAxCreateControlLicEx` benzer [AtlAxCreateControlLic](#atlaxcreatecontrollic) ancak aynı zamanda yeni oluşturulan denetime bir arabirim işaretçisi alır ve denetimi tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak verir.

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) nasıl kullanılacağını gösteren bir örnek `AtlAxCreateControlLicEx`.

##  <a name="atlaxattachcontrol"></a>  AtlAxAttachControl

Önceden oluşturulmuş bir denetimi belirtilen pencereye ekler.

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
[in] Bir işaretçi `IUnknown` denetimi.

*hWnd*<br/>
[in] Denetim barındıracak pencereyi işleyin.

*ppUnkContainer*<br/>
[out] Bir işaretçi işaretçisi `IUnknown` kapsayıcı nesnesinin.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Kullanım [AtlAxCreateControlEx](#atlaxcreatecontrolex) ve [AtlAxCreateControl](#atlaxcreatecontrol) aynı anda oluşturup bir denetim eklemek için.

> [!NOTE]
>  İliştirilmekte olan denetim nesne doğru çağırmadan önce başlatılmalıdır `AtlAxAttachControl`.

##  <a name="atlaxgethost"></a>  AtlAxGetHost

Belirli bir pencere için (varsa), kapsayıcıya tanıtıcısını göz önünde bulundurarak doğrudan bir arabirim işaretçisi alır.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
[in] Denetim barındırma penceresi için bir tanıtıcı.

*PP*<br/>
[out] `IUnknown` Kapsayıcısının denetimi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl

Belirli bir pencere içinde yer alan denetim için, tanıcısını göz önünde bulundurarak doğrudan arabirim işaretçisi alır.

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
[in] Denetim barındırma penceresi için bir tanıtıcı.

*PP*<br/>
[out] `IUnknown` Barındırılması denetimi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="atlsetchildsite"></a>  AtlSetChildSite

Alt nesnenin sitesini ayarlamak için bu işlevi çağırın `IUnknown` üst nesnenin.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>Parametreler

*punkChild*<br/>
[in] Bir işaretçi `IUnknown` alt arabirimi.

*punkParent*<br/>
[in] Bir işaretçi `IUnknown` üst arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="atlaxwininit"></a>  AtlAxWinInit

Bu işlev ATL'nin denetim barındırma kodunu kaydederek başlatır **"AtlAxWin80"** ve **"AtlAxWinLic80"** pencere sınıflarını ve birkaç özel pencere.

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma kodu barındırma denetimi başarılı olursa sıfır dışı; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ATL Denetim barındırma API'si kullanmadan önce çağrılmalıdır. Bu işlev, çağrıyı izleyen **"AtlAxWin"** pencere sınıfını çağrıları kullanılabilir [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) veya [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa)Windows SDK içinde açıklandığı gibi.  

##  <a name="atlaxwinterm"></a>  Zaman AtlAxWinTerm

Bu işlev ATL'nin denetim barındırma kodunu kaydını silerek başlamasını iptal eder **"AtlAxWin80"** ve **"AtlAxWinLic80"** pencere sınıfları.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çağıran [UnregisterClass](https://msdn.microsoft.com/library/windows/desktop/ms644899) Windows SDK içinde açıklandığı gibi.

Çağrılırsa, mevcut tüm ana bilgisayar windows yok edildikten sonra sonra temizlemek için bu işlevi çağırın [zaman Atlaxwinınit](#atlaxwininit) ve, bundan böyle bir ana bilgisayar windows oluşturmanız gerekir. Bu işlev çağırırsanız yoksa, işlem sonlandırıldığında pencere sınıfını otomatik olarak kaydı silinecek.

##  <a name="atlgetobjectsourceinterface"></a>  AtlGetObjectSourceInterface

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
[in] Bilgi döndürülecek nesne işaretçisi.

*plibid*<br/>
[out] Kaynak arabirimi tanımını içeren tür kitaplığının Kitaplık kimliği için bir işaretçi.

*piid*<br/>
[out] Nesnenin varsayılan kaynak arabirimi arabirim kimliği için bir işaretçi.

*pdwMajor*<br/>
[out] Ana sürüm numarası tür kitaplığının kaynak arabirimi tanımını içeren bir işaretçi.

*pdwMinor*<br/>
[out] Alt sürüm numarasını tür kitaplığının kaynak arabirimi tanımını içeren bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

`AtlGetObjectSourceInterface` Varsayılan kaynak arabirimi LIBID birlikte ve ana arabirimi kimliği ve ikincil sürüm numaraları arabirimi açıklayan tür kitaplığının sağlayabilir.

> [!NOTE]
>  Nesne başarıyla istenen bilgileri almak için bu işlevi için temsil ettiği *punkObj* uygulamalıdır `IDispatch` (ve dönüş türü bilgilerini aracılığıyla `IDispatch::GetTypeInfo`) artı ya da uygulamalıdır`IProvideClassInfo2` veya `IPersist`. Kaynak arabirimi için tür bilgisi için tür bilgisi aynı tür kitaplığında olmalıdır `IDispatch`.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir olay havuzu sınıfı nasıl tanımlayabilir gösterir `CEasySink`, iletebileceğiniz şablon bağımsız değişkenleri sayısını azaltan `IDispEventImpl` tam essentials için. `EasyAdvise` ve `EasyUnadvise` kullanın `AtlGetObjectSourceInterface` başlatmak için [Idispeventımpl](../../atl/reference/idispeventimpl-class.md) çağırmadan önce üyeleri [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) veya [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Bileşik Denetim Makroları](../../atl/reference/composite-control-macros.md)
