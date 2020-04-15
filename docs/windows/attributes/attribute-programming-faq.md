---
title: Öznitelik Programlama SSS
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributed programming
- attributes [C++/CLI], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
ms.openlocfilehash: 6c1762994d2cb109e86397bb0a5db1258cf33be2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376059"
---
# <a name="attribute-programming-faq"></a>Öznitelik Programlama SSS

Bu konu, sık sorulan aşağıdaki soruları yanıtlar:

- [HRESULT nedir?](#vcconattributeprogrammmingfaqanchor1)

- [Bir öznitelik için parametre adını ne zaman belirtmem gerekiyor?](#vcconattributeprogrammmingfaqanchor2)

- [Açıklamaları öznitelik bloğunda kullanabilir miyim?](#vcconattributeprogrammmingfaqanchor3)

- [Öznitelikler devralmayla nasıl etkileşime giriyor?](#vcconattributeprogrammmingfaqanchor4)

- [Atfedilmeyen bir ATL projesinde öznitelikleri nasıl kullanabilirim?](#vcconattributeprogrammmingfaqanchor5)

- [Atfedilen bir projede .idl dosyayı nasıl kullanabilirim?](#vcconattributeprogrammmingfaqanchor6)

- [Bir öznitelik tarafından enjekte edilen kodu değiştirebilir miyim?](#vcconattributeprogrammmingfaqanchor7)

- [Atfedilen arabirimi nasıl iledebilirim?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)

- [Öznitelikleri de kullanan bir sınıftan türetilen bir sınıfta öznitelikleri kullanabilir miyim?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)

## <a name="what-is-an-hresult"></a><a name="vcconattributeprogrammmingfaqanchor1"></a>HRESULT nedir?

HRESULT, genellikle öznitelikler ve genel olarak ATL tarafından geri dönüş değeri olarak kullanılan basit bir veri türüdür. Aşağıdaki tabloda çeşitli değerler açıklanmaktadır. Daha fazla değer üstbilgi dosyası winerror.h bulunur.

|Adı|Açıklama|Değer|
|----------|-----------------|-----------|
|S_OK|İşlem başarılı|0x00000000|
|E_unexpected|Beklenmeyen hata|0x8000FFFF|
|E_notımpl|Uygulanmadı|0x80004001|
|E_outofmemory|Gerekli belleği ayırmak için başarısız oldu|0x8007000E|
|E_ınvalıdarg|Bir veya daha fazla bağımsız değişken geçersizdir|0x80070057|
|E_noınterface|Böyle bir arabirim desteklenmedi|0x80004002|
|E_POINTER|Geçersiz işaretçi|0x80004003|
|E_HANDLE|Geçersiz tutamak|0x80070006|
|E_ABORT|İşlem iptal edildi|0x80004004|
|E_faıl|Belirtilmemiş hata|0x80004005|
|E_ACCESSDENIED|Genel erişim reddedilen hata|0x80070005|

## <a name="when-do-i-have-to-specify-the-parameter-name-for-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor2"></a>Bir öznitelik için parametre adını ne zaman belirtmem gerekiyor?

Çoğu durumda, öznitelik tek bir parametre varsa, bu parametre adlandırılır. Kodunuza öznitelik eklenirken bu ad gerekmez. Örneğin, [toplayıcı](aggregatable.md) öznitelik aşağıdaki kullanımı:

```cpp
[coclass, aggregatable(value=allowed)]
class CMyClass
{
// The class declaration
};
```

tam olarak aynıdır:

```cpp
[coclass, aggregatable(allowed)]
class CMyClass
{
// The class declaration
};
```

Ancak, aşağıdaki özniteliklerin tek, adsız parametreleri vardır:

||||
|-|-|-|
|[call_as](call-as.md)|[Durumda](case-cpp.md)|[cpp_quote](cpp-quote.md)|
|[default](default-cpp.md)|[defaultvalue](defaultvalue.md)|[defaultvtable](defaultvtable.md)|
|[emitidl](emitidl.md)|[Giriş](entry.md)|[first_is](first-is.md)|
|[helpcontext](helpcontext.md)|[helpfile](helpfile.md)|[helpstring](helpstring.md)|
|[helpstringcontext](helpstringcontext.md)|[helpstringdll](helpstringdll.md)|[Kimliği](id.md)|
|[iid_is](iid-is.md)|[Ithalat](import.md)|[importlib](importlib.md)|
|[include](include-cpp.md)|[includelib](includelib-cpp.md)|[last_is](last-is.md)|
|[length_is](length-is.md)|[max_is](max-is.md)|[no_injected_text](no-injected-text.md)|
|[pointer_default](pointer-default.md)|[pragma](pragma.md)|[kısıtlı](restricted.md)|
|[size_is](size-is.md)|[Kaynak](source-cpp.md)|[switch_is](switch-is.md)|
|[switch_type](switch-type.md)|[transmit_as](transmit-as.md)|[wire_marshal](wire-marshal.md)|

## <a name="can-i-use-comments-in-an-attribute-block"></a><a name="vcconattributeprogrammmingfaqanchor3"></a>Açıklamaları öznitelik bloğunda kullanabilir miyim?

Öznitelik bloğu içinde hem tek satırlı hem de çok satırlı açıklamaları kullanabilirsiniz. Ancak, parametreleri bir öznitelik tesniye tutan parantez içindeki her iki yorum stilini de kullanamazsınız.

Aşağıdakileri kabul edin:

```cpp
[ coclass, progid("MyClass.CMyClass.1"), /* Multiple-line
                                       comment */
   threading("both") // Single-line comment
]
```

Aşağıdakiler izin verilmez:

```cpp
[ coclass, progid("MyClass.CMyClass.1" /* Multiple-line comment */ ), threading("both" // Single-line comment)
]
```

## <a name="how-do-attributes-interact-with-inheritance"></a><a name="vcconattributeprogrammmingfaqanchor4"></a>Öznitelikler devralmayla nasıl etkileşime giriyor?

Atfedilen veya atfedilmemiş diğer sınıflardan hem atfedilen hem de atfedilmemiş sınıfları devralabilirsiniz. Atfedilen bir sınıftan türeyen sonuç, öznitelik sağlayıcısı kodunu dönüştürdükten sonra bu sınıftan türeyen ile aynıdır. Öznitelikler, C++ kalıtım yoluyla türemiş sınıflara aktarılmez. Bir öznitelik sağlayıcısı yalnızca özniteliklerinin çevresinde kodu dönüştürür.

## <a name="how-can-i-use-attributes-in-a-nonattributed-atl-project"></a><a name="vcconattributeprogrammmingfaqanchor5"></a>Atfedilmeyen bir ATL projesinde öznitelikleri nasıl kullanabilirim?

.idl dosyası olan atfedilmeyen bir ATL projeniz olabilir ve atfedilen nesneleri eklemeye başlamak isteyebilirsiniz. Bu durumda, kodu sağlamak için **Sınıf Ekle Sihirbazı'nı** kullanın.

## <a name="how-can-i-use-an-idl-file-in-an-attributed-project"></a><a name="vcconattributeprogrammmingfaqanchor6"></a>Atfedilen bir projede .idl dosyayı nasıl kullanabilirim?

ATL atfedilen projenizde kullanmak istediğiniz bir .idl dosyanız olabilir. Bu durumda, [importidl](importidl.md) özniteliğini kullanır, .idl dosyasını bir .h dosyasına derlersiniz (projenin **Özellik Sayfaları** iletişim kutusundaki [MIDL Özellik Sayfaları'na](../../build/reference/midl-property-pages.md) bakın) ve ardından .h dosyasını projenize eklersiniz.

## <a name="can-i-modify-code-that-is-injected-by-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor7"></a>Bir öznitelik tarafından enjekte edilen kodu değiştirebilir miyim?

Bazı öznitelikler projenize kod enjekte eder. [/Fx](../../build/reference/fx-merge-injected-code.md) derleyici seçeneğini kullanarak enjekte edilen kodu görebilirsiniz. Ayrıca, enjekte edilen dosyadan kodu kopyalayıp kaynak kodunuza yapıştırmak da mümkündür. Bu, öznitelik davranışını değiştirmenize olanak sağlar. Ancak, kodunuzu diğer bölümlerini de değiştirmeniz gerekebilir.

Aşağıdaki örnek, enjekte edilen kodun bir kaynak kodu dosyasına kopyalanmasısonucu ortaya atılmaktadır:

```cpp
// attr_injected.cpp
// compile with: comsupp.lib
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name="MyLibrary") ];

// ITestTest
[
   object, uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"), dual, helpstring("ITestTest Interface"), pointer_default(unique)
]

__interface ITestTest : IDispatch {
   [id(1), helpstring("method DoTest")]
   HRESULT DoTest([in] BSTR str);
};

// _ITestTestEvents
[
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"), dispinterface, helpstring("_ITestTestEvents Interface")
]

__interface _ITestTestEvents {
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);
};

// CTestTest
[
   coclass, threading(apartment), vi_progid("TestATL1.TestTest"), progid("TestATL1.TestTest.1"), version(1.0), uuid("D9632007-14FA-4679-9E1C-28C9A949E784"), // this line would be commented out from original file
   // event_source("com"), // this line would be added to support injected code
   source(_ITestTestEvents), helpstring("TestTest Class")
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

## <a name="how-can-i-forward-declare-an-attributed-interface"></a><a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a>Atfedilen arabirimi nasıl iledebilirim?

Atfedilen arabirimin ileri bildiriminde bulunacaksanız, gerçek arabirim bildirimine uyguladığınız iletme bildirimine aynı öznitelikleri uygulamanız gerekir. [Dışa](export.md) aktarma özniteliğini de iletme beyanınıza uygulamanız gerekir.

## <a name="can-i-use-attributes-on-a-class-derived-from-a-class-that-also-uses-attributes"></a><a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a>Öznitelikleri de kullanan bir sınıftan türetilen bir sınıfta öznitelikleri kullanabilir miyim?

Hayır, öznitelikleri de kullanan bir sınıftan türetilen bir sınıfta öznitelikleri kullanarak desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[COM ve .NET için C++ Öznitelikleri](cpp-attributes-com-net.md)
