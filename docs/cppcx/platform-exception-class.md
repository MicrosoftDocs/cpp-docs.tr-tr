---
title: "Platform::Exception sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::Exception::Exception
- VCCORLIB/Platform::Exception::CreateException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
dev_langs: C++
helpviewer_keywords: Platform::Exception Class
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70d497275a0af7cfec12123f169240ced47fa958
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformexception-class"></a>Platform::Exception sınıfı
Uygulama yürütmesi sırasında oluşan hataları temsil eder. Özel durum sınıfları türetilen olamaz `Platform::Exception`. Bir özel durum gerektiriyorsa, kullanabileceğiniz `Platform::COMException` ve uygulamaya özgü HRESULT belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class Exception : Object,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="members"></a>Üyeler  
 `Exception` Sınıfının devraldığı `Object` sınıfı ve `IException`, `IPrintable`, ve `IEquatable` arabirimleri.  
  
 `Exception` Sınıfı üyeleri şu tür de vardır.  
  
### <a name="constructors"></a>Oluşturucular  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[Exception::Exception](#ctor)|Yeni bir örneğini başlatır `Exception` sınıfı.|  
  
### <a name="methods"></a>Yöntemler  
 `Exception` Sınıfının devraldığı `Equals()`, `Finalize()`,`GetHashCode()`,`GetType()`,`MemberwiseClose()`, ve `ToString()` yöntemleri [Platform::Object sınıfı](../cppcx/platform-object-class.md). `Exception` Sınıfına aşağıdaki yöntemi de vardır.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[Exception::CreateException](#createexception)|Belirtilen HRESULT değerini temsil eden bir özel durum oluşturur.|  
  
### <a name="properties"></a>Özellikler  
 Özel durum sınıfı ayrıca aşağıdaki özelliklere sahiptir.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[Exception::HResult](#hresult)|Özel durumu karşılık gelen HRESULT.|  
|[Exception::Message](#message)|Özel durumu açıklayan bir ileti. Bu değer salt okunur ve sonra değiştirilemez `Exception` oluşturulur.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  

## <a name="createexception"></a>Exception::CreateException yöntemi
Bir Platform::Exception oluşturur ^ belirtilen HRESULT değerinden.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Exception^ CreateException(int32 hr)  
Exception^ CreateException(int32 hr, Platform::String^ message)  
```  
  
### <a name="parameters"></a>Parametreler  
 İK  
 Genellikle bir COM yöntemi çağrısından al HRESULT değeri. Değer için S_OK eşit olduğu, 0 ise bu yöntem oluşturulur [Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md) başarılı COM yöntemleri özel durumlar oluşturmamalıdır olduğundan.  
  
 iletisi  
 Hatayı açıklayan bir dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 HRESULT hata temsil eden bir özel durum.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum dışında Örneğin, bir COM arabirimi yöntemi çağrısından döndürülen HRESULT oluşturmak için bu yöntemi kullanın. Bir dize alır aşırı yüklemesini kullanabilirsiniz ^ parametresini kullanarak özel bir ileti girin.  
  
 Kesinlikle CreateException kesin türü belirtilmiş bir özel durum oluşturmak için kullanılacak önerilen yerine oluşturma bir [Platform::COMException](../cppcx/platform-comexception-class.md) yalnızca HRESULT içeren.  
  


## <a name="ctor"></a>Exception::Exception Oluşturucusu
Özel durum sınıfının yeni bir örneğini intializes.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
Exception(int32 hresult)  
Exception(int32 hresult, ::Platform::String^ message)  
```  
  
### <a name="parameters"></a>Parametreler  
 `hresult`  
 Özel durum tarafından temsil edilen HRESULT hata.  
  
 `message`  
 Düzenleyici metin gibi kullanıcı tanımlı bir ileti, şu özel durum ile ilişkilidir. Genel hata oluştu, nasıl ve neden hakkında mümkün olduğunca açıklayıcı bir ileti sağlamak için ikinci aşırı tercih etmelisiniz.  
  


## <a name="hresult"></a>Exception::HResult özelliği
Özel durumu karşılık gelen HRESULT.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## <a name="property-value"></a>Özellik Değeri  
 Bir HRESULT değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu özel durumlar HRESULT değerleri döndürülen COM hata olarak başlar. C + +/ CX dönüştürür bu değerleri Platform::Exception ^ nesneleri ve bu özellik özgün hata kodu değerini depolar.  
  


## <a name="message"></a>Exception::Message özelliği
Hatayı açıklayan ileti.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:property String^ Message;  
```  
  
## <a name="property-value"></a>Özellik Değeri  
 Windows çalışma zamanı'nda kaynaklanan durumlar sistem tarafından sağlanmış bir hatanın açıklamasını budur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sürümü Windows çalışma zamanı özel durumları yalnızca HRESULTS olarak ABI üzerinden taşınan çünkü Windows 8'de bu özellik salt okunurdur. Windows 8.1 daha zengin özel durum bilgilerini ABI taşınır ve diğer bileşenleri programlı olarak erişmek özel bir ileti sağlayabilir. Daha fazla bilgi için bkz: [özel durumlar (C + +/ CX)](../cppcx/exceptions-c-cx.md).  
  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)