---
title: PTR::operator = | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr.operator=
- msclr.com.ptr.operator=
- msclr::com::ptr::operator=
- ptr::operator=
dev_langs: C++
helpviewer_keywords: operator=
ms.assetid: 58619910-46c0-4db8-b183-c811b23b2df1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89d26c7011c31e5f4aad66589192ac38e2244e1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ptroperator"></a>ptr::operator=
Bir COM nesnesi ekler bir `com::ptr`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ptr<_interface_type> % operator=(  
   _interface_type * _right  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_right`  
 Eklenecek COM arabirimi işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İzleme başvurusu üzerinde `com::ptr`.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `com::ptr` zaten bir COM nesnesi başvuru sahibi `operator=` oluşturur <xref:System.InvalidOperationException>.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir COM nesnesi atama bir `com::ptr` COM nesnesine başvuruyor ancak arayanın referansı bırakmaz.  
  
 Bu işleç aynı etkiye sahip `Attach`.  
  
## <a name="example"></a>Örnek  
 Bu örnek kullanan bir CLR sınıfı uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesnesi.  `ReplaceDocument` Üye fonksiyonu ilk çağrıları `Release` herhangi nesne ve kullandığı önceden ait `operator=` belge yeni bir nesne eklemek için.  
  
```  
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
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [PTR üyeleri](../dotnet/ptr-members.md)   
 [PTR::Attach](../dotnet/ptr-attach.md)   
 [PTR::detach](../dotnet/ptr-detach.md)   
 [PTR::Release](../dotnet/ptr-release.md)