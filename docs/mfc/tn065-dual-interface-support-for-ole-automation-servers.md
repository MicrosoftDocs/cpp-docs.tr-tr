---
title: 'TN065: OLE Otomasyonu sunucuları için çift arabirim desteği'
ms.date: 06/28/2018
f1_keywords:
- vc.ole
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
ms.openlocfilehash: 1508b5219f7bb7fd2e9c9a56c42c30bb99686804
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630386"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: OLE Otomasyonu sunucuları için çift arabirim desteği

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, MFC tabanlı bir OLE Otomasyonu sunucu uygulamasına çift arabirim desteğinin nasıl ekleneceği açıklanmaktadır. [Acdual](../overview/visual-cpp-samples.md) örneği çift arabirim desteğini gösterir ve bu notdaki örnek kod acdual 'ten alınmıştır. Bu notta açıklanan makrolar, örneğin DECLARE_DUAL_ERRORINFO, DUAL_ERRORINFO_PART ve IMPLEMENT_DUAL_ERRORINFO, ACDUAL örneğinin bir parçasıdır ve MFCDUAL içinde bulunabilir. Olsun.

## <a name="dual-interfaces"></a>Çift arabirimler

OLE Otomasyonu bir `IDispatch` arabirim, bir VTBL arabirimi ya da çift bir arabirim (her ikisini de kapsayan) uygulamanıza izin veriyorsa, Microsoft, sunulan tüm OLE Otomasyonu nesneleri için ikili arabirimler uygulamanızı kesinlikle önerir. Çift arabirimlerin yalnızca daha fazla `IDispatch`veya yalnızca VTBL arabirimler için önemli avantajları vardır:

- Bağlama, VTBL arabirimi aracılığıyla ya da çalışma zamanında aracılığıyla `IDispatch`derleme zamanında gerçekleşebilir.

- VTBL arabirimini kullanabilecek OLE Otomasyonu denetleyicileri, geliştirilmiş performanstan yararlanabilir.

- `IDispatch` Arabirimi kullanan mevcut OLE Otomasyonu denetleyicileri çalışmaya devam edecektir.

- ' Den C++daha kolay çağracak olan VTBL arabirimi.

- Visual Basic nesne desteği özellikleriyle uyumluluk için çift arabirimler gereklidir.

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget tabanlı sınıfa çift arabirim desteği ekleme

Bir çift arabirim aslında yalnızca öğesinden `IDispatch`türetilmiş özel bir arabirimdir. Tabanlı bir `CCmdTarget`sınıfta çift arabirim desteği sağlamanın en kolay yolu, öncelikle MFC ve ClassWizard kullanarak sınıfınıza normal dağıtım arabirimini uygulamaktır, ardından özel arabirimi daha sonra eklemektir. Çoğu bölüm için, özel arabirim uygulamanız yalnızca MFC `IDispatch` uygulamasına yeniden temsilci atamasını sağlar.

İlk olarak, nesneleriniz için ikili arabirimler tanımlamak üzere sunucunuzun ODL dosyasını değiştirin. İkili bir arabirim tanımlamak için, Visual `DISPINTERFACE` C++ sihirbazlarının üretmesindeki deyimin yerine bir arabirim ifadesini kullanmanız gerekir. Varolan `DISPINTERFACE` ifadeyi kaldırmak yerine yeni bir arabirim açıklaması ekleyin. `DISPINTERFACE` Formu koruyarak, deyiminize Özellikler ve yöntemler eklemek için ClassWizard 'ı kullanmaya devam edebilirsiniz, ancak Interface deyiminize eşdeğer özellikleri ve yöntemleri eklemeniz gerekir.

Çift arabirim için bir arabirim bildiriminde, *oleautomation* ve *Dual* özniteliklerine sahip olmalıdır ve arabirim öğesinden `IDispatch`türetilmelidir. Dual arabirimi için bir **IID** oluşturmak üzere [GUIDgen](../overview/visual-cpp-samples.md) örneğini kullanabilirsiniz:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

Arabirim deyiminizi oluşturduktan sonra, Yöntemler ve özellikler için girdi eklemeye başlayın. Çift arabirimler için, Çift arabirimdeki yöntemlerinizin ve özellik erişimcisinin bir **HRESULT** döndürmesi ve dönüş değerlerini özniteliklerle `[retval,out]`parametre olarak iletmeleri için parametre listelerini yeniden düzenlemeniz gerekir. Özellikler için aynı kimliğe sahip bir Read (`propget`) ve Write (`propput`) erişim işlevi eklemeniz gerektiğini unutmayın. Örneğin:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

Yöntemleriniz ve Özellikler tanımlandıktan sonra, coclass deyiminizdeki Interface ifadesine bir başvuru eklemeniz gerekir. Örneğin:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

