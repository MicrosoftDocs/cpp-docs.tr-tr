---
title: "Öznitelik programlama SSS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- attributed programming
- attributes [C++], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c61ced7e0931f1dba46a7a6b760755f799d29b6b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="attribute-programming-faq"></a>Öznitelik Programlama SSS
Bu konuda aşağıdaki sık sorulan sorular yanıtlanmaktadır:  
  
-   [HRESULT nedir?](#vcconattributeprogrammmingfaqanchor1)  
  
-   [Bir öznitelik için parametre adı belirtmek ne zaman var mı?](#vcconattributeprogrammmingfaqanchor2)  
  
-   [Öznitelik bloğunda açıklamaları kullanabilir miyim?](#vcconattributeprogrammmingfaqanchor3)  
  
-   [Öznitelikleri devralma ile nasıl etkileşim?](#vcconattributeprogrammmingfaqanchor4)  
  
-   [Öznitelikleri nonattributed ATL projede nasıl kullanabilirim?](#vcconattributeprogrammmingfaqanchor5)  
  
-   [Öznitelikli projesinde .idl dosyasında nasıl kullanabilir miyim?](#vcconattributeprogrammmingfaqanchor6)  
  
-   [Bir öznitelik tarafından eklenen kod değiştirebilir mi?](#vcconattributeprogrammmingfaqanchor7)  
  
-   [Nasıl öznitelikli arabirim İleri bildirimini yapabilir?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [Ayrıca öznitelikler kullanan bir sınıfından türetilen bir sınıf öznitelikleri kullanabilir miyim?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a>HRESULT nedir?  
 Bir `HRESULT` genellikle dönüş değeri olarak öznitelikleri ve ATL tarafından genel olarak kullanılan bir basit veri türü. Aşağıdaki tabloda, çeşitli değerleri açıklanmaktadır. Daha fazla değer üstbilgi dosyası Winerror.h'de içinde yer alır.  
  
|Ad|Açıklama|Değer|  
|----------|-----------------|-----------|  
|S_OK|İşlem başarılı|0x00000000|  
|E_UNEXPECTED|Beklenmeyen bir hata oluştu|0x8000FFFF|  
|E_NOTIMPL|Uygulanmadı|0x80004001|  
|E_OUTOFMEMORY|Gerekli bellek ayrılamadı.|0x8007000E|  
|E_INVALIDARG|Bir veya daha fazla bağımsız değişken geçersiz|0x80070057|  
|E_NOINTERFACE|Böyle bir arabirim desteklenmiyor|0x80004002|  
|E_POINTER|Geçersiz bir işaretçi|0x80004003|  
|E_HANDLE|Geçersiz tanıtıcı|0x80070006|  
|E_ABORT|İşlem iptal edildi|0x80004004|  
|E_FAIL|Belirtilmeyen hata|0x80004005|  
|E_ACCESSDENIED|Genel erişim reddedildi hatası|0x80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a>Bir öznitelik için parametre adı belirtmek ne zaman var mı?  
 Çoğu durumda, tek bir parametre özniteliğine sahipse, bu parametrenin adı verilir. Bu ad, öznitelik kodunuzda eklerken gerekli değildir. Örneğin, aşağıdaki kullanımı [toplanabilir](../windows/aggregatable.md) özniteliği:  
  
```  
[coclass, aggregatable(value=allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 tam olarak aynı sonucu verir:  
  
```  
[coclass, aggregatable(allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 Ancak, tek, adlandırılmamış parametreleri aşağıdaki özniteliklere sahiptir:  
  
||||  
|-|-|-|  
|[call_as](../windows/call-as.md)|[durumu](../windows/case-cpp.md)|[cpp_quote](../windows/cpp-quote.md)|  
|[Varsayılan](../windows/default-cpp.md)|[DefaultValue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[Giriş](../windows/entry.md)|[first_is](../windows/first-is.md)|  
|[HelpContext](../windows/helpcontext.md)|[HelpFile](../windows/helpfile.md)|[HelpString](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[Kimliği](../windows/id.md)|  
|[iid_is](../windows/iid-is.md)|[içeri aktarma](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[içerir](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last_is](../windows/last-is.md)|  
|[length_is](../windows/length-is.md)|[max_is](../windows/max-is.md)|[no_injected_text](../windows/no-injected-text.md)|  
|[pointer_default](../windows/pointer-default.md)|[pragma](../windows/pragma.md)|[sınırlı](../windows/restricted.md)|  
|[size_is](../windows/size-is.md)|[Kaynak](../windows/source-cpp.md)|[switch_is](../windows/switch-is.md)|  
|[switch_type](../windows/switch-type.md)|[transmit_as](../windows/transmit-as.md)|[wire_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a>Öznitelik bloğunda açıklamaları kullanabilir miyim?  
 Bir öznitelik bloğu içinde tek satırlı ve birden çok satırlı açıklamaları kullanabilirsiniz. Ancak, açıklama parametreleri için bir öznitelik bulunduran parantez içinde ya da bir tarzını kullanamazsınız.  
  
 Aşağıdaki izin verilir:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 Aşağıdaki izin verilmiyor:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a>Öznitelikleri devralma ile nasıl etkileşim?  
 Öznitelikli ve unattributed sınıfları kendilerini veya öznitelikli diğer sınıflardan devralabilirsiniz. Öznitelikli sınıfından türetilen aynı öznitelik sağlayıcı kendi kod dönüştürdü sonra bu sınıftan türetilen sonucudur. Öznitelikler için türetilen sınıflar C++ devralma üzerinden iletilmez. Bir öznitelik sağlayıcısı yalnızca kod özniteliklerini kapsamına dönüştürür.  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a>Öznitelikleri nonattributed ATL projede nasıl kullanabilirim?  
 Bir .idl dosyası olan nonattributed bir ATL Proje olabilir ve öznitelikli nesneleri eklemek isteyebilirsiniz. Bu durumda, kod sağlamak için sınıf Ekleme Sihirbazı'nı kullanın.  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a>Öznitelikli projesinde .idl dosyasında nasıl kullanabilir miyim?  
 Öznitelikli ATL projenizde kullanmak istediğiniz bir .idl dosyanız olabilir. Bu durumda, kullanacağınız [importidl](../windows/importidl.md) öznitelik, bir .h dosyasına .idl dosyasını derleyin (bkz [MIDL özellik sayfaları](../ide/midl-property-pages.md) projenin özellik sayfaları iletişim kutusunda) ve ardından .h dosyası projenize ekleme .  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a>Bir öznitelik tarafından eklenen kod değiştirebilir mi?  
 Bazı öznitelikler kod projenize ekleme. Eklenen kodu kullanarak gördüğünüz [/Fx](../build/reference/fx-merge-injected-code.md) derleyici seçeneği. Eklenen dosyanın kodu kopyalayın ve kaynak kodunuzu yapıştırmak mümkündür. Bu öznitelik davranışını değiştirmenize olanak sağlar. Ancak, diğer bölümleri kodunuzu de değiştirmeniz gerekebilir.  
  
 Aşağıdaki örnek, bir kaynak kodu dosyasına eklenen kodu kopyalama sonucu olan:  
  
```  
// attr_injected.cpp  
// compile with: comsupp.lib  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name="MyLibrary") ];  
  
// ITestTest  
[   
   object,  
   uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"),  
   dual,  
   helpstring("ITestTest Interface"),  
   pointer_default(unique)  
]  
  
__interface ITestTest : IDispatch {  
   [id(1), helpstring("method DoTest")]   
   HRESULT DoTest([in] BSTR str);  
};  
  
// _ITestTestEvents  
[  
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"),  
   dispinterface,  
   helpstring("_ITestTestEvents Interface")  
]  
  
__interface _ITestTestEvents {  
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);  
};  
  
// CTestTest  
[  
   coclass,  
   threading(apartment),  
   vi_progid("TestATL1.TestTest"),  
   progid("TestATL1.TestTest.1"),  
   version(1.0),  
   uuid("D9632007-14FA-4679-9E1C-28C9A949E784"),  
   // this line would be commented out from original file  
   // event_source("com"),  
   // this line would be added to support injected code  
   source(_ITestTestEvents),  
   helpstring("TestTest Class")  
]  
  
class ATL_NO_VTABLE CTestTest : public ITestTest,  
// the following base classes support added injected code  
public IConnectionPointContainerImpl<CTestTest>,  
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>  
{  
public:  
   CTestTest() {  
   }  
   // this line would be commented out from original file  
   // __event __interface _ITestTestEvents;  
   DECLARE_PROTECT_FINAL_CONSTRUCT()  
   HRESULT FinalConstruct() {  
      return S_OK;  
   }  
  
void FinalRelease() {}  
  
public:  
   CComBSTR m_value;  
   STDMETHOD(DoTest)(BSTR str) {  
      VARIANT_BOOL bCancel = FALSE;  
      BeforeChange(str,&bCancel);  
      if (bCancel) {  
          return Error("Error : Someone don't want us to change the value");  
      }  
  
     m_value =str;  
     return S_OK;  
    }  
// the following was copied in from the injected code.  
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {  
   HRESULT hr = S_OK;  
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;  
   VARIANT rgvars[2];  
   Lock();  
   IUnknown** pp = p->m_vec.begin();  
   Unlock();  
   while (pp < p->m_vec.end()) {  
      if (*pp != NULL) {  
         IDispatch* pDispatch = (IDispatch*) *pp;  
         ::VariantInit(&rgvars[1]);  
         rgvars[1].vt = VT_BSTR;  
         V_BSTR(&rgvars[1])= (BSTR) i1;  
         ::VariantInit(&rgvars[0]);  
         rgvars[0].vt = (VT_BOOL | VT_BYREF);  
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;  
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };  
         VARIANT ret_val;  
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);  
         if (FAILED(hr))  
            break;  
      }  
      pp++;  
   }  
   return hr;  
}  
  
BEGIN_CONNECTION_POINT_MAP(CTestTest)  
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))  
END_CONNECTION_POINT_MAP()  
// end added code section  
  
// _ITestCtrlEvents Methods  
public:  
};  
  
int main() {}  
```  
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a>Nasıl öznitelikli arabirim İleri bildirimini yapabilir?  
 Öznitelikli arabirim ileriye dönük bildirimi yapmak için kullanacaksanız, gerçek arabirimi bildirimine uygulayın iletme bildirimine aynı öznitelikleri uygulamanız gerekir. Ayrıca uygulamalısınız [verme](../windows/export.md) özniteliği, ileriye dönük bildirimi.  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a>Ayrıca öznitelikler kullanan bir sınıfından türetilen bir sınıf öznitelikleri kullanabilir miyim?  
 Hayır, öznitelikler de kullanan bir sınıfından türetilmiş bir sınıf öznitelikleri kullanma desteklenmiyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../windows/attributed-programming-concepts.md)