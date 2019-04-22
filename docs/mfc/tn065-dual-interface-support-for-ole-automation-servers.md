---
title: 'TN065: OLE otomasyon sunucuları için çift arabirim desteği'
ms.date: 06/28/2018
f1_keywords:
- vc.ole
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
ms.openlocfilehash: 33828f3979fb938ae6e88fa3cb0d6ee24daa958c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776680"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: OLE otomasyon sunucuları için çift arabirim desteği

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, MFC tabanlı OLE Otomasyon sunucu uygulaması için çift arabirim desteği eklemek anlatılmaktadır. [ACDUAL](../overview/visual-cpp-samples.md) örnek çift arabirim desteği gösterir ve örnek kod bu not, ACDUAL alınır. DECLARE_DUAL_ERRORINFO DUAL_ERRORINFO_PART ve IMPLEMENT_DUAL_ERRORINFO, gibi bu not açıklandığı makroları ACDUAL örneğinde bir parçasıdır ve MFCDUAL içinde bulunabilir. H

## <a name="dual-interfaces"></a>Çift arabirimler

OLE Otomasyonu olanak tanır ancak bir `IDispatch` arabirimi, VTBL arabirimi veya (Bu, her ikisi de kapsayan) çift arabirim, Microsoft önerir tüm OLE Otomasyonu nesneleri kullanıma sunulan için çift arabirim uygular. Çift arabirimler üzerinden önemli avantajları sahip `IDispatch`-yalnızca ya da yalnızca VTBL arabirimleri:

- Bağlama, yer alabilir, derleme zamanında VTBL arabirimi aracılığıyla ya da çalışma zamanında `IDispatch`.

- Geliştirilmiş performans VTBL arabirimi kullanabileceğiniz OLE Otomasyon denetleyicileri avantajlı olabilir.

- Kullanan mevcut OLE Otomasyon denetleyicileri `IDispatch` arabirimi çalışmaya devam eder.

- C++'tan çağırmak daha kolay VTBL arabirimidir.

- Çift arabirimler, Visual Basic nesne destek özellikleri ile uyumluluk için gereklidir.

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget tabanlı sınıf için çift arabirim desteği ekleme

Çift arabirim aslında öğesinden türetilen özel bir arabirim olduğundan `IDispatch`. Çift arabirim desteği uygulamak için en kolay yolu bir `CCmdTarget`-temel sınıfı olduğu için ilk uygulama normal gönderme arabirimi sınıfınıza MFC ClassWizard ile ve özel arabirim daha sonra ekleyebilirsiniz. Çoğunlukla, özel arabirim uygulamanız yalnızca MFC'ye temsilci olarak seçmesi `IDispatch` uygulaması.

ODL dosya sunucunuzun nesneleriniz için çift arabirim tanımlamak ilk olarak değiştirin. Çift arabirim tanımlamak için bir arabirimi deyimi yerine kullanmalısınız `DISPINTERFACE` Visual C++ sihirbazları oluşturma deyimi. Varolan kaldırma yerine `DISPINTERFACE` deyimi, yeni bir arabirim bildirimi ekleyin. Elinizde tutarak `DISPINTERFACE` form devam edebilirsiniz, nesne için özellikler ve yöntemler eklemek için ClassWizard kullanın, ancak eşdeğer özellikleri ve yöntemleri arabirimi Ekstrenizi eklemeniz gerekir.

Bir interface deyimi için çift arabirim olmalıdır *OLEAUTOMATION* ve *çift* öznitelikleri ve arabirimi gerekir türetilen `IDispatch`. Kullanabileceğiniz [GUIDgen](../overview/visual-cpp-samples.md) oluşturmak için örnek bir **IID** çift arabirim için:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

İnterface deyimi sağlandıktan yöntemleri ve özellikleri için girdileri ekleniyor başlatın. İkili arabirimler için yöntem ve özellik erişimci işlevleri ikili arabiriminde döndürür, böylece parametre listeleri düzenlemek gereken bir **HRESULT** ve dönüş değerlerine özniteliklerleparametrelerolarakgeçirin`[retval,out]`. Özellikler için hem bir okuma eklemeniz gerektiğini unutmayın (`propget`) ve yazma (`propput`) erişim işlevi aynı kimliğe sahip. Örneğin:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

Yöntemleri ve özellikleri tanımlandıktan sonra coclass'ı raporunuza interface deyimi bir başvuru eklemeniz gerekir. Örneğin:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

ODL dosyanız güncelleştirildi sonra çift arabirim için bir uygulama sınıf nesnesi Sınıfınız içinde tanımlamak ve MFC'nin içinde karşılık gelen girişler yapmak için MFC'nin arabirim eşleme mekanizmasının kullanın `QueryInterface` mekanizması. Bir girişi ihtiyacınız `INTERFACE_PART` ODL arabirimi deyiminin her giriş yanı sıra, dağıtım arabirimi girişleri için blok. Her bir ODL girdi *propput* özniteliği gerekiyor adlı bir işlev `put_propertyname`. Her bir girdi *propget* özniteliği gerekiyor adlı bir işlev `get_propertyname`.

