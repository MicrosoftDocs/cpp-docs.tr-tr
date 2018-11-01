---
title: ptr::QueryInterface
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr.QueryInterface
- ptr::QueryInterface
- msclr::com::ptr::QueryInterface
- msclr.com.ptr.QueryInterface
helpviewer_keywords:
- QueryInterface method
ms.assetid: c2619517-3fde-493b-b12d-da8f62d5d803
ms.openlocfilehash: f596a26213ad75bc835b01e69fe57cece580f8ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677454"
---
# <a name="ptrqueryinterface"></a>ptr::QueryInterface

Sahip olunan bir COM nesnesi bir arabirim için sorgular ve sonucu bir diğerine ekler `com::ptr`.

## <a name="syntax"></a>Sözdizimi

```
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

#### <a name="parameters"></a>Parametreler

*Diğer*<br/>
`com::ptr` Arabirimi alırsınız.

## <a name="exceptions"></a>Özel Durumlar

Dahili olarak `QueryInterface` sahip olunan bir COM nesnesi ve herhangi bir hata çağrılır `HRESULT` bir özel durumun dönüştürülür <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

## <a name="remarks"></a>Açıklamalar

Geçerli bir sarmalayıcı tarafından sahip olunan COM nesnesinin farklı bir arabirim için COM sarmalayıcı oluşturmak için bu yöntemi kullanın. Bu yöntemin çağırdığı `QueryInterface` com belirli bir arabirim işaretçisi istemek için sahip olunan COM nesnesi aracılığıyla nesne ve geçilen için döndürülen arabirim işaretçisinde ekler `com::ptr`.

## <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. `WriteTopLevelNode` Üye işlevini kullanır `QueryInterface` yerel doldurmak için `com::ptr` ile bir `IXMLDOMNode` geçirir `com::ptr` (yönelik izleme başvurusuna tarafından) bir özel üye işlevine düğümün adını ve metin özellikleri konsola yazar.

```
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

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>Ayrıca Bkz.

[ptr Üyeleri](../dotnet/ptr-members.md)<br/>
[ptr::GetInterface](../dotnet/ptr-getinterface.md)