---
title: 'TN065: OLE otomasyon sunucuları için çift arabirim desteği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 3b1c0d30938529d9eb432e6171b546a42f87905a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386079"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: OLE Otomasyon Sunucuları için Çift Arabirim Desteği
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not bir MFC tabanlı OLE Otomasyon sunucu uygulaması için çift arabirim desteği ekleme açıklanır. [ACDUAL](../visual-cpp-samples.md) örnek çift arabirim desteği gösterir ve bu not örnek kodda ACDUAL alınır. Bu notta gibi açıklandığı makroları `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, ve `IMPLEMENT_DUAL_ERRORINFO`, ACDUAL örneği parçası olan ve MFCDUAL içinde bulunabilir. H.  
  
## <a name="dual-interfaces"></a>Çift arabirimler  
 OLE Otomasyon uygulamak sağlar ancak bir `IDispatch` arabirimi, VTBL arabirimi ya da (her ikisi de kapsar) bir çift arabirimi, Microsoft önerir tüm OLE Otomasyonu nesneleri açığa çıkarılan çift arabirimler uygulayın. Çift arabirimler üzerinden oldukça önemli avantajlara sahip `IDispatch`-yalnızca ya da yalnızca VTBL arabirimleri:  
  
-   Bağlama, yer alabilir, VTBL arabirimi aracılığıyla derleme zamanında ya da aracılığıyla çalışma zamanında `IDispatch`.  
  
-   VTBL arabirimi kullanabileceğiniz OLE Otomasyon denetleyicileri performansı yararlanabilir.  
  
-   Kullanan mevcut OLE Otomasyon denetleyiciler `IDispatch` arabirimi çalışmaya devam edecektir.  
  
-   C++ içinden çağırmak daha kolay VTBL arabirimidir.  
  
-   Çift arabirimler Visual Basic nesne destek özellikleri ile uyumluluk için gereklidir.  
  
## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget tabanlı bir sınıfına çift arabirim desteği ekleme  
 Bir çift arabirim türetilmiş gerçekten yalnızca bir özel arabirimdir `IDispatch`. Çift arabirim desteği uygulamak için en kolay yolu bir `CCmdTarget`-temel sınıftır için ilk uygulama normal gönderme arabirimi kullanarak MFC ve ClassWizard sınıfınız, ardından özel arabirim daha sonra ekleyin. Çoğunlukla, özel arabirim uygulamanız yeterlidir geri MFC'ye temsil edecek `IDispatch` uygulaması.  
  
 İlk olarak, çift arabirimler nesneleriniz için tanımlamak sunucunuzun ODL dosyasını değiştirin. Çift arabirim tanımlamak için bir arabirim deyimi yerine kullanmalısınız `DISPINTERFACE` Visual C++ sihirbazları oluşturma deyimi. Varolan kaldırma yerine `DISPINTERFACE` deyimi, yeni bir arabirim deyimini ekleyin. Koruyarak `DISPINTERFACE` form, devam edebilirsiniz, nesne özellikleri ve yöntemleri eklemek için ClassWizard kullanın, ancak eşdeğer özellikleri ve yöntemleri arabirimi deyiminizde eklemeniz gerekir.  
  
 Çift arabirim için bir arabirim deyimi olmalıdır **OLEAUTOMATION** ve **çift** öznitelikleri ve arabirim türetilmeli `IDispatch`. Kullanabileceğiniz [GUIDgen](../visual-cpp-samples.md) oluşturmak için örnek bir **IID** çift arabirim için:  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
    oleautomation, 
    dual 
]  
interface IDualAClick : IDispatch  
 {  
 };  
```  
  
 İnterface deyimi sağlandıktan sonra yöntemleri ve özellikleri için girişleri eklemeye başlayın. Çift arabirimler için yöntem ve özellik erişimcisi işlevleri çift arabiriminde dönüş böylece parametre listeleri düzenlemek gereken bir `HRESULT` ve dönüş değerlerine özniteliklerle parametre olarak geçirmek `[retval,out]`. Özellikler için hem de bir okuma eklemeniz gerektiğini unutmayın (`propget`) ve yazma (`propput`) erişim işlevi aynı kimliğe sahip. Örneğin:  
  
