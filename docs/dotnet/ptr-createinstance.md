---
title: PTR::CreateInstance | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr.CreateInstance
- msclr::com::ptr::CreateInstance
- msclr.com.ptr.CreateInstance
- ptr::CreateInstance
dev_langs: C++
helpviewer_keywords: ptr::CreateInstance
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 00a107d0f502d29d37ae085548e66012d4d585d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ptrcreateinstance"></a>ptr::CreateInstance
İçinde bir COM nesnesinin örneği oluşturur bir `com::ptr`.  
  
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
 `progid`  
 A `ProgID` dize.  
  
 `pouter`  
 Birleşik nesnenin IUnknown arabirimi (IUnknown) yönelik işaretçi. Varsa `pouter` belirtilmezse, `NULL` kullanılır.  
  
 `cls_context`  
 Yeni oluşturulan nesnenin yönetir kod çalışacağı bağlamı. Değerleri alındığı `CLSCTX` numaralandırması. Varsa `cls_context` belirtilmezse, değerin CLSCTX_ALL kullanılır.  
  
 `rclsid`  
 `CLSID`nesne oluşturmak için kullanılan kod ve veri ile ilişkilendirilmiş.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `com::ptr` zaten bir COM nesnesi başvuru sahibi `CreateInstance` oluşturur <xref:System.InvalidOperationException>.  
  
 Bu işlev çağrılarını `CoCreateInstance` ve kullandığı <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> herhangi bir hata dönüştürmek için `HRESULT` için uygun bir özel durum.  
  
## <a name="remarks"></a>Açıklamalar  
 `CreateInstance`kullanan `CoCreateInstance` ProgID veya CLSID tanımlanan belirtilen nesne yeni bir örneğini oluşturmak için. `com::ptr` Yeni oluşturulan nesnenin başvuruyor ve yok etme bağlı tüm ait başvuruları otomatik olarak serbest bırakır.  
  
## <a name="example"></a>Örnek  
 Bu örnek kullanan bir CLR sınıfı uygulayan bir `com::ptr` kendi özel üye sarmalamak için `IXMLDOMDocument` nesnesi. Sınıf oluşturucuları iki farklı tür kullanmanıza `CreateInstance` ProgID veya CLSID artı bir CLSCTX belge nesnesi oluşturulamadı.  
  
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
 **Üstbilgi dosyası** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [PTR üyeleri](../dotnet/ptr-members.md)