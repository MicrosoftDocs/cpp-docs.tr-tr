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
ms.openlocfilehash: 8a3223543dfa6c1b5b45fef2780cd11b558eab84
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078961"
---
# <a name="comptr-class"></a>com::ptr Sınıfı

Bir CLR sınıfının üyesi olarak kullanılabilecek COM nesnesi için sarmalayıcı.  Sarmalayıcı aynı zamanda COM nesnesinin yaşam süresi yönetimini de otomatikleştirir ve yok edicisi çağrıldığında nesnenin sahip olduğu tüm başvuruları serbest bırakır. [CComPtr sınıfına](../atl/reference/ccomptr-class.md)benzer.

## <a name="syntax"></a>Sözdizimi

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>Parametreler

*_interface_type*<br/>
COM arabirimi.

## <a name="remarks"></a>Açıklamalar

Ayrıca, çeşitli COM görevlerini basitleştirmek ve ömür yönetimini otomatikleştirmek için bir yerel işlev değişkeni olarak bir `com::ptr` kullanılabilir.

Bir `com::ptr` doğrudan bir işlev parametresi olarak kullanılamaz; Bunun yerine bir [izleme başvurusu işleci](../extensions/tracking-reference-operator-cpp-component-extensions.md) veya [nesne işleci (^) için bir tanıtıcı](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) kullanın.

Bir `com::ptr` doğrudan bir işlevden döndürülemez; Bunun yerine bir tanıtıcı kullanın.

## <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular.  Sınıfın ortak yöntemlerini çağırmak, içerilen `IXMLDOMDocument` nesnesine yapılan çağrılara neden olur.  Örnek, bir XML belgesinin bir örneğini oluşturur, onu bir basit XML ile doldurur ve ayrıştırılmış belge ağacındaki düğümlerin, XML 'yi konsola yazdırması için basitleştirilmiş bir yol oluşturur.

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

### <a name="public-constructors"></a>Ortak oluşturucular