```  
[propput,
    id(1)] HRESULT text([in] BSTR newText);

[propget,
    id(1)] HRESULT text([out,
    retval] BSTR* retval);
```  
  
 Yöntemleri ve özellikleri tanımlandıktan sonra coclass deyiminizde arabirimi deyim için bir başvuru eklemeniz gerekir. Örneğin:  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
    dispinterface IAClick;  
 [default] interface IDualAClick;  
};  
```  
  
 ODL dosyanızı güncelleştirilmiş sonra MFC'nin arabirimi eşleme mekanizmasını çift arabirim için bir uygulama sınıf, nesne sınıfında tanımlayın ve karşılık gelen girdilere MFC'nin içinde yapmak için kullanın `QueryInterface` mekanizması. Bir giriş gereksinim `INTERFACE_PART` dağıtma arabirimi girişlerinde yanı sıra ODL arabirimi deyiminin her giriş için bloğu. Her ODL girişle **propput** özniteliği gerekiyor adlı bir işlev `put_propertyname`. Her giriş ile **propget** özniteliği gerekiyor adlı bir işlev `get_propertyname`.  
  
 Çift arabiriminiz için bir uygulama sınıf tanımlamak için ekleyin bir `DUAL_INTERFACE_PART` nesne sınıfı tanımınızı bloğu. Örneğin:  
  
```  
BEGIN_DUAL_INTERFACE_PART(DualAClick,
    IDualAClick)  
    STDMETHOD(put_text)(THIS_ BSTR newText);

    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);

    STDMETHOD(put_x)(THIS_ short newX);

    STDMETHOD(get_x)(THIS_ short FAR* retval);

    STDMETHOD(put_y)(THIS_ short newY);

    STDMETHOD(get_y)(THIS_ short FAR* retval);

    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);

    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);

    STDMETHOD(RefreshWindow)(THIS);

 STDMETHOD(SetAllProps)(THIS_ short x,
    short y,
    BSTR text);

    STDMETHOD(ShowWindow)(THIS);

END_DUAL_INTERFACE_PART(DualAClick) 
```  
  
 MFC'nin için çift arabirim bağlanmak için [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) mekanizması, ekleme bir `INTERFACE_PART` arabirimi Haritası girişine:  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc,
    CDocument)  
    INTERFACE_PART(CAutoClickDoc,
    DIID_IAClick,
    Dispatch)  
    INTERFACE_PART(CAutoClickDoc,
    IID_IDualAClick,
    DualAClick)  
END_INTERFACE_MAP()  
```  
  
 Ardından, arabirim uygulamasında doldurmanız gerekir. Çoğunlukla, varolan MFC temsilci mümkün olacaktır `IDispatch` uygulaması. Örneğin:  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalAddRef();

}  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalRelease();

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfoCount(pctinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo,
    lcid,
    pptinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,  
    LCID lcid,
    DISPID FAR* rgdispid)   
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid,
    rgszNames,
    cNames,   
    lcid,
    rgdispid);

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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember,
    riid,
    lcid,  
    wFlags,
    pdispparams,
    pvarResult,  
    pexcepinfo,
    puArgErr);

}  
```  
  
 Nesnenin yöntem ve özellik erişimcisi işlevleri için uygulamasında doldurmanız gerekir. Yöntem ve özellik işlevlerinizi genellikle ClassWizard kullanılarak oluşturulan yöntemler yeniden atayabilirsiniz. Ancak, değişkenleri doğrudan erişmek için özelliklerini ayarlarsanız, get/değeri değişkene put için kod yazmanız gerekir. Örneğin:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Unicode BSTR to *// Ansi CString,
    if necessary...  
    pThis->m_str = newText;  
    return NOERROR;  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Ansi CString to *// Unicode BSTR,
    if necessary...  
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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDisp;  
    lpDisp = pThis->GetPosition();
lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);

    return NOERROR;  
}  
```  
  
