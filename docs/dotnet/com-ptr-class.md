---
title: com::PTR sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- com::ptr
- msclr::com::ptr
- msclr.com.ptr
- com.ptr
dev_langs:
- C++
helpviewer_keywords:
- ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3cd5b4115d50f9e2db9b1e3dc8a03818e2c8252f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066733"
---
# <a name="comptr-class"></a>com::ptr Sınıfı
Bir CLR sınıfının bir üyesi kullanılabilecek bir COM nesnesi için bir sarmalayıcı.  Sarmalayıcı da yok edici çağrıldığında nesne üzerinde sahip olunan tüm başvurularını serbest COM nesnesi ömrü yönetimini otomatikleştirir. Alınmak üzere [CComPtr sınıfı](../atl/reference/ccomptr-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### <a name="parameters"></a>Parametreler  
*_interface_type*<br/>
COM arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 A `com::ptr` yerel işlev değişken olarak çeşitli COM görevleri basitleştirin ve ömür Yönetimi otomatik hale getirmek için de kullanılabilir.  
  
 A `com::ptr` doğrudan işlevi parametre olarak kullanılamaz; kullanmak bir [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md) veya [işlemek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) bunun yerine.  
  
 A `com::ptr` doğrudan bir işlevden döndürülen kullanılamaz; bunun yerine bir tanıtıcı kullanın.  
  
## <a name="example"></a>Örnek  
 Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne.  Kapsanan çağrılarında sınıfı sonuçları genel yöntemleri çağırma `IXMLDOMDocument` nesne.  Örnek bir XML belgesi bir örneğini oluşturur, bazı basit XML ile doldurur ve Basitleştirilmiş bir Yürüme XML konsola yazdırmak için ayrıştırılmış belge ağacında düğümlerin yapar.  
  
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
 **Üst bilgi dosyası** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ destek kitaplığı](../dotnet/cpp-support-library.md)   
 [ptr Üyeleri](../dotnet/ptr-members.md)