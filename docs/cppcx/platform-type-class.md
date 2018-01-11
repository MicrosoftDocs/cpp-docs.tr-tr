---
title: "Platform::type sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
dev_langs: C++
helpviewer_keywords: Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c292426b9d04fd5b3d9785224f9b2d48f129f0db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformtype-class"></a>Platform::type sınıfı
Çalışma zamanı türü bilgileri içermektedir; özellikle, bir dize adı ve typecode. Çağırılarak alınır [Object::GetType](../cppcx/platform-object-class.md#gettype) herhangi bir nesne üzerinde veya veya kullanarak [TypeID](../windows/typeid-cpp-component-extensions.md) sınıfta veya yapı adı işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class Platform::Type :      
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `Type` Sınıftır kullanarak doğrudan işleme gerekir uygulamalarda yararlı bir `if` veya `switch` dalları nesneyi çalışma zamanı türüne göre deyimi. Kategori türü açıklanır türü kodu kullanılarak alınır [Type::GetTypeCode](#gettypecode) üye işlevi.  
  
## <a name="public-methods"></a>Genel yöntemler  
  
|||  
|-|-|  
|[Type::GetTypeCode yöntemi](#gettypecode)|Döndürür bir [Platform::TypeCode numaralandırma](../cppcx/platform-typecode-enumeration.md) nesne değeri.| 
|[Type::ToString yöntemi](#tostring)|Belirtildiği gibi meta verilerinde türünün adını döndürür.| 

 
## <a name="public-properties"></a>Ortak Özellikler  
  
|||  
|-|-|  
|[Type::FullName](#fullname)|Döndürür bir [Platform::String sınıfı](../cppcx/platform-string-class.md)^ türünün tam adını temsil eder ve kullanır. (bir ayırıcı olarak nokta) değil:: (çift iki nokta üst üste) — Örneğin, `MyNamespace.MyClass`.|  
  
## <a name="conversion-operators"></a>Dönüştürme işleçleri  
  
|||  
|-|-|  
|[işleç türü ^](../cppcx/operator-subtracttype-hat.md)|Dönüştürme işlemini etkinleştirir `Windows::UI::Xaml::Interop::TypeName` için `Platform::Type`.|  
|[Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)|Dönüştürme işlemini etkinleştirir `Platform::Type` için `Windows::UI::Xaml::Interop::TypeName`.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  

 
## <a name="fullname"></a>Type::FullName özelliği
Biçiminde geçerli türünün tam adını alır `Namespace.Type`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
String^ FullName();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tür adı.  
### <a name="example"></a>Örnek  
  
```  
  
//  namespace is TestApp  
MainPage::MainPage()  
{  
    InitializeComponent();  
    Type^ t = this->GetType();  
    auto s = t->FullName; // returns "TestApp.MainPage"  
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"  
}  
```  
  


## <a name="gettypecode"></a>Type::GetTypeCode yöntemi
Yerleşik türler sayısal türün kategorisini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Platform::TypeCode GetTypeCode();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Platform::TypeCode birini değerleri numaralandırılır.  
  
### <a name="remarks"></a>Açıklamalar  
 GetTypeCode() üye yöntemi eşdeğerdir `typeid` özelliği.

## <a name="tostring"></a>Type::ToString yöntemi
Alır bir türünün adı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Platform::String^ ToString();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen meta verilerinde türünün adı.    
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)