ODL dosyanız güncelleştirildikten sonra, nesne sınıfınıza çift arabirim için bir uygulama sınıfı tanımlamak ve MFC `QueryInterface` mekanizmasında karşılık gelen girdileri oluşturmak için MFC 'nin arabirim eşleme mekanizmasını kullanın. ODL 'nin arabirim deyimindeki her `INTERFACE_PART` giriş için bloğunda bir giriş ve bir dağıtım arabirimi için girdiler olması gerekir. *Propput* özniteliğine sahip her BIR ODL girişinin adlı `put_propertyname`bir işlevi olması gerekir. *Propget* özniteliğine sahip her girdinin adlı `get_propertyname`bir işlevi olması gerekir.

Dual Interface için bir uygulama sınıfı tanımlamak üzere, nesne sınıfı tanımınıza bir `DUAL_INTERFACE_PART` blok ekleyin. Örneğin:

```cpp
BEGIN_DUAL_INTERFACE_PART(DualAClick, IDualAClick)
    STDMETHOD(put_text)(THIS_ BSTR newText);
    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);
    STDMETHOD(put_x)(THIS_ short newX);
    STDMETHOD(get_x)(THIS_ short FAR* retval);
    STDMETHOD(put_y)(THIS_ short newY);
    STDMETHOD(get_y)(THIS_ short FAR* retval);
    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);
    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);
    STDMETHOD(RefreshWindow)(THIS);
    STDMETHOD(SetAllProps)(THIS_ short x, short y, BSTR text);
    STDMETHOD(ShowWindow)(THIS);
END_DUAL_INTERFACE_PART(DualAClick)
```

İkili arabirimi MFC 'nin [QueryInterface](/windows/win32/com/queryinterface--navigating-in-an-object) mekanizmasına bağlamak için arabirim eşlemesine bir `INTERFACE_PART` giriş ekleyin:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Ardından, arabirimin uygulamasını doldurmanız gerekir. Çoğu bölüm için, mevcut MFC `IDispatch` uygulamasına temsilci atayabileceksiniz. Örneğin:

```cpp
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalAddRef();
}

STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalRelease();
}

STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalQueryInterface(&iid, ppvObj);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);
    return lpDispatch->GetTypeInfoCount(pctinfo);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo, lcid, pptinfo);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID FAR* rgdispid)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid, rgszNames, cNames, lcid, rgdispid);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS FAR* pdispparams,
    VARIANT FAR* pvarResult,
    EXCEPINFO FAR* pexcepinfo,
    UINT FAR* puArgErr)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember, riid, lcid,
        wFlags, pdispparams, pvarResult, pexcepinfo, puArgErr);
}
```

Nesnenizin yöntemleri ve özellik erişimcisi işlevleri için, uygulamayı doldurmanız gerekir. Yöntem ve özellik işlevleriniz, sınıf Sihirbazı kullanılarak oluşturulan yöntemlere genellikle yeniden temsilci verebilir. Ancak, değişkenlere doğrudan erişmek için özellikler ayarlarsanız, değeri değişkene almak/yerleştirmek için kodu yazmanız gerekir. Örneğin:

```cpp
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    // MFC automatically converts from Unicode BSTR to
    // Ansi CString, if necessary...
    pThis->m_str = newText;
    return NOERROR;
}

STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    // MFC automatically converts from Ansi CString to
    // Unicode BSTR, if necessary...
    pThis->m_str.SetSysString(retval);
    return NOERROR;
}
```

## <a name="passing-dual-interface-pointers"></a>Çift arabirim Işaretçilerini geçirme

Özellikle çağırmanız `CCmdTarget::FromIDispatch`gerekiyorsa çift arabirim işaretçinizi geçirmek basit değildir. `FromIDispatch`yalnızca MFC `IDispatch` işaretçilerinde kullanılabilir. Bu sorunu çözmek için bir yol, MFC tarafından ayarlanan orijinal `IDispatch` işaretçiyi sorgular ve bu işaretçiyi bu işaretçiye gereken işlevlere iletir. Örneğin:

```
STDMETHODIMP CAutoClickDoc::XDualAClick::put_Position(
    IDualAutoClickPoint FAR* newPosition)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDisp = NULL;
    newPosition->QueryInterface(IID_IDispatch, (LPVOID*)&lpDisp);
    pThis->SetPosition(lpDisp);
    lpDisp->Release();
    return NOERROR;
}
```

Bir işaretçiyi çift arabirim yöntemiyle geri geçirmeden önce, MFC `IDispatch` işaretçisinden çift arabirim işaretçinize dönüştürmeniz gerekebilir. Örneğin:

