---
description: 'Hakkında daha fazla bilgi edinin: TN065: Dual-Interface support for OLE Automation Server'
title: 'TN065: OLE Otomasyon Sunucuları için Çift Arabirim Desteği'
ms.date: 06/28/2018
f1_keywords:
- vc.ole
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
ms.openlocfilehash: 9add7b42c832944c10b4b607f26b6ca8f23ae300
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214578"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: OLE Otomasyon Sunucuları için Çift Arabirim Desteği

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, MFC tabanlı bir OLE Otomasyonu sunucu uygulamasına çift arabirim desteğinin nasıl ekleneceği açıklanmaktadır. [Acdual](../overview/visual-cpp-samples.md) örneği çift arabirim desteğini gösterir ve bu notdaki örnek kod acdual 'ten alınmıştır. DECLARE_DUAL_ERRORINFO, DUAL_ERRORINFO_PART ve IMPLEMENT_DUAL_ERRORINFO gibi bu notta açıklanan makrolar, ACDUAL örneğinin bir parçasıdır ve MFCDUAL. H içinde bulunabilir.

## <a name="dual-interfaces"></a>Çift arabirimler

OLE Otomasyonu bir `IDispatch` arabirim, BIR VTBL arabirimi ya da çift bir arabirim (her ikisini de kapsayan) uygulamanıza izin veriyorsa, Microsoft, sunulan tüm OLE Otomasyonu nesneleri için ikili arabirimler uygulamanızı kesinlikle önerir. Çift arabirimlerin yalnızca daha fazla `IDispatch` veya yalnızca VTBL arabirimler için önemli avantajları vardır:

- Bağlama, VTBL arabirimi aracılığıyla ya da çalışma zamanında aracılığıyla derleme zamanında gerçekleşebilir `IDispatch` .

- VTBL arabirimini kullanabilecek OLE Otomasyonu denetleyicileri, geliştirilmiş performanstan yararlanabilir.

- Arabirimi kullanan mevcut OLE Otomasyonu denetleyicileri `IDispatch` çalışmaya devam edecektir.

- VTBL arabirimi C++ ' dan daha kolay çağrmaktır.

- Visual Basic nesne desteği özellikleriyle uyumluluk için çift arabirimler gereklidir.

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget-Based sınıfına Dual-Interface desteği ekleme

Bir çift arabirim aslında yalnızca öğesinden türetilmiş özel bir arabirimdir `IDispatch` . Tabanlı bir sınıfta çift arabirim desteği sağlamanın en kolay yolu, `CCmdTarget` öncelıkle MFC ve ClassWizard kullanarak sınıfınıza normal dağıtım arabirimini uygulamaktır, ardından özel arabirimi daha sonra eklemektir. Çoğu bölüm için, özel arabirim uygulamanız yalnızca MFC uygulamasına yeniden temsilci atamasını sağlar `IDispatch` .

İlk olarak, nesneleriniz için ikili arabirimler tanımlamak üzere sunucunuzun ODL dosyasını değiştirin. Çift arabirimi tanımlamak için, Visual C++ sihirbazları 'nın üretmesindeki deyimin yerine bir arabirim ifadesini kullanmanız gerekir `DISPINTERFACE` . Varolan ifadeyi kaldırmak yerine `DISPINTERFACE` Yeni bir arabirim açıklaması ekleyin. `DISPINTERFACE`Formu koruyarak, deyiminize Özellikler ve yöntemler eklemek Için ClassWizard 'ı kullanmaya devam edebilirsiniz, ancak Interface deyiminize eşdeğer özellikleri ve yöntemleri eklemeniz gerekir.

Çift arabirim için bir arabirim bildiriminde, *oleautomation* ve *Dual* özniteliklerine sahip olmalıdır ve arabirim öğesinden türetilmelidir `IDispatch` . Dual arabirimi için bir **IID** oluşturmak üzere [GUIDgen](../overview/visual-cpp-samples.md) örneğini kullanabilirsiniz:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

Arabirim deyiminizi oluşturduktan sonra, Yöntemler ve özellikler için girdi eklemeye başlayın. Çift arabirimler için, Çift arabirimdeki yöntemlerinizin ve özellik erişimcisinin bir **HRESULT** döndürmesi ve dönüş değerlerini özniteliklerle parametre olarak iletmeleri için parametre listelerini yeniden düzenlemeniz gerekir `[retval,out]` . Özellikler için `propget` aynı kimliğe sahip bir Read () ve Write () erişim işlevi eklemeniz gerektiğini unutmayın `propput` . Örneğin:

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