|Adı|Açıklama|
|---------|-----------|
|[ptr::ptr](#ptr)|Bir COM nesnesini kaydırmak için bir `com::ptr` oluşturur.|
|[ptr::~ptr](#tilde-ptr)|`com::ptr`yapıları kaldırır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|---------|-----------|
|[ptr::Attach](#attach)|`com::ptr`bir COM nesnesi ekler.|
|[ptr::CreateInstance](#createInstance)|`com::ptr`içinde bir COM nesnesi örneği oluşturur.|
|[ptr::Detach](#detach)|COM nesnesinin sahipliğini verir ve nesneye bir işaretçi döndürür.|
|[ptr::GetInterface](#getInterface)|`com::ptr`içinde bir COM nesnesi örneği oluşturur.|
|[ptr::QueryInterface](#queryInterface)|Bir arabirim için sahip olunan COM nesnesini sorgular ve sonucu başka bir `com::ptr`iliştirir.|
|[ptr::Release](#release)|COM nesnesinde sahip olunan tüm başvuruları yayınlar.|

### <a name="public-operators"></a>Ortak işleçler

|Adı|Açıklama|
|---------|-----------|
|[PTR:: operator-&gt;](#operator-arrow)|Üye erişim işleci, sahip olunan COM nesnesinde yöntemleri çağırmak için kullanılır.|
|[ptr::operator=](#operator-assign)|`com::ptr`bir COM nesnesi ekler.|
|[PTR:: operator&nbsp;bool](#operator-bool)|Koşullu ifadede `com::ptr` kullanmak için işleç.|
|[ptr::operator!](#operator-logical-not)|Sahip olunan COM nesnesinin geçersiz olup olmadığını belirleme işleci.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi dosyası** \<msclr\com\ptr.h >

**Ad alanı** msclr:: com

## <a name="ptrptr"></a><a name="ptr"></a>PTR::p tr

Sahip olunan COM nesnesine bir işaretçi döndürür.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bir COM arabirim işaretçisi.

### <a name="remarks"></a>Açıklamalar

No-bağımsız değişken Oluşturucu temel nesne tanıtıcısına `nullptr` atar. `com::ptr` yapılan çağrılar iç nesneyi doğrular ve bir nesne oluşturuluncaya veya iliştirilene kadar sessizce başarısız olur.

Tek değişkenli bir Oluşturucu COM nesnesine bir başvuru ekler ancak çağıranın başvurusunu serbest bırakmaz, bu nedenle çağıran, denetimi gerçekten denetlemek için COM nesnesinde `Release` çağırmalıdır. `com::ptr`yıkıcısı çağrıldığında, başvuruları COM nesnesinde otomatik olarak serbest bırakılır.

Bu oluşturucuya `NULL` geçirmek, bağımsız değişken olmayan sürümü çağırmada de aynıdır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular. Her iki oluşturucunun sürümünün kullanımını gösterir.

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

## <a name="ptrptr"></a><a name="tilde-ptr"></a>PTR:: ~ PTR

`com::ptr`yapıları kaldırır.

```cpp
~ptr();
```

### <a name="remarks"></a>Açıklamalar

Yok etme durumunda `com::ptr`, kendi COM nesnesine sahip olduğu tüm başvuruları yayınlar. COM nesnesinde başka hiçbir başvuru olmadığı varsayılarak, COM nesnesi silinir ve belleği serbest bırakılır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular.  `main` işlevinde, bu iki `XmlDocument` nesnenin yok edicisi `try` bloğunun kapsamından çalıştıklarında çağrılır ve bu, temel alınan `com::ptr` yıkıcıya sahip olan tüm başvuruları COM nesnesine serbest bırakır.

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

## <a name="ptrattach"></a><a name="attach"></a>PTR:: Attach

`com::ptr`bir COM nesnesi ekler.

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
Eklenecek COM arabirimi işaretçisi.

### <a name="exceptions"></a>Özel Durumlar

`com::ptr` bir COM nesnesine bir başvuruya zaten sahipse, `Attach` <xref:System.InvalidOperationException>oluşturur.

### <a name="remarks"></a>Açıklamalar

`Attach` çağrısı COM nesnesine başvurur ancak çağıranın ona başvurusunu serbest bırakmaz.

`NULL` `Attach`, hiçbir eylemde bulunulmasına neden olur.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular. `ReplaceDocument` member işlevi önce daha önce sahip olunan herhangi bir nesne üzerinde `Release` çağırır ve sonra yeni bir belge nesnesi eklemek `Attach` çağırır.

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

## <a name="ptrcreateinstance"></a><a name="createInstance"></a>PTR:: CreateInstance

`com::ptr`içinde bir COM nesnesi örneği oluşturur.

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
Bir `ProgID` dizesi.

*pOuter*<br/>
Toplama nesnesinin IUnknown arabirimine yönelik işaretçi (IUnknown denetimi). `pouter` belirtilmezse, `NULL` kullanılır.

*cls_context*<br/>
Yeni oluşturulan nesneyi yöneten kodun çalışacağı bağlam. Değerler `CLSCTX` numaralandırmasından alınır. `cls_context` belirtilmemişse, CLSCTX_ALL değeri kullanılır.

*rclsıd*<br/>
nesneyi oluşturmak için kullanılacak veriler ve kodla ilişkili `CLSID`.

### <a name="exceptions"></a>Özel Durumlar

`com::ptr` bir COM nesnesine bir başvuruya zaten sahipse, `CreateInstance` <xref:System.InvalidOperationException>oluşturur.

Bu işlev `CoCreateInstance` çağırır ve herhangi bir hata `HRESULT` uygun bir özel duruma dönüştürmek için <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> kullanır.

### <a name="remarks"></a>Açıklamalar

`CreateInstance`, bir ProgID veya CLSID 'den tanımlanan, belirtilen nesnenin yeni bir örneğini oluşturmak için `CoCreateInstance` kullanır. `com::ptr` yeni oluşturulan nesneye başvurur ve yok etme sonrasında tüm sahip olan başvuruları otomatik olarak serbest bırakılır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular. Sınıf oluşturucular, bir ProgID 'den ya da bir CLSID ile CLSCTX arasında belge nesnesini oluşturmak için iki farklı `CreateInstance` biçimi kullanır.

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

## <a name="ptrdetach"></a><a name="detach"></a>PTR::D etach

COM nesnesinin sahipliğini verir ve nesneye bir işaretçi döndürür.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>Dönüş değeri

COM nesnesi işaretçisi.

Hiçbir nesne sahip değilse, NULL döndürülür.

### <a name="exceptions"></a>Özel Durumlar

Dahili olarak, `QueryInterface` sahip olan COM nesnesinde çağrılır ve herhangi bir hata `HRESULT` <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>tarafından özel duruma dönüştürülür.

### <a name="remarks"></a>Açıklamalar

`Detach` önce çağıran adına COM nesnesine bir başvuru ekler ve sonra `com::ptr`ait tüm başvuruları serbest bırakır.  Çağıran, sonunda döndürülen nesneyi yok etmek için serbest bırakmalıdır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular.  `DetachDocument` member işlevi, COM nesnesinin sahipliğini sağlamak için `Detach` çağırır ve çağırana bir işaretçi döndürür.

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

## <a name="ptrgetinterface"></a><a name="getInterface"></a>PTR:: GetInterface

Sahip olunan COM nesnesine bir işaretçi döndürür.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>Dönüş değeri

Sahip olunan COM nesnesine yönelik bir işaretçi.

### <a name="exceptions"></a>Özel Durumlar

Dahili olarak, `QueryInterface` sahip olan COM nesnesinde çağrılır ve herhangi bir hata `HRESULT` <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>tarafından özel duruma dönüştürülür.

### <a name="remarks"></a>Açıklamalar

`com::ptr`, çağıran adına COM nesnesine bir başvuru ekler ve ayrıca COM nesnesinde kendi başvurusunu tutar. Çağıran, sonunda başvuruyu döndürülen nesne üzerinde serbest bırakmalıdır veya hiçbir şekilde yok olmayacaktır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular. `GetDocument` member işlevi COM nesnesine bir işaretçi döndürmek için `GetInterface` kullanır.

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

## <a name="ptrqueryinterface"></a><a name="queryInterface"></a>PTR:: QueryInterface

Bir arabirim için sahip olunan COM nesnesini sorgular ve sonucu başka bir `com::ptr`iliştirir.

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Arabirimi alacak `com::ptr`.

### <a name="exceptions"></a>Özel Durumlar

Dahili olarak, `QueryInterface` sahip olan COM nesnesinde çağrılır ve herhangi bir hata `HRESULT` <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>tarafından özel duruma dönüştürülür.

### <a name="remarks"></a>Açıklamalar

Geçerli sarmalayıcı tarafından sahip olunan COM nesnesinin farklı bir arabirimi için bir COM sarmalayıcısı oluşturmak için bu yöntemi kullanın. Bu yöntem, COM nesnesinin belirli bir arabirimine bir işaretçi istemek için sahip olunan COM nesnesi aracılığıyla `QueryInterface` çağırır ve döndürülen arabirim işaretçisini geçirilen `com::ptr`iliştirir.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular. `WriteTopLevelNode` member işlevi bir `IXMLDOMNode` ile yerel bir `com::ptr` `QueryInterface` ve ardından `com::ptr` (başvuruya göre), düğümün adını ve metin özelliklerini konsola yazan özel bir üye işlevine geçirir.

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

## <a name="ptrrelease"></a><a name="release"></a>PTR:: Release

COM nesnesinde sahip olunan tüm başvuruları yayınlar.

```cpp
void Release();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak COM nesnesinde sahip olunan tüm başvuruları yayınlar ve iç tanıtıcıyı `nullptr`için COM nesnesine ayarlar.  COM nesnesinde başka bir başvuru yoksa, yok edilir.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular.  `ReplaceDocument` member işlevi, yeni belgeyi eklemeden önce herhangi bir önceki belge nesnesini serbest bırakmak için `Release` kullanır.

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

## <a name="ptroperator-gt"></a><a name="operator-arrow"></a>PTR:: operator-&gt;

Üye erişim işleci, sahip olunan COM nesnesinde yöntemleri çağırmak için kullanılır.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>Dönüş değeri

COM nesnesine bir `smart_com_ptr`.

### <a name="exceptions"></a>Özel Durumlar

Dahili olarak, `QueryInterface` sahip olan COM nesnesinde çağrılır ve herhangi bir hata `HRESULT` <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>tarafından özel duruma dönüştürülür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, sahip olunan COM nesnesinin yöntemlerini çağıralmanıza olanak sağlar. Kendi `AddRef` ve `Release`otomatik olarak işleyen geçici bir `smart_com_ptr` döndürür.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular. `WriteDocument` işlevi, belge nesnesinin `get_firstChild` üyesini çağırmak için `operator->` kullanır.

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

## <a name="ptroperator"></a><a name="operator-assign"></a>PTR:: operator =

`com::ptr`bir COM nesnesi ekler.

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
Eklenecek COM arabirimi işaretçisi.

### <a name="return-value"></a>Dönüş değeri

`com::ptr`bir izleme başvurusu.

### <a name="exceptions"></a>Özel Durumlar

`com::ptr` bir COM nesnesine bir başvuruya zaten sahipse, `operator=` <xref:System.InvalidOperationException>oluşturur.

### <a name="remarks"></a>Açıklamalar

Com nesnesine bir `com::ptr` atamak COM nesnesine başvurur ancak çağıranın ona başvurusunu serbest bırakmaz.

Bu işleç `Attach`ile aynı etkiye sahiptir.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular.  `ReplaceDocument` member işlevi önce daha önce sahip olunan herhangi bir nesne üzerinde `Release` çağırır ve sonra yeni bir belge nesnesi iliştirmek `operator=` kullanır.

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

## <a name="ptroperator-bool"></a><a name="operator-bool"></a>PTR:: operator bool

Koşullu ifadede `com::ptr` kullanmak için işleç.

```cpp
operator bool();
```

### <a name="return-value"></a>Dönüş değeri

sahip olan COM nesnesi geçerliyse `true`; Aksi takdirde `false`.

### <a name="remarks"></a>Açıklamalar

Sahip olunan COM nesnesi `nullptr`geçerli değildir.

Bu işleç, bir integral türüne dönüştürülemediğinden, `bool` daha güvenli olan `_detail_class::_safe_bool` dönüştürür.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular. `CreateInstance` member işlevi, yeni bir belge nesnesini oluşturduktan sonra `operator bool` kullanır ve varsa konsola yazar.

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

## <a name="ptroperator"></a><a name="operator-logical-not"></a>PTR:: operator!

Sahip olunan COM nesnesinin geçersiz olup olmadığını belirleme işleci.

```cpp
bool operator!();
```

### <a name="return-value"></a>Dönüş değeri

sahip olan COM nesnesi geçersiz ise `true`; Aksi takdirde `false`.

### <a name="remarks"></a>Açıklamalar

Sahip olunan COM nesnesi `nullptr`geçerli değildir.

### <a name="example"></a>Örnek

Bu örnek, özel üye `IXMLDOMDocument` nesnesini kaydırmak için `com::ptr` kullanan bir CLR sınıfı uygular.  `CreateInstance` member işlevi bir belge nesnesinin zaten sahip olup olmadığını anlamak için `operator!` kullanır ve yalnızca nesne geçersizse yeni bir örnek oluşturur.

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