Ekleme, çift arabirim için bir uygulama sınıf tanımlamak için bir `DUAL_INTERFACE_PART` blok nesne sınıfının tanımı. Örneğin:

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

MFC'nin için çift arabirim bağlanmak için [QueryInterface](/windows/desktop/com/queryinterface--navigating-in-an-object) mekanizması ekleme bir `INTERFACE_PART` arabirim eşleme girişi:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Ardından, arabirim uygulamasında doldurmanız gerekir. Çoğunlukla, varolan bir MFC için temsilci seçmek mümkün olacaktır `IDispatch` uygulaması. Örneğin:

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

Nesnenizin yöntem ve özellik erişimci işlevleri için uygulamasında doldurmanız gerekir. Yöntem ve özellik işlevlerinizi geri ClassWizard kullanılarak oluşturulan yöntemler genellikle devredebilirsiniz. Ancak, doğrudan değişkenlere erişmek için özelliklerini ayarlama, değeri bir değişkene get/put için kod yazma gerekir. Örneğin:

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

Çift arabirim işaretçinizi geçirme özellikle çağırmak gerekiyorsa basit olmayan `CCmdTarget::FromIDispatch`. `FromIDispatch` MFC'nin üzerinde yalnızca çalışır `IDispatch` işaretçileri. Bu sorunu çözmenin bir yolu özgün sorguya `IDispatch` işaretçi kümesi yukarı MFC tarafından ve ihtiyaç duyduğunuz işleve işaretçiyle geçirin. Örneğin:

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

Çift Arabirim yöntemiyle bir işaretçi geçirmeden önce MFC'den dönüştürmeniz gerekebilir `IDispatch` işaretçinizi çift arabirim işaretçisi. Örneğin:

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

## <a name="registering-the-applications-type-library"></a>Uygulamanın tür kitaplığını kaydettirme

AppWizard ile sistem bir OLE Otomasyon sunucusu uygulamanın tür kitaplığını kaydetmek için kod oluşturmaz. Tür kitaplığını kaydetmek için kullanabileceğiniz diğer yöntemler olsa da, tek başına uygulama çalıştırıldığında, OLE tür bilgileri, diğer bir deyişle, güncelleştirilirken tür kitaplığı kaydı uygulama uygundur.

Kaydetmek için uygulama her çalıştırıldığında uygulamanın tür kitaplığı tek başına:

- AFXCTL içerir. H, standart üstbilgi dosyasına STDAFX içerir. Tanımına erişmek için H `AfxOleRegisterTypeLib` işlevi.

- Uygulamanızın `InitInstance` işlev, çağrı bulun `COleObjectFactory::UpdateRegistryAll`. Bu çağrıyı izleyen bir çağrı ekleyin `AfxOleRegisterTypeLib`, belirten **LIBID** , tür kitaplığının adı ile birlikte, tür kitaplığı ile eşleşen:

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

## <a name="modifying-project-build-settings-to-accommodate-type-library-changes"></a>Tür kitaplığı değişikliği karşılamak için proje derleme ayarlarını değiştirme

Bir projenin derleme ayarları değiştirmek için böylece bir üstbilgi dosyasını içeren **UUID** tanımları, her tür kitaplığı yeniden MkTypLib tarafından oluşturulur:

1. Üzerinde **derleme** menüsünde tıklatın **ayarları**ve ardından her bir yapılandırma dosyası listesinden ODL dosyasını seçin.

2. Tıklayın **OLE türleri** sekme ve dosya adını belirtin **çıkış üst** filename alan. MkTypLib varolan dosyanın üzerine yazılacağından projeniz tarafından kullanılmayan bir dosya adı kullanın. Tıklayın **Tamam** kapatmak için **Build Settings** iletişim kutusu.

Eklenecek **UUID** MkTypLib tarafından oluşturulan üstbilgi dosyasını projenize tanımları:

1. MkTypLib oluşturulan dahil, standart üstbilgi dosyasında üstbilgi dosyasına STDAFX içerir. H

2. INITIIDS yeni bir dosya oluşturun. CPP ve projenize ekleyin. Bu dosyada, OLE2 eklendikten sonra MkTypLib tarafından oluşturulan üstbilgi dosyasını dahil. H ve INITGUID. Y:

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. Üzerinde **derleme** menüsünde tıklayın **ayarları**ve ardından INITIIDS seçin. Her yapılandırma dosyası listesinden CPP.

4. Tıklayın **C++** sekmesinde, kategori **önceden derlenmiş üst bilgiler**seçip **önceden derlenmiş üst bilgiler kullanılmıyor** radyo düğmesi. Kapatmak için Tamam'a tıklayın **Build Settings** iletişim kutusu.

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Tür Kitaplığı'nda doğru nesne sınıfı adı belirtme