## <a name="registering-the-applications-type-library"></a>Uygulamanın tür kitaplığı kaydı  
 AppWizard kod sistemiyle OLE Otomasyon sunucusu uygulamanın tür kitaplığının kaydı oluşturmaz. Tür kitaplığı kaydı diğer yolları olsa da, her uygulama tek başına çalıştırdığınızda, OLE türü bilgilerini, diğer bir deyişle, güncelleştirilirken tür kitaplığının kaydı uygulaması sağlamak kullanışlıdır.  
  
 Kaydetmek için her uygulamayı çalıştırdığınızda uygulamanın türü kitaplığı tek başına:  
  
-   AFXCTL içerir. H, standart üstbilgi dosyası, STDAFX içerir. Tanımını erişmek için H `AfxOleRegisterTypeLib` işlevi.  
  
-   Uygulamanızın içinde `InitInstance` işlev, çağrısı bulun `COleObjectFactory::UpdateRegistryAll`. Bu çağrı aşağıdaki eklemek için bir çağrı `AfxOleRegisterTypeLib`, belirten **kitaplık kimliği** türü kitaplığınızın adını yanı sıra, tür kitaplığı karşılık gelen:  
  
 ''' * / Sunucu uygulaması bağımsız olarak başlatıldığında, iyi bir fikir olduğu * / / zarar görmüş durumda sistem kayıt defteri güncelleştirilemiyor.  
    m_server. UpdateRegistry(OAT_DISPATCH_OBJECT);

 COleObjectFactory::UpdateRegistryAll(); *// DUAL_SUPPORT_START *// Make sure the type library is registered or dual interface won't work.  
AfxOleRegisterTypeLib(AfxGetInstanceHandle(), LIBID_ACDual, _T("AutoClik.TLB")); *// DUAL_SUPPORT_END  
 ```  
  
## Modifying Project Build Settings to Accommodate Type Library Changes  
 To modify a project's build settings so that a header file containing **UUID** definitions is generated by MkTypLib whenever the type library is rebuilt:  
  
1.  On the **Build** menu, click **Settings**, and then select the ODL file from the file list for each configuration.  
  
2.  Click the **OLE Types** tab and specify a filename in the **Output header** filename field. Use a filename that is not already used by your project, because MkTypLib will overwrite any existing file. Click **OK** to close the **Build Settings** dialog box.  
  
 To add the **UUID** definitions from the MkTypLib-generated header file to your project:  
  
1.  Include the MkTypLib-generated header file in your standard includes header file, STDAFX.H.  
  
2.  Create a new file, INITIIDS.CPP, and add it to your project. In this file, include your MkTypLib-generated header file after including OLE2.H and INITGUID.H:  
  
 ```  
    initIIDs.c: IID'leri çift arabirimler için tanımlar  
    Bu önceden derlenmiş üst bilgi ile oluşturulmalıdır değil.  
      #<a name="include-ole2h"></a>< ole2.h > içerir  
      #<a name="include-initguidh"></a>< initguid.h > içerir  
      #<a name="include-acdualh"></a>"acdual.h" içerir  
 ```  
  
3.  On the **Build** menu, click **Settings**, and then select INITIIDS.CPP from the file list for each configuration.  
  
4.  Click the **C++** tab, click category **Precompiled Headers**, and select the **Not using precompiled headers** radio button. Click OK to close the **Build Settings** dialog box.  
  
## Specifying the Correct Object Class Name in the Type Library  
 The wizards shipped with Visual C++ incorrectly use the implementation class name to specify the coclass in the server's ODL file for OLE-creatable classes. While this will work, the implementation class name is probably not the class name you want users of your object to use. To specify the correct name, open the ODL file, locate each coclass statement, and replace the implementation class name with the correct external name.  
  
 Note that when the coclass statement is changed, the variable names of **CLSID**s in the MkTypLib-generated header file will change accordingly. You will need to update your code to use the new variable names.  
  
## Handling Exceptions and the Automation Error Interfaces  
 Your automation object's methods and property accessor functions may throw exceptions. If so, you should handle them in your dual-interface implementation and pass information about the exception back to the controller through the OLE Automation error-handling interface, **IErrorInfo**. This interface provides for detailed, contextual error information through both `IDispatch` and VTBL interfaces. To indicate that an error handler is available, you should implement the **ISupportErrorInfo** interface.  
  
 To illustrate the error-handling mechanism, assume that the ClassWizard-generated functions used to implement the standard dispatch support throw exceptions. MFC's implementation of **IDispatch::Invoke** typically catches these exceptions and converts them into an EXCEPTINFO structure that is returned through the `Invoke` call. However, when VTBL interface is used, you are responsible for catching the exceptions yourself. As an example of protecting your dual-interface methods:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE (CAutoClickDoc, DualAClick)  
    TRY_DUAL(IID_IDualAClick) {* / / MFC otomatik olarak dönüştürür Unicode BSTR gelen * / / ANSI CString, gerekirse...  
    pThis -> m_str newText; =  
    NOERROR döndürür;  
 }  
    CATCH_ALL_DUAL}  
```  
  
 `CATCH_ALL_DUAL` takes care of returning the correct error code when an exception occurs. `CATCH_ALL_DUAL` converts an MFC exception into OLE Automation error-handling information using the **ICreateErrorInfo** interface. (An example `CATCH_ALL_DUAL` macro is in the file MFCDUAL.H in the [ACDUAL](../visual-cpp-samples.md) sample. The function it calls to handle exceptions, `DualHandleException`, is in the file MFCDUAL.CPP.) `CATCH_ALL_DUAL` determines the error code to return based on the type of exception that occurred:  
  
- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - In this case, `HRESULT` is constructed using the following code:  
  
 ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR,
    FACILITY_ITF,   
 (e->m_wCode + 0x200));

 ```  
  
     This creates an `HRESULT` specific to the interface that caused the exception. The error code is offset by 0x200 to avoid any conflicts with system-defined `HRESULT`s for standard OLE interfaces.  
  
- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - In this case, `E_OUTOFMEMORY` is returned.  
  
-   Any other exception - In this case, `E_UNEXPECTED` is returned.  
  
 To indicate that the OLE Automation error handler is used, you should also implement the **ISupportErrorInfo** interface.  
  
 First, add code to your automation class definition to show it supports **ISupportErrorInfo**.  
  
 Second, add code to your automation class's interface map to associate the **ISupportErrorInfo** implementation class with MFC's `QueryInterface` mechanism. The `INTERFACE_PART` statement matches the class defined for **ISupportErrorInfo**.  
  
 Finally, implement the class defined to support **ISupportErrorInfo**.  
  
 (The [ACDUAL](../visual-cpp-samples.md) sample contains three macros to help do these three steps, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, and `IMPLEMENT_DUAL_ERRORINFO`, all contained in MFCDUAL.H.)  
  
 The following example implements a class defined to support **ISupportErrorInfo**. `CAutoClickDoc` is the name of your automation class and `IID_IDualAClick` is the **IID** for the interface that is the source of errors reported through the OLE Automation error object:  
  
```  
STDMETHODIMP_(ulong) CAutoClickDoc::XSupportErrorInfo::AddRef()   
{  
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    dönüş pThis ExternalAddRef() ->;

}   
STDMETHODIMP_(ulong) CAutoClickDoc::XSupportErrorInfo::Release()   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    dönüş pThis ExternalRelease() ->;

}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface (REFIID IID, LPVOID * ppvObj)   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    dönüş pThis -> ExternalQueryInterface (& IID, ppvObj);

}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo (REFIID IID)   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    Döndür (IID IID_IDualAClick ==) S_OK: S_FALSE;   
}  
```  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

