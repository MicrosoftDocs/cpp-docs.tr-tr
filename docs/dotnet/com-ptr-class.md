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
ms.openlocfilehash: 9cb0ad23450d06bb314b0e2d6fa1d01784d633e2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214912"
---
# <a name="comptr-class"></a>com::ptr Sınıfı

Bir CLR sınıfının üyesi olarak kullanılabilecek COM nesnesi için sarmalayıcı.  Sarmalayıcı aynı zamanda COM nesnesinin yaşam süresi yönetimini de otomatikleştirir ve yok edicisi çağrıldığında nesnenin sahip olduğu tüm başvuruları serbest bırakır. [CComPtr sınıfına](../atl/reference/ccomptr-class.md)benzer.

## <a name="syntax"></a>Söz dizimi

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>Parametreler

*_interface_type*<br/>
COM arabirimi.

## <a name="remarks"></a>Açıklamalar

`com::ptr`Ayrıca, ÇEŞITLI com görevlerini basitleştirmek ve ömür yönetimini otomatikleştirmek için yerel bir işlev değişkeni olarak da kullanılabilir.

Bir `com::ptr` işlev parametresi olarak doğrudan kullanılamaz; bunun yerine bir [izleme başvurusu işleci](../extensions/tracking-reference-operator-cpp-component-extensions.md) veya [nesne işleci (^) için bir tanıtıcı](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) kullanın.

Bir `com::ptr` işlevden doğrudan döndürülemez; bunun yerine bir tanıtıcı kullanın.

## <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` .  Sınıfın ortak yöntemlerini çağırmak içerilen nesneye yapılan çağrılarla sonuçlanır `IXMLDOMDocument` .  Örnek, bir XML belgesinin bir örneğini oluşturur, onu bir basit XML ile doldurur ve ayrıştırılmış belge ağacındaki düğümlerin, XML 'yi konsola yazdırması için basitleştirilmiş bir yol oluşturur.

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