Visual C++ ile yanlış sevk sihirbazları uygulama sınıf adı OLE RegAsm.exe'nin derlemedeki oluşturulabilir sınıfları için sunucunun ODL dosyasındaki coclass'ı belirtmek için kullanın. Bu çalışır durumdayken uygulama sınıf adı büyük olasılıkla, nesnenizin kullanıcılarının kullanmasını istediğiniz sınıf adı değil. Doğru adını belirtmek için ODL dosyasını açın, her coclass'ı ifadesini bulun ve uygulama sınıf adı doğru dış adı ile değiştirin.

Coclass'ı deyimi değiştirildiğinde, değişken adlarını unutmayın **CLSID**MkTypLib tarafından oluşturulan üstbilgi dosyasında s buna göre değişir. Yeni değişken adlarını kullanmak için kodunuzu güncelleştirmeniz gerekir.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Özel durumları işleme ve Otomasyon hatası arabirimleri

Otomasyon nesnenin yöntemleri ve özellik erişimci işlevleri, özel durumlar. Bu nedenle, bunları çift arabirim uygulamanızda işlemeli ve özel durum hakkında bilgi OLE Otomasyonu hata işleme arabirimi aracılığıyla denetleyiciye geri geçirmek, `IErrorInfo`. Her ikisi de aracılığıyla ayrıntılı ve bağlamsal hata bilgileri için bu arabirimi sağlayan `IDispatch` ve VTBL arabirimleri. Bir hata işleyicisi kullanılabilir, uygulamalıdır belirtmek için `ISupportErrorInfo` arabirimi.

Hata işleme mekanizması göstermek için standart dağıtım desteği uygulamak için kullanılan ClassWizard oluşturulan işlevlere özel durumlar varsayılır. MFC'nin uygulaması `IDispatch::Invoke` genellikle bu özel durumlarını yakalayan ve bunları ile döndürülen bir EXCEPTINFO yapısına dönüştürür `Invoke` çağırın. VTBL arabirimi kullanıldığında, ancak özel durumları kendiniz yakalama için sorumlu olursunuz. Çift arabirim yöntemlerinizi korumaya ilişkin bir örnek:

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

`CATCH_ALL_DUAL` doğru hata kodunu döndüren bir özel durum oluştuğunda üstlenir. `CATCH_ALL_DUAL` OLE Otomasyonu hata işleme bilgileri kullanarak bir MFC özel durum dönüştürür `ICreateErrorInfo` arabirimi. (Örnek `CATCH_ALL_DUAL` MFCDUAL dosyasında makrodur. H [ACDUAL](../overview/visual-cpp-samples.md) örnek. Özel durumları işlemek için çağıran işlev `DualHandleException`, MFCDUAL dosyasıdır. CPP.) `CATCH_ALL_DUAL` oluşan özel durum türüne göre döndürülecek hata kodu belirler:

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - bu durumda, `HRESULT` kullanılarak aşağıdaki kod oluşturulur:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

   Bu, oluşturur bir `HRESULT` özel duruma neden olan arabirimi özgüdür. Hata kodu ile sistem tarafından tanımlanan tüm çakışmaları önlemek için 0x200 tarafından uzaklığı `HRESULT`standart OLE arabirimleri için s.

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - bu durumda, `E_OUTOFMEMORY` döndürülür.

- Diğer özel - bu durumda, `E_UNEXPECTED` döndürülür.

OLE Otomasyonu hata işleyicisini kullanılır, ayrıca uygulamalıdır belirtmek için `ISupportErrorInfo` arabirimi.

İlk olarak, kod desteklediğini göstermek için Otomasyon sınıf tanımına ekleyin `ISupportErrorInfo`.

İkinci olarak, kodu ilişkilendirmek için Otomasyon sınıfın arabirim haritasını ekleyin `ISupportErrorInfo` MFC'nin uygulaması sınıfıyla `QueryInterface` mekanizması. `INTERFACE_PART` Deyimi için tanımlanan sınıfı eşleşen `ISupportErrorInfo`.

Son olarak, desteklemek için tanımlanmış bir sınıf uygulamak `ISupportErrorInfo`.

( [ACDUAL](../overview/visual-cpp-samples.md) örnek içeren aşağıdaki üç adımda yapmanız yardımcı olması için üç makroları `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, ve `IMPLEMENT_DUAL_ERRORINFO`, MFCDUAL içerdiği tüm. H)

Aşağıdaki örnek desteklemek için tanımlanmış bir sınıf uygulayan `ISupportErrorInfo`. `CAutoClickDoc` Otomasyon sınıfınıza adıdır ve `IID_IDualAClick` olduğu **IID** OLE Otomasyonu hata nesnesi bildirilen hatalar kaynağı arabirimi için:

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
