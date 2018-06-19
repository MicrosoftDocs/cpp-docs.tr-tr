---
title: PTR::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::com::ptr::Attach
- ptr::Attach
- ptr.Attach
- msclr.com.ptr.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method
ms.assetid: 81d930de-cb2a-4c30-9bd6-94d65942c47a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 57796a9df96d8bfc5d83594fad48d4e9de5e4303
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161622"
---
# <a name="ptrattach"></a>ptr::Attach
Bir COM nesnesi ekler bir `com::ptr`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void Attach(  
   _interface_type * _right  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_right`  
 Eklenecek COM arabirimi işaretçisi.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `com::ptr` zaten bir COM nesnesi başvuru sahibi `Attach` oluşturur <xref:System.InvalidOperationException>.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrı `Attach` COM nesnesine başvuruyor ancak arayanın referansı bırakmaz.  
  
 Geçirme `NULL` için `Attach` herhangi bir eylemle kalmasına neden olur.  
  
## <a name="example"></a>Örnek  
 Bu örnek kullanan bir CLR sınıfı uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesnesi. `ReplaceDocument` Üye fonksiyonu ilk çağrıları `Release` herhangi nesne ve çağrıları önceden ait `Attach` belge yeni bir nesne eklemek için.  
  
```  
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
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [PTR üyeleri](../dotnet/ptr-members.md)   
 [PTR::operator =](../dotnet/ptr-operator-assign.md)   
 [ptr::Release](../dotnet/ptr-release.md)