```
STDMETHODIMP CAutoClickDoc::XDualAClick::get_Position(
    IDualAutoClickPoint FAR* FAR* retval)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDisp;
    lpDisp = pThis->GetPosition();
    lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);
    return NOERROR;
}
```

## <a name="registering-the-applications-type-library"></a>Uygulamanın tür kitaplığını kaydetme

AppWizard, bir OLE Otomasyonu sunucu uygulamasının tür kitaplığını sistemle kaydetmek için kod oluşturmaz. Tür kitaplığını kaydetmek için başka yollar da olsa da, OLE tür bilgilerini güncelleştirirken uygulamanın tür kitaplığını kaydetmesi, yani uygulamanın tek başına çalıştırıldığı zaman.

Uygulamanın tek başına çalıştırıldığı her seferinde uygulamanın tür kitaplığını kaydetmek için:

- AFXCTL 'yi dahil edin. Standart içindeki H, STBAFX başlık dosyasını içerir. H, `AfxOleRegisterTypeLib` işlevin tanımına erişmek için.

- Uygulamanızın `InitInstance` işlevinde, `COleObjectFactory::UpdateRegistryAll`çağrısını bulun. Bu çağrıdan sonra, tür kitaplığınızın adı ile `AfxOleRegisterTypeLib`birlikte tür kitaplığınıza karşılık gelen **libıd** 'yi belirterek öğesine bir çağrı ekleyin:

    ```cpp
    // When a server application is launched stand-alone, it is a good idea
    // to update the system registry in case it has been damaged.
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);

    COleObjectFactory::UpdateRegistryAll();

    // DUAL_SUPPORT_START
        // Make sure the type library is registered or dual interface won't work.
        AfxOleRegisterTypeLib(AfxGetInstanceHandle(),
            LIBID_ACDual,
            _T("AutoClik.TLB"));
    // DUAL_SUPPORT_END
    ```

## <a name="modifying-project-build-settings-to-accommodate-type-library-changes"></a>Proje derleme ayarlarını tür kitaplığı değişikliklerine uyacak şekilde değiştirme

Bir projenin yapı ayarlarını değiştirmek için, tür kitaplığı yeniden oluşturulduğunda **UUID** tanımlarını içeren bir üstbilgi dosyası MkTypLib tarafından oluşturulur:

1. **Oluştur** menüsünde, **Ayarlar**' a tıklayın ve ardından her yapılandırma için dosya listesinden odl dosyasını seçin.

2. **OLE türleri** sekmesine tıklayın ve **Çıkış üstbilgisi** dosya adı alanında bir dosya adı belirtin. MkTypLib varolan bir dosyanın üzerine yazacak olduğundan, projeniz tarafından zaten kullanılmayan bir dosya adı kullanın. **Tamam** ' a tıklayarak **derleme ayarları** iletişim kutusunu kapatın.

MkTypLib tarafından oluşturulan üstbilgi dosyasındaki **UUID** tanımlarını projenize eklemek için:

1. MkTypLib tarafından oluşturulan üst bilgi dosyasını standart bir şekilde, *stbafx. h*başlık dosyasına ekleyin.

2. Yeni bir dosya, ıNITIıDS oluşturun. CPP ve projenize ekleyin. Bu dosyada, OLE2 dahil olmak üzere MkTypLib tarafından oluşturulan üst bilgi dosyanızı ekleyin. H ve ıNITGUID. Olsun

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. **Yapı** menüsünde **Ayarlar**' a ve ardından ınitiyııds ' ı seçin. Her yapılandırma için dosya listesinden CPP.

4. **C++** Sekmesine tıklayın, kategori **önceden derlenmiş üst bilgiler**' e tıklayın ve **önceden derlenmiş üst bilgiler kullanmayan** radyo düğmesini seçin. Tamam ' a tıklayarak **derleme ayarları** iletişim kutusunu kapatın.

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Tür kitaplığında doğru nesne sınıfı adını belirtme

Visual C++ ile gönderilen sihirbazlar yanlış bir şekilde uygulama sınıfı adını kullanarak, OLE-creatable sınıfları için sunucunun ODL dosyasında coclass 'ı belirtir. Bu işlem işinize başlamadan, uygulama sınıfı adı muhtemelen nesnenizin kullanıcılarının kullanmasını istediğiniz sınıf adı değildir. Doğru adı belirtmek için, ODL dosyasını açın, her coclass bildirisini bulun ve uygulama sınıfı adını doğru dış adla değiştirin.

Coclass deyimin değiştiği zaman, MkTypLib tarafından oluşturulan üst bilgi dosyasındaki **CLSID**öğeleri 'nin değişken adlarının buna göre değişdiğine unutmayın. Yeni değişken adlarını kullanmak için kodunuzu güncelleştirmeniz gerekir.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Özel durumları ve Otomasyon hata arabirimlerini işleme