ODL dosyanız güncelleştirildikten sonra, nesne sınıfınıza çift arabirim için bir uygulama sınıfı tanımlamak ve MFC mekanizmasında karşılık gelen girdileri oluşturmak için MFC 'nin arabirim eşleme mekanizmasını kullanın `QueryInterface` . `INTERFACE_PART`ODL 'nin arabirim deyimindeki her giriş için bloğunda bir giriş ve bir dağıtım arabirimi için girdiler olması gerekir. *Propput* özniteliğine sahip her BIR ODL girişinin adlı bir işlevi olması gerekir `put_propertyname` . *Propget* özniteliğine sahip her girdinin adlı bir işlevi olması gerekir `get_propertyname` .

Dual Interface için bir uygulama sınıfı tanımlamak üzere, `DUAL_INTERFACE_PART` nesne sınıfı tanımınıza bir blok ekleyin. Örneğin:

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

İkili arabirimi MFC 'nin [QueryInterface](/windows/win32/com/queryinterface--navigating-in-an-object) mekanizmasına bağlamak için `INTERFACE_PART` arabirim eşlemesine bir giriş ekleyin:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Ardından, arabirimin uygulamasını doldurmanız gerekir. Çoğu bölüm için, mevcut MFC uygulamasına temsilci atayabileceksiniz `IDispatch` . Örneğin:

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

## <a name="passing-dual-interface-pointers"></a>Dual-Interface Işaretçilerini geçirme

Özellikle çağırmanız gerekiyorsa çift arabirim işaretçinizi geçirmek basit değildir `CCmdTarget::FromIDispatch` . `FromIDispatch` yalnızca MFC `IDispatch` işaretçilerinde kullanılabilir. Bu sorunu çözmek için bir yol, `IDispatch` MFC tarafından ayarlanan orijinal işaretçiyi sorgular ve bu işaretçiyi bu işaretçiye gereken işlevlere iletir. Örneğin:

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

- AFXCTL 'yi dahil edin. Standart içindeki H, STBAFX başlık dosyasını içerir. H, işlevin tanımına erişmek için `AfxOleRegisterTypeLib` .

- Uygulamanızın `InitInstance` işlevinde, çağrısını bulun `COleObjectFactory::UpdateRegistryAll` . Bu çağrıdan sonra, tür kitaplığınızın `AfxOleRegisterTypeLib` adı ile birlikte tür kitaplığınıza karşılık gelen **libıd** 'yi belirterek öğesine bir çağrı ekleyin:

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

1. MkTypLib tarafından oluşturulan üst bilgi dosyasını standart bir şekilde, *stbafx. h* başlık dosyasına ekleyin.

2. Yeni bir dosya, ıNITIıDS oluşturun. CPP ve projenize ekleyin. Bu dosyada, OLE2 dahil olmak üzere MkTypLib tarafından oluşturulan üst bilgi dosyanızı ekleyin. H ve ıNITGUID. Olsun

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. **Yapı** menüsünde **Ayarlar**' a ve ardından ınitiyııds ' ı seçin. Her yapılandırma için dosya listesinden CPP.

4. **C++** sekmesine tıklayın, kategori **önceden derlenmiş üst bilgiler**' e tıklayın ve **önceden derlenmiş üst bilgiler kullanmayan** radyo düğmesini seçin. Tamam ' a tıklayarak **derleme ayarları** iletişim kutusunu kapatın.

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Tür kitaplığında doğru nesne sınıfı adını belirtme

Visual C++ ile birlikte gönderilen sihirbazlar, OLE-creatable sınıfları için sunucunun ODL dosyasında coclass 'ı belirtmek üzere uygulama sınıfı adını yanlış kullanır. Bu işlem işinize başlamadan, uygulama sınıfı adı muhtemelen nesnenizin kullanıcılarının kullanmasını istediğiniz sınıf adı değildir. Doğru adı belirtmek için, ODL dosyasını açın, her coclass bildirisini bulun ve uygulama sınıfı adını doğru dış adla değiştirin.

