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
ms.openlocfilehash: e494285f33cf282d7b7515aac374ec86ef3036b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372485"
---
# <a name="comptr-class"></a>com::ptr Sınıfı

CLR sınıfının bir üyesi olarak kullanılabilecek bir COM nesnesi için sarıcı.  Sarmalayıcı ayrıca COM nesnesinin yaşam boyu yönetimini otomatikleştirir ve yıkıcı çağrıldığında nesne üzerinde sahip olunan tüm başvuruları serbest yapar. [CComPtr sınıfına](../atl/reference/ccomptr-class.md)benzer.

## <a name="syntax"></a>Sözdizimi

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>Parametreler

*_interface_type*<br/>
COM arabirimi.

## <a name="remarks"></a>Açıklamalar

A, `com::ptr` çeşitli COM görevlerini basitleştirmek ve yaşam boyu yönetimini otomatikleştirmek için yerel bir işlev değişkeni olarak da kullanılabilir.

A `com::ptr` doğrudan işlev parametresi olarak kullanılamaz; bunun yerine [nesne işleci (^) için](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) bir [İzleme başvuru işleci](../extensions/tracking-reference-operator-cpp-component-extensions.md) veya Bir Tanıtıcı kullanın.

A `com::ptr` bir işlevden doğrudan döndürülemez; bunun yerine bir tutamaç kullanın.

## <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular.  Sınıfın ortak yöntemlerini çağırmak, içerdiği `IXMLDOMDocument` nesneye yapılan çağrılarla sonuçlanır.  Örnek, bir XML belgesi örneği oluşturur, bazı basit XML ile doldurur ve konsola XML yazdırmak için ayrıştırılmış belge ağacında düğümleri basitleştirilmiş bir yürüyüş yapar.

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

### <a name="public-constructors"></a>Kamu yapıcılar

