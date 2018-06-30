---
title: 'TN065: OLE otomasyon sunucuları için çift arabirim desteği | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.ole
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e30be46aeab92f63f1b4cba593cda52bf9aeef9a
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122189"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: OLE Otomasyon Sunucuları için Çift Arabirim Desteği

> [!NOTE]
> İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.

Bu Not bir MFC tabanlı OLE Otomasyon sunucu uygulaması için çift arabirim desteği ekleme açıklanır. [ACDUAL](../visual-cpp-samples.md) örnek çift arabirim desteği gösterir ve bu not örnek kodda ACDUAL alınır. DECLARE_DUAL_ERRORINFO, DUAL_ERRORINFO_PART ve IMPLEMENT_DUAL_ERRORINFO, gibi bu not açıklandığı makroları ACDUAL örneği parçası olan ve MFCDUAL içinde bulunabilir. H.

## <a name="dual-interfaces"></a>Çift arabirimler

OLE Otomasyon uygulamak sağlar ancak bir `IDispatch` arabirimi, VTBL arabirimi ya da (her ikisi de kapsar) bir çift arabirimi, Microsoft önerir tüm OLE Otomasyonu nesneleri açığa çıkarılan çift arabirimler uygulayın. Çift arabirimler üzerinden oldukça önemli avantajlara sahip `IDispatch`-yalnızca ya da yalnızca VTBL arabirimleri:

- Bağlama, yer alabilir, VTBL arabirimi aracılığıyla derleme zamanında ya da aracılığıyla çalışma zamanında `IDispatch`.

- VTBL arabirimi kullanabileceğiniz OLE Otomasyon denetleyicileri performansı yararlanabilir.

- Kullanan mevcut OLE Otomasyon denetleyiciler `IDispatch` arabirimi çalışmaya devam edecektir.

- C++ içinden çağırmak daha kolay VTBL arabirimidir.

- Çift arabirimler Visual Basic nesne destek özellikleri ile uyumluluk için gereklidir.

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget tabanlı bir sınıfına çift arabirim desteği ekleme

Bir çift arabirim türetilmiş gerçekten yalnızca bir özel arabirimdir `IDispatch`. Çift arabirim desteği uygulamak için en kolay yolu bir `CCmdTarget`-temel sınıftır için ilk uygulama normal gönderme arabirimi kullanarak MFC ve ClassWizard sınıfınız, ardından özel arabirim daha sonra ekleyin. Çoğunlukla, özel arabirim uygulamanız yeterlidir geri MFC'ye temsil edecek `IDispatch` uygulaması.

İlk olarak, çift arabirimler nesneleriniz için tanımlamak sunucunuzun ODL dosyasını değiştirin. Çift arabirim tanımlamak için bir arabirim deyimi yerine kullanmalısınız `DISPINTERFACE` Visual C++ sihirbazları oluşturma deyimi. Varolan kaldırma yerine `DISPINTERFACE` deyimi, yeni bir arabirim deyimini ekleyin. Koruyarak `DISPINTERFACE` form, devam edebilirsiniz, nesne özellikleri ve yöntemleri eklemek için ClassWizard kullanın, ancak eşdeğer özellikleri ve yöntemleri arabirimi deyiminizde eklemeniz gerekir.

Çift arabirim için bir arabirim deyimi olmalıdır *OLEAUTOMATION* ve *çift* öznitelikleri ve arabirim türetilmeli `IDispatch`. Kullanabileceğiniz [GUIDgen](../visual-cpp-samples.md) oluşturmak için örnek bir **IID** çift arabirim için:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

İnterface deyimi sağlandıktan sonra yöntemleri ve özellikleri için girişleri eklemeye başlayın. Çift arabirimler için yöntem ve özellik erişimcisi işlevleri çift arabiriminde dönüş böylece parametre listeleri düzenlemek gereken bir **HRESULT** ve dönüş değerlerine özniteliklerleparametreolarakgeçirmek`[retval,out]`. Özellikler için hem de bir okuma eklemeniz gerektiğini unutmayın (`propget`) ve yazma (`propput`) erişim işlevi aynı kimliğe sahip. Örneğin:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

Yöntemleri ve özellikleri tanımlandıktan sonra coclass deyiminizde arabirimi deyim için bir başvuru eklemeniz gerekir. Örneğin:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

ODL dosyanızı güncelleştirilmiş sonra MFC'nin arabirimi eşleme mekanizmasını çift arabirim için bir uygulama sınıf, nesne sınıfında tanımlayın ve karşılık gelen girdilere MFC'nin içinde yapmak için kullanın `QueryInterface` mekanizması. Bir giriş gereksinim `INTERFACE_PART` dağıtma arabirimi girişlerinde yanı sıra ODL arabirimi deyiminin her giriş için bloğu. Her ODL girişle *propput* özniteliği gerekiyor adlı bir işlev `put_propertyname`. Her giriş ile *propget* özniteliği gerekiyor adlı bir işlev `get_propertyname`.

