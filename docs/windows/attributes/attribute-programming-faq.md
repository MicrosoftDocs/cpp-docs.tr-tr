---
description: 'Daha fazla bilgi edinin: öznitelik programlama SSS'
title: Öznitelik Programlama SSS
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributed programming
- attributes [C++/CLI], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
ms.openlocfilehash: 7a3bdfc8749297d11c5bc33b706265a1f5913a69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240435"
---
# <a name="attribute-programming-faq"></a>Öznitelik Programlama SSS

Bu konu, aşağıdaki sık sorulan soruları yanıtlar:

- [HRESULT nedir?](#vcconattributeprogrammmingfaqanchor1)

- [Bir özniteliğin parametre adını belirtmem gerekir mi?](#vcconattributeprogrammmingfaqanchor2)

- [Bir öznitelik bloğunda açıklamaları kullanabilir miyim?](#vcconattributeprogrammmingfaqanchor3)

- [Öznitelikler devralma ile nasıl etkileşime gidir?](#vcconattributeprogrammmingfaqanchor4)

- [Öznitelikli ATL projesindeki öznitelikleri nasıl kullanabilirim?](#vcconattributeprogrammmingfaqanchor5)

- [Öznitelikli bir projede. IDL dosyasını nasıl kullanabilirim?](#vcconattributeprogrammmingfaqanchor6)

- [Bir öznitelik tarafından eklenen kodu değiştirebilir miyim?](#vcconattributeprogrammmingfaqanchor7)

- [Öznitelikli bir arabirimi nasıl iletirim?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)

- [Öznitelikleri de kullanan bir sınıftan türetilmiş bir sınıfta öznitelikleri kullanabilir miyim?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)

## <a name="what-is-an-hresult"></a><a name="vcconattributeprogrammmingfaqanchor1"></a> HRESULT nedir?

HRESULT, genellikle öznitelikler ve ATL tarafından genel olarak bir dönüş değeri olarak kullanılan basit bir veri türüdür. Aşağıdaki tabloda çeşitli değerler açıklanmaktadır. Daha fazla değer Winerror. h üstbilgi dosyasında bulunur.

|Ad|Açıklama|Değer|
|----------|-----------------|-----------|
|S_OK|İşlem başarılı|0x00000000|
|E_UNEXPECTED|Beklenmeyen hata|0x8000FFFF|
|E_NOTIMPL|Uygulanmadı|0x80004001|
|E_OUTOFMEMORY|Gerekli bellek ayrılamadı|0x8007000E|
|E_INVALIDARG|Bir veya daha fazla bağımsız değişken geçersiz|0x80070057|
|E_NOINTERFACE|Böyle bir arabirim desteklenmiyor|0x80004002|
|E_POINTER|Geçersiz işaretçi|0x80004003|
|E_HANDLE|Geçersiz tanıtıcı|0x80070006|
|E_ABORT|İşlem iptal edildi|0x80004004|
|E_FAIL|Belirtilmeyen hata|0x80004005|
|E_ACCESSDENIED|Genel erişim reddedildi hatası|0x80070005|

## <a name="when-do-i-have-to-specify-the-parameter-name-for-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor2"></a> Bir özniteliğin parametre adını belirtmem gerekir mi?

Çoğu durumda, özniteliğinde tek bir parametre varsa, bu parametre adlandırılır. Bu ad, kodunuza özniteliği eklenirken gerekli değildir. Örneğin, [toplanamayan](aggregatable.md) özniteliğin aşağıdaki kullanımı:

```cpp
[coclass, aggregatable(value=allowed)]
class CMyClass
{
// The class declaration
};
```

tamamen aynıdır:

```cpp
[coclass, aggregatable(allowed)]
class CMyClass
{
// The class declaration
};
```

Ancak, aşağıdaki özniteliklerde tek ve adlandırılmamış parametrelere sahiptir:

:::row:::
   :::column span="":::
      [`call_as`](call-as.md)\
      [`case`](case-cpp.md)\
      [`cpp_quote`](cpp-quote.md)\
      [`default`](default-cpp.md)\
      [`defaultvalue`](defaultvalue.md)\
      [`defaultvtable`](defaultvtable.md)\
      [`emitidl`](emitidl.md)\
      [`entry`](entry.md)\
      [`first_is`](first-is.md)
   :::column-end:::
   :::column span="":::
      [`helpcontext`](helpcontext.md)\
      [`helpfile`](helpfile.md)\
      [`helpstring`](helpstring.md)\
      [`helpstringcontext`](helpstringcontext.md)\
      [`helpstringdll`](helpstringdll.md)\
      [`id`](id.md)\
      [`iid_is`](iid-is.md)\
      [`import`](import.md)
   :::column-end:::
   :::column span="":::
      [`importlib`](importlib.md)\
      [`include`](include-cpp.md)\
      [`includelib`](includelib-cpp.md)\
      [`last_is`](last-is.md)\
      [`length_is`](length-is.md)\
      [`max_is`](max-is.md)\
      [`no_injected_text`](no-injected-text.md)\
      [`pointer_default`](pointer-default.md)
   :::column-end:::
   :::column span="":::
      [`pragma`](pragma.md)\
      [`restricted`](restricted.md)\
      [`size_is`](size-is.md)\
      [`source`](source-cpp.md)\
      [`switch_is`](switch-is.md)\
      [`switch_type`](switch-type.md)\
      [`transmit_as`](transmit-as.md)\
      [`wire_marshal`](wire-marshal.md)
   :::column-end:::
:::row-end:::

## <a name="can-i-use-comments-in-an-attribute-block"></a><a name="vcconattributeprogrammmingfaqanchor3"></a> Bir öznitelik bloğunda açıklamaları kullanabilir miyim?

Tek satırlı ve çok satırlı açıklamaları bir öznitelik bloğu içinde kullanabilirsiniz. Ancak, bir özniteliğe parametreleri tutan parantez içinde Açıklama stilini kullanamazsınız.

Şunlar için izin verilir:

```cpp
[ coclass, progid("MyClass.CMyClass.1"), /* Multiple-line
                                       comment */
   threading("both") // Single-line comment
]
```

Şunlar için izin verilmez:

```cpp
[ coclass, progid("MyClass.CMyClass.1" /* Multiple-line comment */ ), threading("both" // Single-line comment)
]
```

## <a name="how-do-attributes-interact-with-inheritance"></a><a name="vcconattributeprogrammmingfaqanchor4"></a> Öznitelikler devralma ile nasıl etkileşime gidir?

Kendisine öznitelik atanmış olan veya olmayan diğer sınıflardan hem öznitelikli hem de öznitelik atanmamış sınıfları kalýtýmla aktarabilirsiniz. Öznitelikli bir sınıftan Türetmenin sonucu, öznitelik sağlayıcısı kodunu dönüştürdükten sonra bu sınıftan türeterek aynı olur. Öznitelikler, C++ devralımı aracılığıyla türetilmiş sınıflara aktarılmaz. Bir öznitelik sağlayıcısı yalnızca kendi özniteliklerinin çevre alanındaki kodu dönüştürür.

## <a name="how-can-i-use-attributes-in-a-nonattributed-atl-project"></a><a name="vcconattributeprogrammmingfaqanchor5"></a> Öznitelikli ATL projesindeki öznitelikleri nasıl kullanabilirim?

Bir. IDL dosyası olan, öznitelikli bir ATL projenize sahip olabilirsiniz ve öznitelikli nesneler eklemeye başlamak isteyebilirsiniz. Bu durumda, kodu sağlamak için **sınıf ekleme Sihirbazı** ' nı kullanın.

## <a name="how-can-i-use-an-idl-file-in-an-attributed-project"></a><a name="vcconattributeprogrammmingfaqanchor6"></a> Öznitelikli bir projede. IDL dosyasını nasıl kullanabilirim?

ATL öznitelikli projenizde kullanmak istediğiniz bir. IDL dosyasına sahip olabilirsiniz. Bu durumda, [ımportidl](importidl.md) özniteliğini kullanır,. IDL dosyasını bir. h dosyasına derler (projenin **Özellik sayfaları** Iletişim kutusundaki [MIDL özellik sayfalarına](../../build/reference/midl-property-pages.md) bakın) ve ardından. h dosyasını projenize ekleyin.

## <a name="can-i-modify-code-that-is-injected-by-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor7"></a> Bir öznitelik tarafından eklenen kodu değiştirebilir miyim?

Bazı öznitelikler kodu projenize ekler. Eklenen kodu [/FX](../../build/reference/fx-merge-injected-code.md) derleyici seçeneğini kullanarak görebilirsiniz. Ayrıca, eklenen dosyadan kod kopyalamak ve kaynak kodunuza yapıştırmak mümkündür. Bu, özniteliğinin davranışını değiştirmenize olanak sağlar. Ancak, kodunuzun diğer bölümlerini de değiştirmeniz gerekebilir.

Aşağıdaki örnek, eklenen kodu bir kaynak kod dosyasına kopyalamanın sonucudur:

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

## <a name="how-can-i-forward-declare-an-attributed-interface"></a><a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> Öznitelikli bir arabirimi nasıl iletirim?

Öznitelikli bir arabirimin ileri bir bildirimini oluşturacaksanız, gerçek arabirim bildirimine uyguladığınız ileri bildirimine aynı öznitelikleri uygulamanız gerekir. Ayrıca, iletme bildirimindeki [dışarı aktarma](export.md) özniteliğini de uygulamalısınız.

## <a name="can-i-use-attributes-on-a-class-derived-from-a-class-that-also-uses-attributes"></a><a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> Öznitelikleri de kullanan bir sınıftan türetilmiş bir sınıfta öznitelikleri kullanabilir miyim?

Hayır, öznitelikleri kullanan bir sınıftan türetilmiş bir sınıfta özniteliklerin kullanılması desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[COM ve .NET için C++ öznitelikleri](cpp-attributes-com-net.md)
