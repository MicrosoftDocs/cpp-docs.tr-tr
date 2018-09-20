---
title: PTR::CreateInstance | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr.CreateInstance
- msclr::com::ptr::CreateInstance
- msclr.com.ptr.CreateInstance
- ptr::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- ptr::CreateInstance
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 56034267c40e34c2a88295e27372b96c8d32b675
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409750"
---
# <a name="ptrcreateinstance"></a>ptr::CreateInstance

Bir COM nesnesi içinde bir örneği oluşturan bir `com::ptr`.

## <a name="syntax"></a>Sözdizimi

```
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

#### <a name="parameters"></a>Parametreler

*progid*<br/>
A `ProgID` dize.

*pouter*<br/>
Toplam nesnenin IUnknown arabirimi (IUnknown) yönelik işaretçi. Varsa `pouter` belirtilmezse, `NULL` kullanılır.

*cls_context*<br/>
Yeni oluşturulan nesne yöneten kod çalıştırılacağı bağlamı. Değerleri alınmıştır `CLSCTX` sabit listesi. Varsa `cls_context` belirtilmezse, değerin CLSCTX_ALL kullanılır.

*rclsid*<br/>
`CLSID` veri ve nesneyi oluşturmak için kullanılan kod ile ilişkili.

## <a name="exceptions"></a>Özel Durumlar

Varsa `com::ptr` bir COM nesnesine bir başvuru zaten sahip `CreateInstance` oluşturur <xref:System.InvalidOperationException>.

Bu işlev çağrıları `CoCreateInstance` ve kullandığı <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> herhangi bir hata dönüştürmek için `HRESULT` için uygun bir özel durum.

## <a name="remarks"></a>Açıklamalar

`CreateInstance` kullanan `CoCreateInstance` ProgID veya bir CLSID tanımlanan belirtilen bir nesnenin yeni bir örneğini oluşturmak için. `com::ptr` Yeni oluşturulan nesneye başvuran ve yok etme sırasında şirkete ait tüm başvurularını otomatik olarak serbest bırakır.

## <a name="example"></a>Örnek

Bu örnekte kullanan bir CLR sınıf uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesne. İki farklı tür sınıf oluşturucuları kullanmanıza `CreateInstance` ProgID içinden ya bir CLSID değeri artı bir CLSCTX belge nesnesi oluşturulamıyor.

```
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

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>Ayrıca Bkz.

[ptr Üyeleri](../dotnet/ptr-members.md)