|Ad|Açıklama|
|---------|-----------|
|[PTR::p tr](#ptr)|Bir `com::ptr` com nesnesini kaydırmak için a oluşturur.|
|[ptr::~ptr](#tilde-ptr)|Yapıları kaldırır `com::ptr` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|---------|-----------|
|[ptr::Attach](#attach)|Bir COM nesnesini bir öğesine ekler `com::ptr` .|
|[ptr::CreateInstance](#createInstance)|İçindeki bir COM nesnesinin örneğini oluşturur `com::ptr` .|
|[ptr::Detach](#detach)|COM nesnesinin sahipliğini verir ve nesneye bir işaretçi döndürür.|
|[ptr::GetInterface](#getInterface)|İçindeki bir COM nesnesinin örneğini oluşturur `com::ptr` .|
|[ptr::QueryInterface](#queryInterface)|Bir arabirim için sahip olunan COM nesnesini sorgular ve sonucu başka bir öğesine ekler `com::ptr` .|
|[ptr::Release](#release)|COM nesnesinde sahip olunan tüm başvuruları yayınlar.|

### <a name="public-operators"></a>Ortak işleçler

|Ad|Açıklama|
|---------|-----------|
|[PTR:: operator-&gt;](#operator-arrow)|Üye erişim işleci, sahip olunan COM nesnesinde yöntemleri çağırmak için kullanılır.|
|[ptr::operator=](#operator-assign)|Bir COM nesnesini bir öğesine ekler `com::ptr` .|
|[PTR:: operator &nbsp; bool](#operator-bool)|`com::ptr`Bir koşullu ifadede kullanmak için işleci.|
|[PTR:: operator!](#operator-logical-not)|Sahip olunan COM nesnesinin geçersiz olup olmadığını belirleme işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası**\<msclr\com\ptr.h>

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

*P*<br/>
Bir COM arabirim işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bağımsız değişken olmayan Oluşturucu **`nullptr`** temel nesne tanıtıcısına atar. İçin gelecekteki çağrılar `com::ptr` iç nesneyi doğrular ve bir nesne oluşturuluncaya ya da iliştirilene kadar sessizce başarısız olur.

Tek değişkenli bir Oluşturucu COM nesnesine bir başvuru ekler, ancak çağıranın başvurusunu serbest bırakmaz, böylece çağıran, `Release` DENETIMIN com nesnesinde çağırmak zorunda kalmaz. `com::ptr`Yok edicisi çağrıldığında, kendi BAŞVURULARıNı com nesnesinde otomatik olarak serbest bırakılır.

`NULL`Bu oluşturucuya geçen bağımsız değişken olmayan sürümü çağırma ile aynıdır.

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` . Her iki oluşturucunun sürümünün kullanımını gösterir.

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

Yapıları kaldırır `com::ptr` .

```cpp
~ptr();
```

### <a name="remarks"></a>Açıklamalar

Yok etme sırasında, `com::ptr` Tüm BAŞVURULARı com nesnesine sahip olur. COM nesnesinde başka hiçbir başvuru olmadığı varsayılarak, COM nesnesi silinir ve belleği serbest bırakılır.

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` .  `main`İşlevinde, iki `XmlDocument` nesnenin yok edicisi blok kapsamının dışına gittiklerinde çağrılır, bu, **`try`** `com::ptr` ÇAĞRıLAN ve tüm başvurularını com nesnesine serbest bırakır.

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

Bir COM nesnesini bir öğesine ekler `com::ptr` .

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
Eklenecek COM arabirimi işaretçisi.

### <a name="exceptions"></a>Özel durumlar

`com::ptr`Zaten BIR com nesnesine bir başvuruya sahipse, `Attach` oluşturur <xref:System.InvalidOperationException> .

### <a name="remarks"></a>Açıklamalar

`Attach`Com nesnesine başvuruda bulunmak ancak çağıranın ona başvurusunu serbest bırakmayın.

`NULL` `Attach` Hiçbir eylemde bulunulmasına neden olan sonuçlara geçiliyor.

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` . `ReplaceDocument`Üye işlevi, önce `Release` daha önce sahip olunan herhangi bir nesneyi çağırır, sonra `Attach` Yeni bir belge nesnesi eklemek için çağırır.

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

İçindeki bir COM nesnesinin örneğini oluşturur `com::ptr` .

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
Bir `ProgID` dize.

*pOuter*<br/>
Toplama nesnesinin IUnknown arabirimine yönelik işaretçi (IUnknown denetimi). `pouter`Belirtilmemişse, `NULL` kullanılır.

*cls_context*<br/>
Yeni oluşturulan nesneyi yöneten kodun çalışacağı bağlam. Değerler `CLSCTX` numaralandırmasından alınır. `cls_context`Belirtilmemişse, CLSCTX_ALL değeri kullanılır.

*rclsıd*<br/>
`CLSID`nesneyi oluşturmak için kullanılacak verilerle ve kodla ilişkili.

### <a name="exceptions"></a>Özel durumlar

`com::ptr`Zaten BIR com nesnesine bir başvuruya sahipse, `CreateInstance` oluşturur <xref:System.InvalidOperationException> .

Bu işlev `CoCreateInstance` , herhangi bir <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> hatayı `HRESULT` uygun bir özel duruma dönüştürmek için çağırır ve kullanır.

### <a name="remarks"></a>Açıklamalar

`CreateInstance``CoCreateInstance`bir ProgID veya CLSID 'den tanımlanan belirtilen nesnenin yeni bir örneğini oluşturmak için kullanır. , `com::ptr` Yeni oluşturulan nesneye başvurur ve yok etme sırasında sahip olunan tüm başvuruları otomatik olarak serbest bırakılır.

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` . Sınıf oluşturucuları, `CreateInstance` bir ProgID 'den ya da bır CLSID Ile CLSCTX arasında belge nesnesi oluşturmak için iki farklı biçim kullanır.

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

### <a name="return-value"></a>Döndürülen değer

COM nesnesi işaretçisi.

Hiçbir nesne sahip değilse, NULL döndürülür.

### <a name="exceptions"></a>Özel durumlar

Dahili olarak, `QueryInterface` sahip olunan com nesnesinde çağrılır ve herhangi bir hata `HRESULT` , tarafından özel duruma dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> .

### <a name="remarks"></a>Açıklamalar

`Detach`İlk olarak, çağıran adına COM nesnesine bir başvuru ekler ve sonra öğesine ait tüm başvuruları yayınlar `com::ptr` .  Çağıran, sonunda döndürülen nesneyi yok etmek için serbest bırakmalıdır.

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` .  `DetachDocument`Üye işlevi, `Detach` com nesnesinin sahipliğini sağlamak için çağırır ve çağırana bir işaretçi döndürür.

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

### <a name="return-value"></a>Döndürülen değer

Sahip olunan COM nesnesine yönelik bir işaretçi.

### <a name="exceptions"></a>Özel durumlar

Dahili olarak, `QueryInterface` sahip olunan com nesnesinde çağrılır ve herhangi bir hata `HRESULT` , tarafından özel duruma dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> .

### <a name="remarks"></a>Açıklamalar

, `com::ptr` Çağıranın ADıNA com nesnesine bir başvuru ekler ve ayrıca com nesnesinde kendi başvurusunu tutar. Çağıran, sonunda başvuruyu döndürülen nesne üzerinde serbest bırakmalıdır veya hiçbir şekilde yok olmayacaktır.

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` . `GetDocument`Üye IşLEVI `GetInterface` com nesnesine bir işaretçi döndürmek için kullanır.

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

Bir arabirim için sahip olunan COM nesnesini sorgular ve sonucu başka bir öğesine ekler `com::ptr` .

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
`com::ptr`Bu işlem, arabirimini alır.

### <a name="exceptions"></a>Özel durumlar

Dahili olarak, `QueryInterface` sahip olunan com nesnesinde çağrılır ve herhangi bir hata `HRESULT` , tarafından özel duruma dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> .

### <a name="remarks"></a>Açıklamalar

Geçerli sarmalayıcı tarafından sahip olunan COM nesnesinin farklı bir arabirimi için bir COM sarmalayıcısı oluşturmak için bu yöntemi kullanın. Bu yöntem, `QueryInterface` com nesnesinin belirli bir arabirimine bir işaretçi istemek için sahip olunan com nesnesini çağırır ve döndürülen arabirim işaretçisini geçilen-ın öğesine ekler `com::ptr` .

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` . `WriteTopLevelNode`Üye işlevi `QueryInterface` `com::ptr` , ile yerel bir öğesini bir ile doldurmanız için kullanır `IXMLDOMNode` ve sonra `com::ptr` (izleme başvurusu), düğümün adını ve metin özelliklerini konsola yazan özel bir üye işlevine geçirir.

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

Bu işlevi çağırmak, COM nesnesinde sahip olunan tüm başvuruları yayınlar ve iç tanıtıcıyı COM nesnesine olarak ayarlar **`nullptr`** .  COM nesnesinde başka bir başvuru yoksa, yok edilir.

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` .  `ReplaceDocument`Üye işlevi, `Release` Yeni belgeyi eklemeden önce herhangi bir önceki belge nesnesini serbest bırakmak için kullanır.

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

### <a name="return-value"></a>Döndürülen değer

`smart_com_ptr`Com nesnesine bir.

### <a name="exceptions"></a>Özel durumlar

Dahili olarak, `QueryInterface` sahip olunan com nesnesinde çağrılır ve herhangi bir hata `HRESULT` , tarafından özel duruma dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> .

### <a name="remarks"></a>Açıklamalar

Bu işleç, sahip olunan COM nesnesinin yöntemlerini çağıralmanıza olanak sağlar. `smart_com_ptr`Otomatik olarak kendi ve işlemesini sağlayan bir geçici döndürür `AddRef` `Release` .

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` . `WriteDocument`İşlevi, `operator->` `get_firstChild` belge nesnesinin üyesini çağırmak için kullanır.

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

Bir COM nesnesini bir öğesine ekler `com::ptr` .

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
Eklenecek COM arabirimi işaretçisi.

### <a name="return-value"></a>Döndürülen değer

Üzerinde bir izleme başvurusu `com::ptr` .

### <a name="exceptions"></a>Özel durumlar

`com::ptr`Zaten BIR com nesnesine bir başvuruya sahipse, `operator=` oluşturur <xref:System.InvalidOperationException> .

### <a name="remarks"></a>Açıklamalar

Com nesnesine bir COM nesnesi atama, `com::ptr` com nesnesine başvuruda bulunmak ancak çağıranın ona başvurusunu serbest bırakmaz.

Bu işleç ile aynı etkiye sahiptir `Attach` .

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` .  `ReplaceDocument`Üye işlevi, önce `Release` daha önce sahip olunan herhangi bir nesneyi çağırır, sonra `operator=` Yeni bir belge nesnesi eklemek için kullanır.

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

`com::ptr`Bir koşullu ifadede kullanmak için işleci.

```cpp
operator bool();
```

### <a name="return-value"></a>Döndürülen değer

**`true`** sahip olunan COM nesnesi geçerliyse; **`false`** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sahip olunan COM nesnesi, değilse geçerli olur **`nullptr`** .

Bu işleç `_detail_class::_safe_bool` , **`bool`** bir integral türüne dönüştürülemediğinden daha güvenli olan öğesine dönüştürür.

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` . `CreateInstance`Üye işlevi, `operator bool` Yeni bir belge nesnesini oluşturduktan sonra, geçerli olup olmadığını ve varsa konsola yazmadığını anlamak için kullanır.

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

### <a name="return-value"></a>Döndürülen değer

**`true`** sahip olunan COM nesnesi geçersizse; **`false`** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sahip olunan COM nesnesi, değilse geçerli olur **`nullptr`** .

### <a name="example"></a>Örnek

Bu örnek `com::ptr` , özel üye nesnesini kaydırmak için öğesini kullanan BIR clr sınıfı uygular `IXMLDOMDocument` .  `CreateInstance`Üye işlevi `operator!` bir belge nesnesinin zaten sahip olup olmadığını anlamak için kullanır ve yalnızca nesne geçersizse yeni bir örnek oluşturur.

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
