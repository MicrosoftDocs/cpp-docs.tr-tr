---
title: "com::PTR sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- com::ptr
- msclr::com::ptr
- msclr.com.ptr
- com.ptr
dev_langs: C++
helpviewer_keywords: ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ae02518b60190dd129443f00d82b377317c816b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptr-class"></a>com::ptr Sınıfı
Bir CLR sınıf üyesi olarak kullanılabilir bir COM nesnesi için sarmalayıcı.  Sarmalayıcı Ayrıca kendi yıkıcı çağrıldığında nesne üzerinde sahip olunan tüm başvurularını serbest COM nesnesinin ömür yönetimini otomatikleştirir. Benzer [CComPtr sınıfı](../atl/reference/ccomptr-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_interface_type`  
 COM arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 A `com::ptr` yerel işlevi değişken olarak çeşitli COM görevlerini basitleştirmek ve ömür yönetimini otomatikleştirmek için de kullanılabilir.  
  
 A `com::ptr` doğrudan işlevi parametre olarak kullanılamaz; kullanın bir [izleme başvurusu işleci](../windows/tracking-reference-operator-cpp-component-extensions.md) veya [işlemek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) yerine.  
  
 A `com::ptr` doğrudan bir işleve döndürülemiyor; bunun yerine bir tanıtıcı kullanın.  
  
## <a name="example"></a>Örnek  
 Bu örnek kullanan bir CLR sınıfı uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesnesi.  Kapsanan çağrılarında sınıfı sonuçları ortak yöntemleri çağırma `IXMLDOMDocument` nesnesi.  Örnek bir XML belgesi örneği oluşturur, bazı basit XML ile doldurur ve Basitleştirilmiş ilerlemesi konsoluna XML yazdırmak için ayrıştırılmış belge ağacında düğümlerin yapar.  
  
```  
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
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ destek kitaplığı](../dotnet/cpp-support-library.md)   
 [ptr Üyeleri](../dotnet/ptr-members.md)