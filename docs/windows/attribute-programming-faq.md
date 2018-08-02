---
title: Öznitelik programlama SSS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributed programming
- attributes [C++], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5cdc7bb8a97be6fbc8c77c06caaddf95a3095323
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463749"
---
# <a name="attribute-programming-faq"></a>Öznitelik Programlama SSS
Bu konuda aşağıdaki sık sorulan sorular yanıtlanmaktadır:  
  
-   [HRESULT nedir?](#vcconattributeprogrammmingfaqanchor1)  
  
-   [Bir öznitelik parametresi adını belirtmek ne zaman sahip?](#vcconattributeprogrammmingfaqanchor2)  
  
-   [Bir öznitelik bloğunda açıklamaları kullanabilir miyim?](#vcconattributeprogrammmingfaqanchor3)  
  
-   [Öznitelikleri devralma ile nasıl etkileşime?](#vcconattributeprogrammmingfaqanchor4)  
  
-   [Öznitelikleri nonattributed bir ATL projesinde nasıl kullanabilirim?](#vcconattributeprogrammmingfaqanchor5)  
  
-   [Öznitelik atanmış projede bir .idl dosyası nasıl kullanabilirim?](#vcconattributeprogrammmingfaqanchor6)  
  
-   [Bir öznitelik tarafından eklenen kod değiştirebiliyorum?](#vcconattributeprogrammmingfaqanchor7)  
  
-   [Nasıl bir öznitelikli arabirimi İleri bildirme?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [Öznitelikleri kullanan bir sınıftan türetilen bir sınıfta öznitelikleri kullanabilir miyim?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a> HRESULT nedir?  
 Bir `HRESULT` çoğunlukla bir dönüş değeri olarak öznitelikleri ve ATL tarafından genel olarak kullanılan bir basit veri türü. Aşağıdaki tabloda, çeşitli değerleri açıklanmaktadır. Daha fazla değer üst bilgi dosyası wınerror içinde yer alır.  
  
|Ad|Açıklama|Değer|  
|----------|-----------------|-----------|  
|S_OK|İşlem başarılı|0x00000000|  
|E_UNEXPECTED|Beklenmeyen bir hata oluştu|0x8000FFFF|  
|E_NOTIMPL|Uygulanmadı|0x80004001|  
|E_OUTOFMEMORY|Gerekli bellek ayrılamadı|0x8007000E|  
|E_INVALIDARG|Bir veya daha fazla bağımsız değişken geçersiz|0x80070057|  
|E_NOINTERFACE|Böyle bir arabirim desteklenmiyor|0x80004002|  
|E_POINTER|Geçersiz işaretçi|0x80004003|  
|E_HANDLE|Geçersiz işleç|0x80070006|  
|E_ABORT|İşlem iptal edildi|0x80004004|  
|E_FAIL|Belirtilmeyen hata|0x80004005|  
|E_ACCESSDENIED|Genel erişim reddedildi hatası|0x80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a> Bir öznitelik parametresi adını belirtmek ne zaman sahip?  
 Tek bir parametre özniteliğine sahipse, çoğu durumda, bu parametre olarak adlandırılır. Bu ad, öznitelik kodunuzda eklerken gerekli değildir. Örneğin, aşağıdaki kullanımı [toplanabilir](../windows/aggregatable.md) özniteliği:  
  
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
  
 Ancak, tek ve adlandırılmamış parametreler aşağıdaki özniteliklere sahiptir:  
  
||||  
|-|-|-|  
|[call_as](../windows/call-as.md)|[Servis talebi](../windows/case-cpp.md)|[cpp_quote](../windows/cpp-quote.md)|  
|[default](../windows/default-cpp.md)|[defaultvalue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[entry](../windows/entry.md)|[first_is](../windows/first-is.md)|  
|[helpcontext](../windows/helpcontext.md)|[helpfile](../windows/helpfile.md)|[helpstring](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[id](../windows/id.md)|  
|[iid_is](../windows/iid-is.md)|[import](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[İçerir](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last_is](../windows/last-is.md)|  
|[length_is](../windows/length-is.md)|[max_is](../windows/max-is.md)|[no_injected_text](../windows/no-injected-text.md)|  
|[pointer_default](../windows/pointer-default.md)|[pragma](../windows/pragma.md)|[restricted](../windows/restricted.md)|  
|[size_is](../windows/size-is.md)|[Kaynak](../windows/source-cpp.md)|[switch_is](../windows/switch-is.md)|  
|[switch_type](../windows/switch-type.md)|[transmit_as](../windows/transmit-as.md)|[wire_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a> Bir öznitelik bloğunda açıklamaları kullanabilir miyim?  
 Bir öznitelik blok içindeki tek satır hem de birden çok satırlı açıklamaları kullanabilirsiniz. Ancak, ya da yorum parametreleri için bir öznitelik bulunduran parantezlerinin stilini kullanamazsınız.  
  
 Aşağıdaki izin verilir:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 Aşağıdaki izin verilmez:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a> Öznitelikleri devralma ile nasıl etkileşime?  
 Öznitelikli ve unattributed sınıfları kendileri veya kaynağı diğer sınıflardan devralabilir. Öznitelikli bir sınıftan türetme sonucu özniteliği sağlayıcısı kodunu dönüştürdü sonra bu sınıftan türetme aynıdır. Öznitelikler için türetilmiş sınıfları C++ devralma yoluyla iletilmez. Bir öznitelik sağlayıcısı, yalnızca kod kapsamına özniteliklerini dönüştürür.  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a> Öznitelikleri nonattributed bir ATL projesinde nasıl kullanabilirim?  
 Bir .idl dosyası olan nonattributed bir ATL projesine sahip olabilir ve öznitelikli nesne eklemeye başlamak isteyebilirsiniz. Bu durumda, kod sağlamak için sınıf Ekleme Sihirbazı'nı kullanın.  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a> Öznitelik atanmış projede bir .idl dosyası nasıl kullanabilirim?  
 Öznitelikli ATL projenizde kullanmak istediğiniz bir .idl dosyası olabilir. Bu durumda, kullanacağınız [importidl](../windows/importidl.md) öznitelik, bir .h dosyası .idl dosyasına derlemek (bkz [MIDL özellik sayfaları](../ide/midl-property-pages.md) proje özellik sayfaları iletişim kutusunda) ve ardından .h dosyası projenize ekleyin .  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a> Bir öznitelik tarafından eklenen kod değiştirebiliyorum?  
 Bazı öznitelikler kod projenize ekleyin. Eklenen kodu kullanarak gördüğünüz [/Fx](../build/reference/fx-merge-injected-code.md) derleyici seçeneği. Eklenen dosyanın kodu kopyalayın ve kaynak kodunuza yapıştırmak mümkündür. Bu öznitelik davranışını değiştirmenizi sağlar. Ancak, diğer bölümlerinde de kodunuzu değiştirmeniz gerekebilir.  
  
 Aşağıdaki örnek bir kaynak kod dosyasına eklenen kodu kopyalama sonucudur:  
  
```cpp  
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
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> Nasıl bir öznitelikli arabirimi İleri bildirme?  
 Öznitelikli arabirim İleri dönük bildiriminin yapmak için kullanacaksanız, gerçek bir arabirim bildirimi için geçerli İleri dönük bildirimi için aynı öznitelikleri uygulamanız gerekir. Ayrıca uygulamalısınız [dışarı](../windows/export.md) özniteliği, İleri dönük bildirimi için.  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> Öznitelikleri kullanan bir sınıftan türetilen bir sınıfta öznitelikleri kullanabilir miyim?  
 Hayır, öznitelikleri kullanan bir sınıftan türetilen bir sınıfta öznitelikleri kullanma desteklenmiyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../windows/attributed-programming-concepts.md)