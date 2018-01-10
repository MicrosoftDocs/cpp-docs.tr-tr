---
title: "Platform::Object sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
dev_langs: C++
helpviewer_keywords: Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ee718205aa235ee2d93183f131f06ba9f01e40e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformobject-class"></a>Platform::Object sınıfı
Ref sınıfları ve ref yapılar için Windows mağazası uygulamaları için ortak davranış sağlar. Tüm ref sınıfı ve ref yapısı örnekleri için Platform::Object örtük olarak dönüştürülebilir ^ ve kendi sanal ToString yöntemini geçersiz kılabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class Object : Object  
```  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Object::Object](#ctor)|Nesne sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Object::Equals](#equals)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|  
|[Object::GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|  
|[Object::ReferenceEquals](#referenceequals)|Belirtilen nesne örnekleri aynı örneği olup olmadığını belirler.|  
|[ToString](#tostring)|Geçerli nesneyi temsil eden bir dize döndürür. Geçersiz kılınabilir.|  
|[GetType](#gettype)|Alır bir [Platform::Type](../cppcx/platform-type-class.md) geçerli örneğini açıklar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Object`  
  
 `Object`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** vccorlib.h  
  
 **Namespace:** Platform  

  
## <a name="equals"></a>Object::Equals yöntemi
Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
bool Equals(  
    Object^ obj  
)  
```  
  
### <a name="parameters"></a>Parametreler  
 Obj  
 Karşılaştırma yapılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Aksi takdirde nesneleri eşitse, `false`.  
  


## <a name="gethashcode"></a>Object::GetHashCode Yöntemi
Döndürür `IUnknown`* kimlik değeri COM nesnesi ise, bu örnek için veya bir COM nesnesi değilse hesaplanan karma değeri.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu nesneyi benzersiz şekilde tanımlayan bir sayısal değer.  
  
### <a name="remarks"></a>Açıklamalar  
 GetHashCode eşlemelerinin nesneler için anahtarlar oluşturmak için kullanabilirsiniz. Karma kodlarını kullanarak karşılaştırabilirsiniz [Object::Equals](#equals). Kod yolu son derece kritik öneme sahipse ve `GetHashCode` ve `Equals` temel alınan COM katmana açılır ve yerel yapmak yeteri kadar hızlı değildir `IUnknown` işaretçi karşılaştırmaları.  
  


## <a name="gettype"></a>Object::GetType yöntemi
Döndürür bir [Platform::Type](../cppcx/platform-type-class.md) nesneyi çalışma zamanı türünü tanımlayan nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Object::GetType()  
```  

  
### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 A [Platform::Type](../cppcx/platform-type-class.md) nesne çalışma zamanı türünü tanımlayan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Statik [Type::GetTypeCode](../cppcx/platform-type-class.md#gettypecode) almak için kullanılan bir [Platform::TypeCode numaralandırma](../cppcx/platform-typecode-enumeration.md) geçerli türünü temsil eden bir değer. Bu genellikle yerleşik türleri için kullanışlıdır. Herhangi bir ref sınıf yanı sıra türü kodu [Platform::String](../cppcx/platform-string-class.md) nesne (1).  
  
 [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) sınıfı türü bilgileri Windows bileşenleri ve uygulamalar arasında geçirme dilden bağımsız şekilde Windows API'larını kullanılır. T[Platform::Type sınıfı](../cppcx/platform-type-class.md) arasında dönüştürme için işleçleri sahip `Type` ve `TypeName`.  
  
 Kullanım [TypeID](../windows/typeid-cpp-component-extensions.md) döndürülecek işleci bir `Platform::Type` nesne XAML sayfaları arasında gezinirken örneğin bir sınıf adı için:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::type sınıfı](../cppcx/platform-type-class.md)   
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)   
 [Türü System] (.. /cppcx/Type-System-c-CX.MD
  
## <a name="ctor"></a>Object::Object Oluşturucusu
Nesne sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:Object()  
```  

## <a name="referenceequals"></a>Object::ReferenceEquals yöntemi
Belirtilen nesne örnekleri aynı örneği olup olmadığını belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2)  
```  
  
### <a name="parameters"></a>Parametreler  
 obj1  
 Karşılaştırılacak ilk nesne.  
  
 obj2  
 Karşılaştırılacak ikinci nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`iki nesnenin aynı olup olmadığını; Aksi takdirde `false`.  
 
## <a name="tostring"></a>Object::ToString yöntemi (C + +/ CX)
Geçerli nesneyi temsil eden bir dize döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:  
virtual String^ ToString()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli nesneyi temsil eden bir dize. Ref sınıfta veya yapı özel bir dize iletisinde sağlamak için bu yöntemi geçersiz kılabilirsiniz:  
  
```cpp  
public ref class Tree sealed  
{  
public:  
    Tree(){}  
    virtual Platform::String^ ToString() override  
    {  
      return "I’m a Tree";  
    };  
};  
```  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)