Otomasyon nesnenizin yöntemleri ve özellik erişimcisi işlevleri özel durumlar oluşturabilir. Bu durumda, bunları çift arabirim uygulamanızda işlemeli ve OLE Otomasyonu hata işleme arabirimi `IErrorInfo`aracılığıyla denetleyiciye geri dönme hakkında bilgi geçirmeniz gerekir. Bu arabirim, hem hem de `IDispatch` VTBL arabirimleri aracılığıyla ayrıntılı, bağlamsal hata bilgileri sağlar. Bir hata işleyicisinin kullanılabilir olduğunu göstermek için `ISupportErrorInfo` arabirimini uygulamalısınız.

Hata işleme mekanizmasını göstermek için, standart dağıtım desteğini oluşturmak için kullanılan ClassWizard tarafından oluşturulan işlevlerin özel durum oluşturduğunu varsayın. MFC 'nin `IDispatch::Invoke` uygulanması genellikle bu özel durumları yakalar ve `Invoke` çağrı aracılığıyla döndürülen bir EXCEPTINFO yapısına dönüştürür. Ancak, VTBL arabirimi kullanıldığında, özel durumları kendi başınıza yakalamak sizin sorumluluğunuzdadır. Çift arabirim yöntemlerinizi korumanın bir örneği olarak:

```cpp
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    TRY_DUAL(IID_IDualAClick)
    {
        // MFC automatically converts from Unicode BSTR to
        // Ansi CString, if necessary...
        pThis->m_str = newText;
        return NOERROR;
    }
    CATCH_ALL_DUAL
}
```

`CATCH_ALL_DUAL`özel durum oluştuğunda doğru hata kodunu döndürmekten yararlanır. `CATCH_ALL_DUAL``ICreateErrorInfo` arabirimi kullanarak MFC özel durumunu OLE Otomasyonu hata işleme bilgilerine dönüştürür. (Örnek `CATCH_ALL_DUAL` bir makro mfcdual dosyasıdır. Y, [acdual](../overview/visual-cpp-samples.md) örneğinde. Özel durumları `DualHandleException`işlemek için çağrı yaptığı işlev, mfcdual dosyasında bulunur. CPP.) `CATCH_ALL_DUAL` oluşan özel durum türüne göre döndürülecek hata kodunu belirler:

- [Cotadispatchexception](../mfc/reference/coledispatchexception-class.md) -bu durumda, `HRESULT` aşağıdaki kod kullanılarak oluşturulur:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

   Bu, özel `HRESULT` duruma neden olan arabirime özel bir oluşturur. Standart OLE arabirimleri için sistem tarafından tanımlanan `HRESULT`bir çakışmayı önlemek üzere hata kodu 0x200 tarafından denkleştirilir.

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) -bu durumda `E_OUTOFMEMORY` döndürülür.

- Bu durumda `E_UNEXPECTED` başka bir özel durum döndürülür.

OLE Otomasyonu hata işleyicisinin kullanıldığını belirtmek için, `ISupportErrorInfo` arabirimini de uygulamalısınız.

İlk olarak, desteklediği `ISupportErrorInfo`göstermek için Otomasyon sınıfı tanımınıza kod ekleyin.

İkinci olarak, `ISupportErrorInfo` uygulama sınıfını `QueryInterface` MFC mekanizmasıyla ilişkilendirmek için Otomasyon sınıfınızın arabirim eşlemesine kod ekleyin. İfade, için `ISupportErrorInfo`tanımlanan sınıfla eşleşir. `INTERFACE_PART`

Son olarak, desteklemek `ISupportErrorInfo`için tanımlanan sınıfı uygulayın.

( [Acdual](../overview/visual-cpp-samples.md) örneği, bu üç adımı, `DECLARE_DUAL_ERRORINFO` `DUAL_ERRORINFO_PART`,, ve `IMPLEMENT_DUAL_ERRORINFO`, hepsi mfcdual içinde bulundurmaya yardımcı olmak için üç makro içerir. H.)

Aşağıdaki örnek, desteklemek `ISupportErrorInfo`için tanımlanan bir sınıfı uygular. `CAutoClickDoc`, Otomasyon sınıfınızın adıdır ve `IID_IDualAClick` OLE Otomasyonu hata nesnesi aracılığıyla raporlanan hataların kaynağı olan arabirim için **IID** 'dir:

```cpp
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::AddRef()
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalAddRef();
}

STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::Release()
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalRelease();
}

STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalQueryInterface(&iid, ppvObj);
}

STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo(
    REFIID iid)
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return (iid == IID_IDualAClick) S_OK : S_FALSE;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