Çift arabiriminiz için bir uygulama sınıf tanımlamak için ekleyin bir `DUAL_INTERFACE_PART` nesne sınıfı tanımınızı bloğu. Örneğin:

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

MFC'nin için çift arabirim bağlanmak için [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) mekanizması, ekleme bir `INTERFACE_PART` arabirimi Haritası girişine:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Ardından, arabirim uygulamasında doldurmanız gerekir. Çoğunlukla, varolan MFC temsilci mümkün olacaktır `IDispatch` uygulaması. Örneğin:

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

Nesnenin yöntem ve özellik erişimcisi işlevleri için uygulamasında doldurmanız gerekir. Yöntem ve özellik işlevlerinizi genellikle ClassWizard kullanılarak oluşturulan yöntemler yeniden atayabilirsiniz. Ancak, değişkenleri doğrudan erişmek için özelliklerini ayarlarsanız, get/değeri değişkene put için kod yazmanız gerekir. Örneğin:

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

## <a name="passing-dual-interface-pointers"></a>Çift arabirim işaretçileri geçirme

Çift arabirim işaretçinizi geçirme değil özellikle çağırmanız gerekiyorsa basit `CCmdTarget::FromIDispatch`. `FromIDispatch` yalnızca MFC'nin üzerinde çalışır `IDispatch` işaretçileri. Bu sorunu çözmenin bir yolu sorgulamak için özgün `IDispatch` işaretçi kümesi yukarı MFC tarafından ve bu işaretçiyi ihtiyaç işlevleri geçirin. Örneğin:

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

Çift arabirim yöntemle bir işaretçi geçirmeden önce MFC'den dönüştürmeniz gerekebilir `IDispatch` çift arabirim işaretçinizi işaretçi. Örneğin:

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

## <a name="registering-the-applications-type-library"></a>Uygulamanın tür kitaplığı kaydı

AppWizard kod sistemiyle OLE Otomasyon sunucusu uygulamanın tür kitaplığının kaydı oluşturmaz. Tür kitaplığı kaydı diğer yolları olsa da, her uygulama tek başına çalıştırdığınızda, OLE türü bilgilerini, diğer bir deyişle, güncelleştirilirken tür kitaplığının kaydı uygulaması sağlamak kullanışlıdır.

Kaydetmek için her uygulamayı çalıştırdığınızda uygulamanın türü kitaplığı tek başına:

- AFXCTL içerir. H, standart üstbilgi dosyası, STDAFX içerir. Tanımını erişmek için H `AfxOleRegisterTypeLib` işlevi.

- Uygulamanızın içinde `InitInstance` işlev, çağrısı bulun `COleObjectFactory::UpdateRegistryAll`. Bu çağrı aşağıdaki eklemek için bir çağrı `AfxOleRegisterTypeLib`, belirten **kitaplık kimliği** türü kitaplığınızın adını yanı sıra, tür kitaplığı karşılık gelen:

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

## <a name="modifying-project-build-settings-to-accommodate-type-library-changes"></a>Tür kitaplığı değişiklikleri uyum sağlamak için projeyi derleme ayarlarını değiştirme

Bir projenin yapı ayarları değiştirmek için böylece içeren bir üstbilgi dosyası **UUID** tür kitaplığı yeniden her tanımları MkTypLib tarafından oluşturulur:

1. Üzerinde **yapı** menüsünde tıklatın **ayarları**ve ardından her yapılandırma dosyası listesinden ODL dosyasını seçin.

2. Tıklatın **OLE türleri** sekmesinde ve dosya adını belirtin **çıkış üstbilgisi** dosya adı alanı. MkTypLib varolan dosyanın üzerine yazmak için projeniz tarafından kullanılmayan bir dosya adı kullanın. Tıklatın **Tamam** kapatmak için **Build Settings** iletişim kutusu.

Eklemek için **UUID** MkTypLib üretilen üstbilgi dosyası tanımları projenize:

1. MkTypLib oluşturulan dahil, standart üstbilgi dosyasında üstbilgi dosyası, STDAFX içerir. H.

2. INITIIDS yeni bir dosya oluşturun. CPP ve projenize ekleyin. Bu dosyada OLE2 dahil sonra MkTypLib üretilen üstbilgi dosyası içerir. H ve INITGUID. Y:

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. Üzerinde **yapı** menüsünde tıklatın **ayarları**ve ardından INITIIDS seçin. Her yapılandırma dosyası listesinden CPP.

4. ' I tıklatın **C++** sekmesinde, kategori **önceden derlenmiş üstbilgiler**seçip **önceden derlenmiş üstbilgiler kullanmıyorsa** radyo düğmesi. Kapatmak için Tamam'ı **Build Settings** iletişim kutusu.

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Tür Kitaplığı'nda doğru nesne sınıfı adı belirtme

Visual C++ ile yanlış sevk sihirbazları uygulama sınıf adı OLE creatable sınıfları için sunucunun ODL dosyasında coclass'ı belirtmek için kullanın. Bu çalışır durumdayken uygulama sınıf adı büyük olasılıkla kullanıcıların nesnenizin kullanmasını istediğiniz sınıf adı değil. Doğru adını belirtmek için ODL dosyasını açın, her coclass ifadesini bulun ve uygulama sınıf adı doğru dış adıyla değiştirin.

Coclass deyimi değiştirildiğinde, değişken adlarını unutmayın **CLSID**s MkTypLib üretilen üstbilgi dosyasında uygun şekilde değiştirir. Kodunuzu yeni değişken adları kullanacak şekilde güncelleştirmeniz gerekir.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Özel durumlar ve Otomasyon hatası arabirimleri işleme

Özel durumlar, Otomasyon nesnenin yöntem ve özellik erişimcisi işlevleri atabilir. Bu nedenle, size çift arabirim uygulamanızda işlemek ve denetleyici OLE Otomasyon hata işleme arabirimi aracılığıyla dön özel durumla ilgili bilgileri geçirmek `IErrorInfo`. Her ikisi de aracılığıyla ayrıntılı, bağlamsal hata bilgileri için bu arabirimi sağlar `IDispatch` ve VTBL arabirimler. Bir hata işleyicisi kullanılabilir, uygulamanız gerekir belirtmek için `ISupportErrorInfo` arabirimi.

Hata işleme mekanizması göstermek için standart dağıtım desteği uygulamak için kullanılan ClassWizard oluşturulan işlevleri özel durumlar oluşturma varsayalım. MFC'nin uyarlamasını `IDispatch::Invoke` genellikle bu özel durumları yakalar ve bunları yoluyla döndürülen bir EXCEPTINFO yapısına dönüştürür `Invoke` çağırın. VTBL arabirimi kullanıldığında, ancak, özel durumları kendiniz yakalama için sorumluluğu size aittir. Çift arabirim yöntemlerinizi koruma örnek:

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

`CATCH_ALL_DUAL` özel durum oluştuğunda doğru hata kodu döndürüyor mvc'deki. `CATCH_ALL_DUAL` OLE Otomasyon hata işleme bilgileri kullanılarak'ye MFC özel durum dönüştürür `ICreateErrorInfo` arabirimi. (Bir örnek `CATCH_ALL_DUAL` makro MFCDUAL dosyasında oluşur. H [ACDUAL](../visual-cpp-samples.md) örnek. Özel durumları, işleme çağıran işlevi `DualHandleException`, MFCDUAL dosyasıdır. CPP.) `CATCH_ALL_DUAL` oluşan özel durum türüne göre döndürülecek hata kodu belirler:

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - bu durumda, `HRESULT` aşağıdaki kodu kullanarak oluşturulur:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

     Bu oluşturur bir `HRESULT` özel duruma neden arabirimi özgüdür. Hata kodu ile sistem tarafından tanımlanan tüm çakışmaları önlemek için 0x200 tarafından uzaklığı `HRESULT`s standart OLE arabirimleri için.

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - bu durumda, `E_OUTOFMEMORY` döndürülür.

- Tüm diğer özel durum oluştu - Bu durumda, `E_UNEXPECTED` döndürülür.

OLE Otomasyon hatası işleyici kullanılır, ayrıca uygulamalıdır belirtmek için `ISupportErrorInfo` arabirimi.

İlk olarak, kod destekliyorsa göstermek için Otomasyon sınıf tanımına ekleyin `ISupportErrorInfo`.

İkinci olarak, kod ilişkilendirilecek Otomasyonu sınıfınızın arabirimi eşlemesine eklemek `ISupportErrorInfo` MFC'nin uygulama sınıfıyla `QueryInterface` mekanizması. `INTERFACE_PART` Deyimi eşleşen için tanımlanan sınıfı `ISupportErrorInfo`.

Son olarak, destek için tanımlanmış bir sınıf uygulama `ISupportErrorInfo`.

( [ACDUAL](../visual-cpp-samples.md) örnek içeren bu üç adımı yapmak yardımcı olmak için üç makroları `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, ve `IMPLEMENT_DUAL_ERRORINFO`, MFCDUAL içerdiği tüm. H.)

Aşağıdaki örnek desteklemek için tanımlanmış bir sınıf uygulayan `ISupportErrorInfo`. `CAutoClickDoc` Otomasyon sınıfınız adıdır ve `IID_IDualAClick` olan **IID** kaynağı OLE Otomasyon hata nesnesi bildirilen hatalar, arabirim için:

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

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)  
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)  