|Adı|Açıklama|
|---------|-----------|
|[ptr::ptr](#ptr)|Com nesnesini sarmak için a'yı `com::ptr` oluşturuyor.|
|[ptr::~ptr](#tilde-ptr)|Yok eder bir `com::ptr`.|

### <a name="public-methods"></a>Genel yöntemler

|Adı|Açıklama|
|---------|-----------|
|[ptr::Attach](#attach)|Bir COM nesnesine `com::ptr`bir .|
|[ptr::CreateInstance](#createInstance)|Bir `com::ptr`com nesnesi içinde bir örnek oluşturur.|
|[ptr::Detach](#detach)|Bir işaretçiyi nesneye döndürerek COM nesnesinin sahipliğinden vazgeçer.|
|[ptr::GetInterface](#getInterface)|Bir `com::ptr`com nesnesi içinde bir örnek oluşturur.|
|[ptr::QueryInterface](#queryInterface)|Bir arabirim için sahip olunan COM nesnesini `com::ptr`sorgular ve sonucu başka bir arayüze bağlar.|
|[ptr::Release](#release)|COM nesnesindeki tüm sahip olunan başvuruları serbest bırakır.|

### <a name="public-operators"></a>Kamu operatörleri

|Adı|Açıklama|
|---------|-----------|
|[ptr::operatör-&gt;](#operator-arrow)|Üye erişim işleci, sahip olunan COM nesnesi üzerinde yöntemleri aramak için kullanılır.|
|[ptr::operator=](#operator-assign)|Bir COM nesnesine `com::ptr`bir .|
|[ptr::operatör&nbsp;bool](#operator-bool)|Koşullu `com::ptr` bir ifadede kullanmak için işleç.|
|[ptr::operatör!](#operator-logical-not)|Sahip olunan COM nesnesinin geçersiz olup olmadığını belirlemek için işleç.|

## <a name="requirements"></a>Gereksinimler

**Başlık dosyası** \<msclr\com\ptr.h>

**Namespace** msclr::com

## <a name="ptrptr"></a><a name="ptr"></a>ptr::ptr

Bir işaretçiyi sahip olunan COM nesnesine döndürür.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Com arabirim işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bağımsız olmayan oluşturucu, `nullptr` alttaki nesne koluna atar. Gelecekteki çağrılar `com::ptr` iç nesneyi doğrular ve bir nesne oluşturulana veya iliştirilene kadar sessizce başarısız olur.

Tek bağımsız değişken oluşturucu COM nesnesine bir başvuru ekler, ancak arayanın başvuruyu `Release` serbest bırakmaz, bu nedenle arayan com nesnesini gerçekten denetimden vazgeçmek için çağırmalıdır. `com::ptr`'Yıkıcı çağrıldığında, com nesnesi üzerindeki başvurularını otomatik olarak serbest bırakacaktır.

Bu `NULL` oluşturucuya geçmek, bağımsız değişken olmayan sürümü çağırmakla aynıdır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular. Oluşturucunun her iki versiyonunun da kullanımını gösterir.

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

## <a name="ptrptr"></a><a name="tilde-ptr"></a>ptr::~ptr

Yok eder bir `com::ptr`.

```cpp
~ptr();
```

### <a name="remarks"></a>Açıklamalar

Yıkım üzerine, `com::ptr` sahip olduğu tüm başvuruları COM nesnesine bırakır. COM nesnesine başka başvuru yapılmadığını varsayarsak, COM nesnesi silinir ve belleği serbest bırakılır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular.  `main` İşlevde, iki `XmlDocument` nesnenin yıkıcıları `try` bloğun kapsamı dışına çıktıklarında çağrılacak ve altta yatan `com::ptr` yıkıcının çağrılması ve sahip olunan tüm başvurularıcom nesnesine bırakması yla sonuçlanır.

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

## <a name="ptrattach"></a><a name="attach"></a>ptr::Ekle

Bir COM nesnesine `com::ptr`bir .

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
Eklenecek COM arabirim işaretçisi.

### <a name="exceptions"></a>Özel durumlar

Zaten bir COM nesnesi için `Attach` bir başvuru sahibi ise, <xref:System.InvalidOperationException> `com::ptr`

### <a name="remarks"></a>Açıklamalar

COM nesnesine başvuru yapan `Attach` bir çağrı, arayan kişinin başvurularını serbest bırakmaz.

Hiçbir `NULL` `Attach` işlem yapılmazsa sonuçlara geçmek.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular. Üye işlev önce `Release` daha önce sahip olunan herhangi bir nesneyi çağırır, sonra da yeni bir belge nesnesi eklemeyi çağırır. `Attach` `ReplaceDocument`

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

## <a name="ptrcreateinstance"></a><a name="createInstance"></a>ptr::CreateInstance

Bir `com::ptr`com nesnesi içinde bir örnek oluşturur.

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
Bir `ProgID` ip.

*pouter*<br/>
Toplu nesnenin IUnknown arabirimine (IUnknown denetimi) işaretçisi. `pouter` Belirtilmemişse kullanılır. `NULL`

*cls_context*<br/>
Yeni oluşturulan nesneyi yöneten kodun çalışacağı bağlam. Değerler numaralandırmadan `CLSCTX` alınır. `cls_context` Belirtilmemişse, CLSCTX_ALL değeri kullanılır.

*rclsid*<br/>
`CLSID`nesneyi oluşturmak için kullanılacak veri ve kod ile ilişkilidir.

### <a name="exceptions"></a>Özel durumlar

Zaten bir COM nesnesi için `CreateInstance` bir başvuru sahibi ise, <xref:System.InvalidOperationException> `com::ptr`

Bu işlev, <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> herhangi bir `HRESULT` hatayı uygun bir özel özel durum için çağırır `CoCreateInstance` ve kullanır.

### <a name="remarks"></a>Açıklamalar

`CreateInstance`bir `CoCreateInstance` ProgID veya CLSID'den tanımlanan belirtilen nesnenin yeni bir örneğini oluşturmak için kullanır. Yeni `com::ptr` oluşturulan nesneye başvurular ve imha üzerine sahip olunan tüm başvuruları otomatik olarak serbest bırakacaktır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular. Sınıf oluşturucuları, belge nesnesini `CreateInstance` progID'den veya CLSID artı CLSCTX'ten oluşturmak için iki farklı biçim kullanır.

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

## <a name="ptrdetach"></a><a name="detach"></a>ptr::Detach

Bir işaretçiyi nesneye döndürerek COM nesnesinin sahipliğinden vazgeçer.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>Döndürülen değer

COM nesnesinin işaretçisi.

Hiçbir nesneye sahip değilse, NULL döndürülür.

### <a name="exceptions"></a>Özel durumlar

Dahili `QueryInterface` olarak, sahip olunan COM `HRESULT` nesnesi üzerinde çağrılır ve herhangi bir hata tarafından <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>bir özel durum dönüştürülür.

### <a name="remarks"></a>Açıklamalar

`Detach`önce arayan adına COM nesnesine bir başvuru ekler ve sonra `com::ptr`.  Arayan sonuçta onu yok etmek için döndürülen nesneyi serbest bırakmalıdır.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular.  Üye `DetachDocument` işlev, `Detach` COM nesnesinin sahipliğinden vazgeçmeyi ve bir işaretçiyi arayana döndürmeyi çağırır.

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

## <a name="ptrgetinterface"></a><a name="getInterface"></a>ptr::GetInterface

Bir işaretçiyi sahip olunan COM nesnesine döndürür.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>Döndürülen değer

Sahip olunan COM nesnesine bir işaretçi.

### <a name="exceptions"></a>Özel durumlar

Dahili `QueryInterface` olarak, sahip olunan COM `HRESULT` nesnesi üzerinde çağrılır ve herhangi bir hata tarafından <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>bir özel durum dönüştürülür.

### <a name="remarks"></a>Açıklamalar

Arayan `com::ptr` adına COM nesnesine bir başvuru ekler ve aynı zamanda COM nesnesi üzerinde kendi başvuru tutar. Arayan sonuçta döndürülen nesne üzerinde başvuru serbest bırakmak gerekir, ya da yok asla.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular. `GetDocument` Üye işlev, `GetInterface` bir işaretçiyi COM nesnesine döndürmek için kullanır.

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

## <a name="ptrqueryinterface"></a><a name="queryInterface"></a>ptr::QueryInterface

Bir arabirim için sahip olunan COM nesnesini `com::ptr`sorgular ve sonucu başka bir arayüze bağlar.

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Arayüz `com::ptr` eve gelecek.

### <a name="exceptions"></a>Özel durumlar

Dahili `QueryInterface` olarak, sahip olunan COM `HRESULT` nesnesi üzerinde çağrılır ve herhangi bir hata tarafından <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>bir özel durum dönüştürülür.

### <a name="remarks"></a>Açıklamalar

Geçerli sarıcıya ait COM nesnesinin farklı bir arabirimi için bir COM sarıcı oluşturmak için bu yöntemi kullanın. Bu yöntem, com nesnesinin belirli bir arabirimine bir işaretçi istemek için sahip olunan COM nesnesi üzerinden çağırır `QueryInterface` ve döndürülen arabirim işaretçisi `com::ptr`geçirilir.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular. Üye `WriteTopLevelNode` işlev, `QueryInterface` bir yerel `com::ptr` ile `IXMLDOMNode` bir doldurmak `com::ptr` için kullanır ve sonra (izleme başvurusu) düğüm adını ve metin özelliklerini konsola yazan özel bir üye işlev geçer.

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

## <a name="ptrrelease"></a><a name="release"></a>ptr::Yayın

COM nesnesindeki tüm sahip olunan başvuruları serbest bırakır.

```cpp
void Release();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak, COM nesnesindeki tüm sahip olunan `nullptr`başvuruları serbest bırakır ve iç tutamacı COM nesnesine ayarlar.  COM nesnesi üzerinde başka başvuru yoksa, yok edilir.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular.  Üye `ReplaceDocument` işlev, `Release` yeni belgeyi eklemeden önce önceki herhangi bir belge nesnesini serbest bırakmak için kullanır.

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

## <a name="ptroperator-gt"></a><a name="operator-arrow"></a>ptr::operatör-&gt;

Üye erişim işleci, sahip olunan COM nesnesi üzerinde yöntemleri aramak için kullanılır.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>Döndürülen değer

COM `smart_com_ptr` nesnesine A.

### <a name="exceptions"></a>Özel durumlar

Dahili `QueryInterface` olarak, sahip olunan COM `HRESULT` nesnesi üzerinde çağrılır ve herhangi bir hata tarafından <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>bir özel durum dönüştürülür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, sahip olunan COM nesnesinin yöntemlerini aramanızı sağlar. Otomatik olarak `smart_com_ptr` kendi `AddRef` ve işler geçici `Release`döndürür.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular. `WriteDocument` İşlev, `operator->` belge `get_firstChild` nesnesinin üyesini aramak için kullanır.

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

## <a name="ptroperator"></a><a name="operator-assign"></a>ptr::operator=

Bir COM nesnesine `com::ptr`bir .

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
Eklenecek COM arabirim işaretçisi.

### <a name="return-value"></a>Döndürülen değer

Üzerinde bir izleme `com::ptr`başvurusu.

### <a name="exceptions"></a>Özel durumlar

Zaten bir COM nesnesi için `operator=` bir başvuru sahibi ise, <xref:System.InvalidOperationException> `com::ptr`

### <a name="remarks"></a>Açıklamalar

Com nesnesine `com::ptr` bir COM nesnesi atama, ancak arayanın başvurularını serbest bırakmaz.

Bu işleç aynı `Attach`etkiye sahiptir.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular.  Üye işlev önce `Release` daha önce sahip olunan herhangi bir nesneyi çağırır ve ardından yeni bir belge nesnesi eklemek için kullanır. `operator=` `ReplaceDocument`

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

## <a name="ptroperator-bool"></a><a name="operator-bool"></a>ptr::operatör bool

Koşullu `com::ptr` bir ifadede kullanmak için işleç.

```cpp
operator bool();
```

### <a name="return-value"></a>Döndürülen değer

`true`sahip olunan COM nesnesi geçerliyse; `false` aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sahip olunan COM nesnesi `nullptr`değilse geçerlidir.

Bu işleç, `_detail_class::_safe_bool` integral türüne dönüştürülemediği için daha güvenli `bool` olana dönüştürür.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular. Üye `CreateInstance` işlev, `operator bool` yeni belge nesnesini oluşturduktan sonra geçerli olup olmadığını belirlemek için kullanır ve varsa konsola yazar.

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

## <a name="ptroperator"></a><a name="operator-logical-not"></a>ptr::operatör!

Sahip olunan COM nesnesinin geçersiz olup olmadığını belirlemek için işleç.

```cpp
bool operator!();
```

### <a name="return-value"></a>Döndürülen değer

`true`sahip olunan COM nesnesi geçersizse; `false` aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sahip olunan COM nesnesi `nullptr`değilse geçerlidir.

### <a name="example"></a>Örnek

Bu örnek, özel üye `com::ptr` `IXMLDOMDocument` nesnesini sarmak için a kullanan bir CLR sınıfını uygular.  Üye `CreateInstance` işlev, `operator!` bir belge nesnesinin zaten sahip olup olmadığını belirlemek için kullanır ve yalnızca nesne geçersizse yeni bir örnek oluşturur.

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
