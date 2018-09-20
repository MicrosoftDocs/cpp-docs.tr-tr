---
title: PTR::PTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr::ptr
- ptr.ptr
- msclr.com.ptr.ptr
- msclr::com::ptr::ptr
dev_langs:
- C++
helpviewer_keywords:
- ptr::ptr
ms.assetid: 4f5883b4-7c0a-46c6-aa9f-4e49eed463eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 32b142a378fa18f8e14ef48cc75da8db415c2c4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446185"
---
# <a name="ptrptr"></a>ptr::ptr

Oluşturur bir `com::ptr` bir COM nesnesini sarmak için.

## <a name="syntax"></a>Sözdizimi

```
ptr();
ptr(
   _interface_type * p
);
```

#### <a name="parameters"></a>Parametreler

*P*<br/>
Bir COM arabirim işaretçisi.

## <a name="remarks"></a>Açıklamalar

Bağımsız değişken olmayan Oluşturucu atar `nullptr` temel alınan nesne işlenecek. Yapılan sonraki çağrılar `com::ptr` iç nesne doğrulamak ve bir nesneyi gerçekten oluşturulduğunda veya bağlı kadar sessizce başarısız.

Tek bağımsız değişkenli Oluşturucusu COM nesnesine bir başvuru ekler, ancak çağıranın çağırmanız gerekir böylece arayanın başvuru serbest bırakmaz `Release` gerçekten denetimini sağlamak için COM nesne üzerinde. Zaman `com::ptr`ait yok edici çağrıldığında otomatik olarak bir COM nesnesi üzerinde başvuruları serbest bırakır.

Geçirme `NULL` bu oluşturucuya çağırma bağımsız değişkenli sürümü ile aynıdır.

## <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. Bu oluşturucu her iki sürümü de kullanımını gösterir.

```
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

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>Ayrıca Bkz.

[ptr Üyeleri](../dotnet/ptr-members.md)<br/>
[ptr::CreateInstance](../dotnet/ptr-createinstance.md)<br/>
[ptr::~ptr](../dotnet/ptr-tilde-ptr.md)