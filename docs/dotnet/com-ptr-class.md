---
title: com::ptr Sınıfı
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::com::ptr::ptr
- msclr::com::ptr::Attach
- msclr::com::ptr::CreateInstance
- msclr::com::ptr::Detach
- msclr::com::ptr::GetInterface
- msclr::com::ptr::QueryInterface
- msclr::com::ptr::Release
- msclr::com::ptr::operator=
- msclr::com::ptr::operator->
- msclr::com::ptr::operator!
helpviewer_keywords:
- msclr::ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: 342c222b837e179e2e13dbbd27c88efc18b12332
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774179"
---
# <a name="comptr-class"></a>com::ptr Sınıfı

Bir CLR sınıfının bir üyesi kullanılabilecek bir COM nesnesi için bir sarmalayıcı.  Sarmalayıcı da yok edici çağrıldığında nesne üzerinde sahip olunan tüm başvurularını serbest COM nesnesi ömrü yönetimini otomatikleştirir. Alınmak üzere [CComPtr sınıfı](../atl/reference/ccomptr-class.md).

## <a name="syntax"></a>Sözdizimi

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>Parametreler

*_interface_type*<br/>
COM arabirimi.

## <a name="remarks"></a>Açıklamalar

A `com::ptr` yerel işlev değişken olarak çeşitli COM görevleri basitleştirin ve ömür Yönetimi otomatik hale getirmek için de kullanılabilir.

A `com::ptr` doğrudan işlevi parametre olarak kullanılamaz; kullanmak bir [izleme başvurusu işleci](../extensions/tracking-reference-operator-cpp-component-extensions.md) veya [işlemek nesne işleci (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) yerine.

A `com::ptr` doğrudan bir işlevden döndürülen kullanılamaz; bunun yerine bir tanıtıcı kullanın.

## <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne.  Kapsanan çağrılarında sınıfı sonuçları genel yöntemleri çağırma `IXMLDOMDocument` nesne.  Örnek bir XML belgesi bir örneğini oluşturur, bazı basit XML ile doldurur ve Basitleştirilmiş bir Yürüme XML konsola yazdırmak için ayrıştırılmış belge ağacında düğümlerin yapar.

```cpp
// comptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into the document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // simplified function to write just the first xml node to the console
   void WriteXml() {
      IXMLDOMNode* pNode = NULL;

      try {
         // the first child of the document is the first real xml node
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            WriteNode(pNode);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(IXMLDOMNode* pNode) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteXml();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<word>persnickety</word>
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel oluşturucular

|Ad|Açıklama| 
|---------|-----------| 
|[ptr::ptr](#ptr)|Oluşturur bir `com::ptr` bir COM nesnesini sarmak için.| 
|[ptr::~ptr](#tilde-ptr)|Destructs bir `com::ptr`.| 

### <a name="public-methods"></a>Genel yöntemler

|Ad|Açıklama|
|---------|-----------| 
|[ptr::Attach](#attach)|Bir COM nesnesine iliştirir bir `com::ptr`.| 
|[ptr::CreateInstance](#createInstance)|Bir COM nesnesi içinde bir örneği oluşturan bir `com::ptr`.| 
|[ptr::Detach](#detach)|Nesnesine bir işaretçi döndüren COM nesnesi sahipliğini ayarlama olanağı sağlar.| 
|[ptr::GetInterface](#getInterface)|Bir COM nesnesi içinde bir örneği oluşturan bir `com::ptr`.| 
|[ptr::QueryInterface](#queryInterface)|Sahip olunan bir COM nesnesi bir arabirim için sorgular ve sonucu bir diğerine ekler `com::ptr`.| 
|[ptr::Release](#release)|COM nesne üzerinde sahip olunan tüm başvurularını serbest bırakır.|

### <a name="public-operators"></a>Genel işleçler

|Ad|Açıklama|
|---------|-----------| 
|[PTR::operator-&gt;](#operator-arrow)|Üye erişim işleci, sahip olunan bir COM nesnesi üzerinde yöntemleri çağırmak için kullanılır.| 
|[ptr::operator=](#operator-assign)|Bir COM nesnesine iliştirir bir `com::ptr`.| 
|[PTR::operator&nbsp;bool](#operator-bool)|Kullanarak işleci `com::ptr` koşullu ifadede.| 
|[ptr::operator!](#operator-logical-not)|Sahip olunan bir COM nesnesi geçersiz olup olmadığını belirlemek için işleci.| 

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\com\ptr.h >

**Namespace** msclr::com

 

## <a name="ptr"></a>PTR::PTR

Sahip olunan bir COM nesnesi için bir işaretçi döndürür.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bir COM arabirim işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olmayan Oluşturucu atar `nullptr` temel alınan nesne işlenecek. Gelecekteki çağrılar `com::ptr` iç nesne doğrulamak ve bir nesne oluşturulduğunda veya bağlı kadar sessizce başarısız.

Tek bağımsız değişkenli Oluşturucusu COM nesnesine bir başvuru ekler, ancak çağıranın çağırmanız gerekir böylece arayanın başvuru yayın değil `Release` gerçekten denetimini sağlamak için COM nesne üzerinde. Zaman `com::ptr`ait yok edici çağrıldığında otomatik olarak bir COM nesnesi üzerinde başvuruları serbest bırakır.

Geçirme `NULL` bu oluşturucuya çağırma bağımsız değişkenli sürümü ile aynıdır.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. Bu oluşturucu her iki sürümü de kullanımını gösterir.

```cpp
// comptr_ptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="tilde-ptr"></a>ptr::~ptr

Destructs bir `com::ptr`.

```cpp
~ptr();
```

### <a name="remarks"></a>Açıklamalar

Yok etme üzerinde `com::ptr` , COM nesnesine sahip tüm başvurularını serbest bırakır. Orada olduğu varsayılırsa, COM nesnesi için tutulan diğer başvuru, COM nesnesi silinecek ve onun belleğini serbest.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne.  İçinde `main` işlev, iki `XmlDocument` kapsamı dışında gitmeleri olduğunda nesnelerin yıkıcıları çağrılacaktır `try` temel kaynaklanan bloğu `com::ptr` yok Edicisi çağrılır, COM şirkete ait tüm başvurularını serbest bırakma nesne.

```cpp
// comptr_dtor.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="attach"></a>PTR::Attach

Bir COM nesnesine iliştirir bir `com::ptr`.

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
COM arabirimi eklemek için işaretçi.

### <a name="exceptions"></a>Özel Durumlar

Varsa `com::ptr` bir COM nesnesine bir başvuru zaten sahip `Attach` oluşturur <xref:System.InvalidOperationException>.

### <a name="remarks"></a>Açıklamalar

Bir çağrı `Attach` COM nesnesine başvuruyor ancak arayanın referansı sürüm değil.

Geçirme `NULL` için `Attach` alınan hiçbir eylem sonuçlanır.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. `ReplaceDocument` İlk işlev çağrıları, üye `Release` herhangi nesnesi ve ardından aramaları önceden ait `Attach` yeni bir belge nesnesi eklemek için.

```cpp
// comptr_attach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="createInstance"></a>PTR::CreateInstance

Bir COM nesnesi içinde bir örneği oluşturan bir `com::ptr`.

```cpp
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   System::String ^ progid
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   const wchar_t * progid
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter
);
void CreateInstance(
   REFCLSID rclsid
);
```

### <a name="parameters"></a>Parametreler

*progid*<br/>
A `ProgID` dize.

*pouter*<br/>
Toplam nesnenin IUnknown arabirimi (IUnknown) yönelik işaretçi. Varsa `pouter` belirlenmezse, `NULL` kullanılır.

*cls_context*<br/>
Yeni oluşturulan nesne yöneten kod çalıştırılacağı bağlamı. Değerleri alınmıştır `CLSCTX` sabit listesi. Varsa `cls_context` belirlenmezse, değerin CLSCTX_ALL kullanılır.

*rclsid*<br/>
`CLSID` veri ve nesneyi oluşturmak için kullanılan kod ile ilişkili.

### <a name="exceptions"></a>Özel Durumlar

Varsa `com::ptr` bir COM nesnesine bir başvuru zaten sahip `CreateInstance` oluşturur <xref:System.InvalidOperationException>.

Bu işlev çağrıları `CoCreateInstance` ve kullandığı <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> herhangi bir hata dönüştürmek için `HRESULT` için uygun bir özel durum.

### <a name="remarks"></a>Açıklamalar

`CreateInstance` kullanan `CoCreateInstance` ProgID veya bir CLSID tanımlanan belirtilen bir nesnenin yeni bir örneğini oluşturmak için. `com::ptr` Yeni oluşturulan nesneye başvuran ve yok etme sırasında şirkete ait tüm başvurularını otomatik olarak serbest bırakır.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. İki farklı tür sınıf oluşturucuları kullanmanıza `CreateInstance` ProgID içinden ya bir CLSID değeri artı bir CLSCTX belge nesnesi oluşturulamıyor.

```cpp
// comptr_createinstance.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }
   XmlDocument(REFCLSID clsid, DWORD clsctx) {
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc1("Msxml2.DOMDocument.3.0");

      // or from a clsid with specific CLSCTX
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

## <a name="detach"></a>PTR::detach

Nesnesine bir işaretçi döndüren COM nesnesi sahipliğini ayarlama olanağı sağlar.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>Dönüş değeri

COM nesne işaretçisi.

Hiçbir nesnenin sahibi, NULL döndürülür.

### <a name="exceptions"></a>Özel Durumlar

Dahili olarak `QueryInterface` sahip olunan bir COM nesnesi ve herhangi bir hata çağrılır `HRESULT` bir özel durumun dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Açıklamalar

`Detach` ilk çağıranın adına COM nesnesine bir başvuru ekler ve ardından tarafından sahip olunan tüm başvurularını serbest `com::ptr`.  Çağıran, yok etmek için döndürülen nesne sonuçta bırakmalıdır.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne.  `DetachDocument` Üye işlev çağrıları `Detach` COM nesnesi sahipliğini vermek ve çağırana bir işaretçi döndürür.

```cpp
// comptr_detach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // detach the COM object and return it
   // this releases the internal reference to the object
   IXMLDOMDocument* DetachDocument() {
      return m_ptrDoc.Detach();
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.DetachDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release document object as the ref class no longer owns it
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

## <a name="getInterface"></a>PTR::GetInterface

Sahip olunan bir COM nesnesi için bir işaretçi döndürür.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>Dönüş değeri

Sahip olunan bir COM nesnesine bir işaretçi.

### <a name="exceptions"></a>Özel Durumlar

Dahili olarak `QueryInterface` sahip olunan bir COM nesnesi ve herhangi bir hata çağrılır `HRESULT` bir özel durumun dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Açıklamalar

`com::ptr` Arayanın adınıza COM nesnesine bir başvuru ekler ve de COM nesnesi üzerinde kendi başvurusunu tutar. Çağırana döndürülen nesne üzerinde başvuru sonuçta serbest bırakmanız gerekir veya hiç yok edilir.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. `GetDocument` Üye işlevini kullanan `GetInterface` için COM nesnesine bir işaretçi döndürür.

```cpp
// comptr_getinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="queryInterface"></a>PTR::QueryInterface

Sahip olunan bir COM nesnesi bir arabirim için sorgular ve sonucu bir diğerine ekler `com::ptr`.

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
`com::ptr` Arabirimi alırsınız.

### <a name="exceptions"></a>Özel Durumlar

Dahili olarak `QueryInterface` sahip olunan bir COM nesnesi ve herhangi bir hata çağrılır `HRESULT` bir özel durumun dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Açıklamalar

Geçerli bir sarmalayıcı tarafından sahip olunan COM nesnesinin farklı bir arabirim için COM sarmalayıcı oluşturmak için bu yöntemi kullanın. Bu yöntemin çağırdığı `QueryInterface` com belirli bir arabirim işaretçisi istemek için sahip olunan COM nesnesi aracılığıyla nesne ve geçilen için döndürülen arabirim işaretçisinde ekler `com::ptr`.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. `WriteTopLevelNode` Üye işlevini kullanır `QueryInterface` yerel doldurmak için `com::ptr` ile bir `IXMLDOMNode` geçirir `com::ptr` (yönelik izleme başvurusuna tarafından) bir özel üye işlevine düğümün adını ve metin özellikleri konsola yazar.

```cpp
// comptr_queryinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into our document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // write the top level node to the console
   void WriteTopLevelNode() {
      com::ptr<IXMLDOMNode> ptrNode;

      // query for the top level node interface
      m_ptrDoc.QueryInterface(ptrNode);
      WriteNode(ptrNode);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(com::ptr<IXMLDOMNode> % node) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(node->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(node->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteTopLevelNode();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<#document>persnickety</#document>
```

## <a name="release"></a>PTR::Release

COM nesne üzerinde sahip olunan tüm başvurularını serbest bırakır.

```cpp
void Release();
```

### <a name="remarks"></a>Açıklamalar

Bu fonksiyonu çağıran COM nesnesi üzerinde sahip olunan tüm başvurularını serbest bırakır ve iç işleyici COM nesnesine ayarlar `nullptr`.  COM nesne üzerinde diğer başvuru yoksa yok edilir.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne.  `ReplaceDocument` Üye işlevini kullanan `Release` yeni belge eklemeden önce herhangi bir önceki belge nesneyi serbest bırakmak için.

```cpp
// comptr_release.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="operator-arrow"></a>PTR::operator-&gt;

Üye erişim işleci, sahip olunan bir COM nesnesi üzerinde yöntemleri çağırmak için kullanılır.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>Dönüş değeri

A `smart_com_ptr` COM nesnesi için.

### <a name="exceptions"></a>Özel Durumlar

Dahili olarak `QueryInterface` sahip olunan bir COM nesnesi ve herhangi bir hata çağrılır `HRESULT` bir özel durumun dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Açıklamalar

Bu işleç, sahip olunan COM nesnesinin yöntemlerini çağırmanız olanak tanır. Geçici bir döndürür `smart_com_ptr` otomatik olarak işleyen kendi `AddRef` ve `Release`.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. `WriteDocument` İşlevini kullanan `operator->` çağrılacak `get_firstChild` belge nesnenin bir üyesi.

```cpp
// comptr_op_member.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="operator-assign"></a>PTR::operator =

Bir COM nesnesine iliştirir bir `com::ptr`.

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
COM arabirimi eklemek için işaretçi.

### <a name="return-value"></a>Dönüş değeri

İzleme başvurusu üzerinde `com::ptr`.

### <a name="exceptions"></a>Özel Durumlar

Varsa `com::ptr` bir COM nesnesine bir başvuru zaten sahip `operator=` oluşturur <xref:System.InvalidOperationException>.

### <a name="remarks"></a>Açıklamalar

Bir COM nesnesine atamak bir `com::ptr` COM nesnesine başvuruyor ancak arayanın referansı sürüm değil.

Bu işleç aynı etkiye sahiptir `Attach`.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne.  `ReplaceDocument` İlk işlev çağrıları, üye `Release` herhangi nesnesi ve ardından kullanan önceden ait `operator=` yeni bir belge nesnesi eklemek için.

```cpp
// comptr_op_assign.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc = pDoc;
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by the ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="operator-bool"></a> PTR::operator bool

Kullanarak işleci `com::ptr` koşullu ifadede.

```cpp
operator bool();
```

### <a name="return-value"></a>Dönüş değeri

`true` sahip olunan bir COM nesnesi geçerliyse; `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sahip olunan bir COM nesnesi değilse geçerli `nullptr`.

Bu işleç dönüştürür `_detail_class::_safe_bool` daha güvenli olan `bool` bir integral türe dönüştürülemediğinden.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. `CreateInstance` Üye işlevini kullanan `operator bool` geçerli olduğundan ve bu ise, konsola, belirlemek için yeni belge nesnesi oluşturduktan sonra.

```cpp
// comptr_op_bool.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) { // uses operator bool
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```

## <a name="operator-logical-not"></a>PTR::operator!

Sahip olunan bir COM nesnesi geçersiz olup olmadığını belirlemek için işleci.

```cpp
bool operator!();
```

### <a name="return-value"></a>Dönüş değeri

`true` sahip olunan bir COM nesnesi geçersiz `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sahip olunan bir COM nesnesi değilse geçerli `nullptr`.

### <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne.  `CreateInstance` Üye işlevini kullanan `operator!` belge nesnesi zaten sahip olduğu ve Nesne geçersiz ise yalnızca yeni bir örneğini oluşturur, belirlemek için.

```cpp
// comptr_op_not.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) {
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```