Coclass deyimin değiştiği zaman, MkTypLib tarafından oluşturulan üst bilgi dosyasındaki **CLSID** öğeleri 'nin değişken adlarının buna göre değişdiğine unutmayın. Yeni değişken adlarını kullanmak için kodunuzu güncelleştirmeniz gerekir.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Özel durumları ve Otomasyon hata arabirimlerini işleme

Otomasyon nesnenizin yöntemleri ve özellik erişimcisi işlevleri özel durumlar oluşturabilir. Bu durumda, bunları çift arabirim uygulamanızda işlemeli ve OLE Otomasyonu hata işleme arabirimi aracılığıyla denetleyiciye geri dönme hakkında bilgi geçirmeniz gerekir `IErrorInfo` . Bu arabirim, hem hem de VTBL arabirimleri aracılığıyla ayrıntılı, bağlamsal hata bilgileri sağlar `IDispatch` . Bir hata işleyicisinin kullanılabilir olduğunu göstermek için `ISupportErrorInfo` arabirimini uygulamalısınız.

Hata işleme mekanizmasını göstermek için, standart dağıtım desteğini oluşturmak için kullanılan ClassWizard tarafından oluşturulan işlevlerin özel durum oluşturduğunu varsayın. MFC 'nin uygulanması `IDispatch::Invoke` genellikle bu özel durumları yakalar ve çağrı aracılığıyla döndürülen BIR EXCEPTıNFO yapısına dönüştürür `Invoke` . Ancak, VTBL arabirimi kullanıldığında, özel durumları kendi başınıza yakalamak sizin sorumluluğunuzdadır. Çift arabirim yöntemlerinizi korumanın bir örneği olarak:

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

`CATCH_ALL_DUAL` özel durum oluştuğunda doğru hata kodunu döndürmekten yararlanır. `CATCH_ALL_DUAL` arabirimi kullanarak MFC özel durumunu OLE Otomasyonu hata işleme bilgilerine dönüştürür `ICreateErrorInfo` . (Örnek bir `CATCH_ALL_DUAL` makro MFCDUAL dosyasıdır. Y, [acdual](../overview/visual-cpp-samples.md) örneğinde. Özel durumları işlemek için çağrı yaptığı işlev, `DualHandleException` MFCDUAL dosyasında bulunur. CPP.) `CATCH_ALL_DUAL` oluşan özel durum türüne göre döndürülecek hata kodunu belirler:

- [Cotadispatchexception](../mfc/reference/coledispatchexception-class.md) -bu durumda, `HRESULT` Aşağıdaki kod kullanılarak oluşturulur:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

   Bu `HRESULT` , özel duruma neden olan arabirime özel bir oluşturur. Standart OLE arabirimleri için sistem tarafından tanımlanan bir çakışmayı önlemek üzere hata kodu 0x200 tarafından denkleştirilir `HRESULT` .

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) -bu durumda `E_OUTOFMEMORY` döndürülür.

- Bu durumda başka bir özel durum `E_UNEXPECTED` döndürülür.

OLE Otomasyonu hata işleyicisinin kullanıldığını belirtmek için, arabirimini de uygulamalısınız `ISupportErrorInfo` .

İlk olarak, desteklediği göstermek için Otomasyon sınıfı tanımınıza kod ekleyin `ISupportErrorInfo` .

İkinci olarak, `ISupportErrorInfo` uygulama SıNıFıNı MFC mekanizmasıyla ilişkilendirmek için Otomasyon sınıfınızın arabirim eşlemesine kod ekleyin `QueryInterface` . `INTERFACE_PART`İfade, için tanımlanan sınıfla eşleşir `ISupportErrorInfo` .

Son olarak, desteklemek için tanımlanan sınıfı uygulayın `ISupportErrorInfo` .

( [Acdual](../overview/visual-cpp-samples.md) örneği, bu üç adımı,, `DECLARE_DUAL_ERRORINFO` `DUAL_ERRORINFO_PART` ve `IMPLEMENT_DUAL_ERRORINFO` , hepsi mfcdual. H içinde yer alan üç adımı da sağlar.)

Aşağıdaki örnek, desteklemek için tanımlanan bir sınıfı uygular `ISupportErrorInfo` . `CAutoClickDoc` , Otomasyon sınıfınızın adıdır ve `IID_IDualAClick` OLE Otomasyonu hata nesnesi aracılığıyla raporlanan hataların kaynağı olan arabirim Için **IID** 'dir:

